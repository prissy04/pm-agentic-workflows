# Contributing to PM Agentic Workflow Template Library

Thanks for your interest in contributing! This library is built by 
and for Program Managers. If you have a workflow that saves you time 
on a PM task, we want it here.

## What Makes a Good Contribution

A good workflow template for this library:
- Solves a real problem that Program Managers face regularly
- Produces output that is immediately useful
- Is written in plain English that other PMs can read and customize
- Includes a clear problem statement and documented time savings
- Has been tested on at least one real repository

## How to Contribute

1. Fork this repository
2. Create a new branch: `git checkout -b workflow/your-workflow-name`
3. Copy `templates/workflow-template.md` and rename it following 
   the `pm-` naming convention
4. Write your workflow instructions
5. Compile the lockfile: `gh aw compile your-workflow-name.md`
6. Update the workflow table in README.md
7. Open a Pull Request describing:
   - What PM problem this solves
   - How much time it saves per week
   - How you tested it

## Questions?

Open an issue labeled `question` and the maintainer will respond 
within 3 days.
