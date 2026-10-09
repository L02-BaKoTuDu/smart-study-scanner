# 01 — Project Direction and Rationale

> *Trang này chứa Mục 1 và Mục 2 trong khung 13 mục của Assignment 1.*

---

## Mục 1: Project Direction (Định hướng dự án)

### Bài toán cần giải quyết

Tình trạng **quá tải và phân mảnh ảnh chụp** slide, bảng trắng, sơ đồ ở giảng đường. Sinh viên chụp rất nhiều (trung bình 3–5 buổi/tuần theo khảo sát Arena Peer Review) nhưng ảnh biến thành **"text chết"** trong Camera Roll — không thể gõ từ khóa tìm kiếm khi cần ôn thi cấp tốc.

**Trích dẫn từ khảo sát:**

> *"Mỗi khi ôn thi Hệ điều hành tôi phải lướt đi lướt lại hơn 200 ảnh trong album để tìm 1 slide về Deadlock — mất 10–15 phút, nhiều khi bỏ cuộc."*
> — Sinh viên năm 3, ngành KTMT

### Đối tượng người dùng mục tiêu

**Sinh viên đại học**, đặc biệt **khối ngành IT, Kỹ thuật** (KTMT, Khoa học Dữ liệu, CNTT, Điện-Điện tử, Cơ khí…) vì:

- Thường xuyên học qua **công thức, thuật toán, sơ đồ** — khó ghi tay kịp
- Slide bài giảng có **mật độ thông tin cao**, cần xem lại nhiều lần trước khi thi
- Có **thói quen ôn thi cấp tốc** vào đêm trước ngày thi

### Bối cảnh phát sinh vấn đề


| Khi nào                    | Ở đâu                      | Hành vi                                         |
| -------------------------- | -------------------------- | ----------------------------------------------- |
| Trong giờ học (8:00–17:00) | Giảng đường, phòng lab     | Chụp vội slide/bảng khi giảng viên chuyển nhanh |
| 1–2 tháng sau (sát kỳ thi) | Căntin, xe buýt, hành lang | Lướt Camera Roll tìm lại 1 khái niệm cụ thể     |


**Đặc điểm then chốt:** Hành vi **chụp** và hành vi **tìm lại** cách nhau **nhiều tuần đến nhiều tháng** — đây là lý do hình thành "text chết" trong album.

### Hiện trạng giải quyết


| Cách hiện tại                 | Ưu điểm                        | Nhược điểm                                       |
| ----------------------------- | ------------------------------ | ------------------------------------------------ |
| **Lướt Camera Roll thủ công** | Quen thuộc, không cần cài thêm | Mất 5–15 phút/lần, text không search được        |
| **CamScanner**                | Cắt ảnh đẹp, xuất PDF          | Tạo PDF dài phải lật từng trang, nhiều quảng cáo |
| **Microsoft Lens**            | Khử lóa bảng tốt               | Lưu trữ phân tán, không quản lý theo môn học     |
| **Apple Notes / Google Keep** | Có OCR cơ bản                  | Không tối ưu cho slide bài giảng liên tục        |
| **Album/folder thủ công**     | Miễn phí, tự phân loại         | Đòi hỏi kỷ luật cao, thường bị bỏ hoang          |


### Hướng giải pháp đề xuất

Một **ứng dụng di động** tập trung vào **"Post-scan cho học tập"**:

```
Chụp slide/bảng  →  Tự động OCR On-device  →  Lưu theo môn học  →  Search từ khóa <1s  →  Side-Drawer Preview
```

**Khác biệt so với giải pháp hiện có:**

- Tập trung 100% vào **học tập** thay vì scan văn phòng
- **OCR On-device** (Google ML Kit) → chạy offline, không tốn 4G
- **Search toàn văn** theo từ khóa trên text OCR
- **Side-Drawer Preview** xem nhanh không cần chuyển màn hình
- Tự động cấu trúc folder theo **môn học** (gom nhóm thay vì bắt user sắp xếp)

### Thay đổi so với ý tưởng ban đầu (nếu có)

Ý tưởng ban đầu là "app ghi chú tích hợp OCR". Sau khi phân tích 5 existing solutions (Mục 6), nhóm **thu hẹp scope** thành **chỉ tập trung vào Post-scan workflow** — không cạnh tranh trên mặt trận ghi chú tổng quát (đã có Notion, Evernote, Apple Notes), mà đi sâu vào **pain point "text chết"** mà các app kia chưa giải quyết tốt.

---

## Mục 2: Mobile Product Rationale (Lập luận vì sao phải làm Mobile)

### Tác vụ & bối cảnh di động

Hành vi chụp ảnh bài giảng diễn ra **tức thời tại giảng đường** trong vài giây:

- Slide thay đổi nhanh (PowerPoint mỗi 1–2 phút)
- Bảng trắng bị bôi xóa liên tục
- Cửa sổ thời gian để chụp rất ngắn → user cần **sẵn sàng chụp trong 1 chạm**

→ **Điện thoại là thiết bị duy nhất** user có thể rút ra và thao tác trong tích tắc. Laptop, máy tính bàn không khả thi.

### Khai thác phần cứng di động


| Capability                  | Ứng dụng trong Smart Study Scanner                             |
| --------------------------- | -------------------------------------------------------------- |
| **Camera độ phân giải cao** | Chụp ảnh sắc nét 12–50MP, có OIS, HDR                          |
| **CameraX API**             | Xử lý real-time: auto-focus, exposure, flash control           |
| **Local Photo Library**     | Import ảnh cũ đã chụp trước đó (không bắt buộc chụp trong app) |
| **CPU/NPU on-device**       | Chạy ML Kit Text Recognition **offline** — không cần server    |
| **Persistent storage**      | Lưu DB local (SQLite/Room) để search ngay cả khi offline       |


### Ràng buộc di động & cách giải quyết


| Ràng buộc                                        | Giải pháp                                                                |
| ------------------------------------------------ | ------------------------------------------------------------------------ |
| **Màn hình nhỏ** → khó xem nhiều ảnh cùng lúc    | Side-Drawer preview: trượt từ cạnh phải để xem nhanh text + ảnh phóng to |
| **Pin hạn chế** → OCR nặng có thể tốn pin        | Chạy OCR trong coroutine background, tắt khi app background              |
| **Mạng 3G/4G chập chờn** trong giảng đường       | **Offline-first** — toàn bộ pipeline chạy local, không cần internet      |
| **Bộ nhớ hạn chế**                               | Nén ảnh JPEG 80%, lưu OCR text riêng (rất nhẹ)                           |
| **Đa dạng thiết bị** (Android version khác nhau) | Test trên min SDK 24 (Android 7.0) — phủ 95% thiết bị                    |


### Cân nhắc alternative platforms


| Platform        | Có thay thế được mobile? | Lý do                                                                                                     |
| --------------- | ------------------------ | --------------------------------------------------------------------------------------------------------- |
| **Web**         | Không                    | Không truy cập được Camera native; không có offline storage persistent; user phải mở browser mỗi lần chụp |
| **Desktop app** | Không                    | Không mang theo lên giảng đường; thiếu camera chất lượng cao                                              |
| **Smart watch** | Không                    | Màn hình quá nhỏ, camera chất lượng thấp                                                                  |
| **Tablet**      | Một phần                 | Có thể dùng để đọc lại tài liệu, nhưng vẫn cần mobile để chụp                                             |
| **Mobile**      | Đúng công cụ             | Kết hợp đủ: camera + local storage + on-device ML + di động cao                                           |


### Đồng bộ đa nền tảng (điểm bổ sung)

Ứng dụng mobile là **cổng thu nạp dữ liệu chính**, nhưng hỗ trợ **xuất sang Google Docs/Notion** để sinh viên tổng hợp đề cương trên laptop khi ôn thi. Đây là tính năng **Major Project** (xem Mục 9 — Impact-Effort Matrix) chứ không phải core MVP.

### Tổng kết: Mobile có cải thiện có ý nghĩa không?

**Có**, vì:

1. **Tác vụ chụp ảnh** gắn liền với context di động (giảng đường, thời gian thực)
2. **On-device OCR** chỉ khả thi trên mobile có NPU/CPU hiện đại
3. **Offline-first** đáp ứng ràng buộc mạng không ổn định
4. **Side-Drawer preview** tận dụng pattern di động (vuốt từ cạnh)
5. **Local storage** cho phép search ngay lập tức không cần server

