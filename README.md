# @inzumer/prettier

Shared Prettier configuration for Inzumer projects (import order included). Part of the Inzumer shared packages (one repository per package:
`inzumer-<name>` published as `@inzumer/<name>`).

## Install

```sh
pnpm add -D @inzumer/prettier
```

## Usage

```jsonc
// package.json
{ "prettier": "@inzumer/prettier" }
```

- 100 columns, single quotes, trailing commas, LF.
- Imports sorted with `@ianvs/prettier-plugin-sort-imports`: built-ins, third party, `@inzumer/*`,
  project aliases, then relative. Projects with other aliases can extend it:

```js
// prettier.config.mjs
import inzumer from '@inzumer/prettier' with { type: 'json' };

export default { ...inzumer, importOrder: [/* your order */] };
```

## Releases

[Changesets](https://github.com/changesets/changesets): add a changeset (`pnpm changeset`) with each
change. On `main`, `.github/workflows/release.yml` opens a "Version Packages" PR and, when it is
merged, publishes to npm (needs the `NPM_TOKEN` repository secret).

Previously @inzumer/prettier-config (private, in ui-library).
