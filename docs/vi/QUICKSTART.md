# 1ofN — Bắt đầu nhanh

[English](../../QUICKSTART.md) | [Tiếng Việt](QUICKSTART.md)

Dùng 1ofN khi bạn đang nhìn vào nhiều phương án đều hợp lý và không biết phương án nào thực sự đáng commit.

## Ý nghĩa tên

`1ofN` = **1 trong N**.

Chỉ cần hiểu tên một lần. Phương pháp sau đó trả lời:

> Trong N phương án đang cạnh tranh, cái gì đáng giữ, cái gì nên nhập lại, cái gì nên để sau, cái gì có thể bỏ, và bằng chứng đã đủ để quyết định hay chưa?

## Chuẩn bị trong 60 giây

Viết năm dòng:

```text
Decision:
Desired outcome:
Known options:
Constraints:
Evidence / context:
```

Không biết đủ option cũng không sao. EXPAND tồn tại để tìm phần còn thiếu.

**Giới hạn đầu vào:** 1ofN chỉ có thể suy luận từ đề bài, bối cảnh, bằng chứng và trường phương án có trong lượt chạy. Nếu câu hỏi ban đầu bị thiếu, quá hẹp hoặc đặt sai tầng, phân tích vẫn có thể hợp lý trong phạm vi đó nhưng chưa chắc trả lời đúng vấn đề bạn thực sự cần giải. Hãy dùng kết quả như dữ liệu hỗ trợ quyết định; quyết định cuối cùng vẫn thuộc về bạn.

## Chạy năm stage

### 1. FRAME
Viết lại câu hỏi thành đúng decision thật.

### 2. EXPAND
Thêm alternative bị bỏ sót, hybrid, sequencing, “test first”, hoặc “do nothing for now” khi thực sự liên quan.

Với mọi material run, dựng một `FULL_BASELINE` rõ ràng: đường đi đủ đầy cho frame hiện tại. Không mặc định phương án đang dùng đã full. Nếu một option hiện hữu thật sự bao phủ toàn bộ frame, gắn nó làm baseline sau khi kiểm tra thay vì tạo duplicate.

`FULL_BASELINE` là đủ đầy cho material scope, không phải maximal complexity.

### 3. CHALLENGE
Với mỗi candidate, tìm:

- supporting evidence;
- contrary evidence;
- strongest assumption;
- failure mode;
- simpler alternative;
- nếu candidate thách thức full baseline, material net advantage nào được tạo ra và material regression nào có nguy cơ xuất hiện.

### 4. DISTILL
Gán cho mọi candidate:

`KEEP | MERGE | PARK | REMOVE | BLOCKED`

Dùng removal test:

> Nếu option này biến mất, giá trị material nào thực sự mất?

### 5. DECIDE
Trả:

- selected path hoặc PARK/BLOCKED;
- vì sao;
- uncertainty còn lại;
- reversal condition;
- next action.

## Guard

`1ofN` **không bắt buộc phải có một winner duy nhất**.

Hai option nên thành một đường đi → `MERGE`.

Chưa đúng timing → `PARK`.

Thiếu evidence material → `BLOCKED`.

## Ví dụ nhỏ

**Decision:** Một method mới nên được phát hành bằng bề mặt nào trước?

Options:

- web app;
- CLI;
- documentation + examples.

EXPAND thêm:

- documentation trước, chỉ mở app khi usage evidence cho thấy có nhu cầu interaction lặp lại.

Sau CHALLENGE + removal test:

- Web app → `PARK`
- CLI → `REMOVE`
- Docs + examples → `KEEP`
- Docs first → app later → `MERGE` vào staged path

**Decision:** phát hành documentation + examples trước; chỉ mở lại app khi usage evidence chứng minh nhu cầu interaction lặp lại.

## Prompt dùng lại

Xem [PROMPT.md](PROMPT.md).
