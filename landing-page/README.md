# landing-page/ — Marketing Website

Thư mục chứa source code cho **landing page** (sẽ phát triển ở Assignment 2).

## Tech Stack (planned)

| Layer | Tech |
| ----- | ---- |
| Framework | Vite + React 18 |
| Language | TypeScript |
| Styling | TailwindCSS 3 |
| Animations | Framer Motion |
| Icons | Phosphor React |
| Fonts | Inter (Google Fonts) |
| Analytics | Vercel Analytics hoặc Plausible |
| Deploy | Vercel (free tier, 1-click deploy) |

## Cấu trúc dự kiến

```
landing-page/
├── public/                   ← Static assets
│   ├── favicon.ico
│   ├── og-image.png
│   └── screenshots/
│
├── src/
│   ├── main.tsx
│   ├── App.tsx
│   ├── index.css             ← Tailwind imports
│   │
│   ├── components/           ← React components
│   │   ├── Hero/
│   │   ├── Problem/
│   │   ├── Solution/
│   │   ├── HowItWorks/
│   │   ├── Features/
│   │   ├── Screens/
│   │   ├── DesignSystem/
│   │   ├── Testimonials/
│   │   ├── CTA/
│   │   └── Footer/
│   │
│   ├── sections/             ← Section compositions
│   ├── hooks/                ← Custom hooks
│   ├── lib/                  ← Helpers
│   ├── constants.ts          ← Site config
│   └── types.ts
│
├── index.html
├── vite.config.ts
├── tailwind.config.js
├── postcss.config.js
├── tsconfig.json
└── package.json
```

## Sections (theo Wiki Mục GĐ2)

1. **Hero** — Logo + tagline + CTA
2. **Problem** — Pain point visualization
3. **Solution** — Elevator pitch
4. **How it works** — 3-step visual
5. **Features grid** — 4-6 feature cards
6. **Screens showcase** — 4-6 screen mockups
7. **Design System preview** — Color/type/components
8. **Testimonials** — 2-3 quotes từ user test
9. **CTA** — "View on Behance" + "Open Figma"
10. **Footer** — Team credits

## Status

🟡 **Planned** — Sẽ bắt đầu code ở Giai đoạn 2 (sau khi design system hoàn thành).

## Quick Start (placeholder)

```bash
# Khi bắt đầu code (GĐ2):
cd landing-page
npm create vite@latest . -- --template react-ts
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
npm run dev
```

## Deployment (Vercel)

1. Push code lên GitHub
2. Import repo vào Vercel
3. Auto-detect Vite + React
4. Deploy → nhận URL `https://smart-study-scanner.vercel.app`
5. Custom domain (optional): mua tại Namecheap, config DNS

## Tài liệu tham khảo

- [Vite Docs](https://vitejs.dev/)
- [TailwindCSS Docs](https://tailwindcss.com/docs)
- [Vercel Docs](https://vercel.com/docs)
- [Phosphor Icons](https://phosphoricons.com/)
