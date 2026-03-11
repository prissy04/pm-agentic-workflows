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
```

---

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
