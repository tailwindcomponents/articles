# How to Install Tailwindcss In Laravel 8

There are many ways to install tailwindcss in the fresh laravel 8 projects you can configure your application by yourself or use Preset to going fast. 

## Install Tailwindcss

First, let's install tailwindcss via npm

```shell
npm install tailwindcss
```

## Add Tailwindcss to your `resources/css/app.css`

You don't have to install autoprefixer or postcss-import it's coming by default with laravel mix

```css
@import "tailwindcss/base";

@import "tailwindcss/components";

@import "tailwindcss/utilities";
```

## Create your Tailwind config file

```shell
npx tailwindcss init
```

## Update your webpack.mix.js file

```js
mix.js('resources/js/app.js', 'public/js')
    .postCss('resources/css/app.css', 'public/css', [
        require('tailwindcss'),
    ]);
```

## Compile your assets

Now you can compile your assets and you are ready to go

```
npm run dev
```



# How to Install Tailwindcss In Laravel 8

There are many ways to install tailwindcss in the fresh laravel 8 projects you can configure your application by yourself or use Preset to going fast. 

## Install Tailwindcss

First, let's install tailwindcss via npm

```shell
npm install tailwindcss
```

## Add Tailwindcss to your `resources/css/app.css`

You don't have to install autoprefixer or postcss-import it's coming by default with laravel mix

```css
@import "tailwindcss/base";

@import "tailwindcss/components";

@import "tailwindcss/utilities";
```

## Create your Tailwind config file

```shell
npx tailwindcss init
```

## Update your webpack.mix.js file

```js
mix.js('resources/js/app.js', 'public/js')
    .postCss('resources/css/app.css', 'public/css', [
        require('tailwindcss'),
    ]);
```

## Compile your assets

Now you can compile your assets and you are ready to go

```
npm run dev
```

## Use Preset 

They are many presets build for installing tailwindcss in the laravel project you can use them to start fast with authentication UI

- [Jetstream](https://jetstream.laravel.com)
- [Laravel UI](https://github.com/laravel/ui)
- [Laravel Preset](https://github.com/tailwindcomponents/laravel-preset)
- [Laravel 7.0+ Frontend preset for Tailwind CSS](https://github.com/laravel-frontend-presets/tailwindcss)
- [Laravel tailwind css dashboard preset](https://github.com/Miaababikir/laravel-tailwind-css-dashboard-preset)


