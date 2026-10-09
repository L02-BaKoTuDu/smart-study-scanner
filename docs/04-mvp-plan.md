# 04 — MVP Scope and Implementation Plan

> *Trang này chứa Mục 9, 10, 11, 12, 13 trong khung 13 mục bắt buộc.*

---

## Mục 9: Impact–Effort Matrix (Ma trận Tác động - Công sức)

### Ma trận phân loại tính năng

```
                  Effort (Công sức)
                  Low                High
              ┌─────────────────┬─────────────────┐
   Impact     │  [GREEN] QUICK   │  [YELLOW] MAJOR │
   High       │  WINS            │  PROJECTS       │
              │  (Ưu tiên MVP)   │  (Triển khai    │
              │                  │   tiếp theo)    │
              ├─────────────────┼─────────────────┤
   Impact     │  [BLUE] FILL-INS │  [RED] THANKLESS│
   Low        │  (Nếu dư time)   │  (Loại bỏ)      │
              │                  │                 │
              └─────────────────┴─────────────────┘
```

### Quick Wins (High Impact, Low Effort) — Ưu tiên làm ngay

| # | Feature | Impact | Effort | Lý do ưu tiên |
| - | ------- | ------ | ------ | -------------- |
| 1 | **Camera Scan & Auto-crop** | High | Low | CameraX API có sẵn; auto-crop bằng OpenCV đơn giản |
| 2 | **OCR On-device bằng Google ML Kit** | High | Low | ML Kit SDK miễn phí, integrate trong 1–2 ngày |
| 3 | **Full-text Keyword Search trên SQLite/Room** | High | Low | Room có FTS4/FullTextSearch built-in |

→ 3 tính năng này tạo nên **core value path** của MVP (xem Mục 10).

### Major Projects (High Impact, High Effort) — Phát triển tiếp theo

| # | Feature | Impact | Effort | Ghi chú |
| - | ------- | ------ | ------ | ------- |
| 4 | **Side-Drawer Document Preview** | High | High | Component custom, animation phức tạp, cần polish UX |
| 5 | **Sync Backend (Express.js + MongoDB)** và xuất Google Docs/Notion | High | High | OAuth flow, REST API, tốn 2–3 tuần |

→ Hai tính năng này **nên có** nhưng có thể **defer** sang Vòng 3 nếu timeline chậm.

### Fill-ins (Low Impact, Low Effort) — Làm nếu dư thời gian

- Đánh dấu tài liệu yêu thích (favorite/star)
- Chọn nhiều file nén thành ZIP
- Theme toggle (light/dark mode)
- Sort theo ngày chụp / theo môn học

### Thankless Tasks (Low Impact, High Effort) — Chủ động loại bỏ

- Nhận diện công thức toán LaTeX phức tạp
- Dịch thuật đa ngôn ngữ thời gian thực
- Scan hóa đơn, CCCD, ký tên điện tử
- Nhận diện chữ viết tay siêu ẩu
- Backup/restore toàn bộ data

### Tại sao phân loại như vậy?

- **Quick Wins (1, 2, 3):** Trực tiếp giải quyết A1 (OCR accuracy) + A2 (search speed) — 2 assumption rủi ro nhất. Làm sớm để test ASAP.
- **Major Projects (4, 5):** Cải thiện UX đáng kể nhưng tốn thời gian. Có thể MVP vẫn chạy được nếu thiếu.
- **Fill-ins:** Đẹp nhưng không tăng core value. Có thì tốt, không có vẫn OK.
- **Thankless:** Tốn effort nhưng user không cần → dành time cho thứ khác.

---

## Mục 10: MVP Scope (Phạm vi MVP)

### Mục tiêu người dùng chính

> **Sinh viên chụp lại bài giảng trên lớp và tìm lại chính xác nội dung đó trong vòng 1 giây khi cần ôn thi.**

### Core Value Path (Luồng giá trị cốt lõi)

```
Chụp ảnh → Tự động chạy OCR ngầm → Lưu trữ có nhãn môn học
→ Gõ từ khóa tìm kiếm → Xem kết quả qua Side-Drawer
```

→ 5 bước này phải hoạt động **end-to-end** trong MVP.

### Danh sách tính năng tối thiểu BẮT BUỘC

| # | Tính năng | Mô tả | User Story liên quan |
| - | --------- | ------ | -------------------- |
| **F1** | Chụp ảnh bài giảng với auto-crop | Camera UI + ML Kit auto-detect edges | US-01 |
| **F2** | OCR On-device bằng Google ML Kit | Trích xuất text không cần internet | US-02 |
| **F3** | Thanh tìm kiếm từ khóa tra cứu tức thì | Full-text search <1s trên local DB | US-03 |
| **F4** | Quản lý thư mục theo môn học | Tạo/sửa/xóa môn, gán note vào môn | US-03 (hỗ trợ) |
| **F5** | Xem nhanh tài liệu qua Side-Drawer | Vuốt từ cạnh phải để preview OCR + ảnh | US-04 |

### Tính năng CHỦ ĐỘNG LOẠI BỎ khỏi MVP

| # | Tính năng | Lý do loại bỏ |
| - | --------- | -------------- |
| X1 | Scan hóa đơn/CCCD | Không phù hợp target user (sinh viên) |
| X2 | Ký tên điện tử | Là tính năng văn phòng, không phải học tập |
| X3 | Dịch thuật trực tiếp trên ảnh | Tốn effort, không tăng core value |
| X4 | Nhận diện chữ viết tay siêu ẩu | ML Kit chưa hỗ trợ tốt, scope quá lớn |
| X5 | Nhận diện công thức LaTeX | Quá phức tạp cho MVP |
| X6 | Sync Google Docs/Notion | Defer sang Vòng 3 (cần OAuth + backend) |
| X7 | Backup/restore cloud | Không cần cho MVP local-first |
| X8 | Multi-user / collaboration | Không phù hợp MVP, làm sau |

### Rủi ro chính & Assumption chưa resolve

| # | Risk / Assumption | Mitigation |
| - | ----------------- | ---------- |
| **R1** | OCR accuracy có thể < 80% trong điều kiện thực tế | Test sớm với 30 ảnh thật; có fallback "save as image" nếu OCR fail |
| **R2** | User có thể không thấy search nhanh hơn lướt tay | Thêm auto-classify theo môn; thử nghiệm với 5–10 user trong GĐ2 |
| **R3** | Switching cost từ app note hiện tại (Apple Notes, Keep) | Cho phép import ảnh từ Camera Roll, không bắt buộc chụp trong app |
| **R4** | Timeline 8 tuần cho GĐ2 + GĐ3 có thể không đủ | Có buffer 1 tuần + cắt Major Project #4 (Side-Drawer) nếu cần |

### Định nghĩa "MVP thành công"

MVP thành công khi đạt **đồng thời** các tiêu chí:

- [ ] 5 user test có thể hoàn thành 3 task chính (chụp, save, search) với tỷ lệ ≥ 80%
- [ ] Time-on-task trung bình cho search < 15 giây (so với 5–15 phút lướt tay)
- [ ] OCR accuracy ≥ 80% trên 30 ảnh slide thật
- [ ] SUS score ≥ 70
- [ ] App không crash trong 30 phút test liên tục

---

## Mục 11: User Stories (Câu chuyện người dùng)

> *Format: `As a [user], I want to [goal], so that [value]`*

### US-01: Chụp nhanh bài giảng với auto-crop

> **As a** sinh viên đang ngồi trên lớp,
> **I want to** mở camera chụp nhanh bảng trắng và được tự động căn biên,
> **so that** tôi có được bức ảnh rõ ràng trước khi giảng viên bôi bảng.

- **Traceability:** Evidence A1 (OCR accuracy) → Need: chụp nhanh → Requirement: auto-crop → Feature: F1
- **Acceptance:** Auto-crop trong < 2s, accuracy ≥ 90% trên slide thẳng

### US-02: OCR offline tự động

> **As a** sinh viên,
> **I want to** ứng dụng tự động bóc tách chữ từ ảnh bài giảng mà không cần kết nối Internet,
> **so that** tôi không bị tốn dung lượng 4G và có thể tìm kiếm lại sau này.

- **Traceability:** Assumption A1 (OCR ≥ 80%) + Need: offline → Requirement: on-device OCR → Feature: F2
- **Acceptance:** OCR chạy được khi tắt WiFi + 4G; kết quả lưu local DB

### US-03: Tìm kiếm từ khóa nhanh

> **As a** sinh viên đang ôn thi,
> **I want to** gõ từ khóa khái niệm (ví dụ: "Semaphore") vào thanh tìm kiếm,
> **so that** ứng dụng trả về chính xác bức ảnh chứa kiến thức đó trong vài giây thay vì phải lướt cả nghìn ảnh.

- **Traceability:** Assumption A2 (giảm 50% thời gian) → Need: search nhanh → Requirement: full-text search → Feature: F3
- **Acceptance:** Search results trả về trong <1s, highlight từ khóa

### US-04: Xem nhanh qua Side-Drawer

> **As a** sinh viên,
> **I want to** xem nhanh nội dung văn bản bóc tách và ảnh phóng to qua ngăn kéo trượt,
> **so that** tôi kiểm tra được kiến thức ngay mà không cần mở nhiều màn hình phức tạp.

- **Traceability:** Decision D2 (Side-Drawer từ DMS) → Need: preview nhanh → Requirement: drawer component → Feature: F5
- **Acceptance:** Swipe từ cạnh phải mở drawer trong <300ms, hiển thị OCR text + ảnh

### US-05: Tổ chức theo môn học

> **As a** sinh viên,
> **I want to** phân loại ảnh bài giảng theo môn học khi lưu,
> **so that** tôi dễ dàng tìm lại và không phải lướt giữa hàng trăm ảnh hỗn độn.

- **Traceability:** Decision D5 (auto-classify) → Need: tổ chức → Requirement: tag môn học → Feature: F4
- **Acceptance:** Tạo môn mới trong 2 tap, filter theo môn trong 1 tap

### US-06 (Optional, Vòng 3): Đồng bộ sang Google Docs/Notion

> **As a** sinh viên,
> **I want to** xuất nội dung ghi chú đã OCR sang Google Docs/Notion,
> **so that** tôi có thể tổng hợp đề cương ôn thi trên laptop một cách dễ dàng.

- **Traceability:** Assumption A3 (sync need) — cần test thêm
- **Status:** Defer sang Vòng 3+, chỉ làm nếu A3 được ủng hộ

### Mapping tổng hợp: Story → Feature → Assumption

| User Story | MVP Feature | Assumption Tested |
| ---------- | ----------- | ----------------- |
| US-01 | F1 (Camera + Auto-crop) | — |
| US-02 | F2 (ML Kit OCR) | A1 (≥80% accuracy) |
| US-03 | F3 (Full-text search) | A2 (giảm 50% thời gian) |
| US-04 | F5 (Side-Drawer) | D2 (preview UX) |
| US-05 | F4 (Subject management) | D5 (auto-classify) |
| US-06 | (Defer) Sync | A3 (sync need) |

---

## Mục 12: Critical User Flows (Luồng người dùng cốt lõi)

> *Mô tả 2 luồng quan trọng nhất, có start + steps + decision + outcome + failure path.*

### Luồng 1: Scan & OCR Flow (Quét & bóc tách chữ)

#### Happy Path
| Bước | Hành động | Kết quả mong đợi |
| ---- | --------- | ----------------- |
| 1 | User mở app, nhấn tab "Capture" | Camera UI mở |
| 2 | User hướng camera vào slide/bảng, bấm nút Chụp | Ảnh được chụp |
| 3 | Auto-crop tự động phát hiện biên tài liệu | Ảnh được căn chỉnh, preview hiển thị |
| 4 | User bấm "Dùng ảnh này" | App chạy ML Kit OCR |
| 5 | OCR hoàn tất, hiển thị text preview | User kiểm tra nhanh text |
| 6 | User chọn môn học từ dropdown (hoặc tạo mới) | Môn học được gán |
| 7 | User bấm "Lưu" | Note được lưu vào Room DB local |
| 8 | Quay về Home, thấy note mới ở đầu danh sách | Done |

#### Decision Point
- **Bước 5:** Nếu OCR text quá ngắn (< 30 chars) → cảnh báo "Chất lượng ảnh thấp"
- **Bước 6:** Nếu chưa có môn học nào → hiển thị empty state "Tạo môn học đầu tiên"

#### Failure Path
- **Ảnh quá mờ/tối** (bước 3) → App hiển thị: "Không nhận diện được biên. Vui lòng chụp lại với ánh sáng tốt hơn" → Quay lại bước 1
- **OCR fail** (bước 4) → Toast "OCR thất bại, đã lưu ảnh gốc" → Lưu ảnh không có text → User có thể retry OCR sau
- **Permission camera bị từ chối** (bước 1) → Hiển thị màn hình "Cần quyền Camera" với nút "Mở Settings"

#### Outcome
- Note được lưu với OCR text trong DB local
- Note hiển thị trong Home theo môn học
- Note có thể search được ngay lập tức

---

### Luồng 2: Search & Preview Flow (Tìm kiếm & xem nhanh)

#### Happy Path
| Bước | Hành động | Kết quả mong đợi |
| ---- | --------- | ----------------- |
| 1 | User mở app → Home | Thấy thanh Search bar ở top |
| 2 | User nhấn vào Search bar | Bàn phím hiện ra, focus vào input |
| 3 | User gõ "Semaphore" | Real-time search update |
| 4 | Sau khi gõ xong, danh sách results hiện ra | NoteCard hiển thị thumbnail + title + highlight từ khóa |
| 5 | User nhấn vào 1 kết quả | Side-Drawer trượt ra từ cạnh phải |
| 6 | Side-Drawer hiển thị ảnh lớn + OCR text | Text highlight từ khóa "Semaphore" |
| 7 | User có thể: pinch-to-zoom ảnh, copy text, đóng drawer | Tương tác mượt mà |
| 8 | User đóng drawer bằng nút X hoặc swipe down | Quay về Search results |

#### Decision Point
- **Bước 4:** Nếu có > 20 kết quả → phân trang (load more ở scroll cuối)
- **Bước 4:** Nếu 0 kết quả → empty state "Không tìm thấy tài liệu"
- **Bước 6:** Nếu OCR text rỗng → hiển thị "Chưa có text OCR cho ảnh này"

#### Alternative Path (Empty Result)
- User gõ từ khóa không tồn tại
- Empty state hiển thị:
  - Icon: kính lúp
  - Text: "Không tìm thấy tài liệu chứa từ khóa này"
  - Gợi ý 1: "Kiểm tra lại chính tả"
  - Gợi ý 2: "Duyệt theo danh sách Thư mục môn học"
  - Nút CTA: "Mở thư viện môn học"

#### Failure Path
- **DB chưa có data** → Empty state khác: "Bạn chưa có ảnh bài giảng nào. Hãy chụp ảnh đầu tiên!"
- **Search query rỗng** → Hiển thị recent searches + gợi ý môn học
- **App crash** → Toast "Có lỗi xảy ra, vui lòng thử lại" + log to Sentry

#### Outcome
- User tìm được ảnh bài giảng trong < 15 giây (vs 5–15 phút lướt tay)
- User có thể xem preview mà không cần mở nhiều màn hình
- User copy được text để dán vào note tổng hợp

---

### Sơ đồ tổng quát (text-based)

```
LUỒNG 1: SCAN & OCR
[Home] → [Tab Capture] → [Camera] → [Chụp] → [Auto-crop] → [OCR] → [Side-Drawer Preview] → [Chọn môn] → [Lưu] → [Home]

LUỒNG 2: SEARCH & PREVIEW
[Home] → [Search bar] → [Gõ từ khóa] → [Results] → [Tap result] → [Side-Drawer] → [View ảnh + text] → [Close] → [Results]
```

---

## Mục 13: Project Plan & Traceability (Kế hoạch dự án & Tính truy xuất)

### Traceability Chain (Chuỗi liên kết logic)

> *Mỗi assumption được test qua bằng chứng → sinh ra user need → requirement → user story → MVP feature → user flow → dev task*

```
Evidence A1 (OCR accuracy ≥ 80% test trên 30 ảnh)
   ↓
User Need (tin tưởng OCR chạy đúng trên ảnh thật)
   ↓
Requirement (On-device OCR với Google ML Kit)
   ↓
User Story US-02 (OCR offline tự động)
   ↓
MVP Feature F2 (ML Kit Text Recognition)
   ↓
User Flow 1 (Scan & OCR Flow)
   ↓
Dev Task #T26 [FE-04] (Integrate ML Kit Text Recognition on-device)
```

```
Evidence A2 (search giảm 50% thời gian)
   ↓
User Need (tìm ảnh nhanh hơn lướt tay)
   ↓
Requirement (Full-text search <1s trên local DB)
   ↓
User Story US-03 (Tìm kiếm từ khóa nhanh)
   ↓
MVP Feature F3 (Full-text keyword search)
   ↓
User Flow 2 (Search & Preview Flow)
   ↓
Dev Task #T28 [FE-06] (Implement full-text keyword search engine)
```

### Kế hoạch triển khai theo Milestones

| Milestone | Thời gian | Tasks chính | Output |
| --------- | --------- | ----------- | ------ |
| **M1: Assignment 1** — Product Discovery & Foundation | 09–15/10/2026 | Wiki 13 mục, Project Board, Research, User Survey | Wiki + Board + Evidence |
| **M2: Assignment 2** — UI/UX Design & Prototype | 16/10–05/12/2025 | Figma Design System, Wireframe, Hi-fi screens, Interactive Prototype, Behance, Landing Page | Figma + Behance + Landing |
| **M3: Assignment 3** — Runnable Product & Analytics | 06/12/2025–15/01/2026 | Expo + Camera + ML Kit, Room DB, Search engine, Express.js backend, Sentry, Firebase, Unit Test ≥70%, APK release | APK + Analytics + Tests |

### Bảng Milestone ↔ Task (chi tiết)

#### M1: Assignment 1 (10 tasks)
- T01–T04: Viết 4 trang Wiki
- T05–T06: Setup Org + Board (đã done)
- T07: Khảo sát Google Forms
- T08: Phân tích 5+ existing solutions
- T09: User test mini
- T10: Final QA Wiki

#### M2: Assignment 2 (12 tasks)
- T11: Design System foundations
- T12: Component library
- T13–T16: 24 screens (Onboarding, Capture, Search, Settings)
- T17–T18: Interactive prototype (2 flows)
- T19: Behance case study
- T20: Landing Page build + deploy
- T21: Usability test 5–10 users
- T22: Final QA 3 deliverables

#### M3: Assignment 3 (16 tasks)
- T23–T30: Frontend (Expo + Camera + ML Kit + Room + Search + Side-Drawer + Subject)
- T31–T33: Backend (Express + MongoDB + OAuth + Sync)
- T34: Sentry + Firebase Analytics
- T35–T36: Tests (Jest ≥70% + Detox E2E)
- T37: Build APK
- T38: Update Wiki với demo

### Phân công 5 thành viên

| Thành viên | Track chính |
| ---------- | ----------- |
| **Nguyễn Thành Công** (Bắn) | Project lead, Wiki, QA, Submit |
| **Lữ Quốc Pháp** | Capture flow, Frontend |
| **Nguyễn Lê Nguyên** | Design System, Data layer, Tests |
| **Đặng Thành Duy Đan** | Search UX, Landing Page |
| **Trần Trọng Nghĩa** | Backend, Analytics, Docs |

### Tiêu chí thành công cuối kỳ

| Tiêu chí | Target |
| -------- | ------ |
| **M1** — Wiki đầy đủ 13 mục, Board có tasks | Pass 100% |
| **M2** — 3 deliverables public, SUS ≥ 70 | Pass |
| **M3** — APK cài được, search < 1s, OCR ≥ 80%, test coverage ≥ 70% | Pass |
| **Final** — App giảm ≥ 50% thời gian tìm ảnh so với lướt tay (A2 validated) | Pass |

### Thay đổi có thể xảy ra sau Assignment 1

Theo rubric: *"Your project direction is not frozen after Assignment 1."* — có thể revise nếu evidence mới cho thấy cần:

- **Problem:** Có thể thu hẹp thành "sinh viên Bách Khoa năm 2–4" nếu evidence cho thấy khối khác không gặp vấn đề tương tự
- **Target users:** Có thể thêm user phụ (sinh viên năm 1) nếu survey mở rộng cho kết quả tốt
- **MVP scope:** Có thể cắt F5 (Side-Drawer) nếu timeline M3 quá chật
- **Value claim:** Nếu A2 fail, có thể điều chỉnh "tiết kiệm 30% thời gian" thay vì 50–70%

Tất cả thay đổi phải **document lại lý do** trong Wiki.
