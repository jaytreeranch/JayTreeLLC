# JayTree Development Continuity Policy
Version: 1.0 | Effective: 2026-10-31 | Applies to every JayTree software, website, game, media-production, automation, infrastructure and documentation project.

## Non-negotiable preservation rule
Every development session, in every chat or tool, must preserve its work in the project's existing GitHub repository **throughout the work**, not only at the end. Use the existing correct project/repository and an isolated feature branch when other work is active. Do not replace or rebuild working systems to establish a fresh checkout.

**Required checkpoints:** (1) after inspection/baseline, (2) after each coherent implementation or repair stage, (3) after verification/QC, (4) before deployment or promotion, (5) after deployment with actual machine-side receipts, and (6) before a conversation ends, branches, or reaches context limits. An incomplete stage must still receive a truthful WIP checkpoint and handoff. If GitHub is unavailable, preserve a versioned local/LAN recovery copy with hashes and mark GitHub push **PENDING**; reconcile when access returns.

## Files every project must maintain
- `AGENTS.md`: machine-readable development requirements and this continuity rule, preserving any project-specific safeguards.
- `docs/handoff/JAYTREE_START_HERE.md`: current verified status, repository and branch/commit, working locations, architecture, test/QA receipts, blockers, next exact actions, and rollback.
- `docs/handoff/JAYTREE_STAGE_LOG.md`: append-only milestones with UTC timestamps, stage, affected files, tests/results, GitHub commit/branch, deployment and pending items.
- Project-specific architecture, test plan, release/rollback, and operations instructions as appropriate; link them from START_HERE.

Update the handoff during each checkpoint. Distinguish **implemented**, **tested**, **deployed**, **production-certified**, and **blocked**. Never claim one on the evidence of another. Record actual SHA/commit IDs and source locations; do not invent tests or URLs.

## GitHub source-of-truth and safety
1. At the beginning, read AGENTS.md, START_HERE, STAGE_LOG, recent commits and the current working tree. Check for parallel chats/branches and preserve existing production files.
2. Commit and **push** non-sensitive code, application UI, small source assets, tests, scripts, specifications, safe config templates, docs, and handoff records at every checkpoint. Verify the resulting remote branch and SHA, and note unpushed work.
3. Do not force-push or silently rewrite collaborators' changes. Use task-specific branches or draft PRs. Preserve originals, rollback versions and stable release tags. Treat deployment as a separate gated operation.
4. **Never commit** credentials, bearer tokens, certificates/private keys, auth cookies, secrets, real customer/user data, private inventories/photos, databases, huge binary outputs, renders, or backups. Keep those in approved secure asset storage. In GitHub record only safe artifact names, non-sensitive locations, cryptographic hashes, receipts and recovery steps. Public repositories must never disclose private infrastructure details.
5. GitHub Actions and paid services are not mandatory; do not consume CI minutes or paid APIs simply to meet this policy. Use local tests and store their evidence.
6. If work is blocked by access, safety controls, offline hosts or uncertainty, keep handoff status accurate, do not bypass security, and preserve what has been completed.

## Standard stage-log entry
```
### YYYY-MM-DDTHH:MM:SSZ — <project> / <stage>
Status: VERIFIED | PARTIAL | BLOCKED | WIP
Scope and affected files:
What changed:
Source branch / local commit / VERIFIED REMOTE SHA:
Tests run and actual results:
Artifact location and SHA256 (if safe/relevant):
Deployment state (not installed / test / production):
Blockers and security gates:
Rollback / preservation:
Next exact command or development step:
```

## Handoff acceptance gate
A stage is **not complete** until (a) the affected source, tests and documentation are committed, (b) the GitHub remote push and SHA are verified (or explicitly marked PENDING with recoverable backup), and (c) START_HERE and STAGE_LOG accurately show the next resume point. Before handing work to another chat, include the repository and exact handoff file links.

## New projects and projects without GitHub
Before meaningful development, establish a project repository or owner-approved existing repository and create these handoff documents. Never pretend a new repository exists. Until established, preserve locally with explicit `GITHUB_NOT_CONFIGURED` and an actionable next step.

This document is a workflow contract, not an authorization to bypass access controls, publish, delete, deploy, or incur spending.

## Compatibility with existing JayTree project handoffs (2026-10-31 addendum)
Where a repository's existing `AGENTS.md` or project instructions define `docs/CURRENT_HANDOFF.md` or `docs/CURRENT_STATUS.md`, keep that established file as the **authoritative current-status handoff** and append timestamped stages under `docs/handoffs/`. Do not create competing status trackers. The `docs/handoff/JAYTREE_START_HERE.md` and `JAYTREE_STAGE_LOG.md` names in this policy are an accepted alternative for repositories already using them, not a requirement to replace stricter project conventions. For private infrastructure and authorized-host details, the canonical operational policy is the private `jaytreeranch/JayTree-Video-Studio/docs/JAYTREE_DEVELOPMENT_CONTINUITY_POLICY.md`. Project security rules always take precedence over a generic template.
