# react-vite-h5

This template should help get you started developing mobile applications with React and Typescript and Vant in Vite.

## Project setup
```
pnpm install
```

### Compiles and hot-reloads for development
```
pnpm start
```

### Compiles and minifies for production
```
pnpm build
```

### Lints and fixes files (eslint + prettier)
```
pnpm lint
```

### Generate component(page) templates for development
```
pnpm generate
```

### Customize configuration
See [Configuration Reference](https://vitejs.dev/config/).

## Browser adaptation

### Rem Unit (default)

Vant uses `px` unit by default,You can use tools such as `postcss-pxtorem` to transform `px` unit to `rem` unit.

- [postcss-pxtorem](https://github.com/cuth/postcss-pxtorem)
- [lib-flexible](https://github.com/amfe/lib-flexible)

#### PostCSS Config

PostCSS config example:

```js
// .postcssrc.js
module.exports = {
  plugins: {
    'postcss-pxtorem': {
      rootValue: 37.5,
      propList: ['*'],
    },
  },
};
```

### Viewport Units

you can use tools such as [postcss--px-to-viewport](https://github.com/evrone/postcss-px-to-viewport) to transform `px` unit to viewport units (vw, vh, vmin, vmax).

#### PostCSS Config

PostCSS config example:

```js
// .postcssrc.js
module.exports = {
  plugins: {
    'postcss-px-to-viewport': {
      viewportWidth: 375,
    },
  },
};
```

### Custom rootValue

If the size of the design draft is 750 or other sizes, you can adjust the `rootValue` to:

```js
// .postcssrc.js
module.exports = {
  plugins: {
    // postcss-pxtorem version >= 5.0.0
    'postcss-pxtorem': {
      rootValue({ file }) {
        return file.indexOf('vant') !== -1 ? 37.5 : 75;
      },
      propList: ['*'],
    },
  },
};
```
