# Personal Website Roadmap — Dev Bhartra

## Project Goal
Build a personal portfolio website from the ground up as a hands-on software engineering & web development learning project.

- **Primary audience:** Recruiters & engineers — must be scannable, functional, fast, and visually intentional (avoiding generic AI / shadcn tropes), while still showing personality.
- **Mobile-first:** Most traffic is expected on mobile, so fast load times (minimal JS) and mobile-first responsive design are core requirements from Day 1.
- **Long-term features:** Deep user analytics, strong personal-name SEO (`"Dev Bhartra"`), live personal data (Strava, Steam/SteamDB on free tiers), and AI features.

---

## Working Style & Collaboration Rules
When continuing this project in a new session, follow these rules:

1. **Hands-on, step-by-step learning:** Do **not** build the final product in one shot. Walk Dev through terminal commands and code changes one step at a time, explaining the *why* behind each decision.
2. **Karpathy Guidelines:**
   - **Think before coding:** State assumptions explicitly, ask clarifying questions when ambiguous, and present tradeoffs before picking an approach.
   - **Simplicity first:** Write the minimum code needed for the current phase—no speculative abstractions, premature libraries, or unrequested polish.
   - **Surgical changes:** Only touch what belongs to the current phase.
   - **Goal-driven execution:** Verify the current phase's "Done when…" check before moving on.

---

## Confirmed Decisions & Environment
- **OS:** Omarchy Linux (Arch-based, `mise` for runtime management)
- **Runtime:** Node `v26.13.1`, npm `11.20.0`
- **Repository:** `/home/devbhartra/Documents/personal-site`
- **Remote:** `git@github.com:dbhartra/personal-site.git` (`main` branch)
- **Stack:** **Astro + TypeScript**
  - *Why:* Zero client JS by default (fast mobile loads & strong Core Web Vitals), pure static HTML for SEO, first-class Cloudflare Pages/Workers adapter, hybrid rendering when we add server-side APIs (Strava, Steam, AI), and islands architecture so we only ship JS where needed.
- **Domain:** Plan to buy/use a custom domain (e.g., `devbhartra.com` / `.dev`) for SEO.
- **Analytics:** Hybrid approach — a real analytics platform (e.g., PostHog / Cloudflare Web Analytics) + custom event instrumentation built ourselves.

---

## Phases

### [x] Phase 0: Local Setup & Git Foundations
- Configured `git` (`init.defaultBranch = main`, `user.name`, `user.email`).
- Generated Ed25519 SSH key and authenticated GitHub CLI (`gh auth login`).
- Installed Node LTS via `mise`.
- Initialized repo with `.gitignore` and `README.md`, committed (`00f59e5`), and pushed to GitHub.

### [x] Phase 1: Stack & Architecture Decision
- Selected **Astro + TypeScript** after weighing tradeoffs against Next.js, SvelteKit, and plain HTML/Vite.

### [x] Phase 2: Barebones "Hello World"
- Scaffold a minimal Astro + TypeScript project inside this existing Git repo.
- Walk through and understand every generated file (`package.json`, `astro.config.mjs`, `tsconfig.json`, `src/pages/index.astro`).
- Render clean, semantic, mobile-friendly HTML displaying `"Hi, my name is Dev Bhartra."` (no fancy components, no animations, no CSS frameworks yet).
- **Done when:** Site runs cleanly on `localhost`, looks clean in mobile viewport DevTools, and is committed & pushed to `main`.

### [ ] Phase 3: Hosting on Cloudflare Pages & Web Security Fundamentals  ← **START HERE NEXT**
- Deploy the repo to Cloudflare Pages (and attach custom domain + DNS when ready).
- Learn and configure web security fundamentals: HTTPS/TLS, security headers (`Content-Security-Policy`, `Strict-Transport-Security`, `X-Content-Type-Options`, `X-Frame-Options`, `Referrer-Policy`), Cloudflare WAF/DDoS basics, and secret/env-var hygiene.
- **Done when:** Live site is accessible from mobile and other devices with verified security headers.

### [ ] Phase 4: SEO Foundations
- Semantic HTML audit, SSG/SSR verification, `<head>` meta tags, canonical URL, Open Graph / social cards, `robots.txt`, `sitemap.xml`, and JSON-LD `Person` structured data (targeted at ranking for `"Dev Bhartra"`).
- Set up Google Search Console and submit sitemap.
- **Done when:** Rich results / structured data validate cleanly and site is submitted for indexing.

### [ ] Phase 5: Analytics & User Telemetry
- Implement hybrid tracking: privacy-friendly/product analytics (e.g., PostHog / Cloudflare Web Analytics) + custom client-side instrumentation (time on page, scroll depth, section visibility via `IntersectionObserver`, outbound link clicks).
- Learn tradeoffs around ad blockers, privacy, and data accuracy.
- **Done when:** Live visits and custom section-engagement events appear in the analytics dashboard.

### [ ] Phase 6: Real Content & Continuous Deployment Loop
- Add real personal info, experience, and projects (e.g., from LinkedIn) as clean, structured content.
- Exercise the full CD workflow: feature branch → commit → PR → Cloudflare Preview URL → merge to `main` → live production deploy.
- **Done when:** Real content is live via automated Cloudflare preview & production deploys.

### [ ] Phase 7: Intentional Visual Design & Recruiter UX
- Develop a deliberate visual direction step by step (typography, spacing, color palette, hierarchy, mobile-first layout)—no generic AI/shadcn clichés.
- Optimize for recruiter scannability while keeping personality and fun.
- **Done when:** Cohesive, mobile-first, recruiter-ready design is live.

### [ ] Phase 8: Live Personal Data Integrations
- Add Cloudflare Pages Functions / Workers with caching to safely integrate free-tier APIs (Strava, Steam/SteamDB, etc.) without exposing API keys or hitting rate limits.
- **Done when:** Live personal data renders reliably on the site with server-side caching.

### [ ] Phase 9: AI Features
- Build an AI feature fitting an AI developer's portfolio (e.g., grounded Q&A over work/projects or an interactive demo).
- Add rate limiting, cost guardrails, and prompt-injection defenses.
- **Done when:** AI feature is live, responsive on mobile, and protected against abuse.
