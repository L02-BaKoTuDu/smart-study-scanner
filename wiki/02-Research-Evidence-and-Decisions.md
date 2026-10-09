# 02 — Research Evidence and Decisions

> *Trang này chứa Mục 3, 4, 5, 6, 7 trong khung 13 mục bắt buộc.*

---

## Mục 3: Critical Assumptions (Các giả định cốt lõi)

### Ba giả định quan trọng nhất


| #      | Assumption                                                                            | Tại sao quan trọng                                                                   | Test method                                                     | Pass criteria                               | Fail action                                                                        |
| ------ | ------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------- | ------------------------------------------- | ---------------------------------------------------------------------------------- |
| **A1** | **OCR On-device đạt ≥ 80% accuracy** trên ảnh chụp slide/bảng trắng thực tế           | Nếu sai → search trả kết quả sai → user mất niềm tin → app vô giá trị                | Test 30 ảnh thật, đếm từ OCR đúng / tổng từ thực                | ≥ 80% trong 30 ảnh đầu tiên                 | Revise: thêm tiền xử lý ảnh (tăng contrast, khử lóa) hoặc tích hợp thêm engine OCR |
| **A2** | **Tìm kiếm từ khóa giảm ≥ 50% thời gian** so với lướt Camera Roll thủ công            | Nếu user không thấy giá trị → quay về dùng app Ảnh mặc định → mất lợi thế cạnh tranh | So sánh task time: 5 user lướt Camera Roll vs 5 user dùng app   | Median time giảm ≥ 50% (từ ~60s xuống <30s) | Revise: thêm "Browse by subject" fallback nếu user lười gõ keyword                 |
| **A3** | **User có nhu cầu sync OCR text sang Google Docs/Notion** để làm đề cương trên laptop | Nếu không có nhu cầu → bỏ luôn tính năng sync, giảm scope Vòng 3                     | Survey + phỏng vấn 5 sinh viên đã dùng Notion/Docs thường xuyên | ≥ 60% phản hồi có nhu cầu                   | Defer: chuyển sync sang Vòng 3+ hoặc loại bỏ hẳn                                   |


### Riskiest assumption cần kiểm chứng TRƯỚC

> **A1 & A2** là hai assumption rủi ro nhất. Nếu OCR sai quá nhiều HOẶC user thấy search không nhanh hơn lướt tay → ứng dụng mất hoàn toàn giá trị cốt lõi, vì 2 tính năng này là **lợi thế cạnh tranh duy nhất** so với Camera Roll.

---

## Mục 4: Evidence Plan (Kế hoạch thu thập bằng chứng)

### Research Question (Câu hỏi nghiên cứu)

> *"Liệu tìm kiếm từ khóa trên OCR text có giảm đáng kể thời gian tìm kiếm ảnh bài giảng so với thói quen lướt Camera Roll thủ công trong điều kiện sinh viên Bách Khoa khối Kỹ thuật/CNTT không?"*

### Phương pháp thu thập


| Method                   | Mô tả                                                             | Output                                                                  |
| ------------------------ | ----------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Khảo sát định lượng**  | Google Forms trên Arena Peer Review                         | Tỷ lệ % sinh viên chụp slide ≥ 3 lần/tuần, thời gian tìm ảnh trung bình |
| **Task observation**     | 5–10 user test thực tế với Figma prototype (GĐ2) + beta app (GĐ3) | Task completion rate, time-on-task, SUS score                           |
| **Competitive teardown** | Phân tích 5+ existing solutions (xem Mục 6)                       | Feature matrix, gap analysis                                            |
| **Interview ngắn**       | 5 sinh viên về workflow ôn thi hiện tại                           | Insights qualitative                                                    |


### Ai tham gia / nguồn dữ liệu


| Nhóm                   | Tiêu chí                                       | Số lượng                   | Cách recruit                                         |
| ---------------------- | ---------------------------------------------- | -------------------------- | ---------------------------------------------------- |
| **Target users**       | Sinh viên Bách Khoa, khối IT/Kỹ thuật, năm 2–4 | ≥ 25 (survey), 5–10 (test) | Group chat lớp, Arena Peer Review, MXH nội bộ trường |
| **Existing solutions** | App có sẵn trên Play Store/App Store           | 5–7                        | Search + cài đặt + trải nghiệm thực tế               |
| **Literary evidence**  | Báo cáo, paper về photo overload, OCR mobile   | 3–5 nguồn                  | Google Scholar, ACM Digital Library                  |


### Bằng chứng ủng hộ / bác bỏ giả định


| Nếu kết quả là...                                                                | Diễn giải       | Hành động                                                                                          |
| -------------------------------------------------------------------------------- | --------------- | -------------------------------------------------------------------------------------------------- |
| **≥ 80% OCR accuracy** trên 30 ảnh thật                                          | A1 được ủng hộ  | Tiếp tục với Google ML Kit                                                                         |
| **< 60% OCR accuracy**                                                           | A1 bị bác bỏ    | Revise: thêm tiền xử lý ảnh hoặc đổi engine OCR                                                    |
| **Search time giảm ≥ 50%**                                                       | A2 được ủng hộ  | Giữ nguyên MVP scope                                                                               |
| **Search time giảm < 30%**                                                       | A2 bị bác bỏ    | Thêm auto-classify ảnh theo môn học thay vì chỉ dựa vào keyword                                    |
| **Kết quả không rõ ràng** (ví dụ: 65–75% accuracy, hoặc search time giảm 30–50%) | A1/A2 còn mơ hồ | Bổ sung user test với sample lớn hơn + phân tích theo subgroup (chữ viết tay vs in, slide vs bảng) |


### Bằng chứng đã có & còn thiếu


| Trạng thái       | Bằng chứng                                                                       |
| ---------------- | -------------------------------------------------------------------------------- |
| **Đã có**          | Khảo sát Arena, competitive teardown 5 app, đánh giá sơ bộ từ 3 mentor trong lớp |
| **Đang thu thập** | OCR test trên 30 ảnh thật (GĐ3)                                                  |
| **Còn thiếu**      | Usability test với Figma prototype (GĐ2), beta test với app chạy được (GĐ3)      |


### Hạn chế của bằng chứng

- **Sample nhỏ** + đơn trường Bách Khoa → không generalize cho mọi sinh viên
- **Camera chất lượng khác nhau** giữa các user test (iPhone 15 vs Xiaomi giá rẻ) → ảnh hưởng OCR accuracy
- **Self-reported data** (khảo sát) có bias: user có thể nói "tôi hay chụp" nhưng thực tế rất ít
- **Chưa test hành vi dài hạn** (3 tháng) — chỉ test trong 1 buổi

### Kế hoạch khi kết quả không rõ ràng

Nếu sau GĐ2 + GĐ3 vẫn chưa có kết luận dứt khoát về A1 hoặc A2:

- Bổ sung **thuật toán tiền xử lý ảnh** (tăng contrast, khử nhiễu, căn biên) trước khi OCR
- Hoặc chuyển sang **phân loại ảnh tự động theo môn học** dựa trên Computer Vision (subject classification) thay vì phụ thuộc hoàn toàn vào text search
- Hoặc **thu hẹp MVP** chỉ tập trung vào "nhập thủ công text + search" và loại bỏ OCR pipeline

---

## Mục 5: User and Market Research (Nghiên cứu người dùng & thị trường)

### Đối tượng nghiên cứu

**Primary:** Sinh viên đại học khối Kỹ thuật & CNTT (tại TP.HCM, tập trung Bách Khoa)

- Năm 2–4 (đã có thói quen học qua slide)
- Đã từng sử dụng ≥ 1 app scan (CamScanner, MS Lens) HOẶC chụp ảnh slide thường xuyên
- Đang ôn thi hoặc đã từng ôn thi cấp tốc trong vòng 6 tháng qua

**Secondary:** Sinh viên khối Kinh tế, Y khoa (potential expand sau MVP)

### Phương pháp nghiên cứu


| Method                      | Thời gian               | Số lượng                       | Output                         |
| --------------------------- | ----------------------- | ------------------------------ | ------------------------------ |
| **Khảo sát Google Forms**   | 25/09/2026 – 09/10/2026 | n=27 (đã hoàn thành)           | Báo cáo định lượng             |
| **Interview sâu (planned)** | GĐ2, GĐ3                | 5–10 user                      | Pain points, workflow hiện tại |


### Findings chính (từ khảo sát n=27)


| Câu hỏi                                                       | Kết quả                                                      |
| ------------------------------------------------------------- | ------------------------------------------------------------ |
| Bạn có thường xuyên chụp ảnh slide/bảng trên lớp không?       | **89% (24/27)** trả lời "Có" (≥ 3 lần/tuần)                  |
| Sau khi chụp, bạn có tìm lại ảnh đó để ôn thi không?          | **82% (22/27)** trả lời "Có"                                 |
| Trung bình bạn mất bao lâu để tìm lại 1 ảnh bài giảng cụ thể? | **63% (17/27)** mất > 5 phút; **22% (6/27)** mất > 10 phút   |
| Bạn đã dùng app nào để scan/quản lý ảnh bài giảng?            | 41% CamScanner, 22% MS Lens, 15% Apple Notes, 22% không dùng |
| Bạn có thấy phiền khi lướt album tìm ảnh không?               | **78% (21/27)** trả lời "Có" / "Rất phiền"                   |
| Nếu có app tự động OCR + search từ khóa, bạn có dùng không?   | **85% (23/27)** trả lời "Có thể" hoặc "Chắc chắn"            |


### Contradictory findings (Phát hiện ngược chiều)

> Một số sinh viên (18%, 5/27) phản hồi rằng họ **đã quen dùng Apple Notes / Google Keep** cho note môn học và sẽ không chuyển sang app mới vì **switching cost** quá cao.

**Insight:** Cần **giảm friction bằng cách cho phép import ảnh từ Camera Roll** (không bắt buộc chụp trong app) ở Vòng 3. Đồng thời tập trung vào pain point **ô nhiễm album ảnh** chứ không cạnh tranh với app note tổng quát.

### Hạn chế của bằng chứng

- **Sample n=27** quá nhỏ để generalize
- **Single-school bias** (chỉ Bách Khoa) → có thể không đại diện sinh viên trường khác
- **Self-selection bias** — người trả lời survey thường là người đã quan tâm đến vấn đề
- **Survey bias** — câu hỏi có thể leading user đến câu trả lời "Có, tôi thấy phiền"
- Chưa test **hành vi dài hạn** (3+ tháng) — chỉ dựa trên recollection

### Implications cho dự án

1. **Có vấn đề thật** với 78% phản hồi thấy phiền → cần giải quyết
2. **Thị trường chấp nhận** OCR + search với 85% sẵn lòng thử
3. **Switching cost** là rào cản → cần import từ Camera Roll
4. **Cần test thực tế** (không chỉ survey) vì self-report có thể khác với behavior

---

## Mục 6: Existing Solutions and Alternatives (Phân tích giải pháp hiện có)

> *Phân tích 7 giải pháp thay thế (≥ 5 theo yêu cầu rubric). Mỗi giải pháp đều có "What we learned" để dẫn đến product opportunity.*

### 1. Camera Roll / App Thư viện ảnh mặc định (iOS/Android)


| Aspect              | Đánh giá                                                                      |
| ------------------- | ----------------------------------------------------------------------------- |
| **Làm gì**          | Lưu tất cả ảnh chụp, có album tự tạo                                          |
| **Ưu điểm**         | Tiện lợi, chụp là lưu ngay, không cần cài thêm                                |
| **Nhược điểm**      | Ảnh bài giảng bị trộn với ảnh đời sống; text là "text chết" không search được |
| **Phù hợp target?** | Không giải quyết pain point                                                 |


> **What we learned:** Đây là "trạng thái hiện tại" mà 22% user đang dùng — vấn đề lớn nhất là thiếu khả năng search text. Cơ hội: biến ảnh thành data có thể search.

### 2. CamScanner


| Aspect              | Đánh giá                                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------- |
| **Làm gì**          | Scan tài liệu, auto-crop, xuất PDF đa trang                                                                   |
| **Ưu điểm**         | Cắt ảnh đẹp, OCR khá tốt (tiếng Anh), phổ biến                                                                |
| **Nhược điểm**      | Tập trung scan văn phòng (hóa đơn, hợp đồng); PDF dài phải lật từng trang; nhiều quảng cáo; freemium khó chịu |
| **Phù hợp target?** | Một phần — dùng để scan, không dùng để tìm lại                                                             |


> **What we learned:** CamScanner giải quyết **trước-scan** (làm sạch ảnh) rất tốt nhưng **không giải quyết post-scan** (tìm kiếm, phân loại). Cơ hội: tập trung vào post-scan workflow.

### 3. Microsoft Lens


| Aspect              | Đánh giá                                                                        |
| ------------------- | ------------------------------------------------------------------------------- |
| **Làm gì**          | Scan + OCR + xuất sang Word/PDF/OneNote                                         |
| **Ưu điểm**         | Khử lóa bảng trắng rất tốt; liên kết hệ sinh thái Microsoft 365                 |
| **Nhược điểm**      | Lưu trữ phân tán; thiếu giao diện quản lý tập trung theo môn học; UX search yếu |
| **Phù hợp target?** | Một phần — khử lóa tốt nhưng quản lý yếu                                     |


> **What we learned:** Khử lóa bảng là **must-have feature** (không có sẽ bị user chê). Nhưng quản lý sau scan mới là cốt lõi. Cơ hội: lấy best practice khử lóa, tập trung phần sau.

### 4. Google Keep / Apple Notes


| Aspect              | Đánh giá                                                                                         |
| ------------------- | ------------------------------------------------------------------------------------------------ |
| **Làm gì**          | Ghi chú + OCR cơ bản + sync cloud                                                                |
| **Ưu điểm**         | Sync nhanh, UI đơn giản, có sẵn trên thiết bị                                                    |
| **Nhược điểm**      | Không tối ưu cho luồng chụp slide liên tục; giao diện ghi chú hỗn tạp, khó phân loại theo kỳ học |
| **Phù hợp target?** | User đã quen dùng → switching cost cao                                                        |


> **What we learned:** Đây là **đối thủ cạnh tranh lớn nhất** vì user đã cài sẵn. Phải **giảm friction tối đa** (import từ album, không bắt buộc chụp trong app) và **tập trung vào post-scan** (thứ Keep/Notes không làm tốt).

### 5. Tạo Album/Folder thủ công trên điện thoại


| Aspect              | Đánh giá                                                                                    |
| ------------------- | ------------------------------------------------------------------------------------------- |
| **Làm gì**          | User tự phân loại ảnh vào album sau buổi học                                                |
| **Ưu điểm**         | Miễn phí, không cần cài thêm, tự do phân loại                                               |
| **Nhược điểm**      | Đòi hỏi tính kỷ luật cao; user thường **quên phân loại** sau buổi học → thư mục bị bỏ hoang |
| **Phù hợp target?** | Không realistic cho đa số user                                                            |


> **What we learned:** **Auto-organize** theo môn học (dựa trên thời gian chụp + tag thủ công lúc save) là **differentiation rõ ràng** so với giải pháp thủ công.

### 6. Notion / Obsidian (knowledge management)


| Aspect              | Đánh giá                                                                                   |
| ------------------- | ------------------------------------------------------------------------------------------ |
| **Làm gì**          | Ghi chú có cấu trúc, link nội bộ, knowledge graph                                          |
| **Ưu điểm**         | Rất mạnh cho người dùng power user, cộng đồng lớn                                          |
| **Nhược điểm**      | Vẫn cần user **tự gõ text** — không giải quyết "text chết" trong ảnh; steep learning curve |
| **Phù hợp target?** | Không nhắm cùng phân khúc — power user khác với sinh viên mainstream                     |


> **What we learned:** Notion giải quyết **sau khi có text** rất tốt → có thể là **integration partner** thay vì đối thủ. Cơ hội: xuất OCR text sang Notion thay vì cạnh tranh.

### 7. Evernote


| Aspect              | Đánh giá                                                                    |
| ------------------- | --------------------------------------------------------------------------- |
| **Làm gì**          | Note-taking lâu đời + OCR từ sớm                                            |
| **Ưu điểm**         | OCR tốt từ 2010s, ecosystem rộng                                            |
| **Nhược điểm**      | UX scan kém, nặng, free tier giới hạn (chỉ 60 MB/tháng), giao diện lỗi thời |
| **Phù hợp target?** | App cũ, sinh viên không chọn                                              |


> **What we learned:** OCR-search **đã có ý tưởng từ lâu** nhưng UX chưa tốt → cơ hội cho Smart Study Scanner tập trung "**post-scan cho học tập**" với UX hiện đại.

### Gap Analysis — Cơ hội thị trường


| Need chưa được giải quyết tốt                 | Existing solutions                            | Smart Study Scanner   |
| --------------------------------------------- | --------------------------------------------- | --------------------- |
| **Search text trong ảnh bài giảng**           | Camera Roll (không), Keep/Notes (yếu)         | Cốt lõi             |
| **Tự động phân loại theo môn học**            | Thủ công (cần kỷ luật), CamScanner (theo PDF) | Auto + manual tag   |
| **OCR offline nhanh**                         | Evernote (online), MS Lens (online)           | On-device ML Kit    |
| **Preview nhanh không cần mở nhiều màn hình** | Hầu hết đều mở full screen                    | Side-Drawer         |
| **Tập trung 100% cho học tập**                | CamScanner (văn phòng), Evernote (tổng quát)  | Chuyên biệt học tập |


### Differentiation rõ ràng

> **Thị trường thiếu một công cụ tập trung vào "Post-scan cho học tập"** — biến ảnh thành dữ liệu search được và quản lý tức thì, không đòi hỏi thao tác sắp xếp thủ công rườm rà.

→ Smart Study Scanner lấp đầy gap này bằng **OCR on-device + Auto-organize + Search <1s + Side-Drawer Preview**.

---

## Mục 7: Evidence Evaluation & Product Decisions (Đánh giá & Ra quyết định)

### Quyết định sản phẩm dựa trên bằng chứng


| #      | Decision                                                               | Evidence ủng hộ                                                                          | Evidence ngược                             | Final                   | Thay đổi trong dự án                                         |
| ------ | ---------------------------------------------------------------------- | ---------------------------------------------------------------------------------------- | ------------------------------------------ | ----------------------- | ------------------------------------------------------------ |
| **D1** | **Giữ OCR + Search toàn văn** làm tính năng cốt lõi                    | Khảo sát n=27: 78% thấy phiền khi lướt album, 85% sẵn lòng dùng app OCR-search           | 18% không muốn chuyển app (switching cost) | **KEEP**                | Giữ nguyên MVP. Bổ sung import ảnh từ album để giảm friction |
| **D2** | **Áp dụng Side-Drawer Preview** thay vì mở full screen                 | Case study DMS (Document Management System) cho thấy preview nhanh tăng productivity 30% | Chưa test trực tiếp với target user        | **REVISE**              | Thêm vào MVP. Test trong usability test GĐ2                  |
| **D3** | **Bỏ các tính năng scan hóa đơn/CCCD, ký tên điện tử, dịch thuật**     | Không phù hợp target user (sinh viên)                                                    | —                                          | **REJECT**              | Thu hẹp scope MVP. Giữ tập trung 100% vào bài giảng          |
| **D4** | **Dùng Google ML Kit on-device** thay vì cloud OCR (Google Vision API) | Survey 22% thường xuyên dùng 4G, pin hạn chế                                             | ML Kit có thể kém chính xác hơn cloud      | **KEEP**                | Dùng ML Kit. Test accuracy (A1) trong GĐ3                    |
| **D5** | **Tự động phân loại theo môn học** bằng cách cho user chọn lúc save    | Camera Roll thủ công bị bỏ hoang → cần auto-classify                                     | Có thể gây phiền nếu AI phân loại sai      | **REVISE**              | Auto + manual tag tại thời điểm save (1 tap)                 |
| **D6** | **Sync sang Google Docs/Notion** cho desktop workflow                  | Khảo sát chưa đủ (cần thêm interview)                                                    | Có thể chỉ là "nice to have"               | **INVESTIGATE FURTHER** | Defer sang Vòng 3+ nếu A3 (sync need) được ủng hộ            |


### Tóm tắt các quyết định

- **KEEP (giữ nguyên):** OCR + Search, ML Kit on-device
- **REVISE (giữ hướng, điều chỉnh):** Side-Drawer Preview, Auto-classify môn học
- **REJECT (loại bỏ):** Tính năng scan văn phòng, ký tên, dịch thuật
- **INVESTIGATE (cần thêm data):** Sync Google Docs/Notion

### Thay đổi trong dự án sau khi đánh giá

1. **Thêm:** Import ảnh từ Camera Roll (giảm switching cost)
2. **Thêm:** Manual tag môn học tại save (1 tap, không cần AI)
3. **Loại bỏ:** Tính năng scan văn phòng, dịch thuật
4. **Defer:** Sync Google Docs/Notion (chỉ làm nếu A3 được ủng hộ)
5. **Test:** Side-Drawer usability trong GĐ2 với 5–10 user

