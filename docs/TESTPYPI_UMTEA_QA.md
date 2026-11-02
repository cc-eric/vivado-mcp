# TestPyPI-only packaging rehearsal — UMTEA V4.1

This branch is a deliberately isolated **release test**, not the production Vivado MCP distribution. Do **not** merge this branch into `main` and do not point the Windows 168 deployment authority to it.

- Source: `cc-eric/vivado-mcp` (existing project code, still owned by its contributors).
- TestPyPI distribution: `vivado-mcp-cc-eric`.
- Test distribution version: `0.0.1`; not an upstream `vivado-mcp` release.
- Python import package and executable entry point are kept unchanged.
- Project metadata links to the fork and separately acknowledges upstream.
- No Git tag is created and no production policy or CI trust policy is changed.
- Both V4.1 PyPI switches remain disabled and public PyPI must never be the destination.
- Full publishing integration in V4.1 requires its native-host committed SHA, trusted CI receipts and an exact matching release tag; this branch does **not** claim those requirements are satisfied.
- Before any real TestPyPI upload: verify account ownership for that separate test index; keep the TestPyPI API Token off GitHub and in root-owned `0600` NAS credentials. For the first version of a new project, TestPyPI may require a temporary account-scoped token until the package exists, then replace with project-scoped credentials.
- Validation: run real project pytest, build wheel and sdist from the exact branch SHA, run `twine check`, test isolated installation, then compare SHA256 against the TestPyPI JSON index without uploading until credentials are authorized.

**This branch is for review and isolated evidence only.** The official PyPI `vivado-mcp` and Windows 168 deployment remain unchanged.
