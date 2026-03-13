Below is a **production-ready SaaS folder structure for a modern app built with Next.js** using the App Router. This structure separates **marketing pages, authentication, dashboard, API, database logic, and services** so the project stays maintainable as it grows.

---

# Production SaaS Folder Structure

```
saas-app/
│
├─ app/                         # Next.js App Router
│   ├─ (marketing)/             # Public website
│   │   ├─ page.tsx             # Landing page
│   │   ├─ pricing/
│   │   │   └─ page.tsx
│   │   ├─ blog/
│   │   └─ contact/
│   │
│   ├─ (auth)/                  # Authentication pages
│   │   ├─ login/
│   │   │   └─ page.tsx
│   │   ├─ signup/
│   │   │   └─ page.tsx
│   │   └─ reset-password/
│   │
│   ├─ (dashboard)/             # Main SaaS application
│   │   ├─ layout.tsx           # Dashboard layout
│   │   ├─ page.tsx             # Dashboard home
│   │   ├─ clients/
│   │   │   ├─ page.tsx
│   │   │   └─ [id]/
│   │   │       └─ page.tsx
│   │   ├─ messages/
│   │   │   └─ page.tsx
│   │   ├─ files/
│   │   │   └─ page.tsx
│   │   ├─ billing/
│   │   │   └─ page.tsx
│   │   └─ settings/
│   │
│   ├─ api/                     # Backend API routes
│   │   ├─ auth/
│   │   ├─ clients/
│   │   │   ├─ create/
│   │   │   ├─ update/
│   │   │   └─ delete/
│   │   ├─ messages/
│   │   ├─ files/
│   │   └─ billing/
│   │
│   ├─ layout.tsx               # Global layout
│   └─ globals.css
│
├─ components/                  # Reusable UI components
│   ├─ ui/                      # Buttons, inputs, cards
│   ├─ dashboard/
│   ├─ forms/
│   └─ navigation/
│
├─ lib/                         # Core utilities
│   ├─ db.ts                    # DB connection
│   ├─ auth.ts                  # auth config
│   ├─ stripe.ts                # billing logic
│   ├─ permissions.ts           # feature gating
│   └─ utils.ts
│
├─ models/                      # Database models/schemas
│   ├─ User.ts
│   ├─ Client.ts
│   ├─ Message.ts
│   ├─ File.ts
│   └─ Subscription.ts
│
├─ services/                    # Business logic layer
│   ├─ clientService.ts
│   ├─ messageService.ts
│   ├─ fileService.ts
│   └─ billingService.ts
│
├─ hooks/                       # React hooks
│   ├─ useUser.ts
│   ├─ useClients.ts
│   └─ useSubscription.ts
│
├─ middleware.ts                # Auth protection
│
├─ types/                       # TypeScript types
│   ├─ user.ts
│   ├─ client.ts
│   └─ api.ts
│
├─ config/                      # App configuration
│   ├─ plans.ts                 # SaaS plans
│   └─ features.ts              # feature flags
│
├─ public/                      # Static files
│
├─ scripts/                     # DB seeds / jobs
│
├─ .env.local                   # Environment variables
├─ next.config.js
└─ package.json
```

---

# Why This Structure Works

### 1. Marketing vs App Separation

```
(marketing)
(auth)
(dashboard)
```

This allows **landing pages and the SaaS app to live together but stay organized**.

---

### 2. Business Logic Layer

Instead of putting everything in API routes:

```
API → services → database
```

Example:

```
api/clients/create → clientService → MongoDB
```

This makes the code **reusable and testable**.

---

### 3. Models for Database

If using **MongoDB** with **Mongoose**:

```
models/
   User
   Client
   Message
   File
```

Keeps schema definitions clean.

---

# Example Data Flow

User creates a client:

```
Dashboard form
   ↓
POST /api/clients/create
   ↓
clientService.ts
   ↓
MongoDB
```

---

# Example SaaS Feature System

Inside:

```
config/plans.ts
```

```
Free
Pro
Business
```

Example:

```
Free → 3 clients
Pro → 50 clients
Business → unlimited
```

---

# SaaS Infrastructure (Typical)

A modern SaaS stack often uses:

Database
→ MongoDB

Hosting
→ Vercel

Payments
→ Stripe

Storage
→ Amazon Web Services S3

---

# Important Production Features

A real SaaS should include:

✔ authentication
✔ role permissions
✔ plan feature gating
✔ billing system
✔ rate limiting
✔ logging
✔ analytics

---

💡 **Pro tip:**
Large SaaS apps eventually split into **three apps**:

```
marketing site
dashboard app
backend API
```

But early-stage SaaS works perfectly in **one Next.js project**.
