# 📚 Smart Study Scanner

> **Slogan:** *"Chụp một lần, tìm lại ngay lập tức"*

Mobile app giúp sinh viên chuyển ảnh chụp slide/bảng trên lớp thành **Searchable Notes** nhờ OCR On-device (Google ML Kit), tổ chức theo môn học, và tìm kiếm bằng từ khóa trong <1 giây.

---

## 👥 Nhóm phát triển

| Vai trò | Thành viên | Track |
| ------- | ---------- | ----- |
| Nhóm trưởng | **Nguyễn Thành Công** | Project lead, QA, Wiki |
| Thành viên | **Lữ Quốc Pháp** | Capture flow, Frontend |
| Thành viên | **Nguyễn Lê Nguyên** | Design System, Data layer |
| Thành viên | **Đặng Thành Duy Đan** | Search UX, Landing Page |
| Thành viên | **Trần Trọng Nghĩa** | Backend, Analytics, Docs |

**Môn học:** CO3043 — Phát triển Ứng dụng Di động · HK1 2026–2027

---

## 📂 Cấu trúc Repository

```
smart-study-scanner/
├── README.md                          ← File này
├── LICENSE                            ← MIT License
├── .gitignore                         ← Ignore node_modules, build, .env
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── user-story.md              ← Template issue cho FE/BE task
│       └── research.md                ← Template issue cho research/test
│
├── docs/                              ← Tài liệu dự án (mirror Wiki)
│   ├── 01-project-direction.md
│   ├── 02-research-evidence.md
│   ├── 03-business-canvas.md
│   └── 04-mvp-plan.md
│
├── wiki/                              ← Markdown source cho GitHub Wiki
│   ├── Home.md                        ← Trang chủ Wiki
│   ├── 01-Project-Direction-and-Rationale.md
│   ├── 02-Research-Evidence-and-Decisions.md
│   ├── 03-Business-Model-Canvas.md
│   └── 04-MVP-Scope-and-Implementation-Plan.md
│
├── design/                            ← Design assets (GĐ2)
│   ├── design-system/
│   ├── wireframes/
│   └── hi-fi-mockups/
│
├── mobile/                            ← Source code app mobile (GĐ3)
│   ├── src/
│   ├── assets/
│   ├── App.tsx
│   ├── app.json
│   └── package.json
│
├── backend/                           ← Source code backend (GĐ3)
│   ├── src/
│   ├── tests/
│   ├── .env.example
│   └── package.json
│
└── landing-page/                      ← Source code landing page (GĐ2)
    ├── src/
    ├── public/
    └── package.json
```

---

## 🚀 Trạng thái dự án

| Milestone | Trạng thái | Deadline |
| --------- | ---------- | -------- |
| **M1: Assignment 1** — Product Discovery & Foundation | 🟡 In Progress | 15/10/2026 |
| **M2: Assignment 2** — UI/UX Design & Prototype | ⚪ Planned | ~05/12/2025 |
| **M3: Assignment 3** — Runnable Product & Analytics | ⚪ Planned | ~15/01/2026 |

---

## 🔗 Liên kết quan trọng

- 📖 [GitHub Wiki](https://github.com/L02-BaKoTuDu/smart-study-scanner/wiki) — Tài liệu 13 mục
- 📋 [GitHub Project Board](https://github.com/orgs/L02-BaKoTuDu/projects/1) — Scrum board
- 🎨 [Figma Project](#) — Sẽ có ở M2
- 📸 [Behance Case Study](#) — Sẽ có ở M2
- 🌐 [Landing Page](#) — Sẽ deploy ở M2
- 📦 [APK Download](#) — Sẽ có ở M3

---

## 🛠️ Tech Stack (planned)

| Layer | Tech |
| ----- | ---- |
| **Mobile** | React Native (Expo), TypeScript, React Navigation, Reanimated |
| **State** | Zustand hoặc Redux Toolkit |
| **Local DB** | Room (SQLite) với FTS4 |
| **OCR** | Google ML Kit Text Recognition v2 (on-device) |
| **Camera** | Expo Camera + expo-image-manipulator |
| **Backend** | Node.js + Express.js, TypeScript |
| **Database** | MongoDB Atlas (Free tier) |
| **Auth** | Google OAuth 2.0 |
| **Analytics** | Firebase Analytics + Sentry |
| **Testing** | Jest (unit) + Detox (E2E) |
| **Landing Page** | Vite + React + TailwindCSS, deploy Vercel |
| **CI/CD** | GitHub Actions |

---

## 📜 License

MIT License — Xem file [LICENSE](LICENSE)

---

## 📞 Liên hệ

- **Email nhóm:** [l02.bakotudu@gmail.com](mailto:l02.bakotudu@gmail.com) *(cần tạo)*
- **GitHub Organization:** [L02-BaKoTuDu](https://github.com/L02-BaKoTuDu)
