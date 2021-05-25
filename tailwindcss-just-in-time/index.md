# Tailwind CSS Just In Time

***on March 15, 2021 [Adam Wathan](https://adamwathan.me) announced tailwindcss just in time compiler which was a huge game changer***. [The Announcment](https://twitter.com/adamwathan/status/1371505992840663051?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1371505992840663051%7Ctwgr%5E%7Ctwcon%5Es1_&amp;ref_url=https%3A%2F%2Fdaily.dev%2Fblog%2Feverything-you-need-to-know-about-tailwind-css-jit-compiler).

## Before Just In Time Compiler

One of the downsides of tailwindcss is that it generates a ton of CSS code for each rule and variant in your project. If we look at its colors system, as han example, the framework adds a new class for each property that modifies colors, like background, text, hover states... Add responsiveness to the mix and the number of permutations will grow really fast! As you can imagine, the generated CSS code is huge. As solution, tailwind includes out of the box **built-in support for PurgeCSS**, allowing us to get rid of all the unused classes , which is great for production but... what about devlopment? That's where the Just-In-Time (JIT) mode comes into play. 
 
## What is Tailwind JIT

According to the Tailwind CSS github page, it's an experimental Just-In-Time compiler for Tailwind CSS that generates your classes on-demand, as you author your templates instead of generating everything in advance at initial build time.

What this means that the generated css code on your `build.css` file only includes what you are using in your templates. But that is only one of the benefits.

## Another advantages of Tailwind JIT compiler

- **Out-of-the-box variants**
    Before JIT, variants such as `focus:` `active:` `disable:` were not enabled by default, due to file-size considerations, and since JIT generates styles on demand, you can use any variant you want without the need of enabling them.

- **Better Browser performance**
    The browser doesn't have to parse and manage multiple megabytes of pre-generated CSS, specily in heavy customized projects.

- **Dev css = Prod css**
    Beacuse Jit only generates styles on demand or the only used styles you don't need to purge unused styles for production, which means you see the exact same CSS in all environments.

- **Fast Build Time**
    With JIT complier even large tailwind project will take about 80ms to compile regardless of the used build tool.
    
- **Customized values without customization**
    You can now just generate a utility for values that are not included in the default system of tailwind, using square bracket notation like `top-[-113px]`. Works with variants too, like `md:top-[-113px]`. Cool right!?
    
## Enabling JIT mode

To enable just-in-time mode, set the mode option to 'jit' in your `tailwind.config.js` file:
```js
// tailwind.config.js
module.exports = {
 mode: 'jit',
}
```

Remember to configure the files that must be analyzed to find the used classes
```js
// tailwind.config.js
module.exports = {
 mode: 'jit',
 // These paths are just examples, customize them to match your project structure
 purge: [
  './public/**/*.html',
  './src/**/*.{js,jsx,ts,tsx,vue}',
 ],
}
```

For more informations about JIT mode check out Tailwind CSS [Docs](https://tailwindcss.com/docs/just-in-time-mode)
