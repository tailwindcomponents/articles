# What's coming in tailwindcss v2

Hello everyone today I will talk about some break changes and the new feature will come in Tailwindcss  v2.0.

Tailwindcss follows semantic versioning, so will never introduce breaking changes until a new major release (v2.0 is the next one).

## Remove deprecated gap utilities

In  v1.7.0 introduced new `gap-x-{n}` and `gap-y-{n}` utilities to replace the existing `col-gap-{n}` and `row-gap-{n}` utilities. the old utilities still working but will be removed in v2.0.

All Tailwindcss breaking changes are currently available in Tailwind behind flags and you can use these flags to remove old utilities or add the upcoming features.

To remove old gap utilities you can use `removeDeprecatedGapUtilities` flag:

```jsx
// tailwind.config.js
module.exports = {
  future: {
    removeDeprecatedGapUtilities: true,
  },
  // ...
}
```

## Purge layers by default

In v1.8.0 introduced new layers purge mode which will be the default in v2.0. It purges all layers (base, components, and utilities) by default, whereas the previous default mode (conservative, now deprecated) only purged the utility layer.

using the new layers mode by default, use the `purgeLayersByDefault` flag:

```jsx
// tailwind.config.js
module.exports = {
  future: {
    purgeLayersByDefault: true,
  },
  // ...
}
```

If you'd like to only purge the `utilities` layer (like the `conservative` mode did), you can still opt-in with this flag, but then explicitly specify that you'd only like to purge the utility layer:

```jsx
// tailwind.config.js
module.exports = {
  future: {
    purgeLayersByDefault: true,
  },
  purge: {
    layers: ['utilities'],
    content: [
      // Paths to your templates...
    ],
  },
  // ...
}
```

## New Color Scheme

Steve Schoger working on new color 

![EhAGi5JXgAMLSt7.jpeg](EhAGi5JXgAMLSt7.jpeg)