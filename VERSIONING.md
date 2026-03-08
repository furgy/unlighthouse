# Versioning Requirements

## Version Source
The canonical version is stored in `VERSION` file (format: X.Y.Z).

## Version Format
- Use Semantic Versioning (SemVer 2.0.0)
- Format: `MAJOR.MINOR.PATCH` (e.g., `1.2.3`)
- MAJOR: Incompatible API changes
- MINOR: New backward-compatible features
- PATCH: Backward-compatible bug fixes

## Version Bump Requirements
- Every push to `main` branch MUST include a version bump
- Version must be updated in both:
  - `VERSION` file
  - `package.json`
- CI will verify the version was bumped by comparing with the previous commit on main

## CI Version Check
The `test.yml` workflow includes a version check step that:
1. Fetches the previous commit on main
2. Compares VERSION file content
3. Fails if version was not bumped

## Workflow
1. Make changes to the codebase
2. Update version in `VERSION` file and `package.json`
3. Commit with descriptive message
4. Push to main - CI will verify version bump
