# @zhuxiaojt/tsccp

Language: English(now) | [简体中文](https://github.com/zhuxiaojt/tsccp/blob/master/README_CN.md)

TypeScript compiler and asset copier

## Features

- Copy asset files (excluding TypeScript files) to output directory
- Compile TypeScript code
- Auto-detect and install TypeScript

## Installation

```bash
npm install -D @zhuxiaojt/tsccp
```

Or use pnpm:

```bash
pnpm add -D @zhuxiaojt/tsccp
```

## Usage

Make sure your `tsconfig.json` configures `rootDir` and `outDir`:

```json
{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"
  }
}
```

Then add a script to `package.json`:

```json
{
  "scripts": {
    "build": "tsccp"
  }
}
```

Run:

```bash
npm run build
```

## Command Line Arguments

All arguments are passed through to TypeScript compiler `tsc`, for example:

```bash
tsccp --project tsconfig.prod.json
```

## License

MIT
