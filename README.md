<p align="center">
  <img src="client/src/assets/FINAL.png" alt="PricePilot AI Logo" width="120" />
</p>

<h1 align="center">ðŸš€ PricePilot AI â€” Dynamic Pricing & Inventory Intelligence Platform</h1>

<p align="center">
  <strong>An AI-powered e-commerce pricing optimization platform that leverages machine learning, competitor analysis, demand forecasting, and conversational AI to deliver real-time pricing recommendations.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/React-19.x-61DAFB?style=flat-square&logo=react" />
  <img src="https://img.shields.io/badge/Node.js-20.x-339933?style=flat-square&logo=node.js" />
  <img src="https://img.shields.io/badge/FastAPI-0.100+-009688?style=flat-square&logo=fastapi" />
  <img src="https://img.shields.io/badge/MongoDB-7.x-47A248?style=flat-square&logo=mongodb" />
  <img src="https://img.shields.io/badge/Google%20Gemini-AI-4285F4?style=flat-square&logo=google" />
  <img src="https://img.shields.io/badge/LangChain-RAG-1C3C3C?style=flat-square&logo=langchain" />
  <img src="https://img.shields.io/badge/ChromaDB-Vector%20Store-FF6F00?style=flat-square" />
  <img src="https://img.shields.io/badge/Docker-Ready-2496ED?style=flat-square&logo=docker" />
</p>

---

## ðŸ“‹ Project Information

| Field | Details |
|-------|---------|
| **Course Name** | Project |
| **Course Code** | PRO230812 |
| **Department** | CSE (Computer Science and Engineering) |
| **Semester** | V |
| **Topic** | PricePilot AI â€“ Dynamic Pricing and Inventory Intelligence Platform |
| **Academic Year** | 2025â€“2026 |
| **Institution** | Final Year Project |

### ðŸ‘¥ Team Members

| Name | Roll No. |
|------|----------|
| **Rudra Babar** | B002 |
| **Aryan Desale** | B010 |

---

## ðŸ“– Table of Contents

- [About the Project](#-about-the-project)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Environment Variables](#-environment-variables)
- [API Endpoints](#-api-endpoints)
- [Deployment](#-deployment)
- [Screenshots](#-screenshots)
- [Architecture Diagrams](#-architecture-diagrams)
- [Research Papers & Inspiration](#-research-papers--inspiration)
- [License](#-license)

---

## ðŸŽ¯ About the Project

**PricePilot AI** is a full-stack AI-powered platform designed for e-commerce businesses to optimize their pricing strategies in real time. The platform integrates multiple data signals â€” competitor pricing, demand fluctuations, inventory levels, weather patterns, social sentiment, news analysis, and search trends â€” to generate intelligent pricing recommendations that maximize revenue and maintain competitive positioning.

Traditional pricing strategies rely on static rules and manual adjustments, which fail to adapt to rapidly changing market dynamics. PricePilot AI addresses this gap by applying **machine learning**, **time-series forecasting (Prophet/Holt-Winters)**, **Retrieval-Augmented Generation (RAG)**, and **large language models (Google Gemini)** to deliver data-driven, explainable pricing decisions.

### Problem Statement

E-commerce businesses face several pricing challenges:
- **Manual pricing** cannot scale across thousands of SKUs
- **Competitor prices** change frequently and unpredictably
- **Demand patterns** are influenced by seasonality, events, weather, and social trends
- **Inventory management** requires proactive stock-out prevention
- **Revenue optimization** needs balancing margin targets with market competitiveness
- **Decision opacity** â€” merchants don't understand _why_ a price was suggested

PricePilot AI solves these challenges with automated, intelligent, and _explainable_ pricing that adapts in real time.

---

## âœ¨ Key Features

### ðŸ¤– AI-Powered Pricing Engine
- **Binary Search Margin Optimization**: Dynamically finds the exact price point that mathematically maximizes total gross profit
- **Dynamic Price Elasticity Estimation**: Adjusts theoretical volume shifts based on composite demand trend metrics
- **LLM-Powered Explainability**: Google Gemini translates complex pricing math into plain-English insights via the `ExplainabilityPanel` component
- Automated promotion suggestions based on stock ratios and weakened demand signals

### ðŸ’¬ Conversational AI Chatbot (RAG Architecture)
- **Ephemeral Working Memory System**: Each chat session dynamically assembles System Prompt + Chat History + RAG Context into a single context window
- **Dual Vector Store RAG**: Semantic Memory (durable facts & rules) + Episodic Memory (past conversations) via ChromaDB
- **LangChain Integration**: Full RAG chain with `ChatGoogleGenerativeAI` (Gemini) as primary LLM and OpenRouter as fallback
- **Document Upload**: PDF/document context injection into conversation for intelligent Q&A
- **Background Consolidation**: Fire-and-forget episodic interaction saving for future recall

### ðŸ“Š Demand Forecasting
- **Facebook Prophet Integration**: Advanced Bayesian time-series model decomposing weekly/yearly seasonality and non-linear trend curves
- **Graceful Fallbacks**: Automatically falls back to Holt-Winters Exponential Smoothing or Moving Averages if data volume is inadequate
- 30-day forward demand prediction with statistical confidence scores
- Inventory reorder calculations derived directly from expected future depletion rates

### ðŸ·ï¸ Competitor Intelligence
- **Rainforest API Integration**: Real-time distributed web scraping for live Amazon marketplace ASIN telemetry
- **Flipkart Scraper**: BeautifulSoup-powered product price extraction from Flipkart
- **Google Trends Analysis**: Search interest trend data for demand signal enrichment
- **Weighted Analysis**: Adjusts internal pricing gravity based on competitors' actual stock availability and review ratings
- Automated price position analysis (cheapest, average, premium)

### ðŸ“° Multi-Signal Demand Intelligence
- **Weather Impact Analysis**: OpenWeatherMap integration for weather-correlated demand shifts
- **News Sentiment Scoring**: NewsAPI + NLP pipeline for real-time market sentiment from news articles
- **Social Sentiment Analysis**: Text sentiment classification for customer feedback and reviews
- Composite demand scoring combining all external signals

### ðŸ“ˆ Interactive Dashboard
- Real-time KPI cards with revenue, margins, and stock metrics
- 30-day revenue trend and order volume charts (Recharts)
- AI recommendation feed with accept/reject actions
- Alert system with severity-based prioritization (critical/high/medium/low)

### ðŸ§ª A/B Testing Framework
- Create controlled pricing experiments with variant groups
- Statistical significance tracking for pricing strategy validation
- Revenue impact measurement per test variant

### ðŸ”— Integrations Hub
- API key management for external services (Rainforest, SerpAPI, OpenWeather, NewsAPI, SendGrid)
- Connection status monitoring and health checks
- Centralized configuration UI

### ðŸ” Authentication & Security
- JWT-based authentication with secure token management
- Password reset flow (forgot password â†’ email â†’ reset token)
- Role-based access control
- Password hashing with bcrypt
- Protected API routes with middleware guards
- API rate limiting (express-rate-limit)
- NoSQL injection prevention (express-mongo-sanitize)
- XSS protection (xss-clean)
- Security headers (Helmet)
- Gzip compression

### âš¡ Performance & Reliability
- **Redis Caching**: Instantaneous dashboard metrics by caching heavy aggregations
- **Async Job Queue (BullMQ)**: Non-blocking AI recommendations and forecasting processes
- **Server-Sent Events (SSE)**: Real-time streaming for AI generation progress
- **Error Boundaries**: React ErrorBoundary components with graceful fallback UIs
- **Skeleton Loaders**: Premium loading states for better perceived performance
- **Automated Testing**: pytest (AI service) and Jest (Node server) test suites

### ðŸŽ¨ Premium UI/UX
- Dark-mode + Light-mode glassmorphism design system with theme toggle
- Smooth micro-animations and transitions
- Responsive layout with collapsible sidebar
- Gradient accent colors and floating orb backgrounds
- Professional landing page with FAQ section
- Privacy Policy and About pages

---

## ðŸ—ï¸ System Architecture

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚                           REACT CLIENT (Vite)                           â”‚
â”‚  Landing Â· Dashboard Â· Products Â· Forecasts Â· Recommendations Â· Chat    â”‚
â”‚  Competitors Â· Demand Signals Â· Alerts Â· Integrations Â· A/B Tests       â”‚
â”‚                    Tailwind CSS 4 Â· Recharts Â· Axios                    â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
                                â”‚ HTTPS / REST
                                â–¼
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚                     NODE.JS API SERVER (Express)                         â”‚
â”‚                                                                          â”‚
â”‚  Auth Â· Products Â· Competitors Â· Demand Â· Alerts Â· AI Â· Chat Â· Stream   â”‚
â”‚  A/B Tests Â· Integrations                                                â”‚
â”‚                                                                          â”‚
â”‚  Middleware: JWT Â· Rate Limiter Â· Helmet Â· XSS Â· Mongo Sanitize         â”‚
â”‚  Cron Jobs: Scheduled price checks, alert generation                    â”‚
â”‚  SSE: Real-time streaming endpoint                                      â”‚
â”œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¤
â”‚   MongoDB    â”‚         Redis / BullMQ        â”‚    External APIs          â”‚
â”‚   Atlas      â”‚     Caching Â· Job Queues      â”‚  (via AI Service)         â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”´â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
                               â”‚ HTTP (internal)
                               â–¼
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚                    PYTHON AI SERVICE (FastAPI)                            â”‚
â”‚                                                                          â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â” â”‚
â”‚  â”‚  Forecasting â”‚  â”‚   Pricing   â”‚  â”‚  LLM        â”‚  â”‚   Chatbot      â”‚ â”‚
â”‚  â”‚  (Prophet)   â”‚  â”‚  Optimizer  â”‚  â”‚  Insights   â”‚  â”‚  (RAG Agent)   â”‚ â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜ â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â” â”‚
â”‚  â”‚  Rainforest  â”‚  â”‚  Flipkart   â”‚  â”‚  News       â”‚  â”‚   Weather      â”‚ â”‚
â”‚  â”‚  Scraper     â”‚  â”‚  Scraper    â”‚  â”‚  Sentiment  â”‚  â”‚   Service      â”‚ â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜ â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â” â”‚
â”‚  â”‚  Google      â”‚  â”‚  Sentiment  â”‚  â”‚  Product    â”‚  â”‚   Data         â”‚ â”‚
â”‚  â”‚  Trends      â”‚  â”‚  Analysis   â”‚  â”‚  Generator  â”‚  â”‚   Pipeline     â”‚ â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜ â”‚
â”‚                                                                          â”‚
â”‚  Vector Store: ChromaDB (Semantic Memory + Episodic Memory)             â”‚
â”‚  LLM: Google Gemini (primary) Â· OpenRouter (fallback)                   â”‚
â”‚  RAG: LangChain Â· LangChain-Chroma Â· GoogleGenerativeAIEmbeddings      â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

### Chatbot RAG Agent Architecture

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚                  Ephemeral AI Agent Session                   â”‚
â”‚                                                               â”‚
â”‚  â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”    â”‚
â”‚  â”‚              Working Memory (Context RAM)             â”‚    â”‚
â”‚  â”‚                                                        â”‚    â”‚
â”‚  â”‚  System Prompt + Chat History + User Query             â”‚    â”‚
â”‚  â”‚       + Semantic RAG Context (facts & rules)           â”‚    â”‚
â”‚  â”‚       + Episodic RAG Context (past interactions)       â”‚    â”‚
â”‚  â”‚       + Real-time API Context (products, alerts)       â”‚    â”‚
â”‚  â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜    â”‚
â”‚                         â”‚                                     â”‚
â”‚                         â–¼                                     â”‚
â”‚              â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”                             â”‚
â”‚              â”‚   LLM Engine     â”‚                             â”‚
â”‚              â”‚  (Gemini Flash)  â”‚â”€â”€â”€â”€ fallback â”€â”€â–¶ OpenRouter â”‚
â”‚              â””â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜                             â”‚
â”‚                       â”‚                                       â”‚
â”‚                       â–¼                                       â”‚
â”‚                   AI Reply                                    â”‚
â”‚                       â”‚                                       â”‚
â”‚              â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”                             â”‚
â”‚              â”‚ Save to Episodic â”‚  (fire-and-forget)          â”‚
â”‚              â”‚     Memory       â”‚                             â”‚
â”‚              â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜                             â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
         â”‚                              â”‚
    â”Œâ”€â”€â”€â”€â–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”           â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
    â”‚  ChromaDB    â”‚           â”‚     ChromaDB        â”‚
    â”‚  Semantic    â”‚           â”‚     Episodic        â”‚
    â”‚  Memory      â”‚           â”‚     Memory          â”‚
    â”‚  (facts)     â”‚           â”‚  (past events)      â”‚
    â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜           â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

---

## ðŸ› ï¸ Tech Stack

### Frontend
| Technology | Purpose |
|-----------|---------|
| React 19 | UI framework |
| Vite 7 | Build tool & dev server |
| Tailwind CSS 4 | Utility-first styling |
| Recharts | Data visualization (charts) |
| React Router 7 | Client-side routing |
| Axios | HTTP client |
| React Hot Toast | Toast notifications |
| React Icons (Heroicons) | Icon library |

### Backend (Node.js)
| Technology | Purpose |
|-----------|---------|
| Node.js 20 | Server runtime |
| Express 4 | Web framework |
| MongoDB + Mongoose 8 | Database & ODM |
| Redis + BullMQ | In-memory caching & async job queues |
| JWT (jsonwebtoken) | Authentication tokens |
| bcryptjs | Password hashing |
| Helmet | Security headers |
| express-mongo-sanitize | NoSQL injection prevention |
| xss-clean | XSS protection |
| express-rate-limit | API rate limiting |
| node-cron | Scheduled tasks |
| Morgan + Winston | HTTP logging |
| Jest | Automated testing |

### AI Service (Python)
| Technology | Purpose |
|-----------|---------|
| Python 3.12 | Runtime |
| FastAPI | API framework |
| Facebook Prophet | Bayesian time-series forecasting |
| LangChain + LangChain-Chroma | RAG pipeline & chain orchestration |
| ChromaDB | Vector database (semantic + episodic memory) |
| Google Generative AI Embeddings | Document embedding for RAG |
| Google Gemini (ChatGoogleGenerativeAI) | Primary LLM for chatbot & insights |
| OpenRouter (ChatOpenAI) | Fallback LLM provider |
| Rainforest API | Amazon price scraping |
| BeautifulSoup4 | Flipkart web scraping |
| SciPy + Statsmodels | Statistical modeling |
| scikit-learn | ML utilities |
| Pandas / NumPy | Data computation |
| HTTPX | Async HTTP client |
| pytest + pytest-asyncio | Automated testing |

### DevOps & Infrastructure
| Technology | Purpose |
|-----------|---------|
| Docker | Containerization |
| Docker Compose | Multi-container orchestration |
| Render | Cloud deployment (Node server) |
| Vercel | Cloud deployment (React client) |

---

## ðŸ“ Project Structure

```
ecom-ai-project/
â”œâ”€â”€ client/                          # React Frontend (Vite + Tailwind CSS 4)
â”‚   â”œâ”€â”€ src/
â”‚   â”‚   â”œâ”€â”€ api/
â”‚   â”‚   â”‚   â””â”€â”€ index.js             # Centralized Axios API client
â”‚   â”‚   â”œâ”€â”€ assets/                  # Images, logos, backgrounds
â”‚   â”‚   â”œâ”€â”€ components/
â”‚   â”‚   â”‚   â”œâ”€â”€ Layout.jsx           # App shell with sidebar toggle
â”‚   â”‚   â”‚   â”œâ”€â”€ Sidebar.jsx          # Navigation sidebar (collapsible)
â”‚   â”‚   â”‚   â”œâ”€â”€ ChatWidget.jsx       # Floating AI chat widget
â”‚   â”‚   â”‚   â”œâ”€â”€ ExplainabilityPanel.jsx # AI decision explanation UI
â”‚   â”‚   â”‚   â”œâ”€â”€ ErrorBoundary.jsx    # React error boundary
â”‚   â”‚   â”‚   â”œâ”€â”€ ErrorState.jsx       # Error fallback UI
â”‚   â”‚   â”‚   â””â”€â”€ Skeleton.jsx         # Loading skeleton components
â”‚   â”‚   â”œâ”€â”€ context/
â”‚   â”‚   â”‚   â”œâ”€â”€ AuthContext.jsx      # Authentication state management
â”‚   â”‚   â”‚   â””â”€â”€ ThemeContext.jsx     # Dark/Light theme management
â”‚   â”‚   â”œâ”€â”€ pages/
â”‚   â”‚   â”‚   â”œâ”€â”€ Landing.jsx          # Public landing page with FAQ
â”‚   â”‚   â”‚   â”œâ”€â”€ Dashboard.jsx        # Main dashboard with KPIs & charts
â”‚   â”‚   â”‚   â”œâ”€â”€ Products.jsx         # Product CRUD management
â”‚   â”‚   â”‚   â”œâ”€â”€ Competitors.jsx      # Competitor price tracking
â”‚   â”‚   â”‚   â”œâ”€â”€ DemandSignals.jsx    # Demand signal monitoring
â”‚   â”‚   â”‚   â”œâ”€â”€ Forecasts.jsx        # AI demand forecasting
â”‚   â”‚   â”‚   â”œâ”€â”€ Recommendations.jsx  # AI pricing recommendations
â”‚   â”‚   â”‚   â”œâ”€â”€ Chat.jsx             # Full-page AI chatbot interface
â”‚   â”‚   â”‚   â”œâ”€â”€ Alerts.jsx           # Alert management
â”‚   â”‚   â”‚   â”œâ”€â”€ Integrations.jsx     # API integrations hub
â”‚   â”‚   â”‚   â”œâ”€â”€ About.jsx            # About page
â”‚   â”‚   â”‚   â”œâ”€â”€ Docs.jsx             # Documentation page
â”‚   â”‚   â”‚   â”œâ”€â”€ PrivacyPolicy.jsx    # Privacy policy
â”‚   â”‚   â”‚   â”œâ”€â”€ Login.jsx            # User login
â”‚   â”‚   â”‚   â”œâ”€â”€ Register.jsx         # User registration
â”‚   â”‚   â”‚   â”œâ”€â”€ ForgotPassword.jsx   # Password recovery
â”‚   â”‚   â”‚   â””â”€â”€ ResetPassword.jsx    # Password reset
â”‚   â”‚   â”œâ”€â”€ App.jsx                  # Root component with routing
â”‚   â”‚   â”œâ”€â”€ index.css                # Global styles & design system
â”‚   â”‚   â””â”€â”€ main.jsx                 # React entry point
â”‚   â”œâ”€â”€ index.html
â”‚   â”œâ”€â”€ vite.config.js
â”‚   â””â”€â”€ package.json
â”‚
â”œâ”€â”€ server/                          # Node.js Backend (Express)
â”‚   â”œâ”€â”€ config/
â”‚   â”‚   â”œâ”€â”€ db.js                    # MongoDB connection
â”‚   â”‚   â””â”€â”€ logger.js                # Winston logger configuration
â”‚   â”œâ”€â”€ controllers/
â”‚   â”‚   â”œâ”€â”€ aiController.js          # AI recommendation & forecast logic
â”‚   â”‚   â”œâ”€â”€ authController.js        # Login, register, password reset
â”‚   â”‚   â”œâ”€â”€ chatController.js        # Chat CRUD & AI message relay
â”‚   â”‚   â”œâ”€â”€ productController.js     # Product management
â”‚   â”‚   â”œâ”€â”€ competitorController.js  # Competitor tracking
â”‚   â”‚   â”œâ”€â”€ demandController.js      # Demand signal management
â”‚   â”‚   â”œâ”€â”€ alertController.js       # Alert CRUD
â”‚   â”‚   â”œâ”€â”€ abTestController.js      # A/B test management
â”‚   â”‚   â””â”€â”€ integrationController.js # External API integrations
â”‚   â”œâ”€â”€ middleware/
â”‚   â”‚   â”œâ”€â”€ auth.js                  # JWT authentication middleware
â”‚   â”‚   â””â”€â”€ rateLimiter.js           # API rate limiting
â”‚   â”œâ”€â”€ models/
â”‚   â”‚   â”œâ”€â”€ User.js                  # User schema
â”‚   â”‚   â”œâ”€â”€ Product.js               # Product schema
â”‚   â”‚   â”œâ”€â”€ Chat.js                  # Chat conversation schema
â”‚   â”‚   â”œâ”€â”€ CompetitorPrice.js       # Competitor price schema
â”‚   â”‚   â”œâ”€â”€ DemandSignal.js          # Demand signal schema
â”‚   â”‚   â”œâ”€â”€ PricingRecommendation.js # AI recommendation schema
â”‚   â”‚   â”œâ”€â”€ InventoryForecast.js     # Forecast schema
â”‚   â”‚   â”œâ”€â”€ Alert.js                 # Alert schema
â”‚   â”‚   â”œâ”€â”€ ABTest.js                # A/B test schema
â”‚   â”‚   â”œâ”€â”€ FeedbackLog.js           # User feedback schema
â”‚   â”‚   â””â”€â”€ Integration.js           # Integration config schema
â”‚   â”œâ”€â”€ routes/                      # API route definitions
â”‚   â”œâ”€â”€ cron/                        # Scheduled jobs (price checks, alerts)
â”‚   â”œâ”€â”€ seed/                        # Database seeding scripts
â”‚   â”œâ”€â”€ services/                    # External service integrations
â”‚   â”œâ”€â”€ tests/                       # Jest test suites
â”‚   â”œâ”€â”€ server.js                    # Express app entry point
â”‚   â””â”€â”€ package.json
â”‚
â”œâ”€â”€ ai-service/                      # Python AI Microservice (FastAPI)
â”‚   â”œâ”€â”€ routes/
â”‚   â”‚   â”œâ”€â”€ forecast.py              # Demand forecasting endpoint
â”‚   â”‚   â”œâ”€â”€ optimize.py              # Price optimization endpoint
â”‚   â”‚   â”œâ”€â”€ insights.py              # LLM insight generation
â”‚   â”‚   â”œâ”€â”€ chat.py                  # RAG chatbot endpoint
â”‚   â”‚   â”œâ”€â”€ scraper.py               # Competitor scraping endpoint
â”‚   â”‚   â”œâ”€â”€ sentiment.py             # Sentiment analysis endpoint
â”‚   â”‚   â”œâ”€â”€ product_gen.py           # AI product generation
â”‚   â”‚   â”œâ”€â”€ data_pipeline.py         # Data ingestion pipeline
â”‚   â”‚   â””â”€â”€ retrain.py               # ML model retraining
â”‚   â”œâ”€â”€ services/
â”‚   â”‚   â”œâ”€â”€ chatbot.py               # RAG chatbot with WorkingMemory
â”‚   â”‚   â”œâ”€â”€ vector_store.py          # ChromaDB vector store management
â”‚   â”‚   â”œâ”€â”€ forecasting.py           # Prophet/Holt-Winters models
â”‚   â”‚   â”œâ”€â”€ pricing.py               # Multi-factor pricing algorithm
â”‚   â”‚   â”œâ”€â”€ llm_insights.py          # Google Gemini integration
â”‚   â”‚   â”œâ”€â”€ elasticity_model.py      # Price elasticity estimation
â”‚   â”‚   â”œâ”€â”€ rainforest.py            # Amazon scraping (Rainforest API)
â”‚   â”‚   â”œâ”€â”€ flipkart_scraper.py      # Flipkart price scraping
â”‚   â”‚   â”œâ”€â”€ google_trends.py         # Google Trends data
â”‚   â”‚   â”œâ”€â”€ weather.py               # OpenWeatherMap integration
â”‚   â”‚   â”œâ”€â”€ news_sentiment.py        # News sentiment analysis
â”‚   â”‚   â”œâ”€â”€ sentiment.py             # Text sentiment classification
â”‚   â”‚   â”œâ”€â”€ product_gen.py           # AI product content generation
â”‚   â”‚   â””â”€â”€ data_pipeline.py         # Data pipeline orchestration
â”‚   â”œâ”€â”€ models/                      # ML model artifacts & ChromaDB
â”‚   â”œâ”€â”€ tests/                       # pytest test suites
â”‚   â”œâ”€â”€ main.py                      # FastAPI app entry point
â”‚   â””â”€â”€ requirements.txt             # Python dependencies
â”‚
â”œâ”€â”€ docs/                            # Documentation
â”‚   â”œâ”€â”€ architecture/                # Architecture design documents
â”‚   â””â”€â”€ agents/                      # Agent/skill documentation
â”‚
â”œâ”€â”€ screenshots/                     # UI screenshots for documentation
â”œâ”€â”€ docker-compose.yml               # Multi-container Docker setup
â”œâ”€â”€ Dockerfile                       # Node server + React client build
â”œâ”€â”€ Dockerfile.ai                    # Python AI service container
â”œâ”€â”€ render.yaml                      # Render deployment config
â”œâ”€â”€ .env.example                     # Environment variable template
â”œâ”€â”€ .gitignore
â””â”€â”€ README.md                        # This file
```

---

## ðŸš€ Getting Started

### Prerequisites

- **Node.js** â‰¥ 18.x ([Download](https://nodejs.org/))
- **Python** â‰¥ 3.9 ([Download](https://www.python.org/))
- **MongoDB** (local or [MongoDB Atlas](https://www.mongodb.com/atlas))
- **Google Gemini API Key** ([Get one](https://makersuite.google.com/app/apikey))

### 1. Clone the Repository

```bash
git clone https://github.com/rb-369/Price-Pilot-Ai.git
cd Price-Pilot-Ai
```

### 2. Set Up Environment Variables

```bash
cp .env.example .env
```

Edit `.env` with your values:
```env
# Server
MONGODB_URI=mongodb://<username>:<password>@<host>/<database>
JWT_SECRET=your_strong_secret_key
PORT=5000

# AI Service
AI_SERVICE_URL=http://localhost:8000
LLM_API_KEY=your_google_gemini_api_key
OPENROUTER_API_KEY=your_openrouter_key      # Optional fallback

# Client
VITE_API_URL=http://localhost:5000/api

# External APIs (Optional)
RAINFOREST_API_KEY=your_rainforest_key
SERPAPI_KEY=your_serpapi_key
OPENWEATHER_API_KEY=your_openweather_key
NEWSAPI_KEY=your_newsapi_key
SENDGRID_API_KEY=your_sendgrid_key
```

### 3. Install Dependencies

```bash
# Server
cd server && npm install

# Client
cd ../client && npm install

# AI Service
cd ../ai-service
pip install -r requirements.txt
```

### 4. Seed the Database (Optional)

```bash
cd server
npm run seed
```

### 5. Start All Services

Open three terminal windows:

```bash
# Terminal 1 â€” Backend API
cd server && npm run dev

# Terminal 2 â€” React Frontend
cd client && npm run dev

# Terminal 3 â€” AI Service
cd ai-service && uvicorn main:app --reload --port 8000
```

The app will be available at:
- **Client**: http://localhost:5173
- **API Server**: http://localhost:5000
- **AI Service**: http://localhost:8000 (Swagger docs at `/docs`)

---

## ðŸ” Environment Variables

| Variable | Description | Required |
|---------|-------------|----------|
| `MONGODB_URI` | MongoDB connection string | âœ… |
| `JWT_SECRET` | Secret key for JWT signing | âœ… |
| `PORT` | Server port (default: 5000) | âŒ |
| `AI_SERVICE_URL` | AI microservice URL | âœ… |
| `LLM_API_KEY` | Google Gemini API key | âœ… |
| `OPENROUTER_API_KEY` | OpenRouter fallback LLM key | âŒ |
| `VITE_API_URL` | Client-side API base URL | âŒ |
| `RAINFOREST_API_KEY` | Amazon price scraping API | âŒ |
| `SERPAPI_KEY` | Google Trends data API | âŒ |
| `OPENWEATHER_API_KEY` | Weather data API | âŒ |
| `NEWSAPI_KEY` | News sentiment data API | âŒ |
| `SENDGRID_API_KEY` | Email notifications | âŒ |
| `CLIENT_URL` | Allowed CORS origin in production | âŒ |
| `NODE_ENV` | Environment (`development` / `production`) | âŒ |

---

## ðŸ“¡ API Endpoints

### Node.js Server (`/api`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | User registration |
| POST | `/api/auth/login` | User login (returns JWT) |
| POST | `/api/auth/forgot-password` | Password recovery email |
| POST | `/api/auth/reset-password` | Reset password with token |
| GET | `/api/products` | List user's products |
| POST | `/api/products` | Create product |
| PUT | `/api/products/:id` | Update product |
| DELETE | `/api/products/:id` | Delete product |
| GET | `/api/competitor-prices` | Competitor price data |
| GET | `/api/demand-signals` | Demand signal data |
| GET | `/api/alerts` | User alerts |
| POST | `/api/ai/recommend` | Generate AI pricing recommendations |
| POST | `/api/ai/forecast` | Run demand forecasting |
| GET | `/api/chats` | List chat conversations |
| POST | `/api/chats` | Create new chat |
| POST | `/api/chats/:id/message` | Send message to chatbot |
| DELETE | `/api/chats/:id` | Delete chat |
| GET | `/api/ab-tests` | List A/B tests |
| GET | `/api/integrations` | Integration configurations |
| GET | `/api/stream/recommendations` | SSE stream for AI generation |
| GET | `/api/health` | Health check |

### AI Service (`/api`)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/forecast` | Prophet/Holt-Winters forecasting |
| POST | `/api/optimize` | Multi-factor price optimization |
| POST | `/api/insights` | LLM insight generation (Gemini) |
| POST | `/api/chat` | RAG chatbot (LangChain + ChromaDB) |
| POST | `/api/ingest` | Ingest data into ChromaDB |
| POST | `/api/scrape/amazon` | Amazon price scraping |
| POST | `/api/scrape/flipkart` | Flipkart price scraping |
| POST | `/api/sentiment` | Text sentiment analysis |
| POST | `/api/product-gen` | AI product content generation |
| POST | `/api/retrain` | ML model retraining |
| POST | `/api/pipeline/run` | Data pipeline execution |

---

## ðŸ³ Deployment

### Docker Compose (Recommended)

```bash
# Build and start all services
docker-compose up -d --build

# View logs
docker-compose logs -f

# Stop services
docker-compose down
```

This starts:
- **MongoDB** on port 27017
- **Redis** on port 6379 (caching & BullMQ)
- **API Server** on port 5000 (with built React client)
- **AI Service** on port 8000

### Cloud Deployment

| Component | Platform | Method |
|-----------|----------|--------|
| **React Client** | Vercel | `vercel deploy` from `/client` |
| **Node Server** | Render | Web Service with `render.yaml` |
| **AI Service** | Render | Separate service with `Dockerfile.ai` |
| **MongoDB** | MongoDB Atlas | Cloud-managed cluster |

### Live URLs
- **Client**: https://price-pilot-ai-369.vercel.app
- **Server**: Deployed on Render

---

## ðŸ“¸ Screenshots

> _Run the application locally to see the premium glassmorphism UI with dark/light mode, animated dashboard, and interactive charts._

### Pages Overview

**Dashboard** â€” KPI cards, revenue trends, order charts, AI recommendations feed
![Dashboard](screenshots/dashboard.png)

**Products** â€” CRUD table with inline editing and stock management
![Products Page](screenshots/Products%20Page.png)

**Competitors** â€” Track competitor prices with automated scraping
![Competitors View 1](screenshots/Competitors1.png)
![Competitors View 2](screenshots/Competitors2.png)

**Demand Signals** â€” Composite demand scoring with trend visualization
![Demand Signals 1](screenshots/Demand%20Signals1.png)
![Demand Signals 2](screenshots/Demand%20Signals2.png)

**Forecasts** â€” 30-day demand predictions with confidence intervals
![Inventory Forecasts](screenshots/Inventory%20Forecasts.png)

**AI Recommendations** â€” Accept/reject pricing suggestions with LLM explanations
![AI Recommendations](screenshots/AI%20Recommendations.png)

**Alerts** â€” Severity-based alert inbox with mark-as-read functionality
![Alerts](screenshots/Alerts.png)

---

## ðŸ“ Architecture Diagrams

### 1. System Architecture Diagram (High-Level 3-Tier)

![System Architecture](client/public/diagrams/Architecture.png)

The system architecture follows a **three-tier microservices pattern** with clear separation of concerns:

- **Layer 1 â€” Frontend (React Client):** Built with React 19, Vite, and Tailwind CSS 4, the SPA delivers 11 feature pages (Landing, Dashboard, Products, Competitors, Demand Signals, Forecasts, AI Recommendations, AI Chatbot, Alerts, Integrations, A/B Tests). Recharts powers all data visualizations, while Axios handles HTTP communication with the backend.

- **Layer 2 â€” Backend (Node.js API Server):** The Express.js server exposes 10 route groups (Auth, Products, Competitors, Demand, Alerts, AI, Chat, Stream/SSE, A/B Tests, Integrations) protected by a middleware stack of JWT Auth, Rate Limiter, XSS Protection, and Mongo Sanitize. MongoDB Atlas stores all 11 collections, Redis + BullMQ handles caching and async job queues, and a Cron Scheduler runs periodic price checks and alert generation.

- **Layer 3 â€” AI Microservice (Python FastAPI):** The intelligence layer runs 12 service modules â€” Forecasting (Prophet), Pricing Optimizer, LLM Insights (Gemini), RAG Chatbot, Rainforest Scraper (Amazon), Flipkart Scraper, Google Trends, Weather Service, News Sentiment, Sentiment Analysis, Product Generator, and Data Pipeline with Model Retraining. ChromaDB provides dual vector stores for Semantic Memory (long-term knowledge) and Episodic Memory (conversation events).

- **External Services:** Seven third-party APIs power the intelligence pipeline â€” Google Gemini and OpenRouter for LLM capabilities, Rainforest API for Amazon data, OpenWeatherMap for weather impact, NewsAPI for sentiment, SerpAPI for Google Trends, and SendGrid for email notifications.

---

### 2. Data Flow Diagram (DFD â€” Level 1)

![Data Flow Diagram](client/public/diagrams/Data%20Flow%20Diagram.png)

The Level 1 DFD illustrates how data moves through the platform across **8 core processes** and **7 data stores**:

1. **User Authentication** â€” Handles login/register flows, reads and writes to the User Store (D1).
2. **Product Management** â€” Processes CRUD operations from the merchant, persists to the Product Store (D2).
3. **Competitor Data Collection** â€” Pulls live pricing from Amazon (via Rainforest API) and Flipkart (via BeautifulSoup), storing scraped prices in the Competitor Price Store (D3).
4. **Demand Signal Aggregation** â€” Ingests trend data from Google Trends, weather data from OpenWeatherMap, news articles from NewsAPI, and sentiment scores from Process 8. Computes a composite demand score and writes to the Demand Signal Store (D4).
5. **AI Forecasting & Pricing Optimization** â€” Reads product data, competitor prices, and demand signals. Runs Prophet/Holt-Winters forecasting and binary search pricing optimization. Stores results in the Forecast & Recommendation Store (D5).
6. **AI Chat & Insights (LLM)** â€” Receives user chat messages, retrieves context from the Chat History Store (D6), sends assembled prompts to Google Gemini, and returns LLM-powered responses and insights.
7. **Alert & Report Generation** â€” Monitors inventory levels, price changes, and demand drops. Generates severity-tagged alerts delivered in-app and via SendGrid email.
8. **Sentiment Analysis** â€” Processes news articles through NLP pipelines, stores results in the Sentiment Store (D7), and feeds scores back to Demand Signal Aggregation.

---

### 3. RAG Chatbot Architecture (Ephemeral AI Agent Session)

![Chatbot Architecture](client/public/diagrams/Chatbot_architecture.png)

The chatbot implements an **Ephemeral AI Agent Session** architecture where everything inside the session boundary is constructed dynamically per request:

- **Working Memory (Context RAM):** The central assembly point that combines the System Prompt, Current Chat History, and User Prompt into a single context window. RAG-retrieved context from Semantic and Episodic memories is injected here before LLM invocation.

- **Three Memory Systems:**
  - **Procedural Memory** â€” Contains skill files and step-by-step instructions (how to act, pricing strategies, SOPs)
  - **Semantic Memory (ChromaDB Vector Store)** â€” Stores durable facts, user profile data, product/policy/FAQ knowledge, retrieved via top-k similarity search
  - **Episodic Memory (ChromaDB Vector Store)** â€” Stores dated events, past chat history, conversations, and feedback, also retrieved via RAG

- **LLM Q&A Agent:** Takes the fully assembled Working Memory and generates a Reply using Google Gemini (primary) or OpenRouter (fallback). After generating a response, the interaction is saved to Episodic Memory for future recall.

- **Background Consolidation:** A Summarizer Agent (using cheaper models) activates after N new chats or at end of session. It reads recent Episodic Memory, extracts durable facts, and distills them into Semantic Memory â€” keeping context relevant without bloating the episodic store.

- **Tools & Safety Layer:** Includes web/internal search, API calls, calculations, and email/notification capabilities, guarded by content moderation, PII/data protection, jailbreak detection, and policy enforcement.

---

### 4. Component Diagram (Full-Stack)

![Component Diagram](client/public/diagrams/Component_diagram.png)

The UML Component Diagram shows how all software components interact across the three tiers:

- **React Client** â€” Contains 6 component groups: UI Components, Pages (Dashboard, Products, etc.), State Management (Context API for Auth and Theme), Recharts (chart visualizations), Axios (HTTP client), and React Router (routing). Communicates with the backend via HTTP/REST.

- **Node.js API Server** â€” Houses 10 modules: Auth (JWT), Products, Competitors, Demand Signals, Alerts, AI (Insights/Forecast/Recommendations), Chat (CRUD + AI Relay), Stream (SSE), A/B Tests, and Integrations. Connected to MongoDB Atlas (11 collections via Mongoose ODM), Redis + BullMQ (caching and job queues), and a Cron Scheduler for background jobs.

- **AI Microservice (FastAPI + LangChain)** â€” Contains 12 specialized service modules arranged in a grid: Forecasting (Prophet/Holt-Winters), Pricing Optimizer (Binary Search + Elasticity), LLM Insights (Gemini), RAG Chatbot (Working Memory), Rainforest Scraper (Amazon), Flipkart Scraper (BeautifulSoup), Google Trends (SerpAPI), Weather Service (OpenWeatherMap), News Sentiment (NewsAPI + NLP), Sentiment Analysis (NLP), Product Generator (LLM + Rules), and Data Pipeline & Model Retraining. Connects to two ChromaDB vector stores â€” Semantic Memory (Facts & Rules) and Episodic Memory (Past Events).

- **External Services** â€” Seven third-party integrations shown on the right: Google Gemini API (LLM Provider), OpenRouter API (Fallback LLM), Rainforest API (Amazon Data), OpenWeatherMap API (Weather Data), NewsAPI (News & Articles), SerpAPI (Google Trends), and SendGrid (Email Service).

---

### 5. Sequence Diagram (Login â†’ Dashboard â†’ Forecast Flow)

![Sequence Diagram](client/public/diagrams/Sequence_diagram.png)

The sequence diagram traces a **complete user journey** across all system participants â€” from login to dashboard rendering â€” in 20 numbered steps:

**Authentication Flow (Steps 1â€“5):**
The Merchant sends login credentials â†’ React Client forwards `POST /api/auth/login` to the Node.js server â†’ Server validates credentials against MongoDB â†’ User data is returned â†’ JWT token is issued back to the client.

**Dashboard Data Flow (Steps 6â€“11):**
Merchant requests the dashboard â†’ `GET /api/dashboard` is sent â†’ Server checks Redis cache â†’ On cache miss, data is fetched from MongoDB â†’ Aggregated KPI data (revenue, orders, stock metrics) is returned from the database.

**AI Forecasting Flow (Steps 12â€“16):**
Server sends a demand forecast request to the FastAPI AI Microservice â†’ Prophet/Holt-Winters forecasting model runs â†’ (Optional) LLM API is called for plain-English insights on the forecast â†’ Gemini returns the insight text â†’ Forecast results + insights are sent back to the Node.js server.

**Caching & Response (Steps 17â€“20):**
The computed results are cached in Redis for future requests â†’ Cache confirmation is received â†’ Complete dashboard data (charts, metrics, forecasts) is returned to the React Client â†’ The dashboard renders with real-time KPIs, trend charts, and AI-generated insights.


## ðŸ“š Research Papers & Inspiration

### Dynamic Pricing & Revenue Optimization

1. **"Dynamic Pricing in E-Commerce: A Survey"**
   - Authors: M. den Boer
   - Published: *European Journal of Operational Research*, 2015
   - DOI: [10.1016/j.ejor.2015.07.024](https://doi.org/10.1016/j.ejor.2015.07.024)
   - Key Contribution: Comprehensive survey of dynamic pricing models in online retail

2. **"Personalized Dynamic Pricing with Machine Learning"**
   - Authors: N. C. Pereira, et al.
   - Published: *arXiv*, 2023
   - Link: [arxiv.org/abs/2312.10738](https://arxiv.org/abs/2312.10738)
   - Key Contribution: ML-based personalized pricing achieving 8-12% revenue uplift

3. **"Competitive Dynamic Pricing with Reinforcement Learning"**
   - Authors: A. Kastius, R. Schlosser
   - Published: *Journal of Revenue and Pricing Management*, 2022
   - DOI: [10.1057/s41272-021-00285-3](https://doi.org/10.1057/s41272-021-00285-3)
   - Key Contribution: Multi-agent RL models for competitive marketplace pricing

### Demand Forecasting

4. **"Forecasting at Scale" (Facebook Prophet)**
   - Authors: S. J. Taylor, B. Letham
   - Published: *The American Statistician*, 2018
   - DOI: [10.1080/00031305.2017.1380080](https://doi.org/10.1080/00031305.2017.1380080)
   - Key Contribution: Decomposable time-series model handling seasonality at scale

5. **"Deep Learning for Time Series Forecasting: A Survey"**
   - Authors: B. Lim, S. Zohren
   - Published: *Philosophical Transactions of the Royal Society A*, 2021
   - DOI: [10.1098/rsta.2020.0209](https://doi.org/10.1098/rsta.2020.0209)
   - Key Contribution: Overview of LSTM and Transformer approaches for temporal data

### AI & LLM in E-Commerce

6. **"Large Language Models for E-Commerce: A Survey"**
   - Authors: Y. Li, et al.
   - Published: *arXiv*, 2024
   - Link: [arxiv.org/abs/2312.11364](https://arxiv.org/abs/2312.11364)
   - Key Contribution: LLM applications in product descriptions, recommendations, and customer insights

7. **"Competitor Price Monitoring Using Web Scraping and Machine Learning"**
   - Authors: R. Gupta, S. Sharma
   - Published: *International Journal of Computer Applications*, 2020
   - Key Contribution: Automated competitor price tracking methodology

### Inventory Optimization

8. **"Inventory Management with Machine Learning: A Review"**
   - Authors: E. Punia, S. Nikolopoulos, et al.
   - Published: *International Journal of Production Research*, 2020
   - DOI: [10.1080/00207543.2019.1693637](https://doi.org/10.1080/00207543.2019.1693637)
   - Key Contribution: ML-driven inventory policies outperforming traditional statistical methods

### Retrieval-Augmented Generation (RAG)

9. **"Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks"**
   - Authors: P. Lewis, et al.
   - Published: *NeurIPS*, 2020
   - Link: [arxiv.org/abs/2005.11401](https://arxiv.org/abs/2005.11401)
   - Key Contribution: Foundational RAG architecture combining retrieval with generation for factual accuracy

---

## ðŸ“„ License

This project is developed as part of the **Final Year Project (Course: PRO230812)** curriculum in the Department of Computer Science and Engineering. For educational purposes only.

---

<p align="center">
  Developed with â¤ï¸ by <strong>Rudra Babar (B002)</strong> & <strong>Aryan Desale (B010)</strong>
</p>
<p align="center">
  <a href="https://github.com/rb-369/Price-Pilot-Ai">GitHub Repository</a> Â· <a href="https://price-pilot-ai-369.vercel.app">Live Demo</a>
</p>
