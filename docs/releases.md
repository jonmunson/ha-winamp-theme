# Release Process

HACS does not need a `latest` branch for this repository.

For custom theme repositories:

- if the repository has no releases, HACS uses the default branch
- if the repository has releases, HACS uses the latest GitHub release

This repository is configured for the release-based path.

## How to publish an update

1. Merge your changes into `main`.
2. Create a semantic version tag:

```bash
git tag v0.2.0
git push origin v0.2.0
```

3. GitHub Actions runs `.github/workflows/release.yaml`.
4. That workflow creates a GitHub release from the tag.
5. HACS will surface that new version as an update.

## Notes

- Use tags like `v0.1.0`, `v0.2.0`, `v1.0.0`.
- Do not use a moving `latest` branch for releases.
- Keep `main` as the development/default branch.
