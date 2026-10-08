# Day 22 — Nhật ký phản biện (§4.7) và email đối tác

Sản phẩm: AI Nutrition Agent (P-110). Số liệu: `HaThiMyLinh_Day22_model.xlsx`, giá em kiểm tra ngày 08/10/2026.

Em chạy prompt 4.7.1 và 4.7.5 với AI, dán số liệu tab 1–5 làm đầu vào. Với mỗi điểm AI nêu, em ghi em chấp nhận,
chấp nhận một phần hay không chấp nhận, và em đã sửa gì trong file.

## 1. Prompt 4.7.1 — Cost/Job Stress Test

| # | Điểm phản biện | Quyết định của em | Em đã sửa |
|---|---|---|---|
| 1 | **Thiếu chi phí gửi Zalo ZNS** cho tin 5h45 — chính là điểm nhúng em chọn. 7 tin/tuần × 330₫ (200₫ tin thông báo + 100₫ nút + VAT) = $0,088/job, ngang chi phí VPS. | Accept | Cộng vào Infra (1_Cost_Job!B41); vì vậy em nâng giá lên 140.000₫ |
| 2 | **Overhead đang để 0** trong khi em vẫn phải hỗ trợ đối tác và trả gói Zalo OA. | Accept | B59 = $56/tháng; One-Pager ghi cả GM có và không có overhead |
| 3 | **VPS $60 chưa gắn với nhà cung cấp nào.** | Accept | Đổi sang DigitalOcean 4 vCPU/8 GB $48 + backup hằng ngày 30% = $62,4 (có link, ngày) |
| 4 | **Prompt caching khó trúng:** 7 lời gọi sinh thực đơn chạy song song và `candidates` đứng sau `day_index`, nên prefix không được dùng lại. | Partial — em giữ giả định có cache vì sẽ sửa thứ tự payload, nhưng thêm kịch bản không cache | 2_Pricing!B61:B62: không cache thì GM vẫn 63%, trên 60% |
| 5 | **Mẫu số:** em đã chia cho job hoàn thành (364), không phải job thử (520). Nếu chia cho job thử thì Cost/Job thấp hơn 30%. | Giữ nguyên, đã đúng | — |
| 6 | **Token đang là ước tính.** P-110 đã ghi `input_tokens`/`output_tokens` thật vào bảng `agent_runs`, nên thay B20:B22 bằng số đo. | Accept, làm trong tháng 1 | Chưa đo được vì DB eval của nhóm không gọi LLM; em ghi vào việc cần làm |
| 7 | **Giá khuyến mại:** không dòng nào em dùng là giá khuyến mại (Gemini 3.5 Flash-Lite, gpt-4o-mini là giá chuẩn). GPT-5.6 Sol trong bảng benchmark đã đổi giá. | Giữ nguyên | Ghi chú ở 6_Benchmarks!F3 |
| 8 | **Con số có thể giết mô hình: thời gian soạn tay 1 thực đơn (em giả định 30 phút).** Cả trần giá theo lương dựa vào nó. Dưới khoảng 30 phút thì giá $1,24 vượt trần 70%; nếu chỉ 15 phút thì trần còn $0,63, thấp hơn giá sàn $1,21. | Accept | 2_Pricing!B60; mục Neo giá trong One-Pager; em đưa việc đo con số này lên đầu tháng 1 |
| 9 | **Biến thể A là giả định kinh doanh.** Nếu đối tác muốn nhóm em cung cấp luôn chuyên gia (biến thể B), Cost/Job lên khoảng 3,7 lần ($1,51 so với $0,404). | Accept — em sẽ ghi rõ trong thỏa thuận pilot là chuyên gia của Trung tâm duyệt | Ghi lý do ở 1_Cost_Job!E6 |

## 2. Prompt 4.7.5 — One-Pager Defensibility Check

| # | Điểm phản biện | Quyết định của em | Em đã sửa |
|---|---|---|---|
| 1 | **Có số chưa có căn cứ:** 30 phút soạn tay / 5 phút duyệt, 4 câu hỏi đáp/tuần, containment 70% (chỉ từ 7 hồ sơ demo). | Partial — em giữ các số này nhưng ghi rõ là giả định và đưa vào KPI tháng 1 | Nhãn "giả định/ước tính" + KPI pilot |
| 2 | **Benchmark lệch người mua:** The Meal và DiaB đều bán cho cá nhân, còn khách của em là phòng khám. DiaB lại không có giá công khai. | Accept | Thay DiaB bằng Nutrium (phần mềm cho chuyên gia dinh dưỡng, seat theo chuyên gia, có link giá) |
| 3 | **Số học có khớp không?** (1,24 − 0,404)/1,24 = 67,4% ✓; bội số 3,07 ✓; breakeven 57,0% < 70% ✓; ARPU 120 × 140.000₫ / 26.160 = $642 ✓. | Giữ nguyên | — |
| 4 | **Kênh có nối với ARPU và pain moment không?** Có: ARPU $642 không nuôi nổi sales rep (CAC thực gấp 4,9 lần ngân sách), và người chăm sóc nhận lời dặn ở cơ sở y tế. Nhưng thiếu câu nối giữa người dùng (người chăm sóc) và người trả tiền (phòng khám). | Accept | Thêm câu nối ở mục Pain Moment |
| 5 | **Số ICONIQ là số của Mỹ.** | Partial — em giữ benchmark của bài nhưng thêm ngưỡng hòa vốn | Sales-Led chỉ khả thi nếu cost/opportunity ở Việt Nam ≤ khoảng $1.300 |
| 6 | **Sửa một chỗ đáng giá nhất:** liên hệ đối tác trước khi nộp để không còn ghi "Chưa nói chuyện". | Accept — em sẽ gửi email dưới đây | Email ở mục 3 |

## 3. Email giới thiệu em sẽ gửi đối tác

> **Tiêu đề:** Đề xuất thử nghiệm miễn phí — trợ lý soạn thực đơn theo bệnh cho chuyên gia của Trung tâm
>
> Kính gửi Trung tâm Khám tư vấn dinh dưỡng — Viện Dinh dưỡng Quốc gia,
>
> Em là Hà Thị Mỹ Linh, nhóm sinh viên phát triển AI Nutrition Agent (chương trình AI20K). Sản phẩm soạn sẵn thực đơn
> tuần cho từng người bệnh mạn tính (đái tháo đường, tăng huyết áp, thận mạn, gút) từ dữ liệu thành phần thực phẩm Việt
> Nam và ngưỡng trong văn bản của Bộ Y tế. Chuyên gia của Trung tâm duyệt từng thực đơn trước khi người bệnh nhìn thấy.
> Người nhà ghi bữa bằng giọng nói và được cảnh báo ngay khi món ăn vượt ngưỡng hoặc tương tác với thuốc.
>
> Chúng em muốn xin 30 phút để trình bày và đề xuất pilot miễn phí 4 tuần với khoảng 20 người bệnh. Mục tiêu là đo
> thời gian chuyên gia tiết kiệm được trên mỗi thực đơn. Kèm theo là báo cáo đánh giá hiện có của hệ thống.
>
> Trân trọng,
> Hà Thị Mỹ Linh — [email / số điện thoại]
