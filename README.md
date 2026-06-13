# 🗂️ dev-journey

A living record of everything I've built, what I learned from each project, and what I'm working towards. Updated as I go.

> First-year BTech CSE (AIML) @ 2025–2029. Building for real startups. Exploring everything.

---

## 📍 where I'm at

I can build and ship full-stack web apps for real clients. My goal isn't to "finish" web dev — it's to stay good enough to deliver, while I explore DSA, AI/ML, and systems more seriously.

---

## target - Finish DSA and Webdev course these holidays (by 30th July 2026)

Finish the Sigma 8.0 course at least once by this July ending (9th July 2026 marks one year of the course). Do it again to finish placement prep by oct 2027- more than an year to revise

[]Webdev
[]DSA in C++
[]DSA in Java
[]5-6 Webdev projects
[]DSA sheet + videos from the course
[]Aptitude prep

---

## 🏗️ projects

### Uncanned — Startup Campaign Website `2026`
**Stack:** Next.js · TypeScript · Tailwind CSS · Google Sheets (backend) · Google Apps Script · Razorpay · Brevo · AiSensy · Zoho Books · NimbusPost · Vercel

**Live:** [uncanned.in](https://uncanned.in) · [whatsyourun.xyz](https://whatsyourun.xyz)

Real client work. Uncanned is a prebiotic soda startup running their first 500-taster pilot. Built their campaign website from scratch — the site is the entire top-of-funnel for their launch.

**What I actually built:**
- Campaign landing page with strong UI — got publicly praised by other founders in the F&B space
- Early access form + pilot sign-up form feeding into Google Sheets as a lightweight backend
- Razorpay payment integration for pilot orders
- Daily email outreach via Brevo — custom templates, manual sends to segmented lists
- WhatsApp outreach via AiSensy — daily messages to signups
- Zoho Books integration for invoicing, NimbusPost for delivery tracking

**What I actually learned:**
- Google Sheets as a scrappy startup backend — Apps Script to read/write form data, trigger actions
- Third-party integration reality — Brevo, AiSensy, Razorpay, Zoho, NimbusPost all have different APIs, docs, and quirks. Learning to read docs fast and wire things together is the actual skill
- Razorpay payment flow — order creation on server (unique for each person), payment verification
- Email deliverability basics — why emails go to spam, what sender reputation means
- That "good enough and shipped" beats "perfect and delayed" for an early startup

**The number that matters:** 1400+ signups generated through the site. Still running. Looking to expand and help them build much more. 

---

### Bluprynt Consulting Website `2026`
**Stack:** Next.js · TypeScript · NextAuth · Postgres · Neon · Drizzle ORM · Zod · Resend · Vercel

**Live:** [blupryntconsulting.com](https://blupryntconsulting.com) 

Real client project. A marketing site with a CAD-themed UI — custom AutoCAD-style cursor, scroll-driven spotlight effects, interactive project gallery.

**What I actually learned:**
- Three-layer route protection (middleware → layout → API) and why each layer matters
- Drizzle ORM — type-safe queries, schema definition, SQL migrations
- Zod for shared client + server validation (one schema, two uses)
- bcrypt password hashing — why you never store plain text, what salting does
- NextAuth credential provider — how sessions work under the hood
- Admin panel with full CRUD — the boring stuff that actually ships products

**Hardest part:** Getting the three-layer auth to not fight itself. Middleware redirects, layout checks session, API verifies again — understanding why all three are needed was the unlock.

---

### TurNext — Full-Stack E-Commerce `2026`
**Stack:** Next.js · TypeScript · Firebase · Stripe · Resend · Vercel

**Live:** [ecom-website-bice.vercel.app](https://ecom-website-bice.vercel.app)

Full e-commerce flow — product listings, cart, wishlist, reviews, checkout, order history, admin dashboard.

**What I actually learned:**
- React hooks in a real app — useState for cart, useEffect for data fetching, useContext for global cart state
- Stripe payment flow — PaymentIntent on server → client_secret to frontend → Stripe.js confirms → webhook marks order paid
- Why the webhook exists (can't trust the client to report payment success)
- Firebase Firestore — collections, documents, getDocs vs onSnapshot (one-time vs real-time)
- Firebase Auth — how it persists user across refreshes (IndexedDB + token refresh)
- Resend for transactional email — order confirmation on webhook success

**Hardest part:** Stripe webhook verification. The signature check kept failing locally until I understood why raw body matters.

---

### Airbnb Clone — Full-Stack `2026` *(in progress)*
**Stack:** HTML · CSS · JavaScript · Node.js · Express · EJS · MongoDB · Mongoose · Passport.js

No framework. Raw backend. This is where HTTP, routing, and sessions actually make sense.

**What I actually learned:**
- Express routing — app.get/post, Router, why you split routes into files
- Middleware — what next() does, why order matters, method-override for HTML forms
- Mongoose — schemas, models, .populate(), refs between collections
- Sessions via Passport.js — how req.user gets populated on every request
- EJS templating — passing data from routes to views, partials, escaping vs unescaping
- The whole request → middleware → route → DB → response → render cycle

**Hardest part:** Understanding that HTTP is stateless and sessions are the hack around that.

---

### Timetable Sync Platform `2026` *(in progress)*
**Stack:** Next.js · Node.js · Express · PostgreSQL · Supabase · Google Calendar API · OAuth 2.0

Syncs college timetables to Google Calendar and Apple Calendar (.ics).

**What I actually learned:**
- OAuth 2.0 full flow — why Google sends a code first, what happens during the token exchange
- Access tokens vs refresh tokens — why two tokens, where to store them, how to refresh silently
- Google Calendar API — event structure, inserting/updating events programmatically
- .ics format for Apple Calendar (CalDAV via tsdav)
- Supabase — managed Postgres, Row Level Security, when to use the JS client vs raw connection

**Hardest part:** OAuth callback handling. The code → token exchange has to happen server-side and the error messages when it fails are genuinely unhelpful.

---

### DSA in C — Study Tracker `2026`
**Stack:** Next.js · TypeScript · Tailwind CSS · Vercel

**Live:** [dsa-c-course-website.vercel.app](https://dsa-c-course-website.vercel.app)

11 topic pages, subtopic checklists, progress tracked via localStorage.

**What I actually learned:**
- Dynamic routing in Next.js — [slug] pages, generateStaticParams
- localStorage for persistence — when it's acceptable, when it isn't
- Server vs client component architecture — where to draw the line
- Building something useful for myself (actually used this while studying)

---

## Frequently used concepts - very very important 

### JavaScript / TypeScript
- [ ] async/await and Promises — what's actually happening under the hood
- [ ] Event loop — why Node handles many requests without threads
- [ ] Closures and scope — the var/let loop gotcha
- [ ] TypeScript interfaces vs types, generics, optional fields
- [ ] `any` vs `unknown`, when `as` casting is okay

### Backend / HTTP
- [ ] REST API design — HTTP methods, status codes, what each means
- [ ] Sessions vs JWT — trade-offs, where state lives
- [ ] Cookies — HttpOnly, SameSite, what the browser actually sends
- [ ] HTTPS / TLS — the handshake story (not the math)
- [ ] CORS — why it exists, how to actually fix it (not just disable it)
- [ ] OAuth 2.0 — the full code → token → API call flow

### React / Next.js
- [ ] useState, useEffect, useContext — can explain from scratch
- [ ] Server components vs client components — when and why
- [ ] Next.js middleware — what it can and can't do
- [ ] API routes vs server actions — when to use each

### Databases
- [ ] SQL vs NoSQL — genuine trade-off reasoning, not just "SQL has tables"
- [ ] Raw SQL — JOIN, WHERE, GROUP BY without an ORM
- [ ] What an ORM actually does and when to bypass it
- [ ] Database design from scratch — normalization, relations

---

## My Web dev checklist — "good enough to deliver"

These are the things I care about finishing. Not a completionist list — a practical one.

### frontend
- [ ] HTML, CSS, Tailwind, responsive design
- [ ] React — components, hooks, context
- [ ] Next.js — App Router, SSR, dynamic routes
- [ ] Performance basics — lazy loading, image optimization, Core Web Vitals
- [ ] Accessibility fundamentals — ARIA labels, keyboard nav

### backend
- [ ] REST APIs with Express
- [ ] Auth — sessions, JWT, OAuth, NextAuth
- [ ] Input validation with Zod
- [ ] Consistent error handling across all routes
- [ ] Rate limiting + basic API security
- [ ] Writing actual tests (Jest for unit, at least one integration test)

### databases
- [ ] MongoDB + Mongoose
- [ ] PostgreSQL via Drizzle / Supabase
- [ ] Raw SQL — joins, indexes, transactions
- [ ] Designing a schema from scratch without copying one

### devops / deployment
- [ ] Git + GitHub workflow
- [ ] Vercel deployment
- [ ] Cloudfare deployment
- [ ] Environment variables — what happens if you commit .env
- [ ] Docker basics (touched this with MongoDB on Arch)
- [ ] CI/CD — at least understand what a pipeline does

### things I'll learn when I need them
- WebSockets / Socket.io — for real-time features
- Redis — for caching, when apps need to be fast at scale
- Zustand for state management beyond Context
- Framer Motion — for Celestial

---

##  what I'm actually moving towards

Getting bored of webdev, looking forward to explore other things. 

Start (13/06/2026) - end (hopefully by dec 2027)

### DSA — non-negotiable, doing this now
- [ ] Complete Apna College Sigma 8.0 DSA sheet (C++)
- [ ] Start Striver's A2Z / Apna College DSA sheet on LeetCode
- [ ] Target: 150+ problems before end of semester break
- [ ] College DSA test — early August, need to be solid

### Linux — using it, want to go deeper
- [x] Daily driving Arch Linux with Hyprland
- [ ] Basic terminal usage, package management (pacman, AUR)
- [ ] Bash scripting — writing actual scripts, not just one-liners
- [ ] File permissions, processes, signals (`chmod`, `ps`, `kill`, `cron`)
- [ ] Networking commands — `curl`, `netstat`, `ssh`, `scp`
- [ ] Shell config — `.bashrc` / `.zshrc`, aliases, PATH, environment variables
- [ ] systemd basics — services, timers, `journalctl`

### AI / ML — exploring
- [ ] Python fundamentals for ML (NumPy, Pandas, Matplotlib)
- [ ] ML basics — supervised/unsupervised, train/test split, overfitting
- [ ] One complete ML project (not tutorial-following, actually building)
- [ ] OpenAI API integration — already on my list
- [ ] Decide: do I want to go research or applied ML?

### other things on the list
- [ ] Java — for college + Android eventually
- [ ] WebSockets / Socket.io — for real-time features
- [ ] AWS & cloud deployment — beyond Vercel
- [ ] Jest unit testing — write my first real test suite
- [ ] Systems — TCP/IP, DNS, HTTP at the protocol level (once DSA is solid)

---

## 🛠️ skills at a glance

**Languages:** C, C++, JavaScript, TypeScript, SQL  
**Frontend:** HTML, CSS, Bootstrap, Tailwind, React, Next.js  
**Backend:** Node.js, Express, EJS  
**Databases:** MongoDB, PostgreSQL, Firebase, MySQL, Neon, Supabase  
**ORMs:** Drizzle, Mongoose  
**Tools:** Stripe, Resend, NextAuth, Git, Vercel, Cloudfare, Docker (basic)  
**OS:** Linux (Arch + Hyprland, daily driver)  
**Currently learning:** DSA in C++, Linux deeper, AI/ML fundamentals  

---

## 📌 principles I'm trying to hold

1. **Deliver first, polish later.** Real clients > perfect code.
2. **Understand what I ship.** Vibe coding is fine to start, but I go back and read everything I didn't write myself.
3. **One thing deeply > five things barely.** DSA gets full focus this break.
4. **Build things I'd actually use.** DSA tracker, timetable sync — scratch your own itch.

---

*Last updated: 13th June 2026*