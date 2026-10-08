# Track 1 · Day 22 — AI Product GTM & Monetization

Hà Thị Mỹ Linh — 2A202602619

Em làm bài trên sản phẩm của nhóm em ở dự án P-110: **AI Nutrition Agent**. Sản phẩm soạn sẵn thực đơn tuần cho người
bệnh mạn tính (đái tháo đường, tăng huyết áp, thận mạn, gút), và chuyên gia dinh dưỡng của phòng khám duyệt từng thực
đơn trước khi người nhà nhìn thấy.

## File nộp

| File | Nội dung |
|---|---|
| `HaThiMyLinh_Day22_model.xlsx` | Mô hình 5 tab + 2 tab tham chiếu. Cột E mỗi tab em ghi lý do và nguồn cho từng ô. Tab 2, dòng 55–63 là các số em tính thêm để dùng trong One-Pager |
| `HaThiMyLinh_Day22_onepager.pdf` / `.docx` | Monetization One-Pager — mọi số đều lấy từ một ô trong file Excel |
| `HaThiMyLinh_Day22_critique_log.md` | Kết quả em chạy prompt phản biện 4.7.1 và 4.7.5, em chấp nhận / không chấp nhận điểm nào, và email em sẽ gửi đối tác |

## Kết quả chính (giá em kiểm tra ngày 08/10/2026)

| Chỉ số | Giá trị | Ô |
|---|---|---|
| Job | 1 thực đơn tuần (21 bữa) được chuyên gia duyệt và giao tới người chăm sóc | 1_Cost_Job!B5 |
| Cost/Job (biến thể A, chia cho job hoàn thành) | $0,404 · $0,558 nếu tính overhead | 1_Cost_Job!B66:B67 |
| Giá bán | $1,24/job = 140.000₫/người bệnh/tháng (gấp 3,07 lần Cost/Job) | 2_Pricing!B19:B20 |
| Gross Margin | 67,4% · 55,0% nếu tính overhead | 2_Pricing!B21, C63 |
| Breakeven containment | 57,0% (eval hiện tại khoảng 70%, ước tính) | 2_Pricing!B33 |
| Value Metric | Hybrid: phí nền theo người bệnh/tháng + 32.000₫/thực đơn vượt suất | 3_Value_Metric!B30:B34 |
| Kênh | Partner-Led — Viện Dinh dưỡng Quốc gia; CAC nếu đi Sales-Led gấp 4,9 lần ngân sách | 4_Channel_Fit |

**Mô hình của em gãy khi:** containment dưới 46%, một đối tác có dưới khoảng 53 người bệnh, phí Zalo ZNS cao gấp 2,7
lần, hoặc chuyên gia soạn tay một thực đơn mất dưới khoảng 30 phút (lúc đó giá vượt trần neo theo lương).

## Việc em sẽ làm tiếp

- **Bài test người lạ:** em sẽ nhờ một nhóm khác đọc One-Pager trong 2 phút ở buổi học tới, rồi điền kết quả vào
  5_90Day_Plan!B29:B32.
- Gửi email giới thiệu cho Trung tâm Khám tư vấn dinh dưỡng (bản nháp trong critique log).
- Đo token thật từ bảng `agent_runs` của P-110 để thay các số đang ước tính ở 1_Cost_Job!B19:B22.
- Hỏi chuyên gia dinh dưỡng xem soạn tay một thực đơn tuần mất bao lâu — đây là giả định em thấy rủi ro nhất.
