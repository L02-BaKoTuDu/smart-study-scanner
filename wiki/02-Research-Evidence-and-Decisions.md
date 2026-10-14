# 02 — Research Evidence and Decisions

> Trang này bao gồm **Mục 3–7** của Assignment 1. 
>
> **Nguồn dữ liệu:** `Khảo sát Nhu cầu & Trải nghiệm Tìm kiếm Tài liệu Bài giảng — Smart Study Scanner (Câu trả lời).xlsx`. Có **12 phản hồi tổng cộng**, trong đó **10 người trả lời các câu hỏi chính**. Các tỷ lệ phải ghi mẫu số tương ứng; các nhận định về tác động của sản phẩm chỉ là giả thuyết cho đến khi được kiểm chứng bằng user testing.

---

## Mục 3: Critical Assumptions (Các giả định cốt lõi)

| # | Giả định | Vì sao quan trọng? | Phương pháp kiểm chứng | Tiêu chí đề xuất | Hành động nếu không đạt |
| --- | --- | --- | --- | --- | --- |
| **A1** | OCR on-device nhận diện đủ chính xác chữ trong ảnh bài giảng | OCR sai khiến tìm kiếm bỏ sót tài liệu | Benchmark ít nhất 30 ảnh thực tế, phân nhóm slide in, bảng, code, công thức | Accuracy mục tiêu ≥80% trên văn bản thông thường; báo cáo riêng từng nhóm | Tiền xử lý ảnh, thay engine hoặc giới hạn loại nội dung hỗ trợ |
| **A2** | OCR + tìm kiếm từ khóa giúp tìm ảnh nhanh hơn so với cách hiện tại | Hiệu quả tìm lại ảnh mới là giá trị cốt lõi cần chứng minh | Đo cùng người dùng trên các tác vụ tương đương: tìm bằng thư viện mặc định và prototype/app; đảo thứ tự tác vụ | Median time giảm ≥50% **(mục tiêu, chưa phải kết quả)**, không giảm task completion | Thử duyệt theo môn học/buổi học hoặc cách tìm kiếm khác |
| **A3** | Tổ chức ảnh theo môn/buổi học giúp giảm khó khăn khi tìm lại | 8/10 khó nhớ ảnh ở đâu/khi nào; 7/10 ảnh học lẫn ảnh cá nhân | So sánh manual tag, nhóm theo buổi học và keyword search | Đo time-on-task, số thao tác, task completion | Điều chỉnh cơ chế tổ chức; hạn chế nhập liệu thủ công |
| **A4** | Import ảnh từ thư viện làm giảm friction so với bắt buộc chụp trong app | Người dùng đã quen camera và thư viện mặc định | Usability test hai luồng: chụp trong app và import từ Gallery | Đo tỷ lệ hoàn thành, số bước, cảm nhận thuận tiện | Ưu tiên luồng Gallery-first |
| **A5** | Một nhóm người dùng cần xuất/đồng bộ tài liệu sang Docs/Notion | 4/10 chọn nhu cầu xuất/đồng bộ; 6/10 chỉ dùng trên điện thoại | Interview về desktop workflow và thử nghiệm chức năng export trước | Chỉ ưu tiên khi có tình huống sử dụng lặp lại rõ ràng | Trì hoãn đồng bộ hai chiều |

### Riskiest assumptions

**A2 và A3** cần được kiểm chứng sớm vì khảo sát chỉ ra vấn đề *tìm lại và tổ chức ảnh*, chưa xác nhận OCR là giải pháp tối ưu. **A1** cần benchmark ngay khi có prototype để xác định giới hạn thực tế đối với chữ, code và công thức.

---

## Mục 4: Evidence Plan (Kế hoạch thu thập bằng chứng)

### Research question

> Trong quá trình học và ôn thi, sinh viên gặp trở ngại gì khi lưu trữ, tổ chức và tìm lại ảnh bài giảng; và cơ chế nào (keyword search trên OCR text, duyệt theo môn/buổi học, hay kết hợp) giúp hoàn thành tác vụ nhanh và chính xác hơn?

### Phương pháp thu thập

| Method | Trạng thái | Output |
| --- | --- | --- |
| Khảo sát Google Forms | **Đã thu thập**: 12 phản hồi, 10 phản hồi chính | Thói quen chụp, lưu, tìm; pain points; nhu cầu xuất/đồng bộ; phản hồi mở |
| Interview người dùng | **Dự kiến**: 5–10 người | Workflow thực tế, switching cost, hành vi dùng nhiều thiết bị |
| Task observation/usability | **Dự kiến**: 5–10 người, prototype rồi beta app | Time-on-task, task completion, số thao tác, SUS |
| OCR benchmark | **Dự kiến**: ít nhất 30 ảnh thực | Accuracy theo từng loại nội dung, lỗi cụ thể |
| Competitive teardown | **Cần xác minh theo phiên bản sản phẩm** | Feature matrix, task comparison, giới hạn hệ thống có sẵn |

### Tiêu chí ủng hộ và bác bỏ giả định

| Quan sát từ thử nghiệm | Diễn giải | Hành động |
| --- | --- | --- |
| OCR accuracy ≥80% trên văn bản thông thường | Bước đầu ủng hộ A1 | Tiếp tục ML Kit và mở rộng kiểm thử |
| OCR accuracy <60% hoặc sai nghiêm trọng với nội dung mục tiêu | A1 gặp rủi ro | Tiền xử lý, engine khác hoặc giới hạn scope |
| Median tìm ảnh nhanh hơn ≥50% và task completion không giảm | Bước đầu ủng hộ A2 | Giữ hướng giải pháp, tiếp tục test với mẫu lớn hơn |
| Median chỉ cải thiện <30% | Bằng chứng A2 yếu | Thử browse/grouping theo môn hoặc buổi học |
| Kết quả nằm giữa các ngưỡng hoặc khác biệt lớn giữa nhóm ảnh | Chưa kết luận | Bổ sung mẫu và phân tích từng nhóm |

**Lưu ý:** Các ngưỡng này do nhóm đề xuất làm tiêu chí thiết kế thử nghiệm, **không phải các kết quả đã được khảo sát chứng minh**.

### Bằng chứng hiện có và hạn chế

- Đã có khảo sát định lượng nhỏ và một số phản hồi mở.
- Chưa có bằng chứng thực nghiệm trong file Excel về tốc độ tìm kiếm, accuracy OCR, khả năng giữ chân người dùng hay mức sẵn lòng cài ứng dụng.
- Mẫu là convenience sample, tập trung nhóm Máy tính/CNTT; không đủ để suy rộng ra mọi sinh viên.
- Thời gian tìm lại ảnh là số liệu **tự báo cáo**, không phải đo bằng thiết bị.
- Các cột đánh giá mức độ khó khăn, yêu cầu accuracy OCR và mức hấp dẫn của tính năng có phần **không có câu trả lời**; không được tự suy ra tỷ lệ từ các cột trống.
- Việc chọn hoặc yêu thích tính năng trong khảo sát không tương đương với hành vi sử dụng sản phẩm ngoài thực tế.

---

## Mục 5: User and Market Research (Nghiên cứu người dùng & thị trường)

### Đối tượng và mẫu nghiên cứu

- **Target dự kiến:** Sinh viên đại học cần lưu trữ và tìm lại ảnh bài giảng, bước đầu tập trung nhóm CNTT/Kỹ thuật.
- **Mẫu khảo sát thực tế:** **N=12** lượt phản hồi; **n=10** trả lời phần lớn câu hỏi nội dung. Cả 10 người có thông tin ngành học đều thuộc nhóm Máy tính/CNTT.
- **Thời gian phản hồi trong Excel:** Có phản hồi từ **08/10 đến 11/10/2026**. Không tiếp tục ghi “25/09–09/10, n=27” khi không có nguồn xác thực bổ sung.
- Với câu hỏi chọn nhiều đáp án, mỗi đáp án có mẫu số riêng và các tỷ lệ **không cộng thành 100%**.

### Findings định lượng

| Nội dung | Kết quả từ Excel | Diễn giải có căn cứ |
| --- | --- | --- |
| Tần suất chụp | 5/12 hầu như mỗi buổi/hằng ngày; 5/12 khoảng 1–4 lần/tuần; 2/12 hiếm khi/không bao giờ | Có thói quen chụp ở nhiều người; **không thể kết luận 89% chụp ≥3 lần/tuần** |
| Cách lưu/tìm ảnh | 9/10 dùng thư viện mặc định và lướt thủ công; 1/10 tạo album theo môn | Luồng làm việc hiện tại phụ thuộc nhiều vào thư viện ảnh |
| Thời gian tìm một ảnh | 2/10 dưới 30 giây; 6/10 khoảng 1–3 phút; 2/10 trên 5 phút/không tìm được | Chỉ **2/10** thuộc nhóm mất trên 5 phút/không tìm được; không có căn cứ cho 63% |
| Không nhớ vị trí/ngày chụp | **8/10** | Pain point nổi bật nhất trong mẫu |
| Ảnh học trộn lẫn ảnh cá nhân | **7/10** | Nhu cầu tổ chức/nhóm ảnh đáng ưu tiên |
| Ảnh bị lóa/nghiêng/khó đọc | **6/10** | Chất lượng ảnh ảnh hưởng usability |
| Text trong ảnh không thể copy/search | **3/10** | OCR có tiềm năng nhưng không phải pain point được chọn nhiều nhất |
| PDF dài phải lật nhiều trang | **2/10** | Pain point phụ |
| Muốn xuất/đồng bộ sang Docs/Notion | **4/10** | Có phân khúc quan tâm đến desktop/export workflow |
| Chỉ lưu và xem trên điện thoại | **6/10** | Phù hợp tiếp cận mobile-first |
| Bối cảnh dùng keyword search | 5/10 ôn thi cấp tốc; 2/10 tổng hợp ghi chú hằng tuần; 3/10 hầu như không dùng | Không thể suy ra “85% chắc chắn/có thể dùng app” |

### Contradictory findings và phản hồi mở

1. **Lợi thế cạnh tranh OCR không mặc nhiên tồn tại.** Người trả lời lưu ý iOS Live Text và Google Lens/Photos có khả năng xử lý văn bản/ảnh; nhóm phải kiểm tra công cụ hiện có trước khi tuyên bố “Camera Roll hoàn toàn không search được text”.
2. **Mở app riêng để chụp có thể tăng thao tác.** Có phản hồi ưu tiên camera mặc định; import từ Gallery nên là luồng đầu vào chính chứ không phải tiện ích thêm rất muộn.
3. **OCR không đồng nghĩa đọc hiểu ảnh học tập.** Công thức, code, sơ đồ và chữ viết tay cần đánh giá riêng.
4. **Gợi ý về smart grouping.** Một số ý kiến đề xuất gom ảnh theo buổi học, môn học hoặc thời gian/lịch học; đó là **ý tưởng cần thử nghiệm**, không phải nhu cầu đã được xác nhận về tỷ lệ.

### Implications

**Observed need:** Khó nhớ, khó tổ chức và tìm lại ảnh bài giảng.

**Proposed solution hypothesis:** Kết hợp OCR search với duyệt theo môn, buổi hoặc thời điểm chụp — thay vì mặc định keyword search giải quyết mọi vấn đề.

**Next evidence needed:** Test thực tế trên cùng tập ảnh để xác định giải pháp nào ít thao tác, tìm đúng và nhanh hơn.

---

## Mục 6: Existing Solutions and Alternatives (Phân tích giải pháp hiện có)

> Đây là **khung comparative research cần kiểm chứng**; không diễn giải thành kết quả benchmark đã hoàn tất. Tính năng của mỗi sản phẩm phải được xác nhận theo phiên bản/platform cụ thể.

| Giải pháp | Vai trò trong workflow | Cần đánh giá thực nghiệm | Product opportunity/risk |
| --- | --- | --- | --- |
| Camera Roll / Photos mặc định | Chụp, lưu và duyệt ảnh | Search text/nội dung ảnh, albums, cách tìm theo ngày, số bước thao tác | Hành vi đã quen; app mới phải chứng minh giá trị tăng thêm |
| Google Photos / Lens | Xử lý và tìm thông tin từ ảnh | Tính năng nhận diện, keyword search, online/offline | OCR có thể không phải điểm khác biệt đủ lớn |
| Apple Photos / Live Text | Nhận dạng và tương tác với văn bản trong ảnh | Khả năng theo phiên bản iOS/thiết bị và search | Rủi ro trùng chức năng hệ điều hành |
| CamScanner | Scan, OCR, xuất tài liệu | Chất lượng crop, tìm nội dung sau scan, tổ chức ảnh | Cạnh tranh ở **post-scan workflow** nếu chứng minh tốt hơn |
| Microsoft Lens / các công cụ Microsoft | Scan và đưa dữ liệu sang hệ sinh thái tài liệu | Trạng thái sản phẩm hiện tại, luồng xuất, quyền truy cập | Tránh dùng so sánh lỗi thời |
| Google Keep / Apple Notes | Ghi chú có ảnh và đồng bộ | Nhập ảnh, OCR, search, tổ chức theo môn | Switching cost là giả thuyết cần phỏng vấn |
| Notion / Obsidian / Evernote | Quản lý tri thức | OCR, import, tìm kiếm và chi phí thực tế | Có thể là đích export, không nhất thiết là đối thủ trực tiếp |

### Gap hypothesis

> Cơ hội của Smart Study Scanner **không phải** “OCR-search chưa tồn tại”, mà có thể là **workflow tìm lại ảnh bài giảng theo ngữ cảnh học tập**: import ảnh cũ, tổ chức theo môn/buổi, tìm theo text và xác nhận kết quả nhanh với ít thao tác.

**Cách xác thực khác biệt:** Dùng cùng bộ ảnh và cùng các tác vụ tìm ảnh để so sánh giữa prototype và các giải pháp có sẵn. Đo time-to-find, tỷ lệ tìm đúng, số thao tác và khả năng xử lý nội dung đặc thù. Không công bố “search <1s” hoặc “tiết kiệm 50–70%” như thực tế khi chưa đo.

---

## Mục 7: Evidence Evaluation & Product Decisions (Đánh giá và quyết định)

| # | Decision | Bằng chứng hiện có | Điểm chưa rõ | Kết luận và hành động |
| --- | --- | --- | --- | --- |
| **D1** | Giữ hướng tìm kiếm ảnh bằng OCR + keyword | 3/10 chọn khó copy/search text; 8/10 quên nơi/ngày chụp | Search hay grouping hiệu quả hơn? | **KEEP AS HYPOTHESIS** — thử nghiệm song song search và browse |
| **D2** | Import ảnh từ Gallery bên cạnh chụp trong app | 9/10 đang lưu/tìm trong thư viện mặc định; phản hồi mở nêu friction của app chụp riêng | Luồng nào thuận tiện hơn? | **REVISE MVP** — coi Gallery import là luồng chính |
| **D3** | Quản lý theo môn/buổi học | 8/10 khó nhớ vị trí, 7/10 ảnh trộn lẫn | Manual tag có gây phiền? Auto-group có chính xác? | **KEEP + TEST** — bản đầu manual tagging; không gọi là auto-classification |
| **D4** | Thử OCR on-device bằng ML Kit | Phù hợp định hướng thử nghiệm mobile/offline; có phản hồi về code và công thức | Độ chính xác trên dữ liệu thực và khả năng cạnh tranh OCR sẵn có | **EXPERIMENT** — benchmark trước khi khẳng định lợi thế |
| **D5** | Preview nhanh kết quả | Hợp lý về UX nhưng chưa có khảo sát so sánh dạng preview | Side-Drawer có thực sự tốt hơn thumbnail/detail screen? | **TEST UX** — không khóa MVP vào Side-Drawer |
| **D6** | Export Docs/Notion, đồng bộ | 4/10 quan tâm, 6/10 chỉ dùng trên điện thoại | Tần suất dùng laptop và nhu cầu sync hai chiều | **INVESTIGATE** — thử export thủ công, defer sync backend |
| **D7** | Không phát triển hóa đơn/CCCD, ký tên, dịch thuật | Ngoài bài toán đang nghiên cứu | Không cần test trong MVP | **OUT OF SCOPE** |