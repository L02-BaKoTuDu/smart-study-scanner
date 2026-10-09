# mobile/ — React Native App (Expo)

Thư mục chứa source code cho **mobile app** Smart Study Scanner (sẽ phát triển ở Assignment 3).

## Tech Stack (planned)

| Layer | Tech |
| ----- | ---- |
| Framework | React Native + Expo SDK 50+ |
| Language | TypeScript |
| Navigation | React Navigation 6 |
| State | Zustand |
| Local DB | Expo SQLite (với FTS4) hoặc WatermelonDB |
| OCR | `expo-ml-kit-text-recognition` hoặc `react-native-mlkit-ocr` |
| Camera | `expo-camera` |
| Image manipulation | `expo-image-manipulator` |
| File storage | `expo-file-system` |
| Animations | `react-native-reanimated` 3 |
| Testing | Jest + React Native Testing Library + Detox (E2E) |

## Cấu trúc dự kiến

```
mobile/
├── src/
│   ├── app/                  ← Navigation + screens
│   │   ├── App.tsx
│   │   ├── navigation/
│   │   └── screens/
│   │       ├── Home/
│   │       ├── Capture/
│   │       ├── Search/
│   │       ├── NoteDetail/
│   │       └── Settings/
│   │
│   ├── features/             ← Feature modules
│   │   ├── camera/
│   │   ├── ocr/
│   │   ├── search/
│   │   └── storage/
│   │
│   ├── components/           ← Shared UI components
│   │   ├── Button/
│   │   ├── SearchBar/
│   │   ├── NoteCard/
│   │   └── SideDrawer/
│   │
│   ├── db/                   ← Database layer
│   │   ├── schema.ts         ← Room/SQLite schema
│   │   ├── migrations/
│   │   └── repositories/
│   │
│   ├── hooks/                ← Custom React hooks
│   ├── services/             ← Business logic services
│   ├── utils/                ← Helpers
│   ├── constants/            ← Design tokens, app config
│   └── types/                ← TypeScript types
│
├── assets/                   ← Images, fonts, icons
│   ├── icon.png
│   ├── splash.png
│   └── fonts/
│
├── __tests__/                ← Unit tests
├── e2e/                      ← E2E tests (Detox)
│
├── app.json                  ← Expo config
├── eas.json                  ← EAS Build config
├── tsconfig.json
├── babel.config.js
├── metro.config.js
├── jest.config.js
└── package.json
```

## Status

🟡 **Planned** — Sẽ bắt đầu code ở Giai đoạn 3 (sau khi Design ở GĐ2 hoàn thành).

## Quick Start (placeholder)

```bash
# Khi bắt đầu code (GĐ3):
cd mobile
npx create-expo-app@latest . --template blank-typescript
npm install
npm start
```

## Tài liệu tham khảo

- [Expo Documentation](https://docs.expo.dev/)
- [React Native Docs](https://reactnative.dev/docs/getting-started)
- [ML Kit Text Recognition](https://developers.google.com/ml-kit/vision/text-recognition)
- [Expo Camera](https://docs.expo.dev/versions/latest/sdk/camera/)
