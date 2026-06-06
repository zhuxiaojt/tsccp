# @zhuxiaojt/tsccp

语言: [English](https://github.com/zhuxiaojt/tsccp/blob/master/README.md) | 简体中文(当前)

TypeScript 编译和资源复制工具

## 功能

- 复制资源文件（排除 TypeScript 文件）到输出目录
- 编译 TypeScript 代码
- 自动检测并安装 TypeScript

## 安装

```bash
npm install -D @zhuxiaojt/tsccp
```

或使用 pnpm:

```bash
pnpm add -D @zhuxiaojt/tsccp
```

## 使用

确保你的 `tsconfig.json` 配置了 `rootDir` 和 `outDir`：

```json
{
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"
  }
}
```

然后在 `package.json` 中添加脚本：

```json
{
  "scripts": {
    "build": "tsccp"
  }
}
```

运行：

```bash
npm run build
```

## 命令行参数

所有参数会透传给 TypeScript 编译器 `tsc`，例如：

```bash
tsccp --project tsconfig.prod.json
```

## License

MIT
