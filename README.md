# Next.js — Reference Implementations

TypeScript fullstack developer learning modern Next.js patterns through deliberate practice. These repositories explore Next.js 16 App Router features progressively — each POC forks the previous one and adds 1-2 new concepts.

They are proof-of-concept implementations built for learning and portfolio, not production systems. The goal is to understand each pattern in isolation and have working references.

All POCs use the same Weather Dashboard concept, evolving from basic SSR to advanced routing, optimization, auth, and database integration.

**Framework:** Next.js 16 App Router · React 19  
**Deployment:** Cloud Run (GCP) · Docker containers

---

## Projects

### [nextjs-ssr-basics](https://github.com/pawel-janus/nextjs-ssr-basics)

Simple weather application demonstrating Server-Side Rendering (SSR) with Next.js 16 App Router. Hardcoded city (Warsaw), async Server Components, automatic loading states with Suspense, and error boundaries.

**Patterns:** Server Components (async fetch) · Suspense boundaries · error.tsx · layout.tsx · metadata · Tailwind v4 · Docker multi-stage build

`TypeScript` `Next.js 16` `React 19` `Tailwind v4` `Cloud Run` `Docker`

---

### [nextjs-interactive-weather](https://github.com/pawel-janus/nextjs-interactive-weather)

Weather application demonstrating Client Components, API Routes, and client-side interactivity. City selector with search params (`/?city=warsaw`), recent searches stored in memory, Zod validation for API responses.

**Patterns:** Client Components ('use client') · useState/useEffect · API Routes (GET/POST) · useRouter · useSearchParams · Zod validation · in-memory state

`TypeScript` `Next.js 16` `React 19` `Zod` `Cloud Run`

---

### [nextjs-dynamic-routes](https://github.com/pawel-janus/nextjs-dynamic-routes)

Weather application demonstrating dynamic routes, loading states, error boundaries, and shared server-side services. URLs changed from query params to proper routes (`/weather/warsaw`). Shared `weatherService.ts` for server-side data fetching.

**Patterns:** Dynamic routes (`[city]`) · loading.tsx · not-found.tsx · generateMetadata (SEO) · server-side services (not public API) · basePath config

`TypeScript` `Next.js 16` `React 19` `Zod` `Cloud Run`

---

### [nextjs-server-actions](https://github.com/pawel-janus/nextjs-server-actions)

Weather application demonstrating Server Actions and progressive enhancement. Replaced API Route with Server Actions for saving recent cities. Form works without JavaScript enabled.

**Patterns:** Server Actions ('use server') · useActionState (React 19) · useFormStatus · progressive enhancement · FormData handling · no API route boilerplate

`TypeScript` `Next.js 16` `React 19` `Cloud Run`

---

### [nextjs-isr-ssg](https://github.com/pawel-janus/nextjs-isr-ssg)

Weather application demonstrating Incremental Static Regeneration (ISR), Static Site Generation (SSG), time-based revalidation, and cache strategies. Popular cities pre-rendered at build time, revalidated every hour. Kebab-case URL slugs (new-york).

**Patterns:** ISR (revalidate) · generateStaticParams (pre-render popular cities) · time-based cache invalidation · force-cache vs no-store · kebab-case URL normalization

`TypeScript` `Next.js 16` `React 19` `Cloud Run`

---

### [nextjs-route-groups](https://github.com/pawel-janus/nextjs-route-groups)

Weather application demonstrating Route Groups, different layouts per section, code organization without URL changes, and nested layout patterns. Homepage uses centered hero layout, weather pages use sticky search bar layout.

**Patterns:** Route Groups (`(folder)`) · per-group layouts · nested layouts · code organization without URL impact · shared loading/error states per group

`TypeScript` `Next.js 16` `React 19` `Cloud Run`

---

### nextjs-optimizations *(skipped)*

Weather application demonstrating image optimization, script loading strategies, bundle analysis, and Edge Runtime.

*Skipped: Low priority for learning — patterns well-documented in Next.js docs, can reference when needed. Focus on auth and database integration instead.*

**Patterns:** next/image (lazy loading, WebP) · next/script (analytics) · @next/bundle-analyzer · Edge Runtime · streaming responses

`TypeScript` `Next.js 16` `React 19` `Cloud Run`

---

### nextjs-advanced-routing *(skipped)*

Weather application demonstrating Parallel Routes and Intercepting Routes.

*Skipped: Niche patterns rarely used in practice — focus on more common production patterns (auth, database) instead.*

**Patterns:** Parallel Routes (`@folder`) · Intercepting Routes (`(.)folder`) · modal in URL · soft vs hard navigation · complex dashboards

`TypeScript` `Next.js 16` `React 19` `Cloud Run`

---

### nextjs-auth-middleware *(next)*

Weather application demonstrating NextAuth.js integration, middleware for protected routes, OAuth providers, and session management. Google OAuth login, protected `/dashboard`, public `/weather/[city]`.

**Patterns:** NextAuth.js · middleware.ts (route protection) · OAuth (Google) · session management · protected routes · JWT tokens

`TypeScript` `Next.js 16` `React 19` `NextAuth` `Cloud Run`

---

### nextjs-weather-db *(planned)*

Weather application demonstrating Firestore integration, Server Components with database queries, Server Actions for mutations, and optimistic updates. Persistent recent searches and user favorites per authenticated user. Integrates Firestore patterns from GCP POC #1.

**Patterns:** Firestore integration · Server Components + DB queries · Server Actions + mutations · revalidatePath · optimistic updates (useOptimistic) · user-specific data

`TypeScript` `Next.js 16` `React 19` `Firestore` `NextAuth` `Cloud Run`

---

### nextjs-multi-provider-auth *(planned)*

Weather application demonstrating multi-provider OAuth (Google, GitHub, Facebook) with provider-specific data and business logic. Provider info saved to Firestore, different feature limits per provider (GitHub: unlimited favorites, others: max 5).

**Patterns:** Multi-provider OAuth · Provider-specific data persistence · Provider-based business logic · Account linking · Different avatars per provider

`TypeScript` `Next.js 16` `React 19` `Firestore` `NextAuth` `Cloud Run`

---

> These implementations prioritize pattern clarity over production completeness. Error handling, observability, and scalability are simplified or omitted where they would obscure the core pattern being explored.
