# bun-plugin-solid

A plugin to compile Solid.js code with Bun.

```bash
bun add -D bun-plugin-solid
```

```tsx
import { SolidPlugin } from "bun-plugin-solid";

await Bun.build({
  // ...
  plugins: [SolidPlugin()],
});
```

## Options

All passed options are forwarded to [`babel-preset-solid`](https://www.npmjs.com/package/babel-preset-solid). For example:

```tsx
await Bun.build({
  // ...
  plugins: [SolidPlugin({ generate: "ssr", hydratable: true })],
});
```

## About this plugin and motivation

This plugin uses babel under the hood, which is not ideal. However, there is (currently) no clear public roadmap for proper compilation of Solid.js in Bun, so this plugin is a temporary solution for those (like me) who want to use Bun to build their Solid.js projects.

The hope is that it'll become obsolete once there is a better solution, at which point it can simply be removed.

The plugin will only run in for `.jsx` and `.tsx` files.
