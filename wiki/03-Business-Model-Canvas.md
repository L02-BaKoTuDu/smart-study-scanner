# 03 — Business Model Canvas

> *Trang này chứa Mục 8 trong khung 13 mục của Assignment 1: Business Model Canvas 3×3.*
>
> **Căn cứ:** [02 — Research Evidence and Decisions](02-Research-Evidence-and-Decisions.md). Các con số về hiệu quả sản phẩm bên dưới là **mục tiêu hoặc giả thuyết**, không phải kết quả kiểm thử.

---

## Mục 8: Business Model Canvas (Ma trận 3×3)

### Bảng Canvas

| Thành phần | Cột 1 | Cột 2 | Cột 3 |
| :--- | :--- | :--- | :--- |
| **Hàng 1** | **Problem**<br>Ảnh bài giảng bị trộn lẫn, khó nhớ vị trí/thời điểm chụp và khó tìm lại khi học. Khảo sát: **8/10** khó nhớ ảnh ở đâu/ngày nào; **7/10** gặp tình trạng ảnh học lẫn ảnh cá nhân. | **Customer/User**<br>Sinh viên đại học có thói quen chụp/lưu ảnh bài giảng; **mẫu hiện có** tập trung vào ngành Máy tính/CNTT, chưa đủ căn cứ đại diện toàn khối kỹ thuật. | **Channels**<br>Tiếp cận thử nghiệm qua nhóm lớp, nhóm sinh viên, kênh nội bộ trường và bản APK thử nghiệm. **Chưa xác thực** hiệu quả thu hút và giữ người dùng qua các kênh này. |
| **Hàng 2** | **Solution**<br>Import ảnh từ Gallery **hoặc** chụp mới → lưu và gắn nhãn môn/buổi → OCR on-device → tìm từ khóa **hoặc** duyệt theo ngữ cảnh → xem ảnh phù hợp. | **Advantage (hypothesis)**<br>Workflow chuyên cho ảnh học tập, kết hợp tổ chức và tìm lại ảnh trong một nơi; offline-first nếu được triển khai/kiểm thử đạt yêu cầu. **Chưa chứng minh** vượt trội so với Photos/Lens/Notes. | **Costs**<br>Công phát triển của nhóm; kiểm thử trên thiết bị; lưu trữ và bảo trì. Hạ tầng server/cloud chỉ phát sinh nếu triển khai các tính năng có sử dụng backend. |
| **Hàng 3** | **Value (hypothesis)**<br>Giúp sinh viên tìm **đúng ảnh** nhanh hơn và giảm công sức tổ chức tài liệu; **không khẳng định** đã tiết kiệm một tỷ lệ thời gian ôn tập cụ thể. | **Metrics**<br>Median **time-to-find**, tỷ lệ tìm đúng ảnh, task completion, số thao tác để nhập/tổ chức ảnh, OCR accuracy theo loại ảnh. Mục tiêu thử nghiệm ban đầu: thời gian tìm đúng ảnh giảm ≥50% **nếu** không giảm tỷ lệ hoàn thành. | **Revenue**<br>MVP học thuật miễn phí. Freemium cho sync/lưu trữ cloud hoặc export nâng cao chỉ là **phương án tương lai**, chưa có bằng chứng willingness-to-pay. |

---

### Mối liên hệ giữa 3 nhóm thành phần

#### Cặp 1: Problem ↔ Customer/User ↔ Channels

**Observed evidence:** Trong 10 người trả lời phần chính, **8/10** chọn khó nhớ ảnh nằm ở đâu hoặc được chụp khi nào; **7/10** chọn ảnh bài giảng trộn với ảnh cá nhân; **3/10** chọn tình trạng chữ trong ảnh không thể copy/search. Với tần suất chụp ảnh, **5/12** cho biết hầu như mỗi buổi/hằng ngày, **5/12** khoảng 1–4 lần/tuần và **2/12** hiếm khi/không bao giờ.

**Interpretation:** Vấn đề cần ưu tiên là **tổ chức và tìm lại ảnh bài giảng**, không nên đồng nhất toàn bộ vấn đề với thiếu OCR. Mẫu khảo sát hỗ trợ việc tìm hiểu nhóm sinh viên Máy tính/CNTT, **chưa xác nhận quy mô thị trường hay khả năng mở rộng cho mọi sinh viên**.

**Channel hypothesis:** Nhóm lớp và cộng đồng sinh viên có thể giúp tuyển người dùng thử. Việc thu được phản hồi khảo sát **không tương đương** xác thực kênh phân phối ứng dụng; cần đo lượt tiếp cận, cài đặt, kích hoạt và sử dụng trở lại.

#### Cặp 2: Solution ↔ Advantage ↔ Costs

**Product hypothesis:** Kết hợp Gallery Import, tổ chức theo môn/buổi, OCR và hai cách tìm lại (search/browse) có thể giảm thời gian và công sức hơn chỉ sử dụng thư viện mặc định. Đây là **giả thuyết** phải được thử nghiệm đối chứng, không phải ưu thế cạnh tranh đã được chứng minh.

**Scope discipline:** Trong MVP, **chọn môn thủ công** không được gọi là “tự động phân loại”. Tính năng **quick preview** là nhu cầu giao diện; Side-Drawer chỉ là một phương án thiết kế cần thử nghiệm. Cloud sync và export nâng cao chưa phải yêu cầu cốt lõi.

**Cost discipline:** Không đồng nhất sử dụng gói miễn phí với chi phí vận hành bằng 0. Ngay cả MVP local-first vẫn cần công phát triển, kiểm thử trên nhiều thiết bị và hỗ trợ sửa lỗi; lựa chọn backend cần bám theo kiến trúc thực tế.

#### Cặp 3: Value ↔ Metrics ↔ Revenue

**Value proposition cần xác thực:** Giúp người dùng **tìm đúng ảnh bài giảng** nhanh hơn, với tổng công sức lưu/nhập và sắp xếp không tăng bất hợp lý. Không chuyển claim “giảm thời gian tìm ảnh” thành “giảm 50–70% thời gian ôn tập”.

**Validation:** Thử các tác vụ tìm lại ảnh có mức khó tương đương giữa ứng dụng và phương pháp hiện tại; đo cả thời gian, tỷ lệ tìm đúng, hoàn thành tác vụ và công sức tổ chức trước khi tìm. Mục tiêu **median time-to-find giảm ≥50%** là *pass criterion dự kiến* cho thử nghiệm, **chưa phải kết quả**.

**Revenue:** Chưa đo nhu cầu trả phí. Trong khảo sát có **4/10** muốn xuất/đồng bộ sang Docs/Notion và **6/10** chỉ muốn lưu, xem trên điện thoại; các lựa chọn này chỉ gợi ý nhu cầu workflow, **không chứng minh willingness-to-pay**. Giữ Freemium ở mức giả thuyết hậu MVP.

---

### Chi tiết từng ô

#### Problem (Vấn đề)

- **8/10** người trả lời phần chính gặp khó khăn nhớ ảnh chụp vào thời điểm nào/ở vị trí nào.
- **7/10** gặp tình trạng ảnh học trộn với ảnh cá nhân.
- **6/10** nêu ảnh bị lóa, nghiêng hoặc khó đọc.
- **3/10** chọn khó copy/search chữ trong ảnh; **2/10** chọn PDF dài phải lật nhiều trang.
- Thời gian tìm ảnh **tự báo cáo**: **2/10** dưới 30 giây, **6/10** khoảng 1–3 phút, **2/10** trên 5 phút/không tìm thấy. Chưa có benchmark theo dõi trực tiếp.

#### Solution (Giải pháp đề xuất)

- Nhận đầu vào từ **Gallery Import hoặc camera trong app**, để không ép người dùng đổi thói quen chụp ảnh ngay từ đầu.
- Lưu ảnh vào bộ sưu tập học tập, có **môn học/buổi học**; MVP có thể dùng gắn nhãn thủ công.
- OCR on-device và xây chỉ mục text để hỗ trợ keyword search, **đồng thời** cho phép duyệt theo ngữ cảnh khi không nhớ từ khóa.
- Hiển thị kết quả/ảnh để người dùng xác nhận nhanh; chưa ràng buộc vào Side-Drawer.
- Kiểm thử riêng OCR với ảnh code, công thức, chữ viết tay và chất lượng thấp trước khi công bố phạm vi hỗ trợ.

#### Value (Giá trị đề xuất — chưa xác nhận)

- Giảm thời gian **tìm đúng ảnh** cần ôn tập.
- Giảm việc lướt qua nhiều ảnh không liên quan và công sức ghi nhớ nơi lưu ảnh.
- Tạo một workflow riêng cho ảnh bài giảng, không yêu cầu người dùng xây hệ thống ghi chú phức tạp.
- **Status:** Giả thuyết sẽ kiểm chứng bằng task observation; không tuyên bố tiết kiệm 50–70% thời gian ôn tập.

#### Customer/User (Người dùng)

- **Primary hypothesis:** Sinh viên đại học thường chụp/lưu ảnh slide, bảng trắng, tài liệu học tập; ưu tiên thử ở nhóm Máy tính/CNTT.
- **Evidence:** Khảo sát có **N=12**, với **n=10** trả lời các câu hỏi phần chính; cả 10 người khai ngành đều thuộc nhóm Máy tính/CNTT.
- **Not yet established:** Mức độ phù hợp với ngành khác, willingness-to-install, mức độ sử dụng lâu dài và willingness-to-pay.

#### Advantage (Lợi thế cạnh tranh — giả thuyết)

- Workflow kết hợp **nhập ảnh → tổ chức → tìm lại**, dành cho ngữ cảnh học tập.
- Cho phép cả **keyword search** lẫn **browse theo môn/buổi**.
- OCR/local search offline-first là **mục tiêu thiết kế**, cần kiểm chứng điều kiện hoạt động thực tế.
- **Chưa đủ bằng chứng** để nói hệ điều hành và ứng dụng cạnh tranh không thể OCR/search ảnh; cần competitive teardown có phiên bản và bài test cụ thể.

#### Metrics (Chỉ số đo lường)

| Metric | Cách đo | Trạng thái |
| --- | --- | --- |
| **Time-to-find** | Thời gian từ khi bắt đầu yêu cầu tìm ảnh đến khi mở **đúng** ảnh; báo cáo median và tình huống thất bại | Chưa đo; target thử nghiệm giảm ≥50% so với baseline công bằng |
| **Correct retrieval / task success** | Tỷ lệ người dùng mở đúng ảnh trong mỗi kịch bản | Chưa đo |
| **Organization effort** | Số thao tác, thời gian thêm/gắn nhãn/nhập ảnh trước khi tìm | Chưa đo |
| **OCR quality** | Character/word error hoặc accuracy theo loại ảnh; thêm hiệu quả tìm từ khóa trên text OCR | Chưa đo; mục tiêu sơ bộ ≥80% cho văn bản thông thường cần định nghĩa rõ |
| **Usability / retention** | SUS sau test; quay lại dùng ứng dụng qua các buổi học | Chưa đo |

#### Channels (Kênh tiếp cận)

- **Pilot:** Nhóm lớp, nhóm sinh viên, mạng xã hội nội bộ, giới thiệu APK/bản test tới người đồng ý thử.
- **Chưa validate:** Acquisition, conversion sang cài đặt, activation và retention.
- **Future:** Phân phối qua store nếu MVP được kiểm chứng và đáp ứng yêu cầu phát hành.

#### Costs (Chi phí)

- Thời gian của nhóm phát triển, thiết kế, kiểm thử và viết báo cáo trong học kỳ.
- Kiểm thử đa dạng thiết bị, dữ liệu ảnh OCR, hỗ trợ lỗi và bảo trì.
- Hosting/server/database, domain và các dịch vụ khác **chỉ** tính theo phần triển khai thực tế; free tier không bảo đảm vận hành dài hạn miễn phí.
- Không ấn định tổng MVP “0 VND” khi chưa lập bảng chi phí và phạm vi hạ tầng.

#### Revenue (Doanh thu)

- **MVP:** Miễn phí vì mục tiêu học thuật và kiểm chứng giả thuyết.
- **Post-MVP hypothesis:** Freemium cho cloud backup/sync hoặc tính năng xuất tích hợp nâng cao, **nếu** kiểm chứng được nhu cầu và khả năng chi trả.
- Khảo sát hiện tại **không đo mức giá hay khả năng trả phí**, nên chưa thể kết luận tính khả thi thương mại.

---

