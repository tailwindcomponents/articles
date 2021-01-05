# Upgrade laravel mix to v6

Laravel mix v6 comes with support to the latest versions of numerous dependencies, including webpack 5, PostCSS 8, Vue Loader 16, and more. You can install Tailwindcss v2 without compat verion when you upgrade to laravel mix v6, you only have to check your `package.json` dependencies list for any third-party tools or plugins that may not yet be compatible with webpack 5 or PostCSS 8.

## Install laravel mix v6 and postcss8

```bash
// npm
npm install laravel-mix@latest postcss@^8.1 --save-dev

// yarn
yarn add laravel-mix@latest postcss@^8.1 --dev
```

## Update Your NPM Scripts

The Webpack 5 CLI removed a number of options that your NPM scripts was likely referencing.  While you're at it, go ahead and switch over to the new Mix CLI.

### Before 

```json
"scripts": {
    "development": "cross-env NODE_ENV=development node_modules/webpack/bin/webpack.js --progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js",
    "watch": "npm run development -- --watch",
    "watch-poll": "npm run watch -- --watch-poll",
    "hot": "cross-env NODE_ENV=development node_modules/webpack-dev-server/bin/webpack-dev-server.js --inline --hot --disable-host-check --config=node_modules/laravel-mix/setup/webpack.config.js",
    "production": "cross-env NODE_ENV=production node_modules/webpack/bin/webpack.js --no-progress --hide-modules --config=node_modules/laravel-mix/setup/webpack.config.js"
}
```

### After 

```json
"scripts": {
    "dev": "mix",
    "development": "mix",
    "watch": "mix watch",
    "watch-poll": "mix watch -- --watch-options-poll=1000",
    "hot": "mix watch --hot",
    "prod": "mix --production",
    "production": "mix --production"
}
```

## API for JavaScript Frameworks

Laravel mix comes with new Javascript API for Vue and React, extracted to it's own "featured flag": mix.vue() and mix.react().

### Before 

```js
mix.js('resources/js/app.js', 'public/js');

```

### After 

```js
//Vue
mix.js('resources/js/app.js', 'public/js').vue();

// React
mix.js('resources/js/app.js', 'public/js').react();
```

If you want to keep using Vue3 with Laravel mix, mix v6 will automatically detect whether you have Vue 2 or 3 installed, based on your dependencies list.

```js
mix.js('resources/js/app.js', 'public/js').vue({ version: 2 });
```

You can also do the same thing with React

For more information you can check [CHANGELOG](https://github.com/JeffreyWay/laravel-mix/blob/master/CHANGELOG.md) and [UPGRADE GUIDE](https://github.com/JeffreyWay/laravel-mix/blob/master/UPGRADE.md)
