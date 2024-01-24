# @heybrostudio/biome-config

[![NPM Version](https://img.shields.io/npm/v/%40heybrostudio%2Fbiome-config?label=)](https://github.com/heybrostudio/biome-config) ![NPM License](https://img.shields.io/npm/l/%40heybrostudio%2Fbiome-config) [![NPM Version](https://img.shields.io/npm/v/%40biomejs%2Fbiome?label=biome)](https://biomejs.dev/)

## Usage

### Install

```bash
bun(pnpm|npm) add -D @biomejs/biome @heybrostudio/biome-config
```

### Add to `biome.json` file

```json
{
  "$schema": "./node_modules/@biomejs/biome/configuration_schema.json",
  "extends": ["./node_modules/@heybrostudio/biome-config/biome.json"],
  // ...
}
```

### Add script for `package.json`

For example:

```json
{
  "scripts": {
    "lint": "biome lint .",
    "lint:fix": "biome lint . --apply"
  }
}
```

### Lint Staged

If you want to apply lint and auto-fix before each commit, you can add the following to `package.json`:

```json
{
  "simple-git-hooks": {
    "pre-commit": "bun lint-staged"
  },
  "lint-staged": {
    "*": "eslint --fix"
  }
}
```

Then install the dependencies:

```bash
bun(pnpm|npm) i -D lint-staged simple-git-hooks
```

Finally, activate the hooks:

```bash
bunx(pnpx|npx) simple-git-hooks
```

## VS Code support (auto fix)

Install [Biome VS Code Extension](https://marketplace.visualstudio.com/items?itemName=biomejs.biome)

Add the following settings to your `.vscode/settings.json`:

```json
{
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "quickfix.biome": "explicit",
    "source.organizeImports.biome": "explicit"
  },
  "[javascript]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[typescript]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[javascriptreact]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[typescriptreact]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[json]": {
		"editor.defaultFormatter": "biomejs.biome"
	},
	"[jsonc]": {
		"editor.defaultFormatter": "biomejs.biome"
	}
}
```

## License

[MIT](./LICENSE) License &copy; 2024-PRESENT [Caven Ding](https://github.com/keyding)