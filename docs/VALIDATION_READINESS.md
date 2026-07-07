# Validation Readiness

## Purpose

This document evaluates readiness for validation work using the existing specifications and registries. It is a planning artifact and does not create validator behavior.

## Current Readiness Summary

| Area | Readiness | Rationale |
| --- | --- | --- |
| Validation stages | Partial | Lexical, syntactic, structural, referential, semantic, and profile stages are named, but stage contracts require more detail. |
| Severity classes | Partial | Error, warning, and notice categories exist, but stable codes and message formats are not defined. |
| Registry references | Partial | JSON registries exist, but the source-of-truth relationship between `.docx` registries and JSON mirrors needs formalization. |
| Structural rules | Partial | The canonical hierarchy is established by ADR-005 and VLS, but executable fixtures are absent. |
| Semantic rules | Partial | Semantic boundaries exist, but machine-checkable semantic conformance cases are absent. |
| Report format | Partial | Required fields are identified, but schema and examples are not frozen. |
| Test suite | Planned | Existing documents reference future conformance suites. |

## Validation Readiness Gates

### Gate 1: Source-of-Truth Confirmation

The project must identify whether registry JSON files, registry `.docx` files, or a generated artifact is authoritative for validation input.

### Gate 2: Rule Inventory

Each validation stage must list the normative rules it enforces and cite the governing specification section.

### Gate 3: Diagnostic Model

The validator specification must define stable diagnostic identifiers, severity handling, location reporting, and final validity calculation.

### Gate 4: Fixture Set

A validation fixture set must include valid documents, invalid documents, warning-producing documents, registry resolution examples, and compatibility examples.

### Gate 5: Conformance Profile Policy

If partial validation is allowed, profile names and mandatory support levels must be defined before claiming conformance.

## Readiness Decision

The repository is ready for validator planning and requirement analysis. It is not yet ready for a production conformance validator because machine-checkable rule catalogs, diagnostic identifiers, schema artifacts, and fixture suites are not present.

## Dependencies

- `docs/SPEC_DEPENDENCY_MAP.md`
- `docs/BLOCKING_DEPENDENCIES.md`
- `docs/SPECIFICATION_COMPLETION_TRACKER.md`
