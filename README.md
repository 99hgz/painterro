Fork of [Painterro](https://github.com/devforth/painterro)

Changes
========

- Anti-alias off. Brush will have clear, defined edges.
- Support palette.

Configuration ⚙
=============

You can pass parameters map to Painterro constructor:
```js
Painterro({
    palette:[ [255, 255, 255], 
              [220, 147, 77 ], 
              [238, 229, 102],
              [106, 177, 21 ],
              [200, 226, 37 ],
              [233, 5  , 219],
              [116, 116, 138],
              [225, 184, 161]]
  // ... other params here
})
```

| Param | Description | Default |
|-|-|-|
| 'palette' | If provided, then color picker will be replaced by palette | undefined |

Development 🔨
==============

Code written on ES6 which transplited by Babel and packed (minified) to a single file using webpack. All configs are inside so all you have to do after pulling repo is installing node modules:

```bash
cd painterro
npm ci
```

Building painterro
------------------

```bash
npm run build
```

Result file for `<script>` import is `build/painterro.min.js`.

Actually, above command produces 4 versions of library:

- `build/painterro-x.y.z.min.js`, `build/painterro.min.js` the same files but with different filenames (with and without versiontag) - this is `var` version which will be loaded as global variable (`var painterro = <Library class>`) when you will import it as `<script src='painterro.min.js' />` tag. So this is for `script` tag only.   
- `build/painterro.commonjs2.js` - this version sutable for js `require/import`. That's why it is used as entry point in `package.json` file - if you are using webpack or other tool that can handle `require/import` of `commonjs2` libraries then you can do `npm install painterro`, and do `import painterro` and it will use `commonjs2` version.
- `build/painterro.amd.js` and `build/painterro.umd.js` - these both are same as above but for `AMD` and `UMD` importers respectivly.


Dev-server
----------

To start hot-reload dev server (for reloading code "on the fly"):
```bash
npm run dev
```
Then open http://localhost:8080 with demo page
