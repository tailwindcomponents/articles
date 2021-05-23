# Tailwind CSS Just In Time

***on March 15, 2021 [Adam Wathan](https://adamwathan.me) announced tailwindcss just in time compiler which was a huge game changer***. [The Announcment](https://twitter.com/adamwathan/status/1371505992840663051?ref_src=twsrc%5Etfw%7Ctwcamp%5Etweetembed%7Ctwterm%5E1371505992840663051%7Ctwgr%5E%7Ctwcon%5Es1_&amp;ref_url=https%3A%2F%2Fdaily.dev%2Fblog%2Feverything-you-need-to-know-about-tailwind-css-jit-compiler).

## Before Just In Time Compiler

one of the downsides of tailwindcss is that it generates a ton of css code for each rule and variant in your project , for example if we look at its spacing system Tailwind includes a class for a major of included values in addition to the customized values in the `tailwind.config.js` file.he same goes for minimum width, maximum width, height, fonts, colors, and more! As you can imagine, the generated CSS code is huge, and it gets exponentially worse as you add more colors, variants, etc. Out of the box tailwind includes **built-in support for PurgeCSS**, allowing us to get rid of all the unused classes , which is great for production but what about devolpment? That's where the Just-In-Time (JIT) mode comes into play. 
 

## What is Tailwind JIT

according to the Tailwind Css github page  it's an experimental just-in-time compiler for Tailwind CSS that generates your styles on-demand as you author your templates instead of generating everything in advance at initial build time.

What this means that the generated css code on your `build.css` file only includes what you are using in your templates.

## Tailwind JIT ships with features such as 

- **Out-of-the-box variants**
    Before JIT variants such as Focus - active - disable and others was no enabled by default due to file-size considerations , and since JIT generates styles on demand you can use any variant you want, whenever you want.

- **Better Browser performance**
    The browser doesn't have to parse and manage multiple megabytes of pre-generated CSS , specily in heavy customized projects.

- **Dev css = Prod css**
    Beacuse Jit only generates styles on demand or the only used styles you don't need to purge unused styles for production, which means you see the exact same CSS in all environments.

- **Fast Build Time**
    With JIT complier even large tailwind project will take about 800ms to compile regardless of the used build tool.
    
- **Customized values without customization**
    you can now  just generate a utility for values that are not included in the default system of tailwind  as needed using square bracket notation like `top-[-113px]`. Works with variants too, like `md:top-[-113px]`.cool right!.
