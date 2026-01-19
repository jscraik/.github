# .github Repository

Organization-wide GitHub community health files and workflow templates.

## What's in here

This repository provides default templates and automation for all repositories in the organization:

### Issue Templates

- **Bug Report** (`01-bug-report.yml`) - Structured bug reporting with environment details
- **Feature Request** (`02-feature-request.yml`) - Feature proposals with acceptance criteria
- **Documentation** (`03-documentation.yml`) - Documentation improvements
- **Task** (`04-task.yml`) - Internal work items

### PR Template

- Standardized PR description with checklist enforcement
- Security/privacy considerations
- Release notes section

### Label System

- **Type labels**: bug, feature, docs, chore, refactor, perf, test, ci, build, security
- **Status labels**: needs-triage, needs-info, blocked, ready, in-progress, wontfix
- **Priority labels**: p0 (critical), p1 (high), p2 (normal), p3 (low)
- **Size labels**: XS, S, M, L, XL
- **Area labels**: docs, api, ui, cli, core, deps, build, ci, tests

### Automation Workflows

- **label-sync.yml** - Syncs labels across all org repos
- **pr-title.yml** - Enforces Conventional Commits format
- **require-checklist.yml** - Ensures PR checklist completion
- **pr-labeler.yml** - Auto-labels PRs based on changed files

### Community Health Files

- **CODE_OF_CONDUCT.md** - Community behavior expectations and enforcement
- **CONTRIBUTING.md** - Contribution guidelines and PR requirements
- **SECURITY.md** - Vulnerability reporting and security policy
- **SUPPORT.md** - Where to get help and ask questions
- **GOVERNANCE.md** - Project roles and decision-making process
- **FUNDING.yml** - Sponsorship and funding options

### Discussion Templates

- **Q&A** (`q-a.yml`) - Structured help requests
- **Ideas** (`ideas.yml`) - Feature proposals and improvements
- **Announcements** (`announcements.yml`) - Release notes and major updates
- **Show & Tell** (`show-and-tell.yml`) - Community showcases

## Setup Instructions

### 1. Create this repository

Create a repository named `.github` in your organization. GitHub will automatically use these files as defaults for all repos.

### 2. Configure label sync

1. Create a Personal Access Token (PAT) with `repo` scope
2. Add it as a secret named `LABEL_SYNC_TOKEN` in this repository
3. Edit `.github/workflows/label-sync.yml` and add your repositories to the `repository:` list

### 3. Enable branch protection

For each repository (or org-wide via rulesets):

- Require pull request reviews
- Require status checks:
  - `PR title lint (Conventional Commits)`
  - `PR checklist enforcement`
- Require branches to be up to date

### 4. Test it

1. Create a test PR in any repo
2. Verify the PR template appears
3. Check that workflows run
4. Confirm labels are applied

## How it works

GitHub looks for community health files in this order:

1. Target repo's `.github/` folder
2. Target repo's root
3. Target repo's `docs/` folder
4. **Organization's `.github` repo** (this one)

If a repo has its own `.github/ISSUE_TEMPLATE/` folder, it completely overrides the org defaults for that repo.

## Customization per repo

Individual repos can:

- Add repo-specific `area:*` labels (keep the prefix)
- Override templates by creating their own `.github/ISSUE_TEMPLATE/`
- Extend the labeler config with repo-specific paths

## Maintenance

- Labels are synced automatically on push to `main`
- Review and update label taxonomy quarterly
- Keep enforcement workflows updated with latest action versions
- Monitor workflow runs in the Actions tab

## Resources

- [GitHub Docs: Creating default community health files](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Label Syncer Action](https://github.com/micnncim/action-label-syncer)
