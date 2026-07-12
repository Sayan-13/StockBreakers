# StockBreakers

# StockBreakers 📈

> **Simulate. Trade. Insight. Grow.**

An AI-enhanced simulated stock trading platform where users start with **$50,000 in virtual cash** and can trade 20+ stocks with real-time price simulation, portfolio analytics, and AI-driven insights — all risk-free.

Built by Team StormBreakers in a 24-hour hackathon sprint.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Vercel-black?style=for-the-badge&logo=vercel)](https://stockbreakers.vercel.app)
[![Next.js](https://img.shields.io/badge/Next.js-15-black?style=for-the-badge&logo=next.js)](https://nextjs.org)
[![Firebase](https://img.shields.io/badge/Firebase-Firestore-orange?style=for-the-badge&logo=firebase)](https://firebase.google.com)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?style=for-the-badge&logo=typescript)](https://typescriptlang.org)

---

## ✨ Features

### Core Trading
- 🔐 **Auth** — Email/password + Google OAuth via Firebase
- 💸 **Simulated Trading Engine** — Instant buy/sell at live simulated prices
- 📊 **Portfolio Dashboard** — Real-time P&L, allocation charts, performance history
- 👁️ **Watchlist** — Live price cards with sparklines
- 📜 **Transaction History** — Filterable/sortable trade log

### AI Insights
- 📈 **Price Trend Prediction** — 7-day AI forecast with confidence bands
- 📰 **News Sentiment Analysis** — Bullish/Bearish/Neutral badges per stock
- ⚡ **Portfolio Risk Scoring** — Animated 0–100 gauge with breakdown
- 💡 **Personalized Suggestions** — Rule-based recommendations based on your portfolio

---

## 🖥️ Screenshots

> Dashboard · Trade Page · Insights AI · Mobile View

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 15 (App Router) |
| Language | TypeScript 5.x |
| Styling | Tailwind CSS 3.x |
| Charts | Recharts 2.x |
| UI Components | shadcn/ui + Lucide React |
| State Management | Zustand |
| Auth | Firebase Authentication |
| Database | Cloud Firestore |
| AI (optional) | Google Gemini API |
| Deployment | Vercel |

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+
- A Firebase project with Auth + Firestore enabled
- (Optional) A Google Gemini API key

### Installation

```bash
# Clone the repo
git clone https://github.com/your-team/stockbreakers.git
cd stockbreakers

# Install dependencies
npm install

# Set up environment variables
cp .env.local.example .env.local
# Fill in your Firebase + Gemini keys (see below)

# Start the dev server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

### Environment Variables

Create a `.env.local` file in the root directory:

```env
# Firebase
NEXT_PUBLIC_FIREBASE_API_KEY=
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=
NEXT_PUBLIC_FIREBASE_PROJECT_ID=
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=
NEXT_PUBLIC_FIREBASE_APP_ID=

# Google Gemini (optional — falls back to mock data)
NEXT_PUBLIC_GEMINI_API_KEY=
```

---

## 📁 Project Structure

```
stockbreakers/
├── src/
│   ├── app/                  # Next.js App Router pages
│   │   ├── (auth)/           # Login & Signup
│   │   ├── dashboard/
│   │   ├── trade/
│   │   ├── watchlist/
│   │   ├── portfolio/
│   │   ├── history/
│   │   └── insights/
│   ├── components/
│   │   ├── layout/           # Sidebar, TopBar, BottomNav
│   │   ├── dashboard/        # Hero cards, charts, widgets
│   │   ├── trade/            # Stock list, detail panel, order form
│   │   ├── watchlist/        # Price cards, sparklines
│   │   ├── insights/         # Forecast, sentiment, risk gauge
│   │   └── ui/               # Shared primitives
│   ├── lib/
│   │   ├── firebase.ts
│   │   ├── mockData.ts       # 20 stock universe
│   │   ├── priceSimulator.ts # Real-time price drift
│   │   ├── portfolioUtils.ts # P&L, allocation, risk calculations
│   │   └── aiSuggestions.ts  # Rule-based suggestion engine
│   ├── store/                # Zustand stores (prices, portfolio, auth)
│   └── types/                # TypeScript interfaces
```

---

## 📐 Architecture

```
Browser (Next.js 15)
    │
    ├── Firebase Auth (Email + Google OAuth)
    ├── Cloud Firestore (users, transactions, holdings)
    └── Mock Data Layer
            └── setInterval price simulation (±0.05–1.5% every 5s)
                        │
                (Optional) Google Gemini API
                   for live news sentiment
```

---

## 🤖 AI Layer

| Feature | Method |
|---|---|
| Price Forecast | Mock trend line + Gaussian noise, rendered as dashed chart extension |
| News Sentiment | Mock JSON with Bullish/Bearish/Neutral tags; optional Gemini API |
| Risk Score | Client-side calculation: sector concentration (40%) + volatility (35%) + cash ratio (25%) |
| Suggestions | Rule-based engine evaluating portfolio composition against condition thresholds |

---

## 💾 Database Schema

**`users/{userId}`** — profile, cash balance ($50,000 default), watchlist array

**`transactions/{txId}`** — type, ticker, quantity, price, total, timestamp

**`users/{userId}/holdings/{ticker}`** — quantity, average cost, total invested

---

## 📦 Available Scripts

```bash
npm run dev        # Start development server
npm run build      # Build for production
npm run start      # Start production server
npm run lint       # Run ESLint
```

---

## 🤝 Team

Built by **Team StormBreakers** at [Hackathon Name], April 2026.

| Role | Responsibilities |
|---|---|
| Frontend Lead | Dashboard, Trade Page, Watchlist, Charts |
| Backend / Auth Lead | Firebase, Firestore, Trading Logic |
| AI / Data Lead | Mock Data, Price Simulator, Insights Page |
| Design / PM Lead | UI System, Tailwind Config, QA, Demo |

---

## 📄 License

This project was built for a hackathon. Feel free to fork and build on it.

---

*StockBreakers — Simulate. Trade. Insight. Grow.*
