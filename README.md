## Learn the new frontend build tool Vite

> Refer to https://www.youtube.com/watch?v=UJypSr8IhKY

[Vite](https://vitejs.dev/) consists of two major parts:
- A dev server that serves your source files over native ES modules, with rich built-in features and astonishingly fast Hot Module Replacement (HMR).

  > `esbuild`, which is written in Go and very fast, does the transpile things transforming into plain javascript. It will process and prebundle the dependencies into something works in the browser as native es-module. `vite --force` means that ignore the dependency cache and reforce to process all the dependencies.

- A build command that bundles your code with Rollup, pre-configured to output highly optimized static assets for production. (Rollup is a more battle-tested choice in bundling applications)
 
--- 

#### Development
1. Make a new directroy `vite-demo`
2. Run `yarn add -D vite`
3. Create an `index.html` file, and it is the entry point for the whole application
4. Add a `"dev": "vite"` script in `package.json`
5. Run `npm run dev` and the `index.html` is serverd
6. When you debug with Vite, just looking at the network tab and every module is a request here because it doesn't concatenate everything.
7. For build and preview, add `"build": "vite build"` for production build, then `"serve": "vite preview"` to serve the `dist` directory we built.

<img alt="vite build" src="https://tva1.sinaimg.cn/large/008i3skNly1gyuj8fvytaj30s80dsq4u.jpg" width="500">
<img alt="vite preview" src="https://tva1.sinaimg.cn/large/008i3skNly1gyujc8lngoj30j00a23z9.jpg" width="500">

#### Use tailwind CSS https://tailwindcss.com/docs/guides/vite
1. Install tailwind `yarn add -D tailwindcss postcss autoprefixer`
2. Run `npx tailwindcss init -p`, which will create `tailwind.config.js` and `postcss.config.js`
3. Add `@tailwind` directives in the css file

#### Use sass
1. Install `yarn add -D sass`
2. Create a `.scss` file and import that in the `index.html`

#### Use React
1. Install `yarn add react react-dom`
2. Create a `jsx` file that import React and render something
3. `typescript`, `jsx`, `tsx` works out of the box

#### Scaffolding the Vite project
1. `npm init vite@latest` and follow the prompts
2. You can also directly specify the project name and the template you want to use: `npm init vite@latest project-name --template vue` (or vue-ts, react, react-ts...)
