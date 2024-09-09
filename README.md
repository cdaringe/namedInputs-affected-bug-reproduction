# namedInputs don't work in package.json

## Reproduction

1. observe `namedInputs` in [packages/pkg1/package.json](./packages/pkg1/package.json)
2. ensure your git state is clean
3. make an edit in [pkg2mock.json](./packages/pkg2/data/mocks/pkg2mock.json)
4. `pkg1` should be affected by the pkg2mock.json file changing, but is not.
   1. Verify: `NX_DAEMON=false pnpm exec nx affected --base=$(git log -1 --format=%H) -t=build --verbose --skip-nx-cache`
