# rollup-plugin-entrypoint-hashmanifest

A [rollup] plugin that generates a hash manifest for each entrypoint file you give. The manifest is compatible with the one emitted by [hashmark] and can be processed by tools like [injectassets] (née [replaceinfiles]).

```
$ npm install --save rollup-plugin-hashmanifest
```

## Usage

```js
// rollup.config.js
import entrypointHashmanifest from "rollup-plugin-entrypoint-";

export default {
  input: ["src/main.js", "src/worker.js", "src/serviceworker.js"],
  output: {
    dir: "dist",
    format: "amd",
    entryFileNames: "[name]-[hash].js",
    chunkFileNames: "[name]-[hash].js"
  },
  plugins: [entrypointHashmanifest()]
};
```

## Options

```js
{
  // ...
  plugins: [entrypointHashmanifest(options)];
}
```

- `manifestName`: Name of the file to write the manifest to. Default `entrypoint.hashmanifest.json`.

[rollup]: https://rollupjs.org/
[hashmark]: https://www.npmjs.com/package/hashmark
[replaceinfiles]: https://www.npmjs.com/package/@songkick/replaceinfiles
[injectassets]: https://www.npmjs.com/package/@songkick/injectassets

---

License Apache-2.0
