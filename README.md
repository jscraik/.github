# Shared GitHub Community Files

Default support, contribution and issue/PR templates for repositories owned by
[jscraik](https://github.com/jscraik).

## Get help or contribute

- **Using a project:** start with that project's README and docs.
- **Questions or an inaccessible intake route:** read [Support](SUPPORT.md) or email <jscraik@brainwav.io>.
- **Reporting a bug or proposing a feature:** use the project's issue form or its documented public intake route.
- **Contributing a change:** read the project's guidance and [Contributing](CONTRIBUTING.md).
<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:3112e896a831808ca8a8c9ee5e415a4fed73c65e1975b3f555e3cd43810815c6 -->

- **Reporting a vulnerability:** follow the project's security policy. If it has none, use the [shared security policy](SECURITY.md).

<!-- /coderabbit-ai-generated:v1 -->

## What repositories inherit

GitHub uses supported community files from this public `.github` repository when
a repository owned by the account does not provide its own file of that type.

| Resource | Behaviour |
| --- | --- |
| `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md` | Supported default community files, subject to repository overrides. |
| Issue/PR templates, issue chooser and discussion category forms | Shared defaults where the repository has not supplied its own configuration. Discussion forms require Discussions to be enabled in the destination. |
| `FUNDING.yml` | Shared funding configuration where applicable. |
| `GOVERNANCE.md` | A reference for projects that explicitly adopt it. |
| Workflow files and label configuration | Require explicit configuration and adoption; they are not deployed to other repositories by community-file inheritance. |
| A project's licence | Must be supplied by that project; there is no inherited default licence. |

For supported files, GitHub checks the destination repository's `.github/`, root
and `docs/` locations before falling back to this repository. A valid local issue
template or issue-template configuration overrides the whole shared issue-template
configuration. See [GitHub's default community file rules](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

## Templates available here

<!-- coderabbit-ai-generated:v1 -->

<!-- coderabbit-ai-generated-section:v1:e3079626cfe200f18395e76c3ebcfd104f5f036db707e06686d31c9ccd6e4e8b -->

The issue forms cover bug reports, feature requests, documentation and internal
tasks. The PR template asks for a summary, impact and risk, evidence, reviewer
focus, and readiness. Template presence does not prove that a checklist or review
requirement is enforced.

<!-- /coderabbit-ai-generated:v1 -->

Discussion category forms cover Q&A, ideas, announcements and show-and-tell.
This repository's support route is email; do not assume that its Discussions
area is enabled merely because form files exist.

## Automation: explicit adoption

The files in `.github/workflows/` are workflows for this repository. They are not
an automatically inherited CI suite for every repository in the account.

- **Label sync:** `.github/workflows/label-sync.yml` names its target repositories
  explicitly and reads `LABEL_SYNC_TOKEN`. Review those targets and the existing
  credential's permissions before enabling or extending cross-repository sync.
- **PR title and checklist checks:** adopt the intended workflow in each consuming
  repository and verify a real run before requiring its check in branch rules.
- **PR labels:** configure the consuming repository's paths and labels explicitly.

For organisation workflow templates, GitHub provides a separate
[`workflow-templates` mechanism](https://docs.github.com/en/actions/how-tos/reuse-automations/create-workflow-templates).
That mechanism is distinct from the ordinary workflow files stored here.

## Maintainer checks

1. Check that a project's public help and security routes are usable.
2. Review local overrides before expecting shared templates to appear.
3. Keep the explicit label-sync target list current, including archive and rename decisions.
4. Verify each adopted workflow in its destination repository before claiming enforcement.
5. Match each project's support and governance commitments to its actual maintenance policy.

The label-sync workflow is triggered by changes to its configured workflow or
label manifest on `main`; it does not run for every unrelated push. Its current
configuration keeps pruning disabled.

## Maintainer scaffold

The following managed block describes the maintainer's configured environment.
Its personal paths are not prerequisites for users reporting issues or reading
these public community files. A contributor without that environment should
record the unavailable check and use the support route above for handoff.

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
