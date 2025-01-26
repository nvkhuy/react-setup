# Vite + React TS Setup

This guide outlines the steps to set up a Vite + React project with Tailwind CSS, ESLint, Prettier, and TypeScript. All configurations are provided to ensure a consistent and maintainable codebase.

## 🛠️ Installation

Run the following commands in your terminal:

```bash
# Create a new Vite project
npm create vite@latest

# Install Tailwind CSS
npm i -D tailwindcss

# Initialize Tailwind CSS configuration
npx tailwindcss init

# Install Autoprefixer
npm i autoprefixer --save-dev

# Install Prettier and Tailwind CSS Prettier Plugin
npm i -D prettier prettier-plugin-tailwindcss

# Install ESLint and Prettier ESLint Plugins
npm i prettier eslint-config-prettier eslint-plugin-prettier -D

# Install TypeScript Node Types
npm i @types/node -D
```

## 📂 Configuration Files

### `.prettierignore`

```bash
node_modules/
dist/
```

### `.prettierrc`

```json
{
  "plugins": ["prettier-plugin-tailwindcss"],
  "arrowParens": "always",
  "semi": false,
  "trailingComma": "none",
  "tabWidth": 4,
  "endOfLine": "auto",
  "useTabs": false,
  "singleQuote": true,
  "printWidth": 120,
  "jsxSingleQuote": true
}
```

### `eslint.config.js`

```js
import js from "@eslint/js";
import globals from "globals";
import reactHooks from "eslint-plugin-react-hooks";
import reactRefresh from "eslint-plugin-react-refresh";
import tseslint from "typescript-eslint";
import eslintPluginPrettier from "eslint-plugin-prettier";

export default tseslint.config(
  { ignores: ["dist", "vite.config.ts"] },
  {
    extends: [js.configs.recommended, ...tseslint.configs.recommended],
    files: ["**/*.{ts,tsx}"],
    languageOptions: {
      ecmaVersion: 2020,
      globals: globals.browser
    },
    plugins: {
      "react-hooks": reactHooks,
      "react-refresh": reactRefresh,
      prettier: eslintPluginPrettier
    },
    rules: {
      ...reactHooks.configs.recommended.rules,
      "react-refresh/only-export-components": [
        "warn",
        { allowConstantExport: true }
      ],
      "prettier/prettier": [
        "warn",
        {
          arrowParens: "always",
          semi: false,
          trailingComma: "none",
          tabWidth: 4,
          endOfLine: "auto",
          useTabs: false,
          singleQuote: true,
          printWidth: 120,
          jsxSingleQuote: true
        }
      ]
    }
  }
);
```

### `package.json` Script Section

Add the following scripts to your `package.json` file:

```json
{
  "scripts": {
    "dev": "vite",
    "build": "tsc -b && vite build",
    "lint": "eslint .",
    "preview": "vite preview",
    "lint:fix": "eslint . --fix",
    "prettier": "prettier --check \"src/**/(*.tsx|*.ts|*.css|*.scss)\"",
    "prettier:fix": "prettier --write \"src/**/(*.tsx|*.ts|*.css|*.scss)\""
  }
}
```

### `postcss.config.js`

```js
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}
  }
};
```

### `src/index.css`

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### `tsconfig.json`

```json
{
  "files": [],
  "references": [
    { "path": "./tsconfig.app.json" },
    { "path": "./tsconfig.node.json" }
  ],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "~/*": ["src/*"]
    }
  }
}
```

### `vite.config.ts`

```js
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react-swc'
import path from 'path'

// Vite Configuration
export default defineConfig({
    plugins: [react()],
    server: {
        port: 3000
    },
    css: {
        devSourcemap: true
    },
    resolve: {
        alias: {
            '~': path.resolve(__dirname, './src')
        }
    }
})
```

### `.editorconfig`

```
[*]
indent_size = 4
indent_style = space
```

## 🚀 Getting Started

1. Clone the repository and navigate into the project directory.
2. Install dependencies using `npm install`.
3. Start the development server with `npm run dev`.

## 🧹 Linting & Formatting

- Run `npm run lint` to check for linting errors.
- Run `npm run lint:fix` to automatically fix linting issues.
- Run `npm run prettier` to check code formatting.
- Run `npm run prettier:fix` to apply Prettier formatting.

## 📦 Build & Preview

- Use `npm run build` to create a production build.
- Use `npm run preview` to preview the build locally.

## 🔧 Additional Configurations

- Modify `.prettierrc`, `.eslintignore`, or `.eslintrc` as needed for personalized styling and rules.
- Tailwind and PostCSS configurations can be further customized in their respective config files.