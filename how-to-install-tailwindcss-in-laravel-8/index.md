# How to Install Tailwindcss In Laravel 8

There are many ways to install Tailwindcss on a fresh Laravel 8 install. You can configure your application by yourself or use a Preset to do it faster. We'll start with the custom one, skip to the end to check available presets.

## Install Tailwindcss

First, let's install tailwindcss via npm

```shell
npm install tailwindcss
```

## Add Tailwindcss to your `resources/css/app.css`

You don't have to install autoprefixer or postcss-import, because it's already installed with laravel mix

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

Finish by compiling your assets and you'll be ready.

```
npm run dev
```

## Tailwind Css Presets 

There are many presets ready for installing Tailwindcss in a Laravel project, some of them even includes few auth components to get the ball rolling:

- [Jetstream](https://jetstream.laravel.com)
- [Laravel UI](https://github.com/laravel/ui)
- [Laravel Preset](https://github.com/tailwindcomponents/laravel-preset)
- [Laravel 7.0+ Frontend preset for Tailwind CSS](https://github.com/laravel-frontend-presets/tailwindcss)
- [Laravel tailwind css dashboard preset](https://github.com/Miaababikir/laravel-tailwind-css-dashboard-preset)


