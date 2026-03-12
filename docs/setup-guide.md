# Setup Guide: PM Agentic Workflow Template Library

## What You Need Before You Start

- A GitHub account (free) — github.com
- GitHub CLI installed — cli.github.com
- gh-aw extension (free) — installed via GitHub CLI
- An AI API key — choose one of these free options:
  - Anthropic Claude (free tier) — console.anthropic.com
  - GitHub Copilot (free personal plan) — github.com/features/copilot
  - Google Gemini (free tier) — ai.google.dev

Estimated setup time: 30–45 minutes on first attempt.

---

## Step 1: Install GitHub CLI

**Windows:**
1. Go to cli.github.com
2. Click Download for Windows
3. Run the installer, click Next through all screens
4. Click Install, then Finish
5. Close and reopen your Command Prompt

**Mac:**

brew install gh

**Verify it installed:**

gh --version

You should see a version number. If you get an error, 
restart your terminal and try again.

---

## Step 2: Authenticate GitHub CLI

Run this command and follow the prompts:

gh auth login

Answer the questions like this:
- Where do you use GitHub? → GitHub.com
- What is your preferred protocol? → HTTPS
- Authenticate Git with your GitHub credentials? → Y
- How would you like to authenticate? → Login with a web browser

A code will appear. Copy it, press Enter, 
and paste it into the browser window that opens.
Click Authorize and you are logged in.

---

## Step 3: Install Git for Windows

**Windows only — skip if on Mac:**
1. Go to git-scm.com/download/win
2. Download and run the installer
3. Click Next through every screen — keep all defaults
4. Click Install, then Finish
5. Close and reopen your Command Prompt

---

## Step 4: Install the gh-aw Extension

gh extension install github/gh-aw

You should see:
✅ Installed extension github/gh-aw

---

## Step 5: Clone This Repository

gh repo clone prissy04/pm-agentic-workflows
cd pm-agentic-workflows

---

## Step 6: Copy a Workflow Into Your Own Repo

Navigate to your own project repository, then copy 
the workflow files you want:

**Windows:**

copy pm-agentic-workflows.github\workflows\pm-sprint-health-report.md YOUR-REPO.github\workflows
copy pm-agentic-workflows.github\workflows\pm-sprint-health-report.lock.yml YOUR-REPO.github\workflows\

**Mac/Linux:**
cp pm-agentic-workflows/.github/workflows/pm-sprint-health-report.md YOUR-REPO/.github/workflows/
cp pm-agentic-workflows/.github/workflows/pm-sprint-health-report.lock.yml YOUR-REPO/.github/workflows/

Replace YOUR-REPO with the actual path to your repository.

---

## Step 7: Add Your API Key as a Repository Secret

1. Go to your GitHub repository in your browser
2. Click Settings
3. Click Secrets and variables → Actions
4. Click New repository secret
5. Add one of these depending on which AI you chose:

| AI Engine | Secret Name | Where to Get Key |
|-----------|-------------|-----------------|
| Anthropic Claude | ANTHROPIC_API_KEY | console.anthropic.com |
| GitHub Copilot | COPILOT_GITHUB_TOKEN | github.com/settings/tokens |
| Google Gemini | GEMINI_API_KEY | ai.google.dev |

---

## Step 8: Commit and Push the Workflow Files

cd YOUR-REPO
git add .github/workflows/
git commit -m "Add PM Sprint Health Report agentic workflow"
git push

---

## Step 9: Test Your First Workflow

1. Go to your GitHub repository in your browser
2. Click the Actions tab
3. Find PM Sprint Health Report in the left sidebar
4. Click Run workflow → Run workflow
5. Wait 2-3 minutes
6. Click Issues tab — your first Sprint Health Report 
   should appear as a new issue

---

## Customizing the Workflows

Each workflow has a plain English instruction section 
at the bottom of the .md file. Open it in any text 
editor and update:

- Label names to match your team's actual labels
- Timeframes and thresholds to match your sprint length
- Audience descriptions to match your stakeholder level
- Any team-specific terminology

After editing the instruction section, recompile:

gh aw compile .github\workflows\pm-sprint-health-report.md

Then commit and push both files again.

---

## Deploying All Six Workflows

Repeat Steps 6-8 for each workflow:

| Workflow | File Name |
|----------|-----------|
| Sprint Health Report | pm-sprint-health-report.md |
| Intelligent Issue Triage | pm-issue-triage.md |
| Stakeholder Status Summary | pm-stakeholder-summary.md |
| Risk Flag Detector | pm-risk-flag-detector.md |
| PR Velocity Report | pm-pr-velocity-report.md |
| Docs Staleness Alert | pm-docs-staleness-alert.md |

---

## Troubleshooting

**"unable to find git executable"**
Install Git for Windows from git-scm.com/download/win
Close and reopen Command Prompt after installing.

**"not a git repository"**
You are in the wrong folder. Run:
cd YOUR-REPO-FOLDER-NAME

**"no frontmatter found" during compile**
The --- lines at the top of your .md file did not 
save correctly. Use VS Code instead of Notepad to 
edit the file. Install VS Code free at code.visualstudio.com

**"compilation failed — unknown property"**
Check the safe-outputs section of your frontmatter.
Valid values include: create-issue, add-comment, 
add-labels, add-reviewer.

**Workflow runs but no output appears**
Check that your API key secret is added correctly 
in repository Settings → Secrets and variables → Actions.

---

## Questions or Issues?

Open a GitHub Issue in this repository labeled 
with the question label and I will respond within 
3 business days.

Or connect on LinkedIn: 
https://www.linkedin.com/in/priscamanokore/
