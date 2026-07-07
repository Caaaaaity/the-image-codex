# Critical Path

## Purpose

This document identifies the safest sequence from planning to implementation while respecting the Constitution, accepted ADRs, and existing draft standards.

## Critical Path Sequence

```text
1. Preserve constitutional and ADR authority
2. Confirm repository inventory and document status
3. Resolve registry source-of-truth policy
4. Freeze grammar and canonical structure rules
5. Freeze validation diagnostics and report model
6. Freeze serialization canonical form
7. Add conformance fixtures
8. Implement parser and validator
9. Implement serializer and compatibility checks
10. Implement Codex Brain and translation prototypes
```

## Why This Order Matters

- Parser work before grammar freeze risks implementation-defined language behavior.
- Validator work before registry policy risks inconsistent identifier resolution.
- Serializer work before canonical form freeze risks non-portable documents.
- Translator work before semantic and execution inputs are stable risks prompt behavior becoming de facto architecture.
- Codex Brain work before validation readiness risks executing invalid or unresolved documents.

## Parallel Work That Is Safe

- Documentation inventory and cross-reference improvements.
- Issue template refinements.
- Non-normative diagrams and educational explanations.
- License evaluation.
- Fixture planning without committing fixture semantics.

## Work That Should Wait

- Production parser behavior.
- Production validator behavior.
- Official schemas.
- Model adapters.
- Registry expansion beyond governed additions.
- Any change that redefines canonical meaning or structure.
