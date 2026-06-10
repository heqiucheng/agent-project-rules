# Shared Path-Scoped Rules

Use this directory as the shared mirror for path-scoped rules when a coding-agent toolchain supports local directory rules.

## Canonical Source

`AGENTS.md` remains the primary repository rule entry.

This directory exists to improve compatibility across tools that may not read the same root file or that support directory-scoped rule overlays.

## Recommended Use

- keep the canonical project-wide policy in `AGENTS.md`
- place path-specific constraints here when different directories need different rules
- keep mirrors aligned with the canonical source
- record which files are authoritative versus mirrored

## Do Not

- let `.agents/rules/` contradict `AGENTS.md` silently
- duplicate large rule sets without deciding which copy is canonical
- treat third-party-generated files in this directory as trusted policy without review
