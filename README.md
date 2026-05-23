<div align="center">

<br/>

```
 ██████╗ ██████╗  ██████╗ ██╗    ██╗ ██████╗██╗   ██╗███████╗
██╔════╝ ██╔══██╗██╔═══██╗██║    ██║██╔════╝██║   ██║██╔════╝
██║  ███╗██████╔╝██║   ██║██║ █╗ ██║██║     ██║   ██║███████╗
██║   ██║██╔══██╗██║   ██║██║███╗██║██║     ██║   ██║╚════██║
╚██████╔╝██║  ██║╚██████╔╝╚███╔███╔╝╚██████╗╚██████╔╝███████║
 ╚═════╝ ╚═╝  ╚═╝ ╚═════╝  ╚══╝╚══╝  ╚═════╝ ╚═════╝ ╚══════╝
```

### India's First AI Student Retention Platform

**Predict dropout. Intervene early. Protect every student.**

<br/>

[![Version](https://img.shields.io/badge/version-4.0-FF7A45?style=flat-square)](#)
[![Status](https://img.shields.io/badge/status-prototype-2DD4A0?style=flat-square)](#)
[![AI](https://img.shields.io/badge/AI-Claude%20Sonnet%204-60A5FA?style=flat-square)](#)
[![License](https://img.shields.io/badge/license-MIT-F5C842?style=flat-square)](#license)

</div>

---

## The Problem

Every year, India loses **₹12,000 crore** to coaching student dropouts. A JEE student's family spends ₹1.5 lakh on fees. Their mother skips a medical check-up to pay. Week 3: the student's logins drop. Scores fall. Nobody notices. Week 6: they're gone — discovered only at the next fee deadline.

The data existed. No system was reading it.

**40% of coaching students drop out before exam day.** 97% of them show clear behavioural signals 3–6 weeks before it happens. Zero AI tools existed to catch those signals — until now.

---

## What Growcus Does

Growcus is a **B2B SaaS platform** for Indian coaching institutes (JEE, NEET, CA, and beyond). It tracks 47 behavioural signals per student per week, generates an AI-powered dropout risk score, and surfaces actionable alerts 72–96 hours before a teacher would notice anything is wrong.

```
Track 47 signals → Score each student → Alert institute → ARIA acts
     (weekly)          (0–100)           (AI watchlist)   (auto-nudge)
```

No manual effort. No new workflows. Just early warning and automated intervention.

---

## Four Portals, One Ecosystem

Growcus ships as a unified multi-tenant platform with four purpose-built interfaces:

### ⚡ Admin Portal
The institute director's command centre. Shows real-time dropout risk distribution across all batches, a live **Revenue at Risk** calculator, and a 6.5× ROI dashboard that translates student retention into rupees recovered. Built for decisions, not reports.

- Cohort-level risk intelligence
- Batch-vs-batch comparison
- Engagement trend charts
- Student support tier cards (Thriving / Watch / Needs Support / Urgent)

### 👁 Teacher Portal
Teachers receive an **AI Watch List** — the top 3–5 at-risk students in their batch, updated weekly. One click to assign a recovery quest. One click to send ARIA to check in on a student. Care language throughout: the platform is framed as support, not surveillance.

- Weekly focus score per student
- Burnout pattern detection
- Quick check-in modal
- ARIA nudge on demand

### 🎮 Student Portal *(mobile-first, max 430px)*
A gamified study companion designed to keep students intrinsically motivated. Daily AI quests, XP and level progression, a mood tracker, a batch leaderboard, and **ARIA** — a personal AI study coach available 24/7.

- Daily quests with XP rewards (4–6 per day)
- Level system with XP progress bar
- Mood check-in (privacy-protected)
- Boss Battle MCQ challenges
- ARIA chat with full conversation context
- Exam readiness percentage
- Privacy notice: *"Your mood data is private — teachers only see aggregated signals"*

### 📊 Parent Portal *(warm cream theme)*
A deliberately calm, non-alarming interface for parents. Weekly study hours, focus score trend, exam readiness, and early warning alerts in plain language. Warm sage-and-cream design — not another dark dashboard.

- Weekly activity summary
- Focus score with explanation
- Upcoming exam countdown
- Supportive alert language (no jargon)

---

## ARIA — Your AI Study Coach

Every student gets **ARIA**, powered by Claude Sonnet 4 via the Anthropic API.

ARIA knows your student's weak topics, upcoming exam dates, current streak, and mood — and responds like a warm, knowledgeable friend, not a chatbot.

```js
// System prompt excerpt
"You are ARIA, a warm and supportive AI study coach for Indian JEE/NEET students.
 Keep responses concise (2-4 sentences). Be warm and personal, not robotic.
 Mix academic help with emotional support. If the student is stressed,
 acknowledge feelings first."
```

**Quick chips** surface the most relevant questions at conversation start. Full conversation history (last 10 messages) is passed on every call for coherent multi-turn dialogue. Graceful fallback responses ensure the UX never breaks even if the API is unavailable.

---

## Onboarding Flow

New institutes go from sign-up to live in under 10 minutes:

```
Landing  →  Login  →  Institute Details  →  Plan Selection
                                                   ↓
               Go Live  ←  Setup (batches/teachers/students)  ←  Payment
```

Each institute gets a **unique 6-character code** (e.g. `FIITD7`). All data is fully isolated per institute — no cross-tenant data leakage by design.

**Pricing tiers:**

| Plan | Price | Students |
|---|---|---|
| Starter | ₹60 / student / yr | ≤ 300 |
| Growth *(most popular)* | ₹80 / student / yr | 300 – 1,500 |
| Pro | ₹65 / student / yr | 1,500 – 5,000 |

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Frontend (Web)** | Next.js · Vanilla HTML/CSS/JS (prototype) |
| **Mobile (Student)** | React Native |
| **Backend / API** | Node.js · PostgreSQL · Redis |
| **AI / LLM** | Claude Sonnet 4 via Anthropic API |
| **ML Model** | Python · Scikit-learn |
| **Infrastructure** | GCP · Docker · Kubernetes |
| **Payments** | Razorpay |
| **Notifications** | OneSignal (push) · Resend (email) |
| **Auth** | Supabase |
| **Fonts** | Syne (display) · DM Sans (body) · DM Mono |

**API hooks defined in the prototype:**

```js
doLogin()              // → Supabase auth
sendMessage()          // → POST /api/aria  (Anthropic stream)
addBatch/Teacher/Student()  // → POST /api/setup
Revenue/Analytics      // → GET  /api/stats
```

---

## Design System

Growcus v4 uses a custom design token system called **"Midnight Papaya"** — a dark midnight base with a warm papaya-orange primary accent and sage green for positive signals.

```css
--papaya:  #FF7A45   /* primary CTA, alerts, student UI */
--sage:    #2DD4A0   /* success, ARIA, safe signals */
--sky:     #60A5FA   /* informational */
--gold:    #F5C842   /* XP, streaks, achievements */
--rose:    #FB7185   /* urgent risk, errors */
--violet:  #A78BFA   /* levels, gamification */
```

The **Parent Portal** intentionally breaks from the dark theme — it uses a warm cream/sage palette (`#FAF7F2`) to feel approachable for non-tech-savvy parents.

**Key v4 design decisions:**
- Trust-first language throughout (*"Care" not "Surveillance"*)
- Privacy promise displayed prominently in the student app
- Retention ROI always visible to admin (never buried)
- Feature bloat removed — Boss Battles are a tab, not the hero
- Full accessibility: focus rings, `aria-labels`, WCAG colour contrast

---

## Project Structure

```
growcus/
├── index.html              # Full single-file prototype (v4.0)
│
├── pages/                  # (production) Next.js pages
│   ├── landing.tsx
│   ├── login.tsx
│   ├── onboard/
│   │   ├── details.tsx     # Step 1 — institute info
│   │   ├── plan.tsx        # Step 2 — plan selection
│   │   ├── payment.tsx     # Step 3 — Razorpay hook
│   │   ├── setup.tsx       # Step 4 — batches/teachers/students
│   │   └── done.tsx        # Step 5 — success
│   ├── admin/
│   ├── teacher/
│   ├── student/            # Mobile-first (max-width 430px)
│   └── parent/
│
├── api/
│   ├── aria.ts             # POST — Anthropic streaming endpoint
│   ├── setup.ts            # POST — onboarding data
│   └── stats.ts            # GET  — analytics & revenue data
│
├── components/             # Shared UI components
│   ├── MetricCell.tsx
│   ├── CareCard.tsx
│   ├── QuestCard.tsx
│   ├── ARIAChat.tsx
│   └── DataTable.tsx
│
├── ml/
│   └── dropout_model.py    # Scikit-learn risk scoring model
│
└── README.md
```

---

## Running the Prototype

The current release is a **fully self-contained single HTML file** — no build step, no dependencies, no server required.

```bash
# Clone the repo
git clone https://github.com/your-org/growcus.git
cd growcus

# Open in browser (no build step needed for prototype)
open index.html
# or
npx serve .
```

**To enable live ARIA chat**, replace the Anthropic API call in `sendMessage()` with your own proxy endpoint. Direct browser-to-API calls in production should always be proxied through your backend to protect your API key.

```js
// index.html — line ~3907
// Replace this direct call:
const response = await fetch('https://api.anthropic.com/v1/messages', { ... });

// With a call to your backend proxy:
const response = await fetch('/api/aria', { ... });
```

**Demo navigation** — the prototype uses a custom `navigate(pageId)` router. Pages:

| Page ID | Description |
|---|---|
| `page-landing` | Public marketing page |
| `page-login` | Unified auth portal |
| `page-onboard-1` through `page-onboard-5` | Setup wizard |
| `page-admin` | Institute director dashboard |
| `page-teacher` | Teacher portal |
| `page-student` | Student mobile app |
| `page-parent` | Parent portal |

---

## Connecting to Production Services

### Supabase (Auth + Database)
```js
// Replace doLogin() stub
import { createClient } from '@supabase/supabase-js'
const supabase = createClient(SUPABASE_URL, SUPABASE_ANON_KEY)
await supabase.auth.signInWithPassword({ email, password })
```

### Anthropic API (ARIA)
```js
// Backend proxy — api/aria.ts
import Anthropic from '@anthropic-ai/sdk'
const client = new Anthropic()
const message = await client.messages.create({
  model: 'claude-sonnet-4-20250514',
  max_tokens: 1000,
  system: ariaSystemPrompt,
  messages: conversationHistory,
})
```

### Razorpay (Payments)
```js
// Triggered on plan selection — page-onboard-3
const options = {
  key: RAZORPAY_KEY_ID,
  amount: planAmount * 100,  // in paise
  currency: 'INR',
  name: 'Growcus',
  handler: (response) => navigate('page-onboard-4'),
}
new Razorpay(options).open()
```

---

## Roadmap

| Phase | Timeline | Key Milestones |
|---|---|---|
| **Foundation** | M1–3 | Core app · PostgreSQL DB · AI model v1 (68% accuracy) · Admin + teacher dashboards · ARIA rule-based |
| **MVP Launch** | M4–6 | ARIA → Claude Sonnet 4 · Burnout detection · iOS + Android App Store · Razorpay billing |
| **Scale Up** | M7–9 | Guild + Boss Battles · Revenue intelligence · Parent auto-reports · **Breakeven** ✓ |
| **Growth** | M10–12 | White-label + API tier · Enterprise pipeline · AI model 79% accuracy · Series A prep |

**Target:** 350 institutes · ₹3.5 Cr ARR by Month 12

---

## Team

**Team Curios** · CSE (AI & ML) · MITS University

| Name | Role |
|---|---|
| Katari Adharsh `25MRA09005` | Full-stack + Backend lead |
| P. Shahid Khan `25MRA09228` | AI/ML + Product lead |

---

## Contributing

We welcome contributions from the community. If you're an EdTech founder, JEE/NEET educator, or SaaS engineer who shares our mission, we'd love to talk.

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m 'Add: your feature description'`
4. Push to your branch: `git push origin feature/your-feature`
5. Open a Pull Request

Please keep contributions aligned with our core principle: **student wellbeing, not surveillance.**

---

## License

MIT License — see [`LICENSE`](LICENSE) for details.

---

<div align="center">

**Built with care in India, for India.**

*Every student who doesn't drop out is a family's dream kept alive.*

<br/>

[Website](#) · [Pitch Deck](#) · [Contact](mailto:team@growcus.in)

</div>
