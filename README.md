<<<<<<< HEAD
# AI Freelancer Business Risk Analyzer

> **Live Demo:** [yourapp.vercel.app](https://yourapp.vercel.app)  
> **Built by:** Prisca Manokore | [LinkedIn](https://linkedin.com/in/yourprofile) | [GitHub](https://github.com/yourusername)  
> **Stack:** React · Vite · Anthropic Claude API · Vercel

---

## The Problem

**73 million freelancers in the US have no early warning system for business risks that are entirely predictable.**

Freelancer business failures follow a recognizable pattern — the same risks appear repeatedly across different people, industries, and income levels:

| Risk Pattern | Real-World Consequence |
|---|---|
| 70%+ income from a single client | Income collapses the moment that client leaves |
| Too many active projects simultaneously | Burnout, missed deadlines, damaged client reputation |
| Net-30 or Net-60 payment terms across all clients | 30–60 day cash flow gaps with zero income buffer |
| Clients changing requirements mid-project | Skill gaps exposed, scope creep, unpaid rework |
| No pipeline of incoming leads | Income cliff when current projects complete |

These are not random misfortunes. They are **measurable, predictable, and preventable** — if a freelancer has a tool to identify them early enough to act.

**No such tool existed.** Before writing a single line of code, I validated this gap by searching GitHub, Product Hunt, and every major AI tool directory. The specific combination of these five risk dimensions — assessed together as a freelancer business health check — was entirely absent as a standalone, self-serve tool.

---

## The Origin Story

My son is in high school and freelances as a graphic designer on the side.

I watched him take on more projects than he could finish, get caught off guard when clients changed requirements mid-project, and burn out trying to balance school deadlines with client demands. He did not have a word for what was happening to him — and neither the vocabulary nor the tool to see the risks coming.

I went looking for something that could help him. Nothing existed.

So I built it. He was the first user. He read his results and said: *"Yeah, that's exactly what's been happening."*

That was enough for me.

---

## Market Validation

Before building, I confirmed the gap was real and unoccupied:

| What I Searched | What I Found | Gap Confirmed |
|---|---|---|
| GitHub `risk-analytics` topic | Credit risk, financial modeling — nothing for freelancers | ✅ |
| GitHub `freelancer-tools` repos | Rate calculators, invoice tools — no risk assessment | ✅ |
| Product Hunt AI tools | Contract analyzers, job scam detectors — different problem | ✅ |
| Enterprise burnout tools (Microsoft Viva, Workday) | Corporate employee monitoring — not freelancer self-assessment | ✅ |
| Freelancer platforms (Upwork, Fiverr, Toptal) | Client-side tools only — nothing built for the freelancer's business health | ✅ |

**Conclusion:** A self-serve, AI-powered tool that helps freelancers assess their own business risk across income concentration, burnout, cash flow, skill mismatch, and pipeline health does not exist anywhere as a standalone deployed product.

---

## What It Does

A freelancer answers 10 self-assessment questions about their current business situation. The Anthropic Claude API analyzes their responses and returns a personalized, color-coded risk report across five dimensions:

```
Income Concentration Risk    → How dependent are you on a single client?
Overcommitment & Burnout     → Are you taking on more than you can deliver?
Cash Flow Gap Risk           → Will your payment terms leave you without income?
Skill Mismatch Risk          → Are clients asking for skills you don't have?
Pipeline Health Risk         → What happens when your current projects end?
```

Each dimension returns:
- A severity level: **High** (red) / **Medium** (amber) / **Low** (green)
- A two-sentence explanation specific to the user's actual answers — not generic advice
- One concrete, actionable step the user can take this week

**No data is stored. No account required. Results are generated fresh per submission and never logged.**

---

## Technical Architecture

```
User Browser
    │
    ├── React + Vite Frontend
    │   ├── 10-question self-assessment form
    │   ├── Client-side rate limiter (3 analyses/day via localStorage)
    │   ├── Loading state with spinner
    │   └── Color-coded risk report renderer
    │
    └── Anthropic Claude API (claude-haiku model)
        ├── Structured JSON prompt with all 10 answers
        ├── 5-category risk analysis with severity + explanation + action
        └── Personalized response — references actual user inputs
```

**Key technical decisions and reasoning:**

| Decision | Rationale |
|---|---|
| **Claude Haiku model** | Cheapest available model ($0.25/million input tokens). Sufficient for structured analysis tasks. Cost per analysis: ~$0.001 |
| **No database** | Eliminates privacy concerns, GDPR overhead, and infrastructure cost at this stage. Zero data retention by design |
| **localStorage rate limiting** | Prevents API abuse at zero server cost. Simple, effective, no backend required |
| **Environment variables for API key** | Key never appears in code or version control. Stored in Vercel environment variables only |
| **$20/month API spend cap** | Hard ceiling set in Anthropic console. App stops accepting requests rather than generating unexpected charges |
| **Vite build tool** | Faster than Create React App, simpler configuration, better developer experience |

---

## Risk Management

As a TPM, I applied structured risk thinking to the build itself before writing any code:

| Risk | Likelihood | Impact | Mitigation Applied |
|---|---|---|---|
| API cost explosion from viral traffic | Medium | High | Hard $20/month spend cap in Anthropic console + alert at 80% |
| API key exposed in source code | Low | Critical | Environment variables only — `.env` in `.gitignore`, key stored in Vercel settings |
| User abuse or bot automation | Medium | High | 3 analyses per day per browser — localStorage rate limiter |
| Vercel unexpected billing | Low | High | Hobby plan selected — hard usage ceiling, no overage charges |
| Claude API downtime | Low | Medium | Error handling with user-friendly message — graceful failure |
| Viral exposure before safeguards | Low | High | All safeguards built before first public link shared |

---

## Running Locally

```bash
# Clone the repository
git clone https://github.com/yourusername/freelancer-risk-analyzer
cd freelancer-risk-analyzer

# Install dependencies
npm install

# Create environment file
echo "VITE_ANTHROPIC_API_KEY=your-key-here" > .env
# Get your key at: console.anthropic.com

# Start development server
npm run dev
# Open http://localhost:5173
```

**Requirements:** Node.js 18+, an Anthropic API key (free to create, pay-per-use)

---

## Project Structure

```
freelancer-risk-analyzer/
├── src/
│   └── App.jsx          # Main component — form, API call, results
├── public/
├── .env                 # API key (local only — never committed)
├── .gitignore           # Includes .env and node_modules
├── package.json
├── vite.config.js
└── README.md
=======
# 🤖 PM Agentic Workflow Template Library

> AI-powered GitHub workflow templates built by a Program Manager, for Program Managers.
> Automate your most time-consuming weekly tasks — sprint reports, issue triage, stakeholder
> updates, and risk detection — using GitHub Agentic Workflows. No coding required to deploy.

---

## 🚨 The Problem

Program managers spend 8–15 hours every week assembling information instead of acting on it:

- Writing sprint status reports by hand
- Manually triaging GitHub issues every Monday
- Composing stakeholder updates from scratch every week
- Hunting through issues to find stalled or at-risk items
- Checking whether docs stayed in sync after code changes

This is assembly work, not strategic work. This library automates the assembly.

---

## ✅ What This Library Does

| # | Workflow | Trigger | Time Saved/Week |
|----|----------|---------|-----------------|
| 1 | Sprint Health Report | Every Monday 8 AM | 3–4 hours |
| 2 | Intelligent Issue Triage | New issue opened | 2–3 hours |
| 3 | Stakeholder Status Summary | Every Monday 9 AM | 2–4 hours |
| 4 | Risk Flag Detector | Every day 7 AM | 1–2 hours |
| 5 | PR Velocity Report | Every Friday 5 PM | 1–2 hours |
| 6 | Docs Staleness Alert | After PR merges | 1–2 hours |

**Total estimated savings: 10–15 hours per PM per week.**

---

## ⚡ Quick Start
```bash
# 1. Clone this repo
git clone https://github.com/prissy04/pm-agentic-workflows

# 2. Copy the workflow you want into your project repo
cp .github/workflows/pm-sprint-health-report.md /path/to/your/repo/.github/workflows/
cp .github/workflows/pm-sprint-health-report.lock.yml /path/to/your/repo/.github/workflows/

# 3. Commit and push
git add .github/workflows/
git commit -m "Add PM Sprint Health Report agentic workflow"
git push

# 4. Add your API key as a repository secret
# GitHub repo → Settings → Secrets and variables → Actions → New secret
# Name: ANTHROPIC_API_KEY
>>>>>>> 60777bbd4297dfec0e862eefa0868e309803f18e
```

---

<<<<<<< HEAD
## What I Learned Building This

**On product thinking:**
Validating the gap before building was the most important step. Several adjacent ideas were ruled out through research — generic risk analyzers, job posting red-flag detectors, career pivot tools — all had existing competitors. The specific freelancer business health angle was genuinely unoccupied.

**On technical decision-making:**
Choosing Claude Haiku over Sonnet reduced per-analysis cost by approximately 12x with no meaningful quality loss for a structured analysis task. Model selection is a product decision, not just a technical one.

**On risk management:**
Every safeguard — the spend cap, the rate limiter, the environment variables, the Hobby plan selection — was designed and implemented before the first public URL was shared. Managing known risks proactively is cheaper than responding to them after the fact.

**On AI prompt design:**
The prompt instructs Claude to reference the user's actual answers specifically, not return generic freelancer advice. The difference between "you should diversify your clients" and "with 75–100% of your income from one client, losing that relationship would immediately eliminate your revenue" is entirely in the prompt engineering.

---

## Product Roadmap

Planned improvements in priority order:

- [ ] **PDF report download** — User receives a shareable, formatted version of their risk report
- [ ] **Progress persistence** — Save partial answers so users can return to complete the assessment
- [ ] **Month-over-month tracking** — Optional account creation to compare risk scores over time
- [ ] **Contextual resource suggestions** — Relevant tools and resources linked inside each risk category
- [ ] **Mobile-optimized layout** — Improved experience on small screens
- [ ] **Accessibility audit** — WCAG 2.1 AA compliance review

---

## Skills Demonstrated

`AI Application Development` · `Anthropic Claude API` · `Prompt Engineering` · `React` · `Vite` · `REST API Integration` · `API Security` · `Rate Limiting` · `Environment Variable Management` · `Vercel Deployment` · `CI/CD` · `Market Research` · `Competitive Analysis` · `Risk Management` · `Technical Documentation`

---

## About the Builder

**Prisca Manokore** is a Technical Program Manager with experience at Microsoft, SAS, and MetLife, specializing in AI-focused product development and cross-functional program delivery.

This project demonstrates end-to-end problem-solving — from identifying a confirmed market gap through competitive research, to building and deploying a production AI application, to documenting it with the same rigor applied to enterprise programs.

- **LinkedIn:** [linkedin.com/in/yourprofile](https://linkedin.com/in/yourprofile)
- **GitHub:** [github.com/yourusername](https://github.com/yourusername)
- **Live App:** [yourapp.vercel.app](https://yourapp.vercel.app)

---

*Built March 2026 · Open source · Free to use · No data stored*
=======
## 📊 Business Case

At an average TPM salary of $130,000/year:

| Workflow | Hours Saved/Week | Annual Value |
|----------|-----------------|--------------|
| Sprint Health Report | 3.5 hrs | $11,375 |
| Issue Triage | 2.5 hrs | $8,125 |
| Stakeholder Summary | 3.0 hrs | $9,750 |
| Risk Flag Detector | 1.5 hrs | $4,875 |
| PR Velocity Report | 1.5 hrs | $4,875 |
| Docs Staleness Alert | 1.5 hrs | $4,875 |
| **Total** | **13.5 hrs/week** | **$43,875/year** |

---

## 👤 About

Technical Program Manager with 15+ years delivering AI, cloud, and infrastructure
programs at Microsoft, SAS, and MetLife. PMP and Scrum certified.

I built this library because I watched it happen firsthand — PMs spending hours every 
week assembling sprint reports, triaging issues, and writing stakeholder updates by hand 
while working inside GitHub at Microsoft. That assembly work steals time from the 
strategic thinking that actually moves programs forward. These workflows fix that.

Connect on LinkedIn: https://www.linkedin.com/in/priscamanokore/
>>>>>>> 60777bbd4297dfec0e862eefa0868e309803f18e
