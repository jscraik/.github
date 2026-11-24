<!--
Write for maintainers. Keep each answer short and use project terms.
Use the target repository's required fields and checks where applicable.
For an inapplicable required field, write n.a. and give the reason.
Keep credentials, raw transcripts and private local paths out of the PR.
-->

## Summary

<!--
State the problem and the behaviour after this change. Include scope exclusions
when they affect review.

Optional State Map: if the change is easier to review visually, add one small,
editable Mermaid diagram here. Use a connection map for ownership or boundaries,
a workflow or sequence for order, or a state diagram for the lifecycle of one
entity. Label meaningful triggers, conditions and failure or recovery paths.
Add a plain-language walkthrough, cite the source or contract and identify
proposed behaviour. A short diff, tree or sentence may be enough.
-->

## Impact and risk

- **Boundaries:** <!-- Describe the blast radius. Who or what could be affected, including downstream consumers? Consider layout shifts, mobile behaviour, API or schema compatibility, providers, runtime, distribution and data where relevant. -->
- **Merge risk and recovery:** <!-- Is this a two-way door (straightforward to undo), a one-way door (destructive or hard to reverse), or is reversibility still unverified? Explain how to roll back, what reverting the code cannot undo, and whether recovery was tested. -->

## Evidence

- **Behaviour:** <!-- Show before and after with a test, output, screenshot or source comparison. Label inferred behaviour and identify the entry point and environment when relevant. -->
- **Validation:** <!-- Identify the reviewed commit and the tested commit if different. List each exact validation command and its outcome: pass, fail, blocked, or not run. Keep hosted checks pending until GitHub reports results for the reviewed commit. -->
<!-- Add a line for each applicable command. Use the repository's real commands.
- Command: `<exact command>` -> pass
- Command: `<exact command>` -> blocked (concrete reason)
Use fail or not run as appropriate. Explain what remains unverified. -->
- **Limitations:** <!-- Record material paths still untested or blocked. Use n.a. with a reason when there are none to record. -->

## Reviewer focus

<!-- Name the decision, boundary or file that needs attention. Use n.a. with a reason if there is no special focus. -->

## Readiness

- **Receipts:** <!-- State applicable create and update receipt outcomes for this head, or n.a. with a reason. -->
- **Guarded body refresh:** <!-- State the actual helper outcome, or n.a. with a reason. -->
- **Hosted checks and independent review:** <!-- Record outcomes for the current PR commit. A requested review stays pending until the reviewer publishes a completed verdict. -->
- **Unresolved findings:** <!-- Link outstanding findings or say none only after checking. -->

- [ ] I recorded the applicable validation results and any limitations above.
