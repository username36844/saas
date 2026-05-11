# Auth-Focused SaaS Structure

```text id="c9n7yh"
saas-app/
│
├─ app/
│   │
│   ├─ (marketing)/
│   │   ├─ page.tsx
│   │   ├─ pricing/
│   │   └─ contact/
│   │
│   ├─ (auth)/
│   │   │
│   │   ├─ login/
│   │   │   └─ page.tsx
│   │   │
│   │   ├─ signup/
│   │   │   └─ page.tsx
│   │   │
│   │   ├─ verify-email/
│   │   │   ├─ page.tsx
│   │   │   ├─ confirm/
│   │   │   │   └─ page.tsx
│   │   │   └─ success/
│   │   │       └─ page.tsx
│   │   │
│   │   ├─ forgot-password/
│   │   │   ├─ page.tsx
│   │   │   ├─ confirm/
│   │   │   │   └─ page.tsx
│   │   │   └─ success/
│   │   │       └─ page.tsx
│   │   │
│   │   ├─ reset-password/
│   │   │   ├─ page.tsx
│   │   │   └─ success/
│   │   │       └─ page.tsx
│   │   │
│   │   └─ verify-email-required/
│   │       └─ page.tsx
│   │
│   ├─ (dashboard)/
│   │   ├─ layout.tsx
│   │   ├─ page.tsx
│   │   ├─ settings/
│   │   └─ billing/
│   │
│   ├─ api/
│   │   │
│   │   ├─ auth/
│   │   │   ├─ signup/
│   │   │   │   └─ route.ts
│   │   │   ├─ login/
│   │   │   │   └─ route.ts
│   │   │   ├─ logout/
│   │   │   │   └─ route.ts
│   │   │   ├─ verify-email/
│   │   │   │   └─ route.ts
│   │   │   ├─ resend-verification/
│   │   │   │   └─ route.ts
│   │   │   ├─ forgot-password/
│   │   │   │   └─ route.ts
│   │   │   └─ reset-password/
│   │   │       └─ route.ts
│   │
│   ├─ layout.tsx
│   ├─ globals.css
│   └─ favicon.ico
│
├─ components/
│   │
│   ├─ ui/
│   │
│   ├─ auth/
│   │   ├─ login-form.tsx
│   │   ├─ signup-form.tsx
│   │   ├─ forgot-password-form.tsx
│   │   ├─ reset-password-form.tsx
│   │   ├─ resend-verification-form.tsx
│   │   └─ verify-email-card.tsx
│   │
│   └─ dashboard/
│       ├─ sidebar.tsx
│       ├─ navbar.tsx
│       └─ dashboard-shell.tsx
│
├─ lib/
│   │
│   ├─ prisma/
│   │   └─ prisma.ts
│   │
│   ├─ auth/
│   │   ├─ auth.ts
│   │   ├─ session.ts
│   │   ├─ cookies.ts
│   │   ├─ current-user.ts
│   │   └─ guards.ts
│   │
│   ├─ crypto/
│   │   ├─ password.ts
│   │   ├─ token.ts
│   │   └─ session.ts
│   │
│   ├─ validations/
│   │   └─ auth.validation.ts
│   │
│   ├─ api/
│   │   ├─ api-response.ts
│   │   ├─ api-success.ts
│   │   ├─ api-error.ts
│   │   └─ auth-fetch.ts
│   │
│   ├─ email/
│   │   ├─ resend.ts
│   │   ├─ send-email.ts
│   │   ├─ resend-verification-email.ts
│   │   │
│   │   └─ templates/
│   │       ├─ verify-email.tsx
│   │       └─ forgot-password.tsx
│
├─ prisma/
│   │
│   ├─ schema.prisma
│   │
│   └─ migrations/
│
├─ middleware.ts
│
├─ public/
│
├─ .env
├─ .env.local
├─ next.config.ts
├─ tsconfig.json
└─ package.json
```
