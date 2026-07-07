# Specification Dependency Map

## Purpose

This map identifies dependencies among existing repository documents without creating new architecture. Missing or unresolved architectural details are recorded as dependencies rather than filled in by assumption.

## Authority Stack

```text
Constitution
└── ADR-001 through ADR-005
    ├── IC-VLS-001 Visual Language Standard
    ├── IC-SEM-001 Semantic Standard
    └── IC-CBS-001 Codex Brain Specification
        ├── IC-PAR-001 Parser Specification
        ├── IC-VAL-001 Validator Specification
        ├── IC-SER-001 Serialization Specification
        ├── IC-TRN-001 Translation Specification
        ├── IC-CMP-001 Compatibility Specification
        ├── IC-ARC-001 Reference Architecture
        ├── IC-GOV-001 Governance Specification
        ├── IC-PSG-001 Publication Style Guide
        └── IC-REG-001 through IC-REG-006 Registries
```

## Primary Dependencies

| Document | Depends On | Dependency Type |
| --- | --- | --- |
| Constitution | None | Supreme authority |
| ADR-001 | Constitution | Defines project identity as visual language standard |
| ADR-002 | Constitution, ADR-001 | Defines layered standards architecture |
| ADR-003 | Constitution, ADR-001, ADR-002 | Defines object-oriented language architecture |
| ADR-004 | Constitution, ADR-001 through ADR-003 | Defines knowledge graph semantic architecture |
| ADR-005 | Constitution, ADR-001 through ADR-004 | Defines canonical structural model |
| IC-VLS-001 | Constitution, ADRs, registries | Defines structure and grammar boundaries |
| IC-SEM-001 | Constitution, ADRs, registries | Defines canonical semantic meaning boundaries |
| IC-CBS-001 | Constitution, IC-VLS-001, IC-SEM-001, parser, validator, registries | Defines post-validation interpretation and execution boundaries |
| IC-PAR-001 | IC-VLS-001 | Depends on formal grammar and syntax completion |
| IC-VAL-001 | IC-VLS-001, IC-SEM-001, registries | Depends on grammar, semantic rules, registry identifiers, and error requirements |
| IC-SER-001 | IC-VLS-001, registries | Depends on canonical structure and metadata requirements |
| IC-TRN-001 | IC-SEM-001, IC-CBS-001, compatibility rules | Depends on resolved semantics and execution plans |
| IC-CMP-001 | Constitution, governance, registries | Depends on versioning and compatibility policy |
| IC-ARC-001 | Core standards and implementation standards | Describes component interaction without redefining their behavior |
| IC-GOV-001 | Constitution | Defines repository and standards evolution process |
| IC-PSG-001 | Governance and publication process | Defines publication consistency |
| IC-REG-001 to IC-REG-006 | Constitution, ADR-003, ADR-004 | Provide governed identifiers for language concepts |

## Blocking Dependency Themes

1. Parser readiness depends on frozen grammar, lexical rules, syntax examples, and conformance fixtures.
2. Validator readiness depends on complete validation stages, machine-readable registry references, error codes, and report schema.
3. Serializer readiness depends on canonical serialization form, metadata requirements, ordering rules, and round-trip fixtures.
4. Translator readiness depends on resolved semantic rules, compatibility rules, model adapter boundaries, and loss reporting conventions.
5. Codex Brain readiness depends on validated input contracts, semantic resolution contracts, conflict reporting, execution profiles, and trace record expectations.

## Cross-Reference Matrix

| Planning Document | Uses This Map For |
| --- | --- |
| `docs/BLOCKING_DEPENDENCIES.md` | Lists unresolved dependencies that block implementation work |
| `docs/IMPLEMENTATION_REQUIREMENTS.md` | Converts dependencies into implementation-neutral requirements |
| `docs/VALIDATION_READINESS.md` | Evaluates whether validation inputs are ready |
| `docs/SPECIFICATION_COMPLETION_TRACKER.md` | Tracks document completion and freeze readiness |
| `docs/CRITICAL_PATH.md` | Orders dependencies into a safe execution sequence |
