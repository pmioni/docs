---
title: PostCSS plugins
description: How to add PostCSS plugins?
---

# How to add PostCSS plugins?

### Recommended Method
If present, rename or delete the `postcss.config.js` in your project directory. Then, in your `nuxt.config.js` file add the following:

```js
export default {
  build: {
    postcss: {
      // Add plugin names as key and arguments as value
      // Install them before as dependencies with npm or yarn
      plugins: {
        // Disable a plugin by passing false as value 
        'postcss-url': false,
        'postcss-nested': {},
        'postcss-responsive-type': {},
        'postcss-hexrgba': {}
      },
      preset: {
        // Change the postcss-preset-env settings
        autoprefixer: {
          grid: true
        }
      }
    }
  }
}
```

### Traditional Method
Use `postcss.config.js`, for example:

```
const join = require('path').join
const tailwindJS = join(__dirname, 'tailwind.js')

module.exports = {
  plugins: [require('tailwindcss')(tailwindJS), require('autoprefixer')]
}
```
