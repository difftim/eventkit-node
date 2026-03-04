# Fork Notes for `@difftim/eventkit-node`

## What is already prepared

- Package name: `@difftim/eventkit-node`
- Version: `1.0.4`
- Crash fix baseline: includes PR #1 from upstream
- GitHub Packages scope config: `.npmrc` + `publishConfig.registry`
- CI publish workflow: `.github/workflows/publish-gpr.yml`

## Publish from GitHub Actions

1. Create repository `difftim/eventkit-node` and push this fork.
2. Push a tag (for example `v1.0.4`).
3. GitHub Actions will run `Publish GitHub Package` and publish to `npm.pkg.github.com`.

## Local publish fallback

```bash
echo "@difftim:registry=https://npm.pkg.github.com" >> ~/.npmrc
echo "//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}" >> ~/.npmrc

npm ci --ignore-scripts
npm run build
npm publish
```

## Consumer setup

In consuming repos:

```bash
echo "@difftim:registry=https://npm.pkg.github.com" >> .npmrc
```

Then install:

```bash
npm install @difftim/eventkit-node
```
