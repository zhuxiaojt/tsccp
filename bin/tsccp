#!/usr/bin/env node
import fs from 'fs'
import path from 'path'
import child_process from 'child_process'
import copyfiles from 'copyfiles'

const cwd = process.cwd()
const tsconfigPath = path.join(cwd, 'tsconfig.json')

if (!fs.existsSync(tsconfigPath)) {
  console.error('tsconfig.json not found')
  process.exit(1)
}

const tsconfig = JSON.parse(fs.readFileSync(tsconfigPath, 'utf-8'))
const result = child_process.spawnSync(
  'npx',
  ['tsc', ...process.argv.slice(2)],
  { stdio: 'inherit', cwd }
)

if (result.status !== 0) {
  console.error('tsc failed: ', result.stderr)
  process.exit(1)
}

const outDir = tsconfig.compilerOptions.outDir
const srcDir = tsconfig.compilerOptions.rootDir

if (!outDir || !srcDir) {
  console.error('outDir or rootDir not found in tsconfig.json')
  process.exit(1)
}

copyfiles(
  [path.join(srcDir, '**', '*'), outDir],
  { all: true, exclude: ['**/*.ts', '**/*.mts', '**/*.cts'] },
  (err) => {
    if (err) {
      console.error('copyfiles failed: ', err)
      process.exit(1)
    }
  }
)