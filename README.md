# The Image Codex

A formal specification ecosystem for describing, structuring, and communicating visual intent between humans and AI systems.

> **NOTE:** The Image Codex is under active development. Specifications evolve through versioned releases while remaining governed by the Constitution.

## Overview

The Image Codex establishes a standardized language for visual communication through:
- **Semantic Standards** – Unified terminology and conceptual framework
- **Visual Language** – Standardized notation and representation
- **Serialization Formats** – Multi-format support (JSON, XML, and more)
- **Official Registries** – Authoritative object, attribute, relationship, and identifier definitions
- **Governance** – Clear principles, architecture decisions, and evolution processes

## Current Status

- **Version:** 1.0.0 Foundation
- **Phase:** Foundation Specification Development
- **Release:** 2026-07-05

## Architecture Hierarchy

```
The Image Codex
    ↓
Constitution
    ↓
Architectural Decision Records
    ↓
Visual Language Standard
    ↓
Semantic Standard
    ↓
Codex Brain Specification
    ↓
Reference Architecture
    ↓
Official Registries
```

## Repository Contents

| Category | Files | Purpose |
|----------|-------|----------|
| **Constitution** | `IC-CON-001_*` | Foundational principles and governance |
| **Specifications** | `IC-SEM-001_*`, `IC-VLS-001_*`, `IC-SER-001_*`, and 5+ more | Formal specifications for implementation |
| **Architecture Decisions** | `IC-ADR-001_*` through `IC-ADR-005_*` | Ratified architectural decisions |
| **Registries** | `ic_reg_001.json` through `ic_reg_006.json` | Official definitions and identifiers |

## Navigating This Project

1. **New to Image Codex?** Start with the [Constitution](./IC-CON-001_Image_Codex_Constitution_v1.0_Official_Edition.docx)
2. **Need to implement?** Review the [Reference Architecture](./IC-ARC-001_Reference_Architecture_v1.0_Reviewed_Working_Draft.docx) and [Serialization Spec](./IC-SER-001_Serialization_Specification_v1.0_Reviewed_Working_Draft.docx)
3. **Adding to registries?** See [Contributing Guidelines](./CONTRIBUTING.md)

## Official Registries

- **IC-REG-001** – Namespace Registry (namespaces: core, sem, brain, reg, ext, usr)
- **IC-REG-002** – Object Registry (visual entities, scenes, subjects, environments)
- **IC-REG-003** – Attribute Registry (color, scale, position, material, opacity, texture)
- **IC-REG-004** – Modifier Registry
- **IC-REG-005** – Relationship Registry
- **IC-REG-006** – Identifier Registry

## Contributing

All contributions must:
- ✅ Follow the Constitution and ratified ADRs (001-005)
- ✅ Preserve official concept definitions
- ✅ Maintain backward compatibility
- ✅ Align with the Publication Style Guide

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.

## License Status

⚠️ **License Pending** – All rights reserved. No use, modification, or distribution permitted without explicit permission. See [LICENSE_PENDING.md](./LICENSE_PENDING.md).

## Resources

- [CHANGELOG](./CHANGELOG.md) – Version history
- [Contributing](./CONTRIBUTING.md) – How to participate
- [Architecture Decision Records](./IC-ADR-001_v1.0_Official_Edition.docx) – Design decisions

---

**The Image Codex** – *Standardizing visual intent for the AI age.*