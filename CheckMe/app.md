'''
saas-chatbot/
├─ .env.example
├─ .gitignore
├─ README.md
├─ LICENSE
├─ next.config.mjs
├─ package.json
├─ tsconfig.json
├─ .eslintrc.cjs
├─ .prettierrc
├─ postcss.config.js
├─ tailwind.config.ts
├─ Dockerfile
├─ docker-compose.yml
├─ .husky/
│  └─ pre-commit
├─ .github/
│  └─ workflows/
│     └─ ci.yml
├─ prisma/
│  ├─ schema.prisma
│  ├─ seed.ts
│  └─ migrations/
├─ public/
│  ├─ favicon.ico
│  ├─ logo.svg
│  └─ robots.txt
├─ scripts/
│  ├─ migrate-and-seed.ts
│  └─ verify-env.ts
└─ src/
   ├─ app/
   │  ├─ layout.tsx
   │  ├─ globals.css
   │  ├─ middleware.ts
   │  ├─ (marketing)/
   │  │  ├─ page.tsx
   │  │  ├─ pricing/page.tsx
   │  │  └─ terms/page.tsx
   │  ├─ (auth)/
   │  │  ├─ sign-in/page.tsx
   │  │  └─ sign-up/page.tsx
   │  ├─ dashboard/
   │  │  ├─ layout.tsx
   │  │  ├─ page.tsx
   │  │  ├─ usage/page.tsx
   │  │  ├─ conversations/page.tsx
   │  │  ├─ analytics/page.tsx
   │  │  └─ billing/page.tsx
   │  └─ api/
   │     ├─ auth/[...nextauth]/route.ts
   │     ├─ chatbot/proxy/route.ts
   │     ├─ usage/increment/route.ts
   │     ├─ usage/reset/route.ts
   │     └─ webhooks/razorpay/route.ts
   ├─ components/
   │  ├─ layout/Sidebar.tsx
   │  ├─ layout/TopNav.tsx
   │  ├─ dashboard/UsageBar.tsx
   │  ├─ dashboard/ConversationTable.tsx
   │  ├─ dashboard/Charts.tsx
   │  ├─ billing/PlanCard.tsx
   │  └─ ui/* (shadcn UI components)
   ├─ lib/
   │  ├─ env.ts
   │  ├─ prisma.ts
   │  ├─ auth.ts
   │  ├─ razorpay.ts
   │  ├─ webhook.ts
   │  ├─ plans.ts
   │  ├─ usage.ts
   │  ├─ logger.ts
   │  ├─ rbac.ts
   │  ├─ api-ratelimit.ts
   │  ├─ errors.ts
   │  └─ security.ts
   ├─ server/
   │  ├─ repositories/
   │  │  ├─ userRepo.ts
   │  │  ├─ orgRepo.ts
   │  │  ├─ subscriptionRepo.ts
   │  │  ├─ conversationRepo.ts
   │  │  ├─ usageRepo.ts
   │  │  └─ invoiceRepo.ts
   │  └─ services/
   │     ├─ authService.ts
   │     ├─ subscriptionService.ts
   │     ├─ webhookService.ts
   │     ├─ usageService.ts
   │     ├─ invoiceService.ts
   │     ├─ conversationService.ts
   │     └─ chatbotService.ts
   ├─ hooks/
   │  ├─ useUsage.ts
   │  └─ useAuthGuard.ts
   ├─ styles/
   │  └─ shadcn.css
   └─ types/
      ├─ next-auth.d.ts
      └─ index.ts

'''