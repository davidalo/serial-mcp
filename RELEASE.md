# 🚀 Release Process

## Setup (one-time)

1. Create a PyPI API token at https://pypi.org/manage/account/token/
2. Add your token to `.pypi.env`:

```bash
echo "UV_PUBLISH_TOKEN=pypi-your-token-here" > .pypi.env
```

> ⚠️ Never commit `.pypi.env` - it's in `.gitignore`

## Release Steps

### 1. Bump version

Edit `pyproject.toml` and update the version:

```toml
version = "X.Y.Z"
```

### 2. Commit and tag

```bash
git add .
git commit -m "Release vX.Y.Z"
git tag vX.Y.Z
```

### 3. Push to GitHub

```bash
git push && git push --tags
```

### 4. Build and publish

```bash
source .pypi.env && uv build && uv publish
```

## Version Scheme

- **Major** (X.0.0): Breaking changes
- **Minor** (0.X.0): New features, backward compatible
- **Patch** (0.0.X): Bug fixes
