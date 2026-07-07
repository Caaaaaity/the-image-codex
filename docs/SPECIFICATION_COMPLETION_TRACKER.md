# Specification Completion Tracker

## Purpose

This tracker summarizes completion state for existing documents. It uses repository-observed status labels and implementation readiness, not subjective replacement architecture.

## Status Vocabulary

- **Frozen**: ratified or accepted authority that should not change except through formal governance.
- **Complete**: sufficiently written for its current purpose but not necessarily immutable.
- **Draft**: written but explicitly working draft or reviewed working draft.
- **Planned**: referenced as future work or needed but not present.
- **Unknown**: status cannot be determined from repository contents.

## Tracker

| Document Family | Files | Current State | Implementation Readiness |
| --- | --- | --- | --- |
| Constitution | `IC-CON-001...docx` | Frozen | Governing authority ready |
| ADRs | `IC-ADR-001` through `IC-ADR-005` | Frozen | Foundational architecture ready |
| Core standards | `IC-VLS-001`, `IC-SEM-001`, `IC-CBS-001` | Draft | Planning ready; implementation gates remain |
| Parser | `IC-PAR-001` | Draft | Blocked by grammar fixtures and freeze |
| Validator | `IC-VAL-001` | Draft | Blocked by diagnostics, fixtures, and registry policy |
| Serialization | `IC-SER-001` | Draft | Blocked by canonical format and round-trip fixtures |
| Translation | `IC-TRN-001` | Draft | Blocked by execution-plan interface and model capability policy |
| Compatibility | `IC-CMP-001` | Draft | Blocked by compatibility test policy |
| Governance | `IC-GOV-001` | Draft | Usable for process, needs freeze mechanics alignment |
| Reference Architecture | `IC-ARC-001` | Draft | Planning ready |
| Publication Style Guide | `IC-PSG-001` | Draft | Usable for documentation consistency |
| Registries | `IC-REG-001` through `IC-REG-006`, `ic_reg_001.json` through `ic_reg_006.json` | Draft | Blocked by source-of-truth policy |
| Repository process | README, CONTRIBUTING, CHANGELOG, templates | Complete | Usable for contribution workflow |
| License | `LICENSE_PENDING.md` | Planned | Blocks adoption and packaging |
| Test fixtures | none observed | Planned | Blocks conformance claims |

## Completion Priorities

1. Freeze governance and specification freeze process.
2. Resolve registry source-of-truth policy.
3. Complete grammar and serialization canonicalization rules.
4. Complete validation diagnostic and report schema requirements.
5. Add conformance fixtures after rules are frozen.
6. Begin implementation only after readiness gates are passed.
