# Version Control Strategy

## Purpose

This strategy describes how repository changes should be organized to preserve traceability and protect authoritative documents.

## Branching

- `main` should represent the accepted public repository state.
- Feature branches should use descriptive kebab-case names.
- Planning branches should avoid mixing normative architecture changes with non-normative documentation.

## Commit Practices

- Keep commits focused by topic.
- Use clear imperative commit messages.
- Include generated planning documents in the same commit only when they form one coherent planning foundation.
- Do not commit local extraction artifacts, caches, or temporary files.

## Document Change Practices

- Preserve existing authoritative filenames unless a governance decision authorizes reorganization.
- Avoid duplicate planning documents; update existing planning documents when their purpose overlaps.
- Update dependency and inventory documents when adding or changing planning artifacts.
- For `.docx` authority documents, summarize intent clearly in commit and PR text because binary diffs are not review-friendly.

## Registry Practices

- Keep JSON registry changes synchronized with corresponding registry documents once a source-of-truth policy is defined.
- Until that policy is defined, treat registry synchronization as a blocking dependency rather than making unilateral changes.

## Pull Request Practices

- Use the repository pull request checklist.
- State compatibility impact.
- Cite the Constitution and ADR alignment for architecture-adjacent changes.
- Include repository inventory changes when structural documents are added.

## Release Practices

- Tag releases only after changelog, status labels, and freeze state are aligned.
- Record whether release contents are frozen, draft, planned, or unknown.
- Avoid claiming implementation conformance before fixture and validation gates exist.
