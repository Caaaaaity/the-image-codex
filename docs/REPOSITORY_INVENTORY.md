# Repository Inventory Report

## Scope and Method

This inventory was prepared during Phase 0 by recursively inspecting repository directories and reading tracked text, JSON, and `.docx` document content. It excludes Git internals from the product inventory.

## Directory Inventory

| Directory | Purpose | Status |
| --- | --- | --- |
| `/` | Root standards publication package containing authority documents, registries, process files, and Phase 0 structure summary. | Complete |
| `.github/` | GitHub process automation and templates. | Complete |
| `.github/ISSUE_TEMPLATE/` | Issue templates for architecture, bugs, documentation, registries, and clarification requests. | Complete |
| `docs/` | Phase 0 planning, readiness, inventory, and roadmap documentation. | Complete |

## File Inventory

| File | Purpose | State | Relationships and Dependencies |
| --- | --- | --- | --- |
| `.gitignore` | Excludes OS, editor, Python, Office temporary, build, Node, log, and environment files. | Complete | Supports repository hygiene. |
| `.github/pull_request_template.md` | Pull request checklist for summary, issue linkage, change type, alignment, compatibility, documentation, and contribution process. | Complete | References Constitution, ADRs, style guide, registries, and changelog. |
| `.github/ISSUE_TEMPLATE/architecture_proposal.md` | Template for significant architecture changes and possible ADR creation. | Complete | Depends on Constitution and ADR alignment. |
| `.github/ISSUE_TEMPLATE/bug_report.md` | Template for reporting specification or registry bugs. | Complete | Supports clarification and correction workflow. |
| `.github/ISSUE_TEMPLATE/config.yml` | Disables blank issues and links discussions, documentation, and Constitution. | Complete | Points contributors to README and Constitution. |
| `.github/ISSUE_TEMPLATE/documentation_improvement.md` | Template for documentation improvements. | Complete | Supports non-architectural editorial work. |
| `.github/ISSUE_TEMPLATE/registry_addition_request.md` | Template for proposing registry additions with JSON example and alignment checklist. | Complete | Depends on official registry structure and Constitution. |
| `.github/ISSUE_TEMPLATE/specification_clarification.md` | Template for specification ambiguity and clarification requests. | Complete | Supports draft stabilization. |
| `CHANGELOG.md` | Records foundation release contents and planned releases. | Complete | Lists specification families, ADRs, registries, and roadmap themes. |
| `CONTRIBUTING.md` | Defines contribution requirements, authority expectations, normative language, and process. | Complete | Requires reading Constitution and ADRs; references style guide and registries. |
| `LICENSE_PENDING.md` | Records that licensing is pending and rights are reserved until selection. | Planned | Blocks public reuse and implementation packaging decisions. |
| `README.md` | Public repository overview and entry point. | Complete | Introduces the project and references core standards. |
| `IC-CON-001_Image_Codex_Constitution_v1.0_Official_Edition.docx` | Supreme governing document defining purpose, principles, authority, governance, and long-term direction. | Frozen | Highest authority for all official components. |
| `IC-ADR-001_v1.0_Official_Edition.docx` | Accepted ADR establishing The Image Codex as a visual language standard rather than prompt collection. | Frozen | Depends on Constitution; informs all standards. |
| `IC-ADR-002_v1.0_Official_Edition.docx` | Accepted ADR adopting layered standards architecture. | Frozen | Governs separation of responsibilities across specs. |
| `IC-ADR-003_v1.0_Official_Edition_MATCHED.docx` | Accepted ADR adopting object-oriented language architecture. | Frozen | Governs object identity and registry-driven concepts. |
| `IC-ADR-004_v1.0_Official_Edition_MATCHED.docx` | Accepted ADR adopting knowledge graph architecture. | Frozen | Governs semantic relationships among objects. |
| `IC-ADR-005_v1.0_Official_Edition.docx` | Accepted ADR adopting canonical structural model: Visual Program, Scene, Subject, Object. | Frozen | Governs document organization. |
| `IC-VLS-001_Visual_Language_Standard_v1.0_Official_Working_Draft.docx` | Defines formal language structure, grammar, syntax, object model, namespaces, identifiers, composition, validation, extensibility, and conformance boundaries. | Draft | Depends on Constitution, ADRs, Semantic Standard, Codex Brain, and registries. |
| `IC-SEM-001_Semantic_Standard_v1.0_Official_Working_Draft.docx` | Defines semantic meaning and canonical concept interpretation boundaries. | Draft | Depends on Constitution, ADRs, and registries. |
| `IC-CBS-001_Codex_Brain_Specification_v1.0_Official_Working_Draft.docx` | Defines interpretation, constraint handling, scene planning, conflict resolution, prompt assembly, translation coordination, evaluation, profiles, logging, and conformance. | Draft | Operates after parsing, structural validation, and semantic validation. |
| `IC-ARC-001_Reference_Architecture_v1.0_Reviewed_Working_Draft.docx` | Describes reference components and flows among authoring, validation, semantic engine, Codex Brain, translator, model adapter, and image generation system. | Draft | Must not redefine grammar, semantics, or execution rules. |
| `IC-CMP-001_Compatibility_Specification_v1.0_Reviewed_Working_Draft.docx` | Defines compatibility planning for evolution and implementation impact. | Draft | Depends on governance, versioning, and registries. |
| `IC-GOV-001_Governance_Specification_v1.0_Reviewed_Working_Draft.docx` | Defines governance process for standards evolution. | Draft | Subordinate to Constitution. |
| `IC-PAR-001_Parser_Specification_v1.0_Reviewed_Working_Draft.docx` | Defines parser planning and boundaries. | Draft | Depends on VLS grammar and syntax. |
| `IC-PSG-001_Publication_Style_Guide_v1.0_Reviewed_Working_Draft.docx` | Defines publication and style conventions. | Draft | Supports consistent official documents. |
| `IC-SER-001_Serialization_Specification_v1.0_Reviewed_Working_Draft.docx` | Defines storage, exchange, canonicalization, metadata, and round-trip expectations. | Draft | Depends on canonical structure and registry references. |
| `IC-TRN-001_Translation_Specification_v1.0_Reviewed_Working_Draft.docx` | Defines translation boundaries for model-specific output. | Draft | Depends on Semantic Standard and Codex Brain outputs. |
| `IC-VAL-001_Validator_Specification_v1.0_Reviewed_Working_Draft.docx` | Defines validation stages, severity classes, and validation reports. | Draft | Depends on VLS, Semantic Standard, and registries. |
| `IC-REG-001_Official_Namespace_Registry_v1.0_Reviewed_Working_Draft.docx` | Namespace registry source document. | Draft | Mirrored by `ic_reg_001.json`. |
| `IC-REG-002_Official_Object_Registry_v1.0_Reviewed_Working_Draft.docx` | Object registry source document. | Draft | Mirrored by `ic_reg_002.json`; depends on object architecture. |
| `IC-REG-003_Official_Attribute_Registry_v1.0_Reviewed_Working_Draft.docx` | Attribute registry source document. | Draft | Mirrored by `ic_reg_003.json`. |
| `IC-REG-004_Official_Modifier_Registry_v1.0_Reviewed_Working_Draft.docx` | Modifier registry source document. | Draft | Mirrored by `ic_reg_004.json`. |
| `IC-REG-005_Official_Relationship_Registry_v1.0_Reviewed_Working_Draft.docx` | Relationship registry source document. | Draft | Mirrored by `ic_reg_005.json`; depends on knowledge graph architecture. |
| `IC-REG-006_Official_Identifier_Registry_v1.0_Reviewed_Working_Draft.docx` | Identifier registry source document. | Draft | Mirrored by `ic_reg_006.json`. |
| `ic_reg_001.json` | Machine-readable namespace registry mirror. | Draft | Mirrors `IC-REG-001`; source-of-truth policy unresolved. |
| `ic_reg_002.json` | Machine-readable object registry mirror. | Draft | Mirrors `IC-REG-002`; source-of-truth policy unresolved. |
| `ic_reg_003.json` | Machine-readable attribute registry mirror. | Draft | Mirrors `IC-REG-003`; source-of-truth policy unresolved. |
| `ic_reg_004.json` | Machine-readable modifier registry mirror. | Draft | Mirrors `IC-REG-004`; source-of-truth policy unresolved. |
| `ic_reg_005.json` | Machine-readable relationship registry mirror. | Draft | Mirrors `IC-REG-005`; source-of-truth policy unresolved. |
| `ic_reg_006.json` | Machine-readable identifier registry mirror. | Draft | Mirrors `IC-REG-006`; source-of-truth policy unresolved. |
| `PROJECT_STRUCTURE.md` | Phase 0 structure summary, naming conventions, formatting conventions, and organization recommendation. | Complete | Cross-references Phase 0 docs. |
| `docs/REPOSITORY_INVENTORY.md` | Detailed repository inventory report. | Complete | Supports PR description and future organization planning. |
| `docs/SPEC_DEPENDENCY_MAP.md` | Dependency map among authority, standards, registries, and planning docs. | Complete | Feeds blockers, requirements, readiness, and critical path. |
| `docs/IMPLEMENTATION_REQUIREMENTS.md` | Implementation-neutral readiness requirements. | Complete | Depends on dependency map and blockers. |
| `docs/VALIDATION_READINESS.md` | Validation readiness assessment and gates. | Complete | Depends on validator spec, registries, and blocker list. |
| `docs/BLOCKING_DEPENDENCIES.md` | Implementation and freeze blockers. | Complete | Feeds critical path and roadmap. |
| `docs/SPECIFICATION_COMPLETION_TRACKER.md` | Completion state tracker for document families. | Complete | Uses repository-observed status labels. |
| `docs/IMPLEMENTATION_TASK_ROADMAP.md` | Future task roadmap after Phase 0. | Complete | Depends on critical path. |
| `docs/CRITICAL_PATH.md` | Dependency-ordered sequence from planning to implementation. | Complete | Depends on blockers and readiness gates. |
| `docs/SPECIFICATION_FREEZE_PROCESS.md` | Proposed freeze process for draft stabilization. | Complete | Subordinate to Constitution and governance. |
| `docs/VERSION_CONTROL_STRATEGY.md` | Branch, commit, document, registry, PR, and release strategy. | Complete | Supports repository governance and traceability. |

## Duplicate or Overlapping Documents

- Registry information exists in both `.docx` and JSON form for all six registries. This is intentional but needs a source-of-truth and synchronization policy.
- ADR-003 and ADR-004 filenames include `_MATCHED`, unlike the other ADR filenames. The content is accepted official edition, but filename consistency is uneven.
- README, CONTRIBUTING, CHANGELOG, and GitHub templates overlap in contributor guidance; no harmful duplication was found.
- Reference Architecture and Codex Brain Specification both discuss execution flow, but the Reference Architecture describes component relationships while Codex Brain defines execution-layer behavior.

## Missing Documents or Artifacts Implied by Current Architecture

- Formal registry source-of-truth policy.
- Conformance fixture suite.
- Machine-readable parser grammar artifact, if approved by VLS.
- Validation diagnostic code catalog and report schema.
- Canonical serialization schema or equivalent artifact.
- Compatibility test policy and migration fixture set.
- License decision.
- Specification freeze record or release checklist.

## Inconsistencies Discovered

- The Constitution file name says official edition, while its internal status line says ratified draft.
- ADR filename conventions are inconsistent because ADR-003 and ADR-004 include `_MATCHED`.
- Registry content is present in both `.docx` and JSON, but the authoritative source is not declared.
- Formal documents are mostly binary `.docx`, which limits automated diff review.
- Foundation release status is clear at a high level, but implementation conformance artifacts are not present.

## Recommended Repository Organization Diagram

```text
the-image-codex/
├── authority/
│   ├── constitution/
│   └── adr/
├── standards/
│   ├── core/
│   ├── implementation/
│   ├── governance/
│   └── publication/
├── registries/
│   ├── documents/
│   └── json/
├── docs/
│   ├── planning/
│   ├── readiness/
│   └── inventory/
└── .github/
    ├── ISSUE_TEMPLATE/
    └── pull_request_template.md
```

No files were moved in Phase 0 because existing links and publication expectations should remain stable until a governed reorganization is approved.

## Maturity Summary

The repository is at Foundation Specification Development maturity. Foundational authority is strong: the Constitution and five accepted ADRs establish identity, layering, object orientation, knowledge graph architecture, and structural model. Core and implementation specifications are written as working drafts or reviewed working drafts. The repository is not yet implementation-mature because grammar freeze, registry source-of-truth policy, validation diagnostics, serialization canonicalization, compatibility fixtures, and conformance suites are not present.

## Recommended Roadmap After Phase 0

1. Stabilize governance and freeze process.
2. Resolve registry source-of-truth and synchronization.
3. Complete VLS grammar and canonical structure freeze.
4. Complete validator diagnostics, report schema, and rule catalog.
5. Complete serialization canonical form and round-trip fixtures.
6. Add conformance fixture suites.
7. Build reference parser and validator.
8. Build serializer and compatibility tooling.
9. Prototype Codex Brain and translation adapters after validated inputs are stable.
10. Select and publish license.
