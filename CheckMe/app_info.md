
---

📂 SaaS App Repo Map (Enterprise, PAYG, Secure)


---

🔹 Root Level (Project Setup)

.env.example → Example of all environment variables (API keys, DB URL, secrets).

.gitignore → Tells Git which files not to upload (e.g., .env, build files).

README.md → Documentation on how to run the project.

LICENSE → Open-source license file.

next.config.mjs → Next.js settings (image domains, headers, etc.).

package.json → Project dependencies and scripts (dev, build, lint).

tsconfig.json → TypeScript configuration.

.eslintrc.cjs → ESLint config for code quality.

.prettierrc → Prettier config for auto-formatting code.

postcss.config.js → Tailwind CSS + PostCSS setup.

tailwind.config.ts → Tailwind CSS configuration (colors, themes).

Dockerfile → Instructions to build Docker image for deployment.

docker-compose.yml → Local setup (Postgres + Redis + App).

.husky/pre-commit → Git hook to run lint/tests before commit.



---

🔹 .github/workflows/ (CI/CD)

ci.yml → GitHub Actions workflow for:

Run lint & typecheck.

Run tests.

Build app.




---

🔹 prisma/ (Database)

schema.prisma → Database tables (Users, Orgs, Subscriptions, Usage, Invoices).

seed.ts → Seeds DB with test users, plans, orgs.

migrations/ → Auto-generated DB migration history.



---

🔹 public/ (Static Files)

favicon.ico → App icon.

logo.svg → Company logo.

robots.txt → Tells search engines what to crawl.



---

🔹 scripts/ (Utilities)

migrate-and-seed.ts → Runs DB migrations + seeds test data.

verify-env.ts → Checks .env file for missing keys before starting app.



---

🔹 src/app/ (Next.js App Router)

layout.tsx → Root app layout (wraps pages with Nav, Providers).

globals.css → Global styles.

middleware.ts → Protects routes (/dashboard requires login).


🔹 Marketing Pages (/)

(marketing)/page.tsx → Landing page.

(marketing)/pricing/page.tsx → Pricing page.

(marketing)/terms/page.tsx → Terms & conditions.


🔹 Auth Pages

(auth)/sign-in/page.tsx → Sign-in form.

(auth)/sign-up/page.tsx → Sign-up form.


🔹 Dashboard (/dashboard)

layout.tsx → Sidebar + Topnav wrapper.

page.tsx → Dashboard home (summary).

usage/page.tsx → Usage stats, PAYG cost bar.

conversations/page.tsx → Conversation logs.

analytics/page.tsx → Charts, insights.

billing/page.tsx → Subscription + invoices.


🔹 API Routes

auth/[...nextauth]/route.ts → NextAuth login/logout/session.

chatbot/proxy/route.ts → Secure proxy to chatbot (logs usage).

usage/increment/route.ts → Adds usage record (e.g. per message).

usage/reset/route.ts → Reset usage (admin/testing).

webhooks/razorpay/route.ts → Handle Razorpay events (payment, invoice).



---

🔹 src/components/

layout/Sidebar.tsx → Dashboard sidebar.

layout/TopNav.tsx → Dashboard top navigation.

dashboard/UsageBar.tsx → Visual usage bar (PAYG).

dashboard/ConversationTable.tsx → Table of chatbot conversations.

dashboard/Charts.tsx → Usage/analytics charts.

billing/PlanCard.tsx → Pricing plan cards.

ui/ → Shadcn UI components (Button, Input, Card, etc.).



---

🔹 src/lib/ (Helpers & Security)

env.ts → Loads environment variables safely.

prisma.ts → Initializes Prisma client.

auth.ts → NextAuth config.

razorpay.ts → Razorpay API client setup.

webhook.ts → Verifies Razorpay webhook signatures.

plans.ts → Pricing (PAYG rates per unit).

usage.ts → Helpers for logging & calculating usage.

logger.ts → Central logging (Pino, with request IDs).

rbac.ts → Role-based access control (OrgAdmin, Member).

api-ratelimit.ts → Prevents abuse (per-user/org rate limit).

errors.ts → Custom error classes.

security.ts →

HMAC signing for bot requests.

Input validation (Zod).

Helmet headers.

CSRF protection.




---

🔹 src/server/ (Business Logic)

Repositories (server/repositories/)

userRepo.ts → CRUD for users.

orgRepo.ts → CRUD for organizations.

subscriptionRepo.ts → Store Razorpay subscription IDs.

conversationRepo.ts → Save chatbot logs.

usageRepo.ts → Store usage records.

invoiceRepo.ts → Store invoices & statuses.


Services (server/services/)

authService.ts → Login, signup, session.

subscriptionService.ts → Manage subscription states.

webhookService.ts → Process Razorpay events.

usageService.ts → Add/check usage, enforce limits.

invoiceService.ts → Generate PAYG invoices, send Razorpay links.

conversationService.ts → Fetch/store conversations.

chatbotService.ts → Secure proxy to open-source chatbot (with HMAC).



---

🔹 src/hooks/

useUsage.ts → Hook to fetch usage stats for dashboard.

useAuthGuard.ts → Protects pages from unauthorized access.



---

🔹 src/styles/

shadcn.css → Custom Shadcn UI styling overrides.



---

🔹 src/types/

next-auth.d.ts → Extend NextAuth session types (add orgId, role).

index.ts → Shared types (User, Org, Subscription, Invoice, etc.).



---

🔒 Security Recap

middleware.ts → Stops unauthorized dashboard access.

lib/security.ts → Anti-bypass (HMAC), validation, CSP, CSRF.

lib/api-ratelimit.ts → Stops abuse per user/org.

lib/rbac.ts → Prevents non-admins from touching billing.

server/services/chatbotService.ts → Proxy only, bot never public.

RLS in DB → Org-level separation.

Audit logs → Sensitive actions logged.



---

✅ This is now a full production-grade file map for a SaaS chatbot platform with:

PAYG billing (Razorpay).

Multi-tenant.

Enterprise-grade security.

No bypass.



---
