# Blocking Dependencies

## Purpose

This document lists dependencies that block implementation or specification freeze. It records gaps without supplying architectural decisions.

## Critical Blockers

| Blocker | Blocks | Required Resolution Path |
| --- | --- | --- |
| Registry source-of-truth policy is not explicit | Validators, parsers, translators, registry tooling | Governance or registry specification clarification |
| Canonical grammar freeze is not recorded | Parser implementation and syntax validation | Visual Language Standard completion and freeze process |
| Validation diagnostic schema is not frozen | Validator implementation and tooling interoperability | Validator Specification update |
| Serialization canonical form is not frozen | Serializer implementation and round-trip tests | Serialization Specification update |
| Conformance fixture suite is absent | Parser, validator, serializer, translator, Codex Brain conformance | Dedicated fixtures specification or repository structure decision |
| Compatibility test policy is not defined | Migration, deprecation, and version claims | Compatibility Specification update |
| License remains pending | Public reuse, implementation adoption, packaging | License selection and publication |

## Non-Critical Blockers

| Blocker | Impact |
| --- | --- |
| Formal documents are primarily `.docx` | Harder automated diffing and validation of normative text |
| Repository lacks grouped standards directories | Discoverability depends on filename conventions |
| Issue templates reference discussion workflows but no issue-to-freeze checklist exists | Governance execution may be inconsistent |
| Visual diagrams are deferred | Some architecture communication remains prose-only |

## Dependency Handling Rule

When an implementation encounters a blocker, it must not silently choose behavior. The correct response is one of:

1. cite the governing document that resolves the question;
2. open a clarification or architecture issue;
3. mark the capability unsupported in a partial conformance profile; or
4. defer implementation until the dependency is resolved.
