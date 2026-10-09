# Smart Study Scanner — Trang chủ Wiki

> **Slogan:** *"Chụp một lần, tìm lại ngay lập tức"* — *Scan. Search. Succeed.*

---

## Thông tin dự án

| Hạng mục | Chi tiết |
| -------- | -------- |
| **Tên dự án** | Smart Study Scanner |
| **Môn học** | CO3043 — Phát triển Ứng dụng trên thiết bị Di động |
| **Học kỳ** | HK1 — Năm học 2026–2027 |
| **Nhóm** | L02_BaKoTuDu |
| **GitHub Org** | [L02-BaKoTuDu](https://github.com/L02-BaKoTuDu) |
| **Repository** | [smart-study-scanner](https://github.com/L02-BaKoTuDu/smart-study-scanner) |
| **Project Board** | [Scrum Board](https://github.com/orgs/L02-BaKoTuDu/projects/1) |

---

## Thành viên nhóm

| Vai trò | Họ và tên | Track chính |
| ------- | --------- | ----------- |
| **Nhóm trưởng** | **Nguyễn Thành Công** | Project lead, Wiki, QA |
| Thành viên | **Lữ Quốc Pháp** | Capture flow, Frontend |
| Thành viên | **Nguyễn Lê Nguyên** | Design System, Data layer |
| Thành viên | **Đặng Thành Duy Đan** | Backend, Analytics, Docs |
| Thành viên | **Trần Trọng Nghĩa** | Search UX, Landing Page |

---

## Tóm tắt dự án

**Smart Study Scanner** là nền tảng di động số hóa ảnh chụp bài giảng (slide, bảng trắng) thành các **Searchable Notes** — ghi chú có thể tìm kiếm được bằng từ khóa — nhờ công nghệ **OCR On-device** (Google ML Kit).

### Vấn đề

Sinh viên đại học (đặc biệt khối kỹ thuật, IT) chụp rất nhiều ảnh slide/bảng trên lớp, nhưng ảnh biến thành **"text chết"** trong Camera Roll — không thể tìm kiếm lại khi ôn thi.

### Giải pháp

Một mobile app:

1. **Chụp** ảnh bài giảng với auto-crop
2. **OCR On-device** bóc tách chữ ngay trên máy (offline)
3. **Tổ chức** theo môn học
4. **Tìm kiếm** bằng từ khóa trong <1 giây
5. **Xem nhanh** qua Side-Drawer preview

### Giá trị cốt lõi

> Tiết kiệm **50–70% thời gian tìm kiếm** tài liệu ôn thi so với lướt Camera Roll thủ công.

---

## Mục lục tài liệu Wiki

| Trang | Nội dung | Mục |
| ----- | -------- | --- |
| [01 — Project Direction and Rationale](./01-Project-Direction-and-Rationale) | Định hướng dự án + Lập luận vì sao chọn Mobile | **1, 2** |
| [02 — Research Evidence and Decisions](./02-Research-Evidence-and-Decisions) | Giả định, kế hoạch thu thập bằng chứng, nghiên cứu người dùng, phân tích giải pháp hiện có, đánh giá và ra quyết định | **3, 4, 5, 6, 7** |
| [03 — Business Model Canvas](./03-Business-Model-Canvas) | Ma trận 3×3 — mối liên kết giữa Problem, Solution, Value, Customer, Advantage, Metrics, Channels, Costs, Revenue | **8** |
| [04 — MVP Scope and Implementation Plan](./04-MVP-Scope-and-Implementation-Plan) | Impact-Effort Matrix, MVP Scope, User Stories, Critical User Flows, Project Plan + Traceability | **9, 10, 11, 12, 13** |

---

## Liên kết nhanh

- **Design (sẽ có ở Assignment 2):** Figma Prototype
- **Behance Case Study (sẽ có ở Assignment 2):** Behance Project
- **Landing Page (sẽ có ở Assignment 2):** [smart-study-scanner.vercel.app](https://smart-study-scanner.vercel.app)
- **APK (sẽ có ở Assignment 3):** Download link

---

> **Mục tiêu cuối cùng:** Biến ảnh chụp bài giảng từ "text chết" thành một **kho tri thức cá nhân tra cứu nhanh** cho sinh viên.
