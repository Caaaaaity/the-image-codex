# Project Structure

## Purpose

This document records the repository structure observed during Phase 0 Planning Foundation work. It is descriptive rather than normative: it does not redefine the Constitution, ADRs, specifications, registries, parser behavior, validator behavior, schemas, or implementation architecture.

## Authority Order

Planning documents in this repository use the following authority order:

1. `IC-CON-001_Image_Codex_Constitution_v1.0_Official_Edition.docx` as the supreme governing document.
2. Ratified ADRs `IC-ADR-001` through `IC-ADR-005` as accepted foundational architecture.
3. Official Working Draft core standards: `IC-VLS-001`, `IC-SEM-001`, and `IC-CBS-001`.
4. Reviewed Working Draft implementation, governance, compatibility, publication, architecture, and registry documents.
5. JSON registry mirrors `ic_reg_001.json` through `ic_reg_006.json`.
6. Repository process files, templates, and Phase 0 planning documents.

## Current Top-Level Organization

```text
the-image-codex/
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── pull_request_template.md
├── docs/
│   └── Phase 0 planning foundation documents
├── IC-*.docx
├── ic_reg_*.json
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE_PENDING.md
├── PROJECT_STRUCTURE.md
└── README.md
```

## Document Families

### Constitutional and Architectural Authority

- Constitution: one `.docx` file, official edition, supreme authority.
- ADRs: five `.docx` files, accepted official editions, foundational architecture.

### Core Technical Standards

- Visual Language Standard: grammar, syntax, structure, namespaces, identifiers, composition, validation requirements, extensibility, and conformance boundaries.
- Semantic Standard: meaning, semantic objects, graph relationships, canonical definitions, and semantic resolution boundaries.
- Codex Brain Specification: interpretation and execution layer after parsing and validation.

### Implementation and Ecosystem Standards

- Parser, validator, serialization, translation, compatibility, governance, reference architecture, and publication style guide documents are present as reviewed working drafts.
- These documents define planning dependencies but are not treated by Phase 0 as frozen implementation-ready schemas.

### Registries

- Six registry `.docx` documents define namespace, object, attribute, modifier, relationship, and identifier registries.
- Six JSON files mirror the same registry families in machine-readable draft form.

### Repository Process Files

- `README.md`, `CONTRIBUTING.md`, `CHANGELOG.md`, `LICENSE_PENDING.md`, `.gitignore`, issue templates, and the pull request template define publication and contribution process expectations.

## Current Naming Conventions

- Formal documents use uppercase document identifiers and long descriptive filenames.
- JSON registry mirrors use lowercase snake-case filenames: `ic_reg_001.json` through `ic_reg_006.json`.
- GitHub templates use lowercase descriptive filenames under `.github/ISSUE_TEMPLATE/`.
- Phase 0 planning documents use uppercase descriptive Markdown filenames under `docs/`, except `PROJECT_STRUCTURE.md` at repository root.

## Formatting Conventions

- Formal specification documents use metadata blocks with document ID, title or status, version, authority, publication track, language, review status, and related documents.
- Markdown process files use ATX headings, bullet lists, and checklist syntax.
- JSON registries use a consistent top-level shape with `document_id`, `title`, `version`, `status`, and `records`.

## Recommended Organization Diagram

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
│   ├── source-documents/
│   └── json/
├── docs/
│   ├── planning/
│   ├── readiness/
│   └── inventory/
└── .github/
    ├── ISSUE_TEMPLATE/
    └── pull_request_template.md
```

This diagram is a recommendation only. Phase 0 does not move existing files because moving authoritative documents would create unnecessary churn and possible broken links.

## Cross-References

- Inventory: `docs/REPOSITORY_INVENTORY.md`
- Dependency map: `docs/SPEC_DEPENDENCY_MAP.md`
- Implementation requirements: `docs/IMPLEMENTATION_REQUIREMENTS.md`
- Roadmap: `docs/IMPLEMENTATION_TASK_ROADMAP.md`
