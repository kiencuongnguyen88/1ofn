# 1ofN

[English](README.md) | [Tiếng Việt](README.vi.md)

**Khi nhiều phương án đều có lý. Hãy tìm cái thật sự đáng giữ.**

AI tạo thêm phương án ngày càng rẻ. `1ofN` bắt đầu ở chỗ việc sinh thêm phương án kết thúc: khi nhiều lựa chọn đều có vẻ hợp lý và phần khó là xác định cái gì đáng để cam kết mà không âm thầm làm mất giá trị quan trọng.

`1ofN` đọc đơn giản là **“1 trong N”**: bạn có nhiều lựa chọn đều hợp lý, nhưng vẫn cần biết **cái gì thực sự đáng giữ, cái gì nên nhập lại, cái gì nên để sau, cái gì có thể bỏ, và liệu bằng chứng đã đủ để quyết định hay chưa**.

Chỉ cần hiểu tên một lần. Từ đó, `1ofN` vừa là tên của bài toán vừa là tên của phương pháp xử lý bài toán đó.

> N phương án hợp lý → thử thách từng phương án → thu hẹp mà không làm mất giá trị quan trọng → đưa ra quyết định có lý do.

**Tạo bởi Thầy Cường — kiencuongnguyen88.** 1ofN sinh ra từ một failure lặp lại: khi nhiều phương án đều có lý, càng phân tích từng phương án riêng lẻ thì đôi khi *tất cả* lại càng có vẻ hợp lý hơn, nhưng quyết định thật sự vẫn không dễ hơn. 1ofN được tạo ra để biến vùng mơ hồ đó thành một quyết định có thể kiểm tra.

## Khi nào nên dùng 1ofN?

Dùng khi:

- có nhiều phương án thật sự đều hợp lý;
- bảng pros/cons đơn giản không đủ để chốt;
- một số phương án có thể đang trùng nhau hoặc nên ghép theo trình tự;
- bằng chứng đang lẫn với giả định;
- chọn quá sớm có thể làm mất một đường đi tốt hơn;
- bạn muốn biết **vì sao** một phương án sống sót, không chỉ biết nó “được điểm cao hơn”.

Không cần dùng cho lựa chọn nhỏ, hiển nhiên, ít tốn kém hoặc rất dễ đảo ngược.

## 1ofN làm gì?

1. **FRAME** — xác định đúng việc đang phải chọn.
2. **EXPAND** — mở đủ trường phương án trước khi thu hẹp.
3. **CHALLENGE** — tìm bằng chứng ngược, giả định yếu và failure mode.
4. **DISTILL** — gán trạng thái rõ ràng cho mọi candidate: `KEEP | MERGE | PARK | REMOVE | BLOCKED`.
5. **DECIDE** — chốt đường đi mạnh nhất còn đứng vững, hoặc nói rõ vì sao chưa nên commit.

## Guard FULL_BASELINE

Với một material run, `EXPAND` không được mặc định các option đang nhìn thấy đã chứa một đường đi đầy đủ. 1ofN phải có một **FULL_BASELINE** rõ ràng trước khi bắt đầu thu hẹp.

Phương án current/incumbent không tự động là full. Nếu nó thật sự bao phủ toàn bộ decision frame, có thể gắn chính nó làm baseline sau khi kiểm tra độ đầy đủ. `FULL_BASELINE` nghĩa là đủ đầy cho material scope, **không phải maximal complexity**.

Một challenger làm mất material force của baseline chỉ nên thay thế khi so sánh chứng minh được **material net advantage** mà không tạo **material regression**. Baseline vẫn phải bị challenge; nó là reference chứ không phải winner bắt buộc.

Xem canonical deep-dive tại [docs/REPLACEMENT_DECISIONS.md](docs/REPLACEMENT_DECISIONS.md).

## Core ổn định, phương pháp sống

`1ofN` được thiết kế để người dùng vẫn nhận ra cùng một phương pháp ngay cả khi năng lực thực thi mạnh lên rất nhiều.

Bốn điều định nghĩa identity của 1ofN:

1. **WHAT** — một phương pháp chuyên biệt để thu hẹp nhiều phương án hợp lý mà không âm thầm làm mất giá trị quan trọng;
2. **PROBLEM** — nhiều phương án đều đủ hợp lý khiến so sánh đơn giản không cho biết cái gì nên sống sót;
3. **WHO / WHEN** — dùng khi nhiều hướng hợp lý cạnh tranh nhau theo cách có thể làm thay đổi quyết định;
4. **HOW** — `FRAME → EXPAND → CHALLENGE → DISTILL → DECIDE`, giữ Removal Test và ý nghĩa verdict ổn định.

**Phương pháp giữ ổn định.** **Năng lực có thể trưởng thành qua case, eval và learning.** **Công cụ thực thi có thể được thay thế khi có công cụ tốt hơn.**

Vì vậy bản public đầu tiên có thể giữ đơn giản, dễ nhớ và chi phí thấp mà không đóng trần tương lai.

Kiến trúc chi tiết giữ ở [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) và [docs/ROADMAP.md](docs/ROADMAP.md).


## Một guard quan trọng

Tên `1ofN` **không có nghĩa mọi run đều phải kết thúc bằng đúng một winner**.

Một run hợp lệ có thể kết thúc bằng:

- một phương án được chọn;
- nhiều phương án được **MERGE** thành một đường đi mạnh hơn;
- một phương án được **PARK** để mở lại sau;
- quyết định bị **BLOCKED** vì còn thiếu bằng chứng material.

`1ofN` đặt tên cho **bài toán bắt đầu**, không ép hình dạng kết quả.

## Core verdicts

- **KEEP** — bỏ nó sẽ làm mất một giá trị riêng mà các candidate khác không hấp thụ được.
- **MERGE** — có giá trị thật, nhưng nên nhập vào candidate khác thay vì tồn tại độc lập.
- **PARK** — có thể hữu ích, nhưng timing, dependency hoặc evidence hiện tại chưa cho phép commit.
- **REMOVE** — bỏ đi không làm mất outcome, protection, optionality hoặc decision quality material.
- **BLOCKED** — chưa thể kết luận vì thiếu bằng chứng đủ quan trọng để có thể đổi quyết định.

Không candidate nào được biến mất âm thầm.

## Removal test

Một câu hỏi trung tâm của 1ofN:

> **Nếu phương án này biến mất ngay bây giờ, ta thực sự mất điều gì mà các phương án còn lại không hấp thụ được?**

Nếu câu trả lời là “không mất gì material”, phương án đó không nên sống sót chỉ vì nghe hay hoặc trông phức tạp.

## Bắt đầu nhanh

- [Quick Start tiếng Việt](docs/vi/QUICKSTART.md)
- [Prompt tiếng Việt](docs/vi/PROMPT.md)
- [METHOD.md — canonical English](METHOD.md)

Các bề mặt canonical tiếng Anh:

- [README.md](README.md)
- [QUICKSTART.md](QUICKSTART.md)
- [PROMPT.md](PROMPT.md)

## Worked cases

Các case canonical hiện giữ bằng tiếng Anh:

- [Chọn bề mặt phát hành đầu tiên](examples/01-release-surface.md)
- [Chọn cách học một kỹ năng mới](examples/02-learning-path.md)
- [Chọn hướng tiếp theo cho một sản phẩm nhỏ](examples/03-product-direction.md)
- [Chọn một thông điệp chính cho lần truyền thông ra công chúng](examples/04-communication-message.md)

## Theo dõi kết quả sau quyết định

Khi một quyết định đã tạo ra kết quả thực tế có thể quan sát, có thể dùng [evals/outcome-followup.md](evals/outcome-followup.md) để giữ lại cơ sở quyết định ban đầu, ghi nhận điều thực sự xảy ra và rút ra evidence cho các run sau.

Đây là eval tùy chọn, không phải stage thứ sáu, không dùng kết quả sau này để viết lại quyết định ban đầu, và không thay đổi phương pháp năm stage.

Regression case cho failure “toàn bộ option đầu vào đều partial” nằm tại [evals/full-baseline-regression.md](evals/full-baseline-regression.md).

## Ngôn ngữ và đồng bộ

English là **canonical language**. Tiếng Việt là localization hạng nhất đầu tiên.

Quy tắc đồng bộ: [docs/LOCALIZATION.md](docs/LOCALIZATION.md)

## License

Các material non-software hiện nằm trong scope công khai được cấp phép theo **CC BY 4.0**.

Attribution gọn được ưu tiên: **1ofN by kiencuongnguyen88**

Xem [LICENSE](LICENSE), [ATTRIBUTION.md](ATTRIBUTION.md) và [docs/LICENSE_SCOPE.md](docs/LICENSE_SCOPE.md).

## Lineage

Người dùng không cần biết DIAMOND OS hay BBR để sử dụng 1ofN. Lineage kỹ thuật chỉ được ghi riêng tại [docs/lineage.md](docs/lineage.md).

## Trạng thái

`v0.1.3 public release`
