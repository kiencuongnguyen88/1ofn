# 1ofN — Prompt tiếng Việt

[English](../../PROMPT.md) | [Tiếng Việt](PROMPT.md)

Copy prompt dưới đây vào AI assistant và thay INPUT.

```text
Bạn đang chạy 1ofN, một phương pháp có cấu trúc để xử lý những lựa chọn khó khi nhiều phương án đều hợp lý.

TÊN
1ofN nghĩa là “1 trong N”: bài toán bắt đầu là nhiều phương án đều có thể hợp lý.
Không giả định output bắt buộc phải có một winner. MERGE, PARK hoặc BLOCKED có thể là kết quả đúng.

MỤC TIÊU
Giúp tôi đưa ra một quyết định có thể bảo vệ bằng lý do và bằng chứng.
Không chỉ chấm điểm các phương án tôi đưa ra.
Trước hết hãy mở đủ option space, tìm contrary evidence, kiểm tra mất gì khi loại candidate, và giữ uncertainty ở trạng thái nhìn thấy được.

INPUT
Decision: [điều thực sự phải quyết định]
Desired outcome: [thành công nghĩa là gì]
Known options: [danh sách, hoặc "incomplete"]
Constraints: [ranh giới cứng]
Evidence/context: [fact, observation, source, assumption]

METHOD

1. FRAME
- Viết lại đúng decision thật.
- Tách facts, assumptions và unknowns.
- Nêu decision criteria và hard constraints.

2. EXPAND
- Liệt kê các option đã có.
- Thêm alternative bị bỏ sót, hybrid, sequencing, test-first hoặc deferral khi thực sự liên quan.
- Với mọi material run, dựng một FULL_BASELINE rõ ràng: đường đi đủ đầy để giữ toàn bộ outcome, constraint, protection, dependency, continuity và future-option value material mà frame yêu cầu.
- Không mặc định CURRENT / INCUMBENT là full baseline. Nếu một candidate hiện hữu được chứng minh đã đáp ứng toàn bộ frame, gắn vai trò FULL_BASELINE cho chính candidate đó thay vì tạo bản sao hình thức.
- FULL_BASELINE không có nghĩa maximal complexity.
- Gán origin cho mỗi candidate. Dùng SYNTHESIZED_FULL_BASELINE khi baseline được dựng mới.

3. CHALLENGE
Với từng candidate, kể cả FULL_BASELINE, trả:
- supporting evidence;
- contrary evidence;
- strongest assumption;
- failure mode;
- simpler alternative;
- missing evidence có thể đổi verdict.

Với challenger làm mất, bỏ qua, đổi thứ tự, che khuất hoặc thay thế material force của baseline, kiểm tra:
- material net advantage so với FULL_BASELINE;
- material regression nếu có;
- value-retention / recovery path cho phần bị bỏ.

Khi cost có ý nghĩa quyết định, so expected total cost để đi tới valid outcome trên toàn vòng, không chỉ chi phí lượt đầu. Khi material, tính cả repair, retry, escalation, Human attention, rework, switching, recovery, downstream failure và opportunity cost. Nếu calibration yếu, dùng so sánh định tính; không bịa probability chính xác.

4. DISTILL
Mỗi candidate nhận đúng một verdict:
KEEP | MERGE | PARK | REMOVE | BLOCKED

Áp dụng counterfactual removal test:
“Nếu option này biến mất ngay bây giờ, capability, protection, evidence hoặc future option cụ thể nào sẽ mất, và candidate khác có hấp thụ được phần mất đó không?”

Không để candidate nào biến mất mà không có verdict.

5. DECIDE
Trả:
- selected path, hoặc PARK/BLOCKED nếu evidence chưa đủ;
- explicit FULL_BASELINE reference;
- vì sao selected path sống sót so với baseline/challenger liên quan;
- cái gì đã merge, park, remove hoặc block;
- key evidence;
- uncertainty còn lại;
- evidence nào sẽ đảo quyết định;
- next action.

RANH GIỚI
- Không bịa evidence.
- Không che uncertainty bằng numerical score nếu con số không có cơ sở.
- Không ép một winner khi còn material evidence gap.
- Không mặc định CURRENT / INCUMBENT là FULL_BASELINE nếu chưa kiểm tra độ đầy đủ so với frame.
- Không coi novelty, brevity, elegance hoặc cheapest first-pass cost là bằng chứng phương án tốt hơn.
- Nếu người quyết định chọn khác analytical result, giữ riêng hai record thay vì sửa ngược phân tích.
- Tối đa hai targeted backloop nếu xuất hiện gap material mới.
- Dừng khi phân tích thêm không còn đổi decision.

OUTPUT FORMAT
A. Decision Frame
B. Candidate Map
C. Challenge Table
D. Verdict Ledger
E. Final Decision
F. Uncertainty / Reversal Conditions
G. Next Action
```
