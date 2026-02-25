<p align="center">
  <img src="https://img.shields.io/badge/Next.js-15.5-black?style=for-the-badge&logo=nextdotjs&logoColor=white" alt="Next.js" />
  <img src="https://img.shields.io/badge/React-19-61DAFB?style=for-the-badge&logo=react&logoColor=white" alt="React" />
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Firebase-11-FFCA28?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase" />
  <img src="https://img.shields.io/badge/Genkit_AI-Google-4285F4?style=for-the-badge&logo=google&logoColor=white" alt="Genkit AI" />
  <img src="https://img.shields.io/badge/TailwindCSS-3.4-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white" alt="TailwindCSS" />
</p>

<h1 align="center">
  🚛 FleetFlow
</h1>

<p align="center">
  <strong>The Logistics Operating System — AI-Powered Fleet & Cargo Intelligence Platform</strong>
</p>

<p align="center">
  A full-stack, enterprise-grade SaaS application for managing fleet operations, trip dispatching,<br/>
  driver safety compliance, expense auditing, and AI-driven business insights — all in real time.
</p>

<p align="center">
  <a href="#-features">Features</a> •
  <a href="#%EF%B8%8F-tech-stack">Tech Stack</a> •
  <a href="#-architecture">Architecture</a> •
  <a href="#-getting-started">Getting Started</a> •
  <a href="#-project-structure">Project Structure</a> •
  <a href="#-role-based-access-control">RBAC</a> •
  <a href="#-ai-integration">AI</a> •
  <a href="#-screenshots">Screenshots</a> •
  <a href="#-license">License</a>
</p>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#%EF%B8%8F-tech-stack)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [Role-Based Access Control (RBAC)](#-role-based-access-control)
- [Database Schema](#-database-schema)
- [AI Integration](#-ai-integration)
- [Security](#-security)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌐 Overview

**FleetFlow** is a modern, full-stack logistics management platform that provides a unified command environment for fleet operators. Built with **Next.js 15 (App Router)**, **Firebase**, and **Google Genkit AI**, it delivers real-time fleet monitoring, intelligent dispatching, financial auditing, and AI-driven operational insights.

The application is designed around a **military-grade role-based access control (RBAC)** system, ensuring that each user — from Fleet Manager to Financial Analyst — sees only the data and controls relevant to their operational scope.

### Why FleetFlow?

| Problem                                   | FleetFlow Solution                                  |
| ----------------------------------------- | --------------------------------------------------- |
| Scattered fleet data across spreadsheets  | Centralized digital twin for every vehicle          |
| Manual trip tracking with no visibility   | 4-stage cargo lifecycle with real-time status       |
| No compliance enforcement                 | Automated license expiry detection & safety scoring |
| Uncontrolled operational costs            | Integrated fuel, maintenance, and expense ledger    |
| Data overload with no actionable insights | Google Gemini-powered AI insight generation         |

---

## ✨ Features

### 🏠 Landing Page

- Premium, conversion-optimized landing page with glassmorphism design
- Animated hero section with live statistics and interactive UI elements
- Capability showcase, role hierarchy display, and footer navigation
- Fully responsive across all device breakpoints

### 📊 Operational Dashboard

- **Real-time KPI cards** — Active Fleet, Maintenance Alerts, Active Cargo
- **Live Dispatch Ledger** — Searchable table of all active and completed trips
- **Contextual navigation** — Menu items filtered by user role

### 🚛 Vehicle Registry

- Full CRUD operations for fleet vehicles
- Track vehicle model, license plate, capacity (kg), odometer, acquisition cost, region
- Status management: `Available`, `On Trip`, `In Shop`
- Role-gated to Fleet Managers

### 🗺️ Trip Command Center (Dispatcher)

- **4-Stage Cargo Lifecycle:** `Scheduled → Dispatched → In Transit → Completed`
- Create trips with origin, destination, assigned vehicle/driver, cargo weight, and ETA
- Stage advancement with a single click
- Overload enforcement: cargo weight validated against vehicle max capacity
- Driver availability sync — only `On Duty` drivers can be assigned

### 🔧 Maintenance Module

- Log maintenance and service records per vehicle
- Track service type (Oil Change, Tire Rotation, Brake Inspection, Full Service, etc.)
- Record cost, date, and current odometer reading
- Fleet Manager-exclusive access

### 💰 Trip & Expense Hub

- Comprehensive expense tracking per vehicle: **Fuel**, **Maintenance**, **Toll/Parking**, **Insurance**, **Other**
- Auto-calculated total operational cost per vehicle
- Fuel log tracking with liters, cost per liter, and total fuel cost
- Dual-role access: Fleet Managers + Financial Analysts

### 👥 Driver Roster & Safety Profiles

- Full driver management with CRUD operations
- **License compliance enforcement** — Expired licenses auto-flag the driver
- **Safety scoring system** — Calculated from accident history and trip completion rates
- Status logic: `On Duty`, `Off Duty`, `Suspended` (auto-forced for expired license or zero safety score)
- Performance metrics: total trips, completed trips, completion rate

### 📈 Analytics & Visualizations

- **Revenue & Cost Trends** — Interactive line charts (Recharts)
- **Fuel Consumption Analysis** — Bar charts with per-vehicle breakdown
- **Expense Category Distribution** — Visual cost analysis
- Data aggregated in real-time from Firestore collections

### 🤖 AI-Powered Insights (Google Genkit + Gemini)

- **Automated Data Insights** — AI agent analyzes fleet data to identify:
  - Key operational trends
  - Anomalies and unusual patterns
  - Business opportunities and optimization recommendations
- Powered by **Google Genkit** with the **Gemini 2.5 Flash** model
- Zod-validated input/output schemas for type-safe AI flows

### 🔐 Authentication & Authorization

- Firebase Authentication (Email/Password)
- Smart role determination during registration:
  - **Fleet Manager** — Requires admin secret key
  - **Safety Officer** — Auto-assigned via email keyword detection
  - **Financial Analyst** — Auto-assigned via email keyword detection
  - **Dispatcher** — Default role for all other users
- Persistent auth state with automatic redirect logic

---

## 🛠️ Tech Stack

### Frontend

| Technology                                | Purpose                                                       |
| ----------------------------------------- | ------------------------------------------------------------- |
| **Next.js 15.5** (App Router + Turbopack) | React framework with server components and file-based routing |
| **React 19**                              | UI rendering with concurrent features                         |
| **TypeScript 5**                          | Static type safety across the entire codebase                 |
| **Tailwind CSS 3.4**                      | Utility-first styling with custom design tokens               |
| **shadcn/ui** (Radix UI primitives)       | 35+ accessible, customizable UI components                    |
| **Recharts**                              | Composable charting library for analytics visualizations      |
| **Lucide React**                          | Beautiful, consistent SVG icon library                        |
| **React Hook Form + Zod**                 | Form management with schema validation                        |

### Backend & Infrastructure

| Technology                   | Purpose                                                 |
| ---------------------------- | ------------------------------------------------------- |
| **Firebase Authentication**  | Secure email/password authentication                    |
| **Cloud Firestore**          | Real-time NoSQL database with live subscriptions        |
| **Firestore Security Rules** | Server-side RBAC enforcement at the database level      |
| **Firebase App Hosting**     | Production deployment with auto-scaling                 |
| **Google Genkit**            | AI orchestration framework for Gemini model integration |
| **Gemini 2.5 Flash**         | Google's latest generative AI model for data insights   |

### Design System

| Element             | Value                                    |
| ------------------- | ---------------------------------------- |
| **Primary Color**   | Deep Logistics Blue (`#1E40AF`)          |
| **Accent Color**    | Electric Cyan (`hsl(182, 100%, 74%)`)    |
| **Background**      | Cool Gray (`#F8FAFC`)                    |
| **Body Font**       | Inter (400–700)                          |
| **Headline Font**   | Space Grotesk (400–700)                  |
| **Border Radius**   | `1rem` (design token `--radius`)         |
| **Component Style** | Glassmorphism + clean card-based layouts |

---

## 🏗 Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        CLIENT (Browser)                         │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                    Next.js 15 App Router                  │   │
│  │  ┌────────────┐  ┌────────────┐  ┌───────────────────┐   │   │
│  │  │  Landing    │  │   Auth     │  │    Dashboard      │   │   │
│  │  │  Page (SSR) │  │  Login /   │  │  (Client-Side)    │   │   │
│  │  │             │  │  Register  │  │                   │   │   │
│  │  └────────────┘  └────────────┘  │  ┌─────────────┐  │   │   │
│  │                                   │  │  Vehicles    │  │   │   │
│  │  ┌────────────────────────────┐  │  │  Trips       │  │   │   │
│  │  │     shadcn/ui Components   │  │  │  Maintenance │  │   │   │
│  │  │  (35+ Radix UI Primitives) │  │  │  Expenses    │  │   │   │
│  │  └────────────────────────────┘  │  │  Drivers     │  │   │   │
│  │                                   │  │  Analytics   │  │   │   │
│  │  ┌────────────────────────────┐  │  │  AI Insights │  │   │   │
│  │  │  Custom Firebase Hooks     │  │  └─────────────┘  │   │   │
│  │  │  useCollection, useDoc,    │  └───────────────────┘   │   │
│  │  │  useMemoFirebase           │                           │   │
│  │  └────────────────────────────┘                           │   │
│  └──────────────────────────────────────────────────────────┘   │
└────────────────────────────┬────────────────────────────────────┘
                             │  Real-time Subscriptions (onSnapshot)
                             │  Auth State (onAuthStateChanged)
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    FIREBASE BACKEND (BaaS)                       │
│  ┌──────────────┐  ┌───────────────┐  ┌───────────────────┐    │
│  │  Firebase     │  │  Cloud        │  │  Firestore        │    │
│  │  Auth         │  │  Firestore    │  │  Security Rules   │    │
│  │  (Email/Pwd)  │  │  (NoSQL DB)   │  │  (RBAC Enforced)  │    │
│  └──────────────┘  └───────────────┘  └───────────────────┘    │
│                                                                  │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                 Firebase App Hosting                      │   │
│  │              (Production Deployment Target)               │   │
│  └──────────────────────────────────────────────────────────┘   │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                    AI LAYER (Google Genkit)                       │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │  Genkit AI Orchestration                                  │   │
│  │  ├─ automatedDataInsightsFlow                             │   │
│  │  ├─ Zod-validated I/O Schemas                             │   │
│  │  └─ Gemini 2.5 Flash Model (Google AI Plugin)             │   │
│  └──────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

### Key Architectural Patterns

- **Real-time Data Subscriptions** — Custom `useCollection` and `useDoc` hooks wrap Firestore's `onSnapshot` for live data sync
- **Non-blocking Writes** — `setDocumentNonBlocking`, `updateDocumentNonBlocking`, and `deleteDocumentNonBlocking` utilities for optimistic UI updates
- **Memoized Firebase References** — `useMemoFirebase` ensures stable Firestore references to prevent unnecessary re-renders
- **Global Error Propagation** — Custom `FirestorePermissionError` with a global `errorEmitter` for centralized error handling
- **Server Actions for AI** — AI flows run as Next.js server actions (`'use server'`) for secure API key handling

---

## 📁 Project Structure

```
fleet-flow/
├── src/
│   ├── ai/                          # AI / Genkit integration
│   │   ├── genkit.ts                # Genkit instance configuration (Gemini 2.5 Flash)
│   │   ├── dev.ts                   # Genkit development server entry point
│   │   └── flows/
│   │       └── automated-data-insights.ts  # AI flow for business intelligence
│   │
│   ├── app/                         # Next.js App Router pages
│   │   ├── layout.tsx               # Root layout (Firebase Provider, fonts, Toaster)
│   │   ├── page.tsx                 # Landing page (/)
│   │   ├── globals.css              # Global styles & CSS design tokens
│   │   │
│   │   ├── auth/                    # Authentication routes
│   │   │   ├── login/page.tsx       # User sign-in page
│   │   │   └── register/page.tsx    # User registration with role assignment
│   │   │
│   │   └── dashboard/              # Protected dashboard routes
│   │       ├── layout.tsx           # Sidebar navigation + auth guard + role filter
│   │       ├── page.tsx             # Main dashboard (KPIs + Dispatch Ledger)
│   │       ├── vehicles/page.tsx    # Vehicle fleet registry (CRUD)
│   │       ├── trips/page.tsx       # Trip dispatcher (4-stage lifecycle)
│   │       ├── maintenance/page.tsx # Maintenance log management
│   │       ├── expenses/page.tsx    # Trip & expense tracking hub
│   │       ├── performance/page.tsx # Driver roster & safety profiles
│   │       ├── analytics/page.tsx   # Charts and financial analytics
│   │       ├── ai/page.tsx          # AI-powered data insights
│   │       └── data/page.tsx        # Transaction history table
│   │
│   ├── components/                  # Reusable components
│   │   ├── FirebaseErrorListener.tsx # Global Firebase error toast handler
│   │   └── ui/                      # 35 shadcn/ui components
│   │       ├── accordion.tsx
│   │       ├── alert-dialog.tsx
│   │       ├── avatar.tsx
│   │       ├── badge.tsx
│   │       ├── button.tsx
│   │       ├── calendar.tsx
│   │       ├── card.tsx
│   │       ├── chart.tsx
│   │       ├── dialog.tsx
│   │       ├── sidebar.tsx
│   │       ├── table.tsx
│   │       ├── toast.tsx
│   │       └── ... (22 more)
│   │
│   ├── firebase/                    # Firebase SDK abstraction layer
│   │   ├── index.ts                 # App initialization & SDK exports
│   │   ├── config.ts                # Firebase project configuration
│   │   ├── provider.tsx             # React context provider (auth + services)
│   │   ├── client-provider.tsx      # Client-side provider wrapper
│   │   ├── errors.ts               # Custom FirestorePermissionError class
│   │   ├── error-emitter.ts         # Global error event emitter
│   │   ├── non-blocking-login.tsx   # Optimistic auth state updates
│   │   ├── non-blocking-updates.tsx # Optimistic Firestore write utilities
│   │   └── firestore/
│   │       ├── use-collection.tsx   # Real-time collection subscription hook
│   │       └── use-doc.tsx          # Real-time document subscription hook
│   │
│   ├── hooks/                       # Custom React hooks
│   │   ├── use-mobile.tsx           # Responsive breakpoint detection
│   │   └── use-toast.ts            # Toast notification hook
│   │
│   └── lib/                         # Utility functions
│       └── utils.ts                 # cn() classname merge utility
│
├── docs/                            # Project documentation
│   ├── blueprint.md                 # Original project blueprint & design spec
│   └── backend.json                 # Backend API & schema documentation
│
├── firestore.rules                  # Firestore Security Rules (RBAC)
├── apphosting.yaml                  # Firebase App Hosting configuration
├── next.config.ts                   # Next.js configuration
├── tailwind.config.ts               # Tailwind CSS theme configuration
├── tsconfig.json                    # TypeScript configuration
├── components.json                  # shadcn/ui component registry
└── package.json                     # Dependencies & scripts
```

---

## 🚀 Getting Started

### Prerequisites

- **Node.js** ≥ 18.x
- **npm** ≥ 9.x (or yarn/pnpm)
- A **Firebase project** with Authentication and Firestore enabled
- _(Optional)_ Google AI API key for Genkit AI features

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/your-username/fleet-flow.git
cd fleet-flow

# 2. Install dependencies
npm install

# 3. Configure Firebase (see Environment Variables section below)

# 4. Start the development server
npm run dev
```

The application will start on **http://localhost:9002** with Turbopack enabled for fast HMR.

### Available Scripts

| Script                 | Description                                  |
| ---------------------- | -------------------------------------------- |
| `npm run dev`          | Start dev server with Turbopack on port 9002 |
| `npm run build`        | Create production build                      |
| `npm run start`        | Start production server                      |
| `npm run lint`         | Run ESLint                                   |
| `npm run typecheck`    | Run TypeScript type checking                 |
| `npm run genkit:dev`   | Start Genkit AI development server           |
| `npm run genkit:watch` | Start Genkit with hot reload                 |

---

## 🔑 Environment Variables

Create a `.env.local` file in the project root:

```env
# Firebase Configuration
NEXT_PUBLIC_FIREBASE_API_KEY=your_api_key
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=your_project.firebaseapp.com
NEXT_PUBLIC_FIREBASE_PROJECT_ID=your_project_id
NEXT_PUBLIC_FIREBASE_APP_ID=your_app_id

# Google AI (for Genkit)
GOOGLE_GENAI_API_KEY=your_google_ai_api_key
```

> **Note:** The Firebase config is currently stored in `src/firebase/config.ts`. For production deployments via Firebase App Hosting, the SDK auto-initializes without explicit config.

---

## 🛡 Role-Based Access Control

FleetFlow implements **deep RBAC** at both the **application layer** and the **database layer** (Firestore Security Rules).

### Role Hierarchy

```
┌─────────────────────────────────────────────────────────────┐
│                                                               │
│   👑 FLEET MANAGER        (Full Access — Admin Secret Key)   │
│   ├── Vehicle Registry    ✅ Full CRUD                       │
│   ├── Trip Dispatcher     ✅ Full CRUD                       │
│   ├── Maintenance Logs    ✅ Full CRUD                       │
│   ├── Expense Tracking    ✅ Full CRUD                       │
│   ├── Driver Roster       ✅ Full CRUD                       │
│   ├── Analytics           ✅ Read                            │
│   ├── AI Insights         ✅ Read                            │
│   └── Demo Seed           ✅ Available                       │
│                                                               │
│   📡 DISPATCHER            (Operations Focused)               │
│   ├── Vehicle Registry    ✅ Read Only                       │
│   ├── Trip Dispatcher     ✅ Create + Update                 │
│   ├── Driver Roster       ✅ Read Only                       │
│   └── Dashboard           ✅ Read                            │
│                                                               │
│   🛡️ SAFETY OFFICER        (Compliance Focused)               │
│   ├── Vehicle Registry    ✅ Read Only                       │
│   ├── Driver Roster       ✅ Create + Update                 │
│   └── Dashboard           ✅ Read                            │
│                                                               │
│   💼 FINANCIAL ANALYST     (Financial Focused)                │
│   ├── Expense Tracking    ✅ Create + Update                 │
│   ├── Analytics           ✅ Read                            │
│   └── Dashboard           ✅ Read                            │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

### Registration Role Assignment Logic

```
Email contains "safety"  ────────→  Safety Officer
Email contains "finance" ────────→  Financial Analyst
Admin key provided       ────────→  Fleet Manager (requires: FLEET-ADMIN-2024)
Default                  ────────→  Dispatcher
```

### Firestore Security Rules

All RBAC is enforced server-side via Firestore Security Rules with helper functions:

```javascript
function isFleetManager() {
  return hasRole("roles_fleetManagers");
}
function isDispatcher() {
  return hasRole("roles_dispatchers");
}
function isSafetyOfficer() {
  return hasRole("roles_safetyOfficers");
}
function isFinancialAnalyst() {
  return hasRole("roles_financialAnalysts");
}
```

---

## 🗄 Database Schema

FleetFlow uses **Cloud Firestore** with the following collections:

| Collection                | Description                   | Key Fields                                                                                              |
| ------------------------- | ----------------------------- | ------------------------------------------------------------------------------------------------------- |
| `users`                   | User profile documents        | `roleId`, `email`, `displayName`                                                                        |
| `vehicles`                | Fleet vehicle registry        | `name`, `model`, `licensePlate`, `maxCapacityKg`, `odometerKm`, `status`, `type`, `region`              |
| `drivers`                 | Driver personnel records      | `name`, `licenseCategory`, `licenseExpiryDate`, `status`, `safetyScore`, `totalTrips`, `completedTrips` |
| `trips`                   | Trip/cargo lifecycle records  | `origin`, `destination`, `vehicleId`, `driverId`, `cargoWeightKg`, `status`, `eta`                      |
| `maintenance_logs`        | Vehicle maintenance records   | `vehicleId`, `serviceType`, `cost`, `date`, `odometerReading`                                           |
| `fuel_logs`               | Fuel consumption records      | `vehicleId`, `liters`, `costPerLiter`, `totalCost`, `date`                                              |
| `expenses`                | Operational expense records   | `vehicleId`, `category`, `amount`, `description`, `date`                                                |
| `roles_fleetManagers`     | Fleet Manager role tokens     | `id`, `name`, `accessScope`                                                                             |
| `roles_dispatchers`       | Dispatcher role tokens        | `id`, `name`, `accessScope`                                                                             |
| `roles_safetyOfficers`    | Safety Officer role tokens    | `id`, `name`, `accessScope`                                                                             |
| `roles_financialAnalysts` | Financial Analyst role tokens | `id`, `name`, `accessScope`                                                                             |

---

## 🤖 AI Integration

FleetFlow integrates **Google Genkit** with the **Gemini 2.5 Flash** model for intelligent business analytics.

### Automated Data Insights Flow

```typescript
// Input Schema (Zod-validated)
{
  salesDataJson: string;              // JSON array of revenue data points
  performanceIndicatorsJson: string;  // JSON array of KPI metrics
}

// Output Schema (Zod-validated)
{
  summary: string;           // High-level analysis summary
  trends: string[];          // Identified operational trends
  anomalies: string[];       // Detected unusual patterns
  opportunities: string[];   // Actionable business recommendations
}
```

### How It Works

1. Fleet data (expenses, fuel logs, trip metrics) is collected from Firestore
2. Data is serialized to JSON and sent to the Genkit AI flow
3. The Gemini model analyzes the data for patterns, anomalies, and opportunities
4. Structured, type-safe results are returned and displayed in the AI Insights dashboard

---

## 🔒 Security

| Layer                 | Implementation                                                          |
| --------------------- | ----------------------------------------------------------------------- |
| **Authentication**    | Firebase Auth with email/password provider                              |
| **Authorization**     | Multi-collection RBAC with Firestore Security Rules                     |
| **Data Access**       | Role-gated Firestore reads/writes enforced server-side                  |
| **API Keys**          | AI keys handled server-side via Next.js server actions (`'use server'`) |
| **Client Protection** | Auth guard on dashboard layout with automatic redirect                  |
| **Error Handling**    | Custom `FirestorePermissionError` with structured debugging context     |
| **Input Validation**  | Zod schemas for all AI flow inputs/outputs                              |

---

## 🚢 Deployment

### Firebase App Hosting (Recommended)

FleetFlow is configured for **Firebase App Hosting** out of the box:

```yaml
# apphosting.yaml
runConfig:
  maxInstances: 1
```

```bash
# Deploy to Firebase App Hosting
firebase apphosting:backends:create
```

### Alternative: Vercel / Self-Hosted

```bash
# Build for production
npm run build

# Start production server
npm run start
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Commit** your changes (`git commit -m 'feat: add amazing feature'`)
4. **Push** to the branch (`git push origin feature/amazing-feature`)
5. **Open** a Pull Request

### Commit Convention

This project follows [Conventional Commits](https://www.conventionalcommits.org/):

| Prefix      | Purpose                 |
| ----------- | ----------------------- |
| `feat:`     | New feature             |
| `fix:`      | Bug fix                 |
| `docs:`     | Documentation           |
| `style:`    | Code formatting         |
| `refactor:` | Code restructuring      |
| `perf:`     | Performance improvement |
| `test:`     | Adding tests            |
| `chore:`    | Tooling/config changes  |

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<p align="center">
  <br/>
  <strong>Built with ❤️ using Next.js, Firebase & Google AI</strong>
  <br/>
  <sub>FleetFlow — The Logistics Operating System</sub>
</p>
