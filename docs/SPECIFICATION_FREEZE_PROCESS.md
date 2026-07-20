# Specification Freeze Process

## Purpose

This document proposes a planning process for freezing specifications. It does not freeze any existing draft and does not supersede governance authority.

## Freeze Principles

1. The Constitution remains supreme.
2. Accepted ADRs remain binding unless formally amended or superseded.
3. A freeze records stability for implementation; it does not transfer authority away from governing documents.
4. Freezing must not silently change canonical meaning.
5. Implementation convenience is not sufficient reason to alter architecture.

## Freeze Candidate Requirements

A document may become a freeze candidate only when:

- its authority and dependencies are identified;
- normative language is internally consistent;
- unresolved architectural questions are listed;
- examples do not contradict normative text;
- registry references are resolvable;
- compatibility impact is understood;
- required machine-readable artifacts are identified; and
- open blockers are either resolved or explicitly scoped out.

## Freeze Review Steps

1. Inventory affected files and dependent documents.
2. Verify consistency with the Constitution and ADRs.
3. Verify cross-document references.
4. Review registry references.
5. Review compatibility impact.
6. Review implementation readiness gates.
7. Record final status label and version.
8. Update changelog and repository inventory if applicable.

## Post-Freeze Change Classes

| Change Class | Examples | Required Handling |
| --- | --- | --- |
| Editorial | typos, formatting, broken links | May be accepted if meaning is unchanged |
| Clarifying | wording that removes ambiguity | Requires review against authority documents |
| Additive | new registry entry or optional profile | Requires compatibility review |
| Behavioral | grammar, validation, semantic, or execution change | Requires formal governance and likely ADR or specification revision |
| Breaking | incompatible canonical meaning or structure | Extraordinary; requires formal approval and migration plan |

## Freeze Outputs

- Updated status in the affected document.
- Changelog entry.
- Dependency map update.
- Completion tracker update.
- Conformance fixture update when applicable.
