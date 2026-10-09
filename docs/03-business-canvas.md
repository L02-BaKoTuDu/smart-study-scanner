# 03 — Business Model Canvas

> *Trang này chứa Mục 8 trong khung 13 mục bắt buộc — Business Model Canvas 3×3.*

---

## Mục 8: Business Model Canvas (Ma trận 3×3)

### Bảng Canvas

| Thành phần | Cột 1 | Cột 2 | Cột 3 |
| :--- | :--- | :--- | :--- |
| **Hàng 1** | **Problem**<br>Quá tải ảnh slide/bảng; "text chết" không thể tra cứu khi ôn thi. | **Customer/User**<br>Sinh viên ĐH khối IT/Kỹ thuật chụp bài giảng 3–5 lần/tuần (Evidence: n=27). | **Channels**<br>Cài APK trực tiếp; chia sẻ qua Arena Peer Review, group chat lớp, MXH nội bộ trường. |
| **Hàng 2** | **Solution**<br>Chụp ảnh → OCR On-device → Tìm kiếm từ khóa & xem qua Side-Drawer. | **Advantage**<br>Tốc độ search <1s; hoạt động offline (Offline-First); chuyên biệt cho học tập. | **Costs**<br>Chi phí phát triển (5 thành viên × 1 học kỳ); hosting server Express.js & MongoDB Atlas (Free-tier). |
| **Hàng 3** | **Value**<br>Tiết kiệm 50–70% thời gian ôn tập; biến ảnh thành kho tri thức cá nhân tra cứu nhanh. | **Metrics**<br>Thời gian tìm kiếm bài giảng (target <15s); tần suất search/ngày; độ chính xác OCR (target ≥80%). | **Revenue**<br>Mô hình học thuật miễn phí trong MVP; định hướng **Freemium** cho lưu trữ cloud & sync đa thiết bị ở giai đoạn sau. |

---

### Mối liên hệ giữa 3 cặp thành phần (theo rubric)

#### Cặp 1: Problem ↔ Customer ↔ Channels

> **Problem (text chết trong ảnh)** được giải quyết bằng cách phục vụ **Customer (sinh viên IT/Kỹ thuật)** — nhóm đã được xác nhận qua khảo sát (n=27, 78% thấy phiền khi lướt album). **Channels** (Arena + group chat lớp) là cách tiếp cận đã validate vì khảo sát được thu thập thành công qua Arena Peer Review.

→ **Nhất quán:** Giải quyết đúng vấn đề, đúng người, qua đúng kênh.

#### Cặp 2: Solution ↔ Advantage ↔ Costs

> **Solution (OCR On-device + Search)** tận dụng **Advantage (Offline-First + <1s search + chuyên biệt học tập)** — 3 lợi thế cạnh tranh đã được xác nhận qua Mục 6 (Gap Analysis). **Costs** (5 người × 1 HK + Free-tier hosting) là chi phí khởi đầu thấp, phù hợp với dự án học thuật.

→ **Nhất quán:** Solution khai thác Advantage để giải quyết Problem với Costs hợp lý.

#### Cặp 3: Value ↔ Metrics ↔ Revenue

> **Value (tiết kiệm 50–70% thời gian ôn tập)** được đo lường bằng **Metrics (task time + search frequency + OCR accuracy)** — đây là các chỉ số có thể đo lường khách quan trong GĐ2 + GĐ3. **Revenue (Freemium)** là mô hình chưa tập trung ở MVP nhưng đã định hướng cho giai đoạn sau.

→ **Nhất quán:** Value claim (50–70%) là **assumption cần test** (A2), không phải fact. Metrics sẽ validate hoặc bác bỏ Value này. Revenue chỉ khả thi khi Value được xác nhận.

---

### Chi tiết từng ô

#### Problem (Vấn đề)
- Quá tải ảnh slide/bảng trong Camera Roll
- "Text chết" — không thể tra cứu khi ôn thi
- Mất 5–15 phút cho mỗi lần tìm ảnh
- 78% sinh viên (n=27) thấy phiền

#### Solution (Giải pháp)
- Ứng dụng di động Android (Expo/React Native)
- Auto-crop + OCR On-device (Google ML Kit)
- Tự động lưu theo môn học
- Full-text search từ khóa <1s
- Side-Drawer preview không cần mở full screen

#### Value (Giá trị mang lại)
- **Claim chính:** Tiết kiệm 50–70% thời gian ôn tập
- Biến ảnh "chết" thành kho tri thức cá nhân tra cứu nhanh
- Tăng hiệu quả ôn thi cấp tốc
- **Status:** Đây là **assumption** (A2) cần test trong GĐ2/GĐ3

#### Customer/User (Khách hàng)
- **Primary:** Sinh viên ĐH khối Kỹ thuật/CNTT, năm 2–4
- Đã từng chụp slide ≥ 3 lần/tuần
- Đang ôn thi hoặc đã từng ôn thi cấp tốc
- Có smartphone Android (min SDK 24)
- **Evidence:** Khảo sát n=27, 89% chụp slide thường xuyên

#### Advantage (Lợi thế vượt trội)
- **Tốc độ:** Search <1s (vs 5–15 phút lướt tay)
- **Offline-First:** OCR On-device, không cần internet
- **Chuyên biệt:** 100% tập trung cho học tập (khác CamScanner, Evernote)
- **Privacy:** Ảnh không rời khỏi máy → an tâm về dữ liệu cá nhân

#### Metrics (Chỉ số đo lường)
- **Time-on-task:** Thời gian tìm ảnh từ khóa (target <15s)
- **Search frequency:** Số lần search/ngày/user (proxy cho engagement)
- **OCR accuracy:** % text đúng trên 30 ảnh test (target ≥80%)
- **SUS score:** System Usability Scale (target ≥70)
- **Task completion rate:** % user hoàn thành 3 task chính (target ≥80%)

#### Channels (Kênh tiếp cận)
- **Primary:** Arena Peer Review (đã dùng để khảo sát n=27)
- **Secondary:** Group chat lớp, MXH nội bộ trường (BK Messenger, BK Connect)
- **Tertiary:** Sideload APK + GitHub release
- **Future:** Google Play Store (sau khi MVP validate)

#### Costs (Chi phí)
- **Nhân lực:** 5 thành viên × 1 học kỳ (~15 tuần) — chi phí cơ hội
- **Hosting:** Express.js + MongoDB Atlas Free-tier (0 VND/tháng)
- **Domain + deploy:** Vercel/Netlify Free-tier (0 VND/tháng)
- **Tools:** Figma Free plan, GitHub Free plan (0 VND)
- **Tổng ước tính MVP:** ~0 VND tiền mặt (chỉ chi phí cơ hội)

#### Revenue (Doanh thu)
- **MVP:** **Miễn phí hoàn toàn** — đây là dự án học thuật
- **Giai đoạn sau (post-MVP):** Mô hình **Freemium**
  - **Free:** Lưu local, OCR cơ bản, search unlimited
  - **Premium (potential):** Cloud sync đa thiết bị, OCR nâng cao (handwriting), export Notion/Docs
- **Status:** Revenue là **hướng đi tương lai**, không phải mục tiêu MVP

---

### Lưu ý quan trọng

- **Value (50–70%)** và **Advantage (<1s)** là các **claim chưa được validate** — cần test trong GĐ2 + GĐ3
- Nếu validation fail → phải điều chỉnh Value claim và có thể phải revise Advantage
- **Costs** hiện tại chỉ tính cho MVP, chưa bao gồm chi phí vận hành nếu scale lên 10.000+ user
