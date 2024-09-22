<div align="center">
    <img  src="https://i.imgur.com/75yNf1K.png" alt="react-cheat-sheet" width="400" height="400">
</div>



<div align="center">
  <h1>React Cheat Sheet</h1>
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
### Create React Project
First, create your React project using `Vite`:
```bash
npm create vite@latest
```
### Install Tailwind
```bash
npm install -D tailwindcss
```
```bash
npx tailwindcss init
```
### Configure `tailwind.config.js`
```css
/** @type {import("tailwindcss").Config} */
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"], theme: {
    extend: {}
  }, plugins: []
};
```
### Install `autoprefixer`
```bash
npm install autoprefixer --save-dev
```
### Configure `postcss.config.js`
```css
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {}
  }
};
```
### Add tailwind directives to CSS in `src/index.css`
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```
### Install prettier-plugin-tailwindcss
```bash
npm install -D prettier prettier-plugin-tailwindcss
```
### Configure `.prettierrc`
```css
{
  "plugins": ["prettier-plugin-tailwindcss"]
}
```
### Install React Query 
```bash
npm i @tanstack/react-query
```
### Project Tree
```bash
tree -I 'node_modules'
```
