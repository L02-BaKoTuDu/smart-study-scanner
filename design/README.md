# design/ — Design Assets

Thư mục chứa toàn bộ design assets cho **Assignment 2 — UI/UX Design & Prototype**.

## Cấu trúc

```
design/
├── design-system/        ← Foundations (color, typography, spacing, components)
│   ├── foundations.fig
│   ├── components.fig
│   └── tokens.json       ← Design tokens (export sang code)
│
├── wireframes/           ← Lo-fi wireframes
│   ├── 01-onboarding.fig
│   ├── 02-capture.fig
│   └── ...
│
├── hi-fi-mockups/        ← Hi-fi screens
│   ├── 01-splash.png
│   ├── 02-onboarding-1.png
│   └── ...
│
├── prototype/            ← Figma prototype + exports
│   ├── prototype.fig
│   └── prototype-video.mp4
│
└── exports/              ← PNG/SVG exports để dùng trong docs
    ├── splash.png
    ├── icon.svg
    └── ...
```

## Workflow

1. **Mỗi sprint design** → tạo file `.fig` mới trong folder tương ứng
2. **Export PNG/SVG** → lưu vào `exports/` để dùng trong Wiki, README, Behance
3. **Update design tokens** → `tokens.json` để dev team sử dụng

## Tools

- **Figma** (free plan) — primary tool
- **Phosphor Icons** — open source icon set
- **Inter** + **JetBrains Mono** — Google Fonts
- **Coolors.co** — palette generator
- **Figma Tokens plugin** — sync design ↔ code

> 💡 **Tip:** Khi export design tokens sang code, dùng [Style Dictionary](https://amzn.github.io/style-dictionary/) để generate tự động cho React Native, Tailwind, v.v.
