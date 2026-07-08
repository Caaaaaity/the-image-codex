# The Image Codex Metadata Schema

**Document:** Metadata Schema  
**Identifier:** `METADATA_SCHEMA`  
**Series:** Foundation Series  
**Status:** Official Working Draft  
**Version:** 1.0  
**Canonical location:** `METADATA_SCHEMA.md`

## 1. Purpose

This document defines the official metadata standard for The Image Codex. It establishes the required and optional metadata fields used to describe Foundation Series documents, architecture decision records, registries, technical standards, governance documents, historical references, and future machine-readable repository indexes.

The schema is intended to make every official Image Codex artifact identifiable, traceable, reviewable, and automatable without changing the normative meaning of any existing specification.

## 2. Scope

This schema applies to metadata about Image Codex documents and document-like artifacts, including:

- Foundation Series specifications.
- Architecture Decision Records (ADRs).
- Constitution and governance documents.
- Registry specifications and machine-readable registry artifacts.
- Technical standards, parser specifications, validator specifications, and compatibility specifications.
- Future repository manifests, generated document indexes, release indexes, and validation tooling.

This schema does not redefine the contents of any existing Image Codex specification. It defines how documents are described, classified, cross-referenced, and validated.

## 3. Design Goals

The metadata model is designed to support the following goals:

1. **Canonical identification** — every official document has a stable identifier that can be referenced consistently.
2. **Human readability** — metadata remains understandable in Markdown, document headers, manifests, and review materials.
3. **Machine validation** — fields use predictable names, controlled values, and deterministic rules suitable for CI validation.
4. **Foundation continuity** — metadata can describe existing Foundation Series documents without requiring file renames or content rewrites.
5. **Version traceability** — document versions, editions, statuses, and successor relationships can be tracked over time.
6. **Governance clarity** — publication, review, and decision status are represented separately so that draft maturity is not confused with decision authority.
7. **Registry alignment** — registry documents and machine-readable registry artifacts can be paired and validated together.
8. **Legacy accommodation** — historical names, matched files, and earlier references can be preserved without becoming canonical identifiers.

## 4. Metadata Model

The Image Codex metadata model is a document-level record. A metadata record may be represented in Markdown front matter, a JSON manifest, a generated index, or validation output.

A metadata record has four conceptual layers:

| Layer | Purpose |
|---|---|
| Identity | Names, identifiers, canonical filename, and title. |
| Classification | Document class, document type, publication track, and series. |
| Lifecycle | Version, publication status, review status, decision status, dates, and supersession information. |
| Relationships | Dependencies, related documents, registry artifacts, legacy references, and cross-references. |

The canonical field names are written in `snake_case` for machine-readable use. Human-readable Markdown may present equivalent labels, but automated systems should normalize to the canonical field names defined here.

## 5. Required Metadata Fields

Every official Image Codex metadata record MUST include the following fields:

| Field | Type | Requirement |
|---|---|---|
| `document_id` | string | Stable official identifier. |
| `title` | string | Human-readable official title. |
| `document_class` | controlled string | High-level classification. |
| `document_type` | controlled string | More specific document kind. |
| `publication_track` | controlled string | Publication stream for governance and release planning. |
| `version` | string | Document version, without filename decoration. |
| `publication_status` | controlled string | Publication maturity of the document. |
| `review_status` | controlled string | Review state of the document. |
| `decision_status` | controlled string | Decision authority or applicability state. |
| `canonical_filename` | string | Official repository filename for the described artifact. |
| `canonical_path` | string | Repository-relative path to the canonical file. |
| `summary` | string | Brief description of the document's purpose. |

## 6. Optional Metadata Fields

A metadata record MAY include the following fields when applicable:

| Field | Type | Use |
|---|---|---|
| `series` | string | Publication series, such as `Foundation Series`. |
| `edition` | string | Human-readable edition label. |
| `effective_date` | date | Date on which the document became effective. |
| `publication_date` | date | Date on which the document was published. |
| `last_reviewed` | date | Most recent completed review date. |
| `maintainer` | string | Responsible maintainer, owner, or governing body. |
| `creator` | string | Original creator when attribution is required. |
| `supersedes` | list of strings | Document IDs or versions replaced by this document. |
| `superseded_by` | string | Document ID or version that replaces this document. |
| `depends_on` | list of strings | Normative upstream dependencies. |
| `related_documents` | list of strings | Non-normative or contextual related documents. |
| `adr_references` | list of strings | ADRs that govern or explain the document. |
| `registry_artifacts` | list of strings | Machine-readable registry artifact paths. |
| `legacy_filenames` | list of strings | Historical filenames or previously circulated names. |
| `aliases` | list of strings | Non-canonical labels, abbreviations, or search terms. |
| `change_summary` | string | Summary of changes from the previous version. |
| `validation_notes` | string | Notes for validation tools or maintainers. |
| `external_references` | list of strings | External references, if permitted by governance. |

## 7. Field Definitions

### `document_id`

The stable official identifier for the document. For numbered Image Codex documents, this value SHOULD follow the pattern `IC-AAA-NNN`, where `AAA` is the document series code and `NNN` is a three-digit number. Repository-level standards without an assigned `IC-` identifier MAY use a stable uppercase identifier such as `METADATA_SCHEMA` until a formal series identifier is assigned.

### `title`

The official human-readable document title. The title SHOULD match the title used in document indexes, manifests, and publication materials.

### `document_class`

The high-level classification of the document. Allowed values are defined in [Document Class](#document-class).

### `document_type`

The specific kind of document within its class. Allowed values are defined in [Document Type](#document-type).

### `publication_track`

The publication stream that governs how the document is reviewed, approved, and released. Allowed values are defined in [Publication Track](#publication-track).

### `version`

The version assigned to the document. The preferred form is semantic or edition-style versioning such as `1.0`, `1.1`, or `2.0`. Filenames MAY include a decorated form such as `v1.0`, but the metadata value SHOULD omit the leading `v` unless a future release process requires otherwise.

### `publication_status`

The maturity of the published artifact. Publication status answers whether the document is an official edition, official working draft, reviewed working draft, draft, deprecated document, or historical reference.

### `review_status`

The state of review. Review status answers whether the document is unreviewed, under review, reviewed, approved, ratified, or retired.

### `decision_status`

The authority of a decision embodied by or referenced by the document. Decision status is especially important for ADRs and governance documents.

### `canonical_filename`

The official filename of the document or artifact as stored in the repository. The filename MUST NOT be inferred from title alone when a canonical filename is already recorded.

### `canonical_path`

The repository-relative path to the canonical file. For root-level files, this is the same as `canonical_filename`.

### `summary`

A concise statement of the document purpose. The summary SHOULD be short enough to appear in generated indexes and manifests.

### Relationship fields

Relationship fields (`supersedes`, `superseded_by`, `depends_on`, `related_documents`, `adr_references`, and `registry_artifacts`) SHOULD use document IDs when referencing Image Codex documents and repository-relative paths when referencing files.

## 8. Allowed Values

### Publication Status

| Value | Meaning |
|---|---|
| `Official Edition` | Stable official document approved for authoritative use. |
| `Official Working Draft` | Officially maintained draft that may still change before edition release. |
| `Reviewed Working Draft` | Draft that has received review but is not an official edition. |
| `Draft` | Work in progress without completed review. |
| `Deprecated` | No longer recommended for current use but retained for compatibility or history. |
| `Historical Reference` | Preserved for traceability and historical context only. |

### Review Status

| Value | Meaning |
|---|---|
| `Unreviewed` | No formal review has been completed. |
| `In Review` | Formal review is active. |
| `Reviewed` | Review has been completed, but final approval or ratification may be separate. |
| `Approved` | Accepted for publication or use by the appropriate authority. |
| `Ratified` | Formally adopted as binding architecture, governance, or decision record. |
| `Retired` | Review lifecycle is closed and the artifact is no longer active. |

### Decision Status

| Value | Meaning |
|---|---|
| `Proposed` | Proposed but not accepted. |
| `Accepted` | Accepted as the current decision or direction. |
| `Ratified` | Ratified as binding within its governance scope. |
| `Superseded` | Replaced by a later decision or document. |
| `Deprecated` | Retained but discouraged for new use. |
| `Rejected` | Considered and rejected. |
| `Not Applicable` | The document does not represent a decision. |

### Document Class

| Value | Meaning |
|---|---|
| `architecture_decision_record` | ADR documenting an architectural or governance decision. |
| `constitution` | Foundational constitutional authority. |
| `governance` | Governance rules, processes, or contributor authority. |
| `technical_standard` | Normative technical standard. |
| `technical_specification` | Normative or implementation-facing specification. |
| `registry` | Registry specification or registry family document. |
| `reference_architecture` | Reference architecture or architecture model. |
| `publication_style_guide` | Publication, formatting, or editorial standard. |
| `metadata_schema` | Metadata standard or schema document. |
| `repository_documentation` | Repository-level documentation that is not itself a specification. |
| `historical_reference` | Preserved non-current artifact. |

### Document Type

| Value | Meaning |
|---|---|
| `adr` | Architecture Decision Record. |
| `constitution` | Constitution document. |
| `governance_specification` | Governance process or authority specification. |
| `semantic_standard` | Semantic model or terminology standard. |
| `visual_language_standard` | Visual language and representation standard. |
| `codex_brain_specification` | Codex Brain architecture or execution specification. |
| `serialization_specification` | Serialization rules and formats. |
| `parser_specification` | Parser behavior and requirements. |
| `validator_specification` | Validation behavior and requirements. |
| `translation_specification` | Translation behavior and requirements. |
| `compatibility_specification` | Compatibility and interoperability requirements. |
| `reference_architecture` | Reference architecture document. |
| `publication_style_guide` | Publication and style guidance. |
| `registry_specification` | Registry document defining a controlled vocabulary or registry. |
| `machine_readable_registry` | JSON or other machine-readable registry artifact. |
| `metadata_schema` | Metadata field and validation schema. |
| `repository_index` | Generated or curated repository index. |
| `repository_policy` | Repository policy document. |

### Publication Track

| Value | Meaning |
|---|---|
| `foundation` | Foundation Series material defining the initial authoritative corpus. |
| `governance` | Governance, authority, process, and contributor rules. |
| `architecture` | Architecture models and architecture decisions. |
| `standard` | Normative technical standards. |
| `registry` | Registry documents and machine-readable registry artifacts. |
| `operations` | Repository operations, release operations, and automation. |
| `historical` | Preserved historical material not intended for current normative use. |

## 9. Metadata Rules

### ADR Metadata

ADR metadata MUST include:

- `document_id` using the `IC-ADR-NNN` pattern.
- `document_class` set to `architecture_decision_record`.
- `document_type` set to `adr`.
- `publication_track` set to `architecture` unless the ADR is explicitly governance-only.
- `decision_status` set to one of `Proposed`, `Accepted`, `Ratified`, `Superseded`, `Deprecated`, or `Rejected`.

Ratified ADRs SHOULD use `publication_status` of `Official Edition` and `review_status` of `Ratified` when they are part of the official Foundation Series.

### Constitution Metadata

Constitution metadata MUST include:

- `document_class` set to `constitution`.
- `document_type` set to `constitution`.
- `publication_track` set to `foundation` or `governance`.
- `decision_status` set to `Ratified` when the constitution is authoritative.

The Constitution SHOULD be treated as a normative upstream dependency for governance specifications, ADRs, and official technical standards.

### Registry Metadata

Registry metadata MUST distinguish between registry specifications and machine-readable registry artifacts.

A registry specification MUST use:

- `document_class` set to `registry`.
- `document_type` set to `registry_specification`.
- `publication_track` set to `registry`.

A machine-readable registry artifact MUST use:

- `document_class` set to `registry`.
- `document_type` set to `machine_readable_registry`.
- `publication_track` set to `registry`.
- `canonical_path` pointing to the machine-readable artifact.

Registry specifications SHOULD list their corresponding JSON artifacts in `registry_artifacts`. Registry artifacts SHOULD reference their governing registry specification through `depends_on` or an equivalent manifest relationship.

### Technical Standard Metadata

Technical standards and specifications MUST include:

- `document_class` set to `technical_standard`, `technical_specification`, `reference_architecture`, or `publication_style_guide` as appropriate.
- `publication_track` set to `standard`, `architecture`, or `foundation` as appropriate.
- `decision_status` set to `Not Applicable` unless the document itself records a binding decision.

Technical standards SHOULD list applicable ADRs in `adr_references` and SHOULD list normative upstream dependencies in `depends_on`.

## 10. Cross-Reference Rules

1. Cross-references to official Image Codex documents SHOULD use `document_id` rather than filename.
2. Cross-references to files SHOULD use repository-relative paths.
3. Cross-references MUST NOT depend on display titles alone.
4. A document MAY reference a future or pending document, but the reference MUST be marked as proposed, pending, or future in the appropriate relationship field or validation notes.
5. Circular references SHOULD be avoided for normative dependencies. Contextual circular references MAY be allowed in `related_documents`.
6. ADR references SHOULD point to ADR IDs and SHOULD NOT use informal shorthand unless the shorthand is listed as an alias.
7. Registry records SHOULD reference registry-controlled identifiers rather than duplicating uncontrolled labels.

## 11. Legacy and Historical Reference Rules

1. Legacy filenames MUST be recorded in `legacy_filenames` and MUST NOT replace `canonical_filename`.
2. Historical aliases MAY be recorded in `aliases` to improve searchability.
3. Historical references MUST NOT be treated as current normative dependencies unless explicitly listed in `depends_on`.
4. Deprecated or superseded documents MUST identify their successor in `superseded_by` when a successor exists.
5. A legacy reference MAY remain valid for citation and audit purposes even when it is no longer canonical.
6. Validation tools SHOULD warn, rather than fail, when they encounter a known legacy filename that maps cleanly to a canonical document.

## 12. Canonical Filename Rules

Canonical filenames SHOULD be stable, descriptive, and compatible with repository automation.

For numbered Image Codex DOCX specifications, the preferred filename pattern is:

```text
IC-AAA-NNN_Descriptive_Title_vX.Y_Status_Label.docx
```

For Markdown repository standards, the preferred filename pattern is:

```text
UPPERCASE_DESCRIPTIVE_NAME.md
```

Canonical filename rules:

1. The `document_id` portion MUST match the assigned document identifier when one exists.
2. The version portion SHOULD match the `version` metadata field.
3. Status labels in filenames SHOULD be treated as display labels and normalized through `publication_status`.
4. Existing canonical filenames MUST NOT be changed merely to satisfy a preferred pattern.
5. Machine-readable registry artifacts SHOULD use stable lowercase filenames when already established by repository convention.
6. Filename changes require explicit migration planning, legacy filename recording, and manifest updates.

## 13. Metadata Templates

### Generic Document

```yaml
document_id: "DOCUMENT_ID"
title: "Document Title"
document_class: "technical_specification"
document_type: "repository_policy"
publication_track: "operations"
version: "1.0"
publication_status: "Draft"
review_status: "Unreviewed"
decision_status: "Not Applicable"
canonical_filename: "DOCUMENT_FILENAME.md"
canonical_path: "DOCUMENT_FILENAME.md"
summary: "Brief description of the document."
series: "Foundation Series"
depends_on: []
related_documents: []
legacy_filenames: []
```

### Constitution

```yaml
document_id: "IC-CON-001"
title: "Image Codex Constitution"
document_class: "constitution"
document_type: "constitution"
publication_track: "foundation"
version: "1.0"
publication_status: "Official Edition"
review_status: "Ratified"
decision_status: "Ratified"
canonical_filename: "IC-CON-001_Image_Codex_Constitution_v1.0_Official_Edition.docx"
canonical_path: "IC-CON-001_Image_Codex_Constitution_v1.0_Official_Edition.docx"
summary: "Foundational principles and governance authority for The Image Codex."
```

### ADR

```yaml
document_id: "IC-ADR-001"
title: "Architecture Decision Record Title"
document_class: "architecture_decision_record"
document_type: "adr"
publication_track: "architecture"
version: "1.0"
publication_status: "Official Edition"
review_status: "Ratified"
decision_status: "Ratified"
canonical_filename: "IC-ADR-001_v1.0_Official_Edition.docx"
canonical_path: "IC-ADR-001_v1.0_Official_Edition.docx"
summary: "Decision summary."
depends_on:
  - "IC-CON-001"
```

### Registry

```yaml
document_id: "IC-REG-001"
title: "Official Namespace Registry"
document_class: "registry"
document_type: "registry_specification"
publication_track: "registry"
version: "1.0"
publication_status: "Reviewed Working Draft"
review_status: "Reviewed"
decision_status: "Not Applicable"
canonical_filename: "IC-REG-001_Official_Namespace_Registry_v1.0_Reviewed_Working_Draft.docx"
canonical_path: "IC-REG-001_Official_Namespace_Registry_v1.0_Reviewed_Working_Draft.docx"
summary: "Official namespace registry specification."
registry_artifacts:
  - "ic_reg_001.json"
```

### Technical Standard

```yaml
document_id: "IC-SEM-001"
title: "Semantic Standard"
document_class: "technical_standard"
document_type: "semantic_standard"
publication_track: "standard"
version: "1.0"
publication_status: "Official Working Draft"
review_status: "Reviewed"
decision_status: "Not Applicable"
canonical_filename: "IC-SEM-001_Semantic_Standard_v1.0_Official_Working_Draft.docx"
canonical_path: "IC-SEM-001_Semantic_Standard_v1.0_Official_Working_Draft.docx"
summary: "Semantic terminology and conceptual framework for The Image Codex."
adr_references:
  - "IC-ADR-001"
```

## 14. Validation Rules

Validation tools SHOULD enforce the following rules:

1. Required fields MUST be present and non-empty.
2. Controlled-value fields MUST use one of the allowed values defined in this document.
3. `canonical_path` MUST resolve to an existing repository file when validating the current repository state.
4. `canonical_filename` MUST match the final path segment of `canonical_path`.
5. `document_id` values MUST be unique within a manifest or generated index.
6. Relationship fields MUST be lists when present, except `superseded_by`, which MAY be a single string.
7. Every `depends_on`, `related_documents`, and `adr_references` value SHOULD resolve to a known `document_id` or be explicitly marked as external.
8. Registry specification records SHOULD resolve every listed `registry_artifacts` path.
9. Machine-readable registry artifacts SHOULD identify or be linked to their governing registry specification.
10. Deprecated, superseded, and historical records SHOULD include explanatory relationship or validation notes.
11. Validation MUST NOT require renaming existing files unless a repository migration explicitly authorizes it.

## 15. Manifest Migration Strategy

The manifest migration strategy is incremental and compatibility-preserving:

1. **Inventory current records** — identify every existing manifest entry, document file, and machine-readable registry artifact.
2. **Map existing fields** — map current manifest fields to the canonical metadata fields defined here.
3. **Add missing fields** — add required metadata fields where absent, using existing repository facts as the source of truth.
4. **Normalize statuses** — convert filename status labels and manifest status values to the controlled `publication_status`, `review_status`, and `decision_status` fields.
5. **Record legacy data** — preserve historical filenames, matched names, aliases, and previous references in `legacy_filenames` or `aliases`.
6. **Validate paths** — confirm that `canonical_path` and registry artifact paths resolve correctly.
7. **Introduce schema validation** — add a machine-readable schema after the human-readable standard is accepted.
8. **Automate reporting** — generate document indexes, status summaries, and consistency warnings from the migrated manifest.

No migration step should require modifying official DOCX specifications solely for metadata normalization.

## 16. Future Automation

Future automation MAY include:

- A JSON Schema for metadata records and repository manifests.
- CI validation for required metadata fields and controlled values.
- File-existence checks for `canonical_path` and `registry_artifacts`.
- Cross-reference validation for `depends_on`, `related_documents`, and `adr_references`.
- Generated document indexes grouped by document class, publication track, and status.
- Status dashboards showing official editions, working drafts, reviewed drafts, deprecated documents, and historical references.
- Release readiness checks that confirm versions, statuses, filenames, registry artifacts, and manifest records are aligned.
- Migration reports that identify missing metadata, legacy filenames, and ambiguous cross-references.

## 17. Appendix

### Complete metadata schema example

```yaml
document_id: "IC-VAL-001"
title: "Validator Specification"
document_class: "technical_specification"
document_type: "validator_specification"
publication_track: "standard"
version: "1.0"
publication_status: "Reviewed Working Draft"
review_status: "Reviewed"
decision_status: "Not Applicable"
canonical_filename: "IC-VAL-001_Validator_Specification_v1.0_Reviewed_Working_Draft.docx"
canonical_path: "IC-VAL-001_Validator_Specification_v1.0_Reviewed_Working_Draft.docx"
summary: "Defines validation behavior and requirements for Image Codex artifacts."
series: "Foundation Series"
edition: "v1.0 Reviewed Working Draft"
effective_date: null
publication_date: "2026-07-05"
last_reviewed: "2026-07-05"
maintainer: "The Image Codex Project"
creator: "Cait Obrien"
supersedes: []
superseded_by: null
depends_on:
  - "IC-CON-001"
  - "IC-SEM-001"
related_documents:
  - "IC-PAR-001"
  - "IC-SER-001"
adr_references:
  - "IC-ADR-001"
registry_artifacts: []
legacy_filenames: []
aliases:
  - "Validator Spec"
change_summary: "Initial Foundation Series validator specification."
validation_notes: "Metadata example for schema documentation."
external_references: []
```

### Field relationship diagram (Markdown)

```text
Metadata Record
├── Identity
│   ├── document_id
│   ├── title
│   ├── canonical_filename
│   └── canonical_path
├── Classification
│   ├── document_class
│   ├── document_type
│   ├── publication_track
│   └── series
├── Lifecycle
│   ├── version
│   ├── edition
│   ├── publication_status
│   ├── review_status
│   ├── decision_status
│   ├── publication_date
│   ├── effective_date
│   └── last_reviewed
└── Relationships
    ├── depends_on
    ├── related_documents
    ├── adr_references
    ├── registry_artifacts
    ├── supersedes
    ├── superseded_by
    ├── legacy_filenames
    └── aliases
```

### Status transition table

| From | To | Allowed? | Notes |
|---|---|---:|---|
| `Draft` | `Reviewed Working Draft` | Yes | Requires completed review. |
| `Draft` | `Official Working Draft` | Yes | Requires official publication authority. |
| `Reviewed Working Draft` | `Official Working Draft` | Yes | Indicates official maintenance before edition release. |
| `Official Working Draft` | `Official Edition` | Yes | Requires final approval or ratification as applicable. |
| `Reviewed Working Draft` | `Official Edition` | Yes | Allowed when review and approval are completed together. |
| `Official Edition` | `Deprecated` | Yes | Requires a replacement, rationale, or governance decision. |
| `Official Edition` | `Historical Reference` | Conditional | Allowed only when no longer current and preserved for traceability. |
| `Deprecated` | `Historical Reference` | Yes | Indicates archival use only. |
| `Superseded` decision | `Ratified` decision | No | A superseded decision cannot become current without a new decision record. |
| `Rejected` decision | `Accepted` decision | No | A rejected proposal requires a new or revised decision record. |
