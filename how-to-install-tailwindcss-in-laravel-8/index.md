# How to Install Tailwindcss In Laravel 8

There are many ways to install tailwindcss in fresh laravel 8 project you can configuration your application by your self or use Preset to going fast. 

## Install Tailwindcss

First let's install tailwindcss via npm

```shell
npm install tailwindcss
```

## Add Tailwindcss to your `resources/css/app.css`

You don't have to install autoprefixer or postcss-import it's comes by default with laravel mix

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

