# Edu-Platform
project-root/
├─ docker-compose.yml
├─ README.md
├─ server/
│ ├─ package.json
│ ├─ prisma/schema.prisma
│ ├─ .env.example
│ └─ src/
│ ├─ index.js
│ ├─ app.js
│ ├─ routes/
│ │ ├─ auth.js
│ │ ├─ admin.js
│ │ └─ courses.js
│ ├─ middleware/auth.js
│ ├─ services/storage.js # يمكنك تركه فارغ أو إضافة خدمات التخزين
│ ├─ services/notifications.js # يمكنك تركه فارغ أو إضافة وظائف الإشعارات
│ └─ seed/adminSeed.js
└─ client/
├─ package.json
├─ vite.config.ts
├─ tsconfig.json
├─ index.html
└─ src/
├─ index.tsx
├─ main.tsx
├─ App.tsx
├─ components/Hello.tsx
├─ styles.css
└─ __tests__/
├─ App.test.tsx
└─ Hello.test.tsx
