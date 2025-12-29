# SOUL CORE Web Platform

## Full-Stack Web Application | Next.js + FastAPI

### [🔗 Live Demo: soulcore-web.vercel.app](https://soulcore-web.vercel.app)

---

## Overview

Modern, production-ready web platform built with cutting-edge technologies. Full-stack architecture with separate frontend and backend services, deployed on cloud infrastructure.

---

## System Architecture

```mermaid
flowchart TB
    subgraph CLIENT["🌐 Client"]
        BROWSER[Browser]
    end

    subgraph FRONTEND["⚡ Frontend - Vercel"]
        NEXT[Next.js 14<br/>App Router]
        SSR[Server-Side<br/>Rendering]
        STATIC[Static<br/>Assets]
    end

    subgraph BACKEND["🔧 Backend - Railway"]
        FAST[FastAPI<br/>Python 3.11]
        AUTH[Auth<br/>Middleware]
        ROUTES[API<br/>Routes]
    end

    subgraph DATA["💾 Data - Supabase"]
        PG[(PostgreSQL)]
        STORE[Storage]
        SUPA_AUTH[Auth<br/>Service]
    end

    BROWSER --> NEXT
    NEXT --> SSR
    NEXT --> STATIC
    NEXT <--> FAST
    FAST --> AUTH --> ROUTES
    ROUTES --> PG
    ROUTES --> STORE
    AUTH <--> SUPA_AUTH

    style CLIENT fill:#e3f2fd
    style FRONTEND fill:#e8f5e9
    style BACKEND fill:#fff3e0
    style DATA fill:#fce4ec
```

---

## Request Flow

```mermaid
sequenceDiagram
    participant U as User
    participant V as Vercel (CDN)
    participant N as Next.js
    participant F as FastAPI
    participant S as Supabase

    U->>V: Request page
    V->>N: Route to Next.js
    N->>N: Server-Side Render
    N->>F: API call (if needed)
    F->>S: Query database
    S-->>F: Data response
    F-->>N: JSON response
    N-->>V: Rendered HTML
    V-->>U: Complete page

    Note over V,N: Edge caching enabled
```

---

## Tech Stack

```mermaid
flowchart LR
    subgraph FRONT["Frontend"]
        NEXT2[Next.js 14]
        TS[TypeScript]
        TW[Tailwind CSS]
        SHAD[shadcn/ui]
    end

    subgraph BACK["Backend"]
        PY[Python 3.11]
        FAST2[FastAPI]
        PYD[Pydantic]
    end

    subgraph INFRA["Infrastructure"]
        VER[Vercel]
        RAIL[Railway]
        SUP[Supabase]
    end

    NEXT2 --> TS --> TW --> SHAD
    PY --> FAST2 --> PYD
    VER --> RAIL --> SUP

    style FRONT fill:#e3f2fd
    style BACK fill:#fff3e0
    style INFRA fill:#e8f5e9
```

| Layer | Technology | Purpose |
|-------|------------|---------|
| **Frontend** | Next.js 14 | React framework with SSR |
| **Styling** | Tailwind CSS | Utility-first CSS |
| **UI Components** | shadcn/ui | Accessible components |
| **Language** | TypeScript | Type safety |
| **Backend** | FastAPI | High-performance API |
| **Database** | PostgreSQL | Relational database |
| **BaaS** | Supabase | Auth + DB + Storage |
| **Frontend Host** | Vercel | Edge deployment |
| **Backend Host** | Railway | Container platform |

---

## Project Structure

```mermaid
flowchart TB
    subgraph ROOT["📁 Project Root"]
        subgraph FE["frontend/"]
            APP[app/<br/>Pages & Routes]
            COMP[components/<br/>UI Components]
            LIB[lib/<br/>Utilities]
            STYLES[styles/<br/>Global CSS]
        end

        subgraph BE["backend/"]
            MAIN[app/<br/>Main App]
            API[api/<br/>Endpoints]
            MODELS[models/<br/>Data Models]
            SERVICES[services/<br/>Business Logic]
        end

        SHARED[shared/<br/>Common Schemas]
        DOCS[docs/<br/>Documentation]
    end

    style ROOT fill:#f5f5f5
    style FE fill:#e3f2fd
    style BE fill:#fff3e0
```

---

## Key Features

```mermaid
mindmap
  root((SOUL CORE<br/>Web))
    Performance
      SSR with Next.js 14
      Edge caching
      Optimized bundles
    Security
      JWT Authentication
      CORS protection
      Input validation
    Modern UI
      Responsive design
      Dark mode support
      Accessible components
    Developer Experience
      TypeScript
      Hot reload
      API auto-docs
    Deployment
      CI/CD pipeline
      Auto-deploy on push
      Environment configs
```

---

## Deployment Pipeline

```mermaid
flowchart LR
    subgraph DEV["Development"]
        CODE[Code Push]
        GIT[GitHub]
    end

    subgraph CI["CI/CD"]
        BUILD[Build]
        TEST[Test]
        DEPLOY[Deploy]
    end

    subgraph PROD["Production"]
        VER2[Vercel<br/>Frontend]
        RAIL2[Railway<br/>Backend]
    end

    CODE --> GIT
    GIT --> BUILD --> TEST --> DEPLOY
    DEPLOY --> VER2
    DEPLOY --> RAIL2

    style DEV fill:#e3f2fd
    style CI fill:#fff3e0
    style PROD fill:#e8f5e9
```

---

## API Design

```mermaid
flowchart TB
    subgraph ENDPOINTS["API Endpoints"]
        AUTH_EP["/auth/*"<br/>Authentication]
        USER_EP["/users/*"<br/>User Management]
        DATA_EP["/data/*"<br/>Data Operations]
    end

    subgraph FEATURES["Features"]
        SWAGGER[OpenAPI/Swagger<br/>Auto Documentation]
        VALID[Pydantic<br/>Validation]
        ERR[Error<br/>Handling]
    end

    AUTH_EP & USER_EP & DATA_EP --> SWAGGER
    AUTH_EP & USER_EP & DATA_EP --> VALID
    AUTH_EP & USER_EP & DATA_EP --> ERR

    style ENDPOINTS fill:#e3f2fd
    style FEATURES fill:#e8f5e9
```

---

## Development Standards

```mermaid
flowchart LR
    TS2[TypeScript<br/>Type Safety]
    LINT[ESLint<br/>Code Quality]
    FMT[Prettier<br/>Formatting]
    COMP2[Component<br/>Architecture]
    DOC[OpenAPI<br/>Documentation]
    ENV[Environment<br/>Config]

    TS2 --> LINT --> FMT --> COMP2 --> DOC --> ENV

    style TS2 fill:#e3f2fd
    style LINT fill:#fff3e0
    style FMT fill:#e8f5e9
    style COMP2 fill:#fce4ec
    style DOC fill:#e3f2fd
    style ENV fill:#fff3e0
```

---

## Capabilities Demonstrated

- **Full-Stack Development** - Complete frontend and backend implementation
- **Modern React** - Next.js 14 with App Router and Server Components
- **API Design** - RESTful API with FastAPI and automatic documentation
- **Database Design** - PostgreSQL with proper schema design
- **Cloud Deployment** - Multi-service deployment with CI/CD
- **UI/UX** - Modern, responsive design with accessibility

---

**Technologies:** Next.js | TypeScript | FastAPI | Python | PostgreSQL | Tailwind CSS | Vercel | Railway

**Category:** Web Development | Full-Stack | Cloud Architecture

---

*This project demonstrates capability to build and deploy production-ready full-stack web applications with modern technologies.*
