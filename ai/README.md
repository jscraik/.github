# AI Artifacts (Model A)

This directory stores committed AI artifacts for pull requests created with AI assistance.

## Structure

```
ai/
├── prompts/      # Committed prompt files (.yaml)
├── sessions/     # Committed session summaries (.json)
├── tmp/          # Transient (gitignored)
├── cache/        # Transient (gitignored)
└── raw/          # Transient (gitignored)
└── README.md     # This file
```

## Usage

When creating a PR with AI assistance:

1. **Prompt file**: Save final prompt to `ai/prompts/YYYY-MM-DD-<slug>.yaml`
2. **Session log**: Save summary to `ai/sessions/YYYY-MM-DD-<slug>.json`
3. **Reference**: Add the committed repository-relative paths to an AI assistance entry under PR **Evidence**.

See template files:
- `ai/prompts/.template.yaml`
- `ai/sessions/.template.json`
