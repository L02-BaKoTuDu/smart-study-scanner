# backend/ — Express.js + MongoDB API

Thư mục chứa source code cho **backend API** (sẽ phát triển ở Assignment 3 — chỉ khi Assumption A3 được ủng hộ).

## Tech Stack (planned)

| Layer | Tech |
| ----- | ---- |
| Runtime | Node.js 20 LTS |
| Framework | Express.js 4 |
| Language | TypeScript |
| Database | MongoDB Atlas (Free tier) |
| ODM | Mongoose 8 |
| Auth | Google OAuth 2.0 (`passport-google-oauth20`) |
| Validation | Zod hoặc Joi |
| Logging | Winston + Morgan |
| Testing | Jest + Supertest |
| Deploy | Railway / Render (free tier) |

## Cấu trúc dự kiến

```
backend/
├── src/
│   ├── index.ts              ← Entry point
│   ├── app.ts                ← Express app setup
│   ├── config/
│   │   ├── env.ts            ← Environment variables
│   │   ├── db.ts             ← MongoDB connection
│   │   └── logger.ts
│   │
│   ├── routes/               ← Express routes
│   │   ├── notes.routes.ts
│   │   ├── subjects.routes.ts
│   │   ├── auth.routes.ts
│   │   └── sync.routes.ts
│   │
│   ├── controllers/          ← Route handlers
│   ├── services/             ← Business logic
│   ├── models/               ← Mongoose schemas
│   │   ├── Note.model.ts
│   │   ├── Subject.model.ts
│   │   └── User.model.ts
│   │
│   ├── middlewares/          ← Auth, error handler, etc.
│   ├── utils/                ← Helpers
│   └── types/                ← TypeScript types
│
├── tests/                    ← Unit + integration tests
│   ├── unit/
│   └── integration/
│
├── .env.example              ← Example env vars
├── tsconfig.json
├── jest.config.js
└── package.json
```

## API Endpoints (planned)

### Notes
- `GET    /api/notes` — List user's notes
- `POST   /api/notes` — Create new note
- `GET    /api/notes/:id` — Get note by ID
- `PUT    /api/notes/:id` — Update note
- `DELETE /api/notes/:id` — Delete note
- `GET    /api/notes/search?q=keyword` — Full-text search

### Subjects
- `GET    /api/subjects` — List subjects
- `POST   /api/subjects` — Create subject
- `PUT    /api/subjects/:id` — Update subject
- `DELETE /api/subjects/:id` — Delete subject

### Auth
- `GET    /auth/google` — Google OAuth start
- `GET    /auth/google/callback` — OAuth callback
- `POST   /auth/logout`
- `GET    /auth/me` — Current user info

### Sync (optional, Major Project)
- `POST   /api/sync/notes` — Bulk sync notes from device
- `POST   /api/export/notion` — Export to Notion
- `POST   /api/export/gdocs` — Export to Google Docs

## Status

🟡 **Planned** — Sẽ bắt đầu code ở Giai đoạn 3 (nếu Assumption A3 — sync need — được ủng hộ qua user test).

## Environment Variables (placeholder)

Tạo file `.env` (KHÔNG commit) với các biến:

```env
NODE_ENV=development
PORT=3000
MONGODB_URI=mongodb+srv://user:pass@cluster.mongodb.net/smart-study-scanner
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret
JWT_SECRET=your-jwt-secret
SENTRY_DSN=your-sentry-dsn
```

## Tài liệu tham khảo

- [Express.js Docs](https://expressjs.com/)
- [Mongoose Docs](https://mongoosejs.com/docs/)
- [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
- [Passport.js Google OAuth](http://www.passportjs.org/packages/passport-google-oauth20/)
