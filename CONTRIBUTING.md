# Contributing to The Image Codex

Thank you for your interest in contributing to this formal specification project.

## Before Contributing

**Required reading:**
1. [Constitution](./IC-CON-001_Image_Codex_Constitution_v1.0_Official_Edition.docx) – Foundational principles
2. [ADRs 001-005](./IC-ADR-001_v1.0_Official_Edition.docx) – Ratified architecture decisions
3. This document – Contribution process

## Project Status

- **Version:** 1.0.0 Foundation
- **Phase:** Foundation Specification Development
- **Maturity:** Foundation specifications ratified; ongoing refinement

## Creator Authority

Per Article V of the Constitution, the project creator retains final authority over official standards during the Foundation Series. This ensures specification integrity and coherent evolution during this formative phase.

## Types of Contributions

### Bug Reports & Clarifications
Use the [Bug Report template](./.github/ISSUE_TEMPLATE/bug_report.md) for:
- Unclear or ambiguous wording
- Inconsistencies or errors
- Missing information

### Registry Additions
Use the [Registry Addition Request template](./.github/ISSUE_TEMPLATE/registry_addition_request.md) to propose:
- New object types or attributes
- Additional relationships or identifiers
- Standard definitions

### Specification Improvements
Use the [Specification Clarification template](./.github/ISSUE_TEMPLATE/specification_clarification.md) for:
- Suggested clarifications
- Better examples
- Wording improvements

### Architecture Changes
Use the [Architecture Proposal template](./.github/ISSUE_TEMPLATE/architecture_proposal.md) for:
- Significant specification changes
- New major components
- Modifications affecting multiple registries

**Note:** Accepted architectural changes may require a new ADR to formalize the decision.

### Documentation Fixes
Use the [Documentation Improvement template](./.github/ISSUE_TEMPLATE/documentation_improvement.md) for:
- Typos and grammar
- Clearer explanations
- Updated examples

## Contribution Requirements

All contributions must:

1. **Follow the Constitution** – Respect foundational principles and governance
2. **Respect ADRs 001-005** – Align with ratified architecture decisions
3. **Preserve Canonical Meaning** – Existing semantic definitions shall not be modified. New meanings require new concepts.
4. **Maintain Compatibility** – Do NOT break existing implementations
5. **Follow Style Guide** – Use [Publication Style Guide](./IC-PSG-001_Publication_Style_Guide_v1.0_Reviewed_Working_Draft.docx)
6. **Use Official Identifiers** – Reference objects from official registries
7. **Document Changes** – Clearly explain the "why" behind modifications

## Normative Language

This project uses normative language as defined in [RFC 2119](https://tools.ietf.org/html/rfc2119) and [RFC 8174](https://tools.ietf.org/html/rfc8174):

- **MUST** – Requirement; mandatory behavior
- **SHALL** – Requirement; mandatory behavior
- **SHOULD** – Recommendation; optional but encouraged
- **MAY** – Optional; implementation choice
- **MUST NOT** – Prohibition
- **SHALL NOT** – Prohibition
- **SHOULD NOT** – Recommendation against

When these terms appear in specifications, they carry formal significance.

## Contribution Process

1. **Create an Issue** – Use appropriate template describing your contribution
2. **Await Feedback** – Maintainers will review and provide guidance
3. **Fork & Branch** – Create feature branch from main
4. **Make Changes** – Follow requirements above
5. **Submit PR** – Use [PR template](./.github/pull_request_template.md)
6. **Address Feedback** – Iterate based on maintainer review
7. **Merge** – Once approved, your contribution is included

## What We Won't Accept

- ❌ Changes violating the Constitution or ADRs
- ❌ Modification of existing semantic definitions without creating new concepts
- ❌ Breaking changes without migration path
- ❌ Contributions without prior issue discussion
- ❌ Changes not following style guides

## Registry Addition Example

```json
{
  "identifier": "object.new_type",
  "definition": "Clear, concise definition",
  "namespace": "core",
  "examples": ["usage_example_1", "usage_example_2"],
  "related_concepts": ["existing_concept"]
}
```

## Questions?

- Open an issue using the appropriate template
- Check existing specifications first
- Reference the Constitution and ADRs

---

**Last Updated:** 2026-07-05 | **Version:** 1.0.0