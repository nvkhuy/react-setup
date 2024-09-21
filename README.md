<div align="center">
    <img  src="https://i.imgur.com/75yNf1K.png" alt="react-cheat-sheet" width="200" height="200">
</div>



<div align="center">
  <h1>React Cheat Sheet</h1>
  <a href="https://www.npmjs.com/package/prisma"><img src="https://img.shields.io/npm/v/prisma.svg?style=flat" /></a>
  <a href="https://github.com/nvkhuy/react-cheat-sheet/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue" /></a>
  <br />
  <br />
  <a href="https://nvkhuy.com/">Website</a>
  <span>&nbsp;&nbsp;•&nbsp;&nbsp;</span>
  <a href="https://x.com/nvkhuy">X</a>
  <br />
  <hr />
</div>

## Setup
- React
- Tailwind
- React Query
### 1. Create React Project
First, create your React project using `Vite`:
```bash
npm create vite@latest
```
### 2. Install Tailwind
```bash
npm install -D tailwindcss
npx tailwindcss init
```
### 3. Configure `tailwind.config.js`
```css
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./src/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```
### 3. Configure `postcss.config.js`
```css
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
};
```
### 4. Add tailwind directives to CSS
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
### 5. Install prettier-plugin-tailwindcss
```bash
npm install -D prettier prettier-plugin-tailwindcss
```
### 6. Configure `.prettierrc`
```css
{
  "plugins": ["prettier-plugin-tailwindcss"]
}
```
### 7. Install React Query 
```bash
npm i @tanstack/react-query
```
### Project Tree
```bash
tree -I 'node_modules'
```