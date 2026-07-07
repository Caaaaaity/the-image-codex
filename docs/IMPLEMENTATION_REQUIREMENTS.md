# Implementation Requirements

## Purpose

This document identifies requirements that must be satisfied before implementation can proceed responsibly. It does not define parser algorithms, validator algorithms, schemas, grammars, registries, identifiers, or model-specific behavior.

## Implementation Boundary Principles

- Implementations must preserve canonical language structure and official semantics.
- Prompt artifacts, model adapters, and execution plans are translations or implementation artifacts, not replacements for the official language.
- Missing architecture must be escalated to the relevant specification or ADR process rather than invented inside implementation code.
- Implementations must retain traceability to document versions, registry versions, and tool versions where applicable.

## Required Inputs Before Parser Implementation

1. Frozen or explicitly versioned grammar rules from the Visual Language Standard.
2. Lexical token definitions and invalid-token behavior.
3. Canonical structural hierarchy expectations.
4. Namespace and identifier resolution boundaries.
5. Positive and negative parse fixtures.
6. Conformance profile definitions if partial parser support is permitted.

## Required Inputs Before Validator Implementation

1. Complete validation stage definitions.
2. Machine-readable registry source of truth or official synchronization policy between `.docx` and JSON registries.
3. Error, warning, and notice message requirements.
4. Location reporting requirements.
5. Validation report serialization requirements.
6. Semantic validation boundaries and conflict with execution behavior prevention.

## Required Inputs Before Serialization Implementation

1. Canonical serialization target and version metadata rules.
2. Required ordering and normalization rules.
3. Round-trip success criteria.
4. Treatment of insignificant whitespace and significant literal values.
5. Compatibility expectations for future representations.

## Required Inputs Before Codex Brain Implementation

1. Validated canonical input contract.
2. Resolved semantic input contract.
3. Constraint priority and conflict reporting requirements.
4. Execution profile declaration format.
5. Trace record fields and privacy boundary.
6. Translator and model adapter interface boundaries.

## Required Inputs Before Translation Implementation

1. Translation input artifact definition.
2. Target model capability declaration structure.
3. Loss-of-fidelity reporting rules.
4. Fallback behavior boundaries.
5. Prohibition against canonical document mutation.

## Required Repository Infrastructure

- Test fixture directories once fixtures are authorized.
- Machine-readable schema or schema-generation policy once approved.
- Registry validation checks once the registry source of truth is settled.
- Release process for specification freeze and implementation compatibility.
- Changelog requirements for specification and registry updates.

## Non-Requirements for Phase 0

Phase 0 does not require runnable parser, validator, serializer, translator, model adapter, or Codex Brain code. It establishes readiness criteria and prevents premature implementation from hard-coding unstable architectural choices.
