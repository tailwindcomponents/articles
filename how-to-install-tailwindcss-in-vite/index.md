# How to Install Tailwindcss In Vite

[Vite](https://github.com/vitejs/vite) is an opinionated web dev build tool that serves your code via native ES Module imports during dev and bundles it with Rollup for production.

> Note Vite comes with vue 3 by default

First let's create new vite project:

```shell
npm init vite-app <project-name>
cd <project-name>
npm install
npm run dev
```

Next install tailwindcss

```
npm install tailwindcss
```

Create your Tailwind config file
```
npx tailwindcss init
```

Vite automatically applies your PostCSS config to all styles in *.vue files and imported plain .css files. Just add a postcss.config.js in your project root.

```
touch postcss.config.js
```

Add module to postcss.config.js

```js
module.exports = {
    plugins: [
        require("tailwindcss"),
        require("autoprefixer"),
    ],
};
```

Create app.css file in src/assets/app.css and import tailwindcss to it

```css
@import "tailwindcss/base";
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

Finally you have to import app.css to main.js file

```js
import './assets/app.css'
```

And Every things ready to go.