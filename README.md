# .github Repository

GitHub community health defaults and workflow templates for the jscraik account.

## What's in here

This repository provides community health defaults and workflow files. Each repository configures its own checks.

### Issue Templates

- **Bug Report** (`01-bug-report.yml`) - Structured bug reporting with environment details
- **Feature Request** (`02-feature-request.yml`) - Feature proposals with acceptance criteria
- **Documentation** (`03-documentation.yml`) - Documentation improvements
- **Task** (`04-task.yml`) - Internal work items

### PR Template

- The [shared PR template](.github/pull_request_template.md) covers summary,
  impact and risk, evidence, reviewer focus, and readiness.
- Complete its required checklist item after recording applicable validation and
  any limitations. The checklist workflow runs where installed. Each repository
  owns its validation commands, receipts, and branch protection.

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

### 1. Configure label sync

1. Create a Personal Access Token (PAT) with `repo` scope
2. Add it as a secret named `LABEL_SYNC_TOKEN` in this repository
3. Edit `.github/workflows/label-sync.yml` and add your repositories to the `repository:` list

### 2. Install and verify the checks

For repositories that use the shared title and checklist checks, install
`pr-title.yml` and `require-checklist.yml` in the target repository's
`.github/workflows/` directory. GitHub inherits the PR template from this account
repository. Each workflow runs only where installed.

Open a test PR and confirm that both workflows report their check runs. Use the
check names GitHub reports for that repository when configuring branch protection.

### 3. Enable branch protection

For each repository (or org-wide via rulesets):

- Require pull request reviews
- Require the verified status checks for `PR title lint (Conventional Commits)`
  and `PR checklist enforcement` where those workflows are used.
- Require branches to be up to date

### 4. Verify template inheritance

1. Open the new pull request form in a repository without its own PR template.
2. Verify that GitHub prefills the shared template.
3. For repositories with automated labelling, verify labels on a submitted test PR.

<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:3e8008b45773b78253ec71ba8d08715119c5e60ea9fb890437aa1b69959c7221 -->

### Validation evidence

These local source checks ran in Bash against commit
`dd05be13e1173ba0531e9abcb9594dfeffe05c73`. They don’t verify hosted workflow runs or branch protection settings.

**Setup order — PASS (exit 0)**

```bash
git show dd05be13e1173ba0531e9abcb9594dfeffe05c73:README.md | awk '/^### 2\. Install and verify the checks$/ {i=NR} /^Open a test PR and confirm that both workflows report their check runs\./ {v=NR} /^### 3\. Enable branch protection$/ {p=NR} END {exit !(i && i<v && v<p)}'
```

**Template headings — PASS (exit 0)**

```bash
diff -u <(printf '%s\n' '## Summary' '## Impact and risk' '## Evidence' '## Reviewer focus' '## Readiness') <(git grep -h '^## ' dd05be13e1173ba0531e9abcb9594dfeffe05c73 -- .github/pull_request_template.md)
```

**Template checkbox — PASS (exit 0)**

```bash
diff -u <(printf '%s\n' '- [ ] I recorded the applicable validation results and any limitations above.') <(git grep -hE '^[[:blank:]]*[-*+] \[[ xX]\]' dd05be13e1173ba0531e9abcb9594dfeffe05c73 -- .github/pull_request_template.md)
```

**Artifact guidance — PASS (exit 0)**

```bash
git grep -Fn 'Add an AI assistance entry under **Evidence** with the repository-relative' dd05be13e1173ba0531e9abcb9594dfeffe05c73 -- CLAUDE.md && git grep -Fn 'Add the committed repository-relative paths to an AI assistance entry under PR **Evidence**.' dd05be13e1173ba0531e9abcb9594dfeffe05c73 -- ai/README.md
```

The earlier checklist controls proof at `2454ad7` applies only to the workflow’s handling of optional controls.

<!-- /coderabbit-ai-generated:v1 -->

## How it works

GitHub looks for community health files in this order:

1. Target repo's `.github/` folder
2. Target repo's root
3. Target repo's `docs/` folder
4. **Account’s `.github` repository** (this one)

If a repo has its own `.github/ISSUE_TEMPLATE/` folder, it completely overrides the account defaults for that repo.

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

<!-- AGENT-FIRST-WORKFLOW:START -->
## Agent-first workflow

1. Create/update implementation plan using `.agent/PLANS.md` contract.
2. Validate plan graph:

```bash
python3 /Users/jamiecraik/.codex/scripts/plan-graph-lint.py .agent/PLANS.md
```

3. Run canonical verification:

```bash
/Users/jamiecraik/.codex/scripts/verify-work.sh
```

4. Follow global scaffold policy:

- `/Users/jamiecraik/.codex/instructions/agent-first-scaffold-spec.md`
<!-- AGENT-FIRST-WORKFLOW:END -->
