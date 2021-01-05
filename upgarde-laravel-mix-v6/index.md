# Upgrade laravel mix to v6

Laravel mix v6 comes with support the latest versions of numerous dependencies, including webpack 5, PostCSS 8, Vue Loader 16, and more.


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
    "development": "mix",
    "watch": "mix watch",
    "watch-poll": "mix watch -- --watch-options-poll=1000",
    "hot": "mix watch --hot",
    "production": "mix --production"
}
```

## API for JavaScript Frameworks

Laravel mix comes with new Javascript API for Vue and React, extracted it to its own "featured flag": mix.vue() and mix.react().

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




