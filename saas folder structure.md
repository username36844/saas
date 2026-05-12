```txt id="t84n97"
src/
│
├── app/
│   │
│   ├── (marketing)/
│   │   │
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   │
│   │   ├── pricing/
│   │   │   └── page.tsx
│   │   │
│   │   ├── features/
│   │   │   └── page.tsx
│   │   │
│   │   └── contact/
│   │       └── page.tsx
│   │
│   │
│   ├── (auth)/
│   │   │
│   │   ├── layout.tsx
│   │   │
│   │   ├── signup/
│   │   │   └── page.tsx
│   │   │
│   │   ├── login/
│   │   │   └── page.tsx
│   │   │
│   │   ├── verify/
│   │   │   └── page.tsx
│   │   │
│   │   ├── resend-verification/
│   │   │   └── page.tsx
│   │   │
│   │   ├── forgot-password/
│   │   │   └── page.tsx
│   │   │
│   │   ├── reset-password/
│   │   │   └── page.tsx
│   │   │
│   │   └── onboarding/
│   │       └── page.tsx
│   │
│   │
│   ├── api/
│   │   └── auth/
│   │       │
│   │       ├── signup/
│   │       │   └── route.ts
│   │       │
│   │       ├── login/
│   │       │   └── route.ts
│   │       │
│   │       ├── verify/
│   │       │   └── route.ts
│   │       │
│   │       ├── resend-verification/
│   │       │   └── route.ts
│   │       │
│   │       ├── forgot-password/
│   │       │   └── route.ts
│   │       │
│   │       ├── reset-password/
│   │       │   └── route.ts
│   │       │
│   │       └── logout/
│   │           └── route.ts
│   │
│   │
│   ├── globals.css
│   └── layout.tsx
│
│
├── components/
│   │
│   ├── auth/
│   │   │
│   │   ├── auth-shell.tsx
│   │   ├── auth-card.tsx
│   │   ├── auth-header.tsx
│   │   ├── auth-transition.tsx
│   │   │
│   │   ├── signup-form.tsx
│   │   ├── login-form.tsx
│   │   ├── forgot-password-form.tsx
│   │   ├── reset-password-form.tsx
│   │   ├── resend-verification-form.tsx
│   │   │
│   │   ├── verify-success.tsx
│   │   ├── auth-success-state.tsx
│   │   ├── auth-error-state.tsx
│   │   ├── auth-loading-state.tsx
│   │   │
│   │   ├── password-strength.tsx
│   │   ├── password-input.tsx
│   │   │
│   │   └── open-email-button.tsx
│   │
│   │
│   ├── ui/
│   │   │
│   │   ├── button.tsx
│   │   ├── input.tsx
│   │   ├── spinner.tsx
│   │   ├── surface.tsx
│   │   └── modal.tsx
│   │
│   │
│   └── shared/
│       │
│       ├── logo.tsx
│       └── ambient-background.tsx
│
│
├── features/
│   │
│   └── auth/
│       │
│       ├── actions/
│       │   │
│       │   ├── signup.ts
│       │   ├── login.ts
│       │   ├── verify-email.ts
│       │   ├── resend-verification.ts
│       │   ├── forgot-password.ts
│       │   ├── reset-password.ts
│       │   └── logout.ts
│       │
│       │
│       ├── hooks/
│       │   │
│       │   ├── use-auth-redirect.ts
│       │   ├── use-auth-modal.ts
│       │   └── use-password-strength.ts
│       │
│       │
│       ├── schemas/
│       │   │
│       │   ├── signup-schema.ts
│       │   ├── login-schema.ts
│       │   ├── forgot-password-schema.ts
│       │   └── reset-password-schema.ts
│       │
│       │
│       ├── lib/
│       │   │
│       │   ├── auth-client.ts
│       │   ├── auth-errors.ts
│       │   ├── token.ts
│       │   ├── cookies.ts
│       │   ├── session.ts
│       │   └── hash.ts
│       │
│       │
│       ├── constants/
│       │   └── auth.constants.ts
│       │
│       └── types/
│           └── auth.types.ts
│
│
├── lib/
│   │
│   ├── prisma.ts
│   ├── mail.ts
│   ├── env.ts
│   ├── utils.ts
│   └── rate-limit.ts
│
│
├── prisma/
│   │
│   ├── schema.prisma
│   └── migrations/
│
│
├── styles/
│   │
│   ├── animations.css
│   └── theme.css
│
│
└── middleware.ts
```

---

# NOW — What Each File Contains

This is the important part.

---

# `app/(auth)/layout.tsx`

## Purpose

Persistent auth layout.

## Contains

* centered auth shell
* background atmosphere
* shared auth spacing
* auth transitions wrapper

Example responsibility:

```txt id="9wf1ja"
same layout for:
signup
login
verify
forgot password
reset password
```

This is what creates:

# continuity.

---

# `app/(auth)/signup/page.tsx`

## Purpose

Thin route entry only.

## Contains

* imports signup form
* route-level metadata
* minimal orchestration

NOT:

* validation logic
* fetch logic
* animation logic

Keep pages thin.

---

# `components/auth/auth-shell.tsx`

## Purpose

The MOST important file.

## Contains

* centered auth container
* max width
* spacing system
* animation wrapper
* background layering

This file creates:

# premium continuity feeling.

---

# `components/auth/auth-transition.tsx`

## Purpose

Reusable transition system.

## Contains

Framer Motion:

* fade up
* exit transitions
* shared timing
* easing

Used everywhere.

This creates:

# motion consistency.

---

# `components/auth/auth-card.tsx`

## Purpose

Shared surface/card UI.

## Contains

* rounded surface
* padding
* blur
* shadow
* border logic

Every auth screen uses same card.

Creates:

# visual consistency.

---

# `components/auth/signup-form.tsx`

## Purpose

Actual signup UI + state transitions.

## Contains

* react-hook-form
* zod validation
* API action calls
* loading states
* success states
* animated transitions

NOT backend code.

---

# `components/auth/auth-success-state.tsx`

## Purpose

Shared success surface.

Used for:

* verification sent
* password reset success
* login success

Contains:

* icon
* success animation
* title
* subtitle
* optional redirect countdown

This prevents duplicated UX.

---

# `components/auth/auth-error-state.tsx`

## Purpose

Inline contextual auth errors.

Instead of:

# toast spam.

Contains:

* animated error surface
* icon
* retry CTA
* descriptive messaging

---

# `components/auth/open-email-button.tsx`

## Purpose

Reusable:

```txt id="e3xb6x"
Open Gmail
Open Outlook
```

logic.

Can detect provider from email.

Very premium detail.

---

# `components/auth/password-strength.tsx`

## Purpose

Live password feedback.

Contains:

* strength scoring
* animated bars
* realtime validation indicators

Replaces:

# giant password paragraphs.

---

# `components/shared/ambient-background.tsx`

## Purpose

Creates premium atmosphere.

Contains:

* gradients
* subtle noise
* blur lights
* mesh background

This file contributes MASSIVELY to:

# “alive feeling.”

---

# `features/auth/actions/signup.ts`

## Purpose

Frontend auth business action.

## Contains

* fetch request
* response normalization
* error mapping

NOT:

* UI
* forms
* components

---

# `features/auth/lib/auth-client.ts`

## Purpose

Centralized auth API client.

Contains:

* fetch wrapper
* credentials include
* headers
* response parsing

Prevents duplicated fetch code.

---

# `features/auth/lib/auth-errors.ts`

## Purpose

Maps backend errors to UI-safe messages.

Example:

```txt id="10e1tb"
INVALID_CREDENTIALS
→
"Email or password is incorrect"
```

Very important for polished UX.

---

# `features/auth/hooks/use-auth-modal.ts`

## Purpose

Controls:

* auth state surfaces
* animated modal/sheet states
* success/error transitions

This becomes core to:

# seamless auth UX.

---

# `features/auth/schemas/*.ts`

## Purpose

All zod schemas.

Separate:

* signup
* login
* reset password

Keeps validation centralized.

---

# `app/api/auth/*`

## Purpose

Pure backend routes.

Contains:

* DB logic
* cookies
* sessions
* token verification
* rate limiting
* email sending

NO frontend concerns.

---

# `lib/mail.ts`

## Purpose

Centralized email logic.

Contains:

* resend/nodemailer integration
* email templates
* verification email
* reset email

---

# `styles/animations.css`

## Purpose

Shared motion system.

Contains:

* keyframes
* auth easing
* duration tokens

This creates:

# cohesive motion language.

---

# Most Important Architecture Principle

Your structure should separate:

| Layer       | Responsibility       |
| ----------- | -------------------- |
| app/        | routing              |
| components/ | UI                   |
| features/   | business logic       |
| api/        | backend              |
| lib/        | infrastructure       |
| styles/     | system-level styling |

This is scalable product architecture.

---

# Biggest Mistake To Avoid

DO NOT put:

* auth fetch logic
* zod schemas
* transitions
* state machines

directly inside:

```txt id="ufvzvj"
page.tsx
```

That destroys maintainability quickly.

---

# Your Current Architecture Level

You are now building:

# a scalable SaaS platform structure

—not:

# a collection of auth pages.
