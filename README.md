# @tenedev/tsconfig

> Shared TypeScript configuration

[![npm version](https://img.shields.io/npm/v/@tenedev/tsconfig.svg?logo=npm&color=brightgreen)](https://www.npmjs.com/package/@tenedev/tsconfig)
[![Downloads](https://img.shields.io/npm/dt/@tenedev/tsconfig?logo=npm)](https://www.npmjs.com/package/@tenedev/tsconfig)

## Install

```sh
npm i -D @tenedev/tsconfig
```

> Requires TypeScript `^6`

## Usage

Extend it in your `tsconfig.json`:

```jsonc
{
  "extends": "@tenedev/tsconfig",
  "compilerOptions": {
    "rootDir": "src",
    "outDir": "dist",
  },
  "include": ["src"],
}
```

## What's included

### Environment

| Option             | Value                                          | Description                                                                                                   |
| ------------------ | ---------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| `target`           | `esnext`                                       | Compile to latest JS syntax                                                                                   |
| `module`           | `esnext`                                       | Emits native ES module syntax without transforming imports/exports                                            |
| `moduleResolution` | `bundler`                                      | Uses bundler-style resolution, bypassing Node ESM extension requirements and supporting flexible import paths |
| `lib`              | `ESNext, DOM, DOM.Iterable, DOM.AsyncIterable` | Full browser + modern JS type definitions                                                                     |

### Strict & Safety

| Option                               | Description                                    |
| ------------------------------------ | ---------------------------------------------- |
| `strict`                             | Enables all strict checks                      |
| `alwaysStrict`                       | Emits `"use strict"` in every file             |
| `noImplicitAny`                      | Error when TS infers `any`                     |
| `noImplicitOverride`                 | Must use `override` keyword in class methods   |
| `noImplicitReturns`                  | All code paths must return                     |
| `noFallthroughCasesInSwitch`         | No accidental switch fallthrough               |
| `noUnusedLocals`                     | Error on unused variables                      |
| `noUnusedParameters`                 | Error on unused function params                |
| `noUncheckedIndexedAccess`           | Index access returns `T \| undefined`          |
| `noPropertyAccessFromIndexSignature` | Must use bracket notation for index types      |
| `exactOptionalPropertyTypes`         | Optional props can't be explicitly `undefined` |
| `useUnknownInCatchVariables`         | Catch variables are `unknown` not `any`        |
| `allowUnreachableCode`               | Error on unreachable code                      |
| `allowUnusedLabels`                  | Error on unused labels                         |
| `noErrorTruncation`                  | Full type printed in error messages            |

### Interop

| Option                             | Description                                        |
| ---------------------------------- | -------------------------------------------------- |
| `verbatimModuleSyntax`             | Enforces `import type` at syntax level             |
| `esModuleInterop`                  | Default imports from CJS modules                   |
| `allowSyntheticDefaultImports`     | `import x from 'y'` without default export         |
| `allowJs`                          | Allows `.js` files in project                      |
| `allowImportingTsExtensions`       | Import `.ts` files with extension                  |
| `importHelpers`                    | Uses `tslib` instead of inlining helpers           |
| `resolveJsonModule`                | Import `.json` files                               |
| `isolatedModules`                  | Each file transpilable independently               |
| `forceConsistentCasingInFileNames` | Error on casing mismatches in imports              |
| `skipLibCheck`                     | Skip type checking of `node_modules` `.d.ts` files |

### Output

| Option           | Description                       |
| ---------------- | --------------------------------- |
| `declaration`    | Generates `.d.ts` files           |
| `declarationMap` | Generates `.d.ts.map` source maps |
| `sourceMap`      | Generates `.js.map` source maps   |
| `noEmit`         | No file output - use your bundler |
