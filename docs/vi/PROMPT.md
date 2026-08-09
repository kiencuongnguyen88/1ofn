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
- Gán origin cho mỗi candidate.

3. CHALLENGE
Với từng candidate, trả:
- supporting evidence;
- contrary evidence;
- strongest assumption;
- failure mode;
- simpler alternative;
- missing evidence có thể đổi verdict.

4. DISTILL
Mỗi candidate nhận đúng một verdict:
KEEP | MERGE | PARK | REMOVE | BLOCKED

Áp dụng counterfactual removal test:
“Nếu option này biến mất ngay bây giờ, capability, protection, evidence hoặc future option cụ thể nào sẽ mất, và candidate khác có hấp thụ được phần mất đó không?”

Không để candidate nào biến mất mà không có verdict.

5. DECIDE
Trả:
- selected path, hoặc PARK/BLOCKED nếu evidence chưa đủ;
- vì sao nó sống sót;
- cái gì đã merge, park, remove hoặc block;
- key evidence;
- uncertainty còn lại;
- evidence nào sẽ đảo quyết định;
- next action.

RANH GIỚI
- Không bịa evidence.
- Không che uncertainty bằng numerical score nếu con số không có cơ sở.
- Không ép một winner khi còn material evidence gap.
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
