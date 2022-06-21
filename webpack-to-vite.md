## Webpack to Vite
> Webpack
> - supported modules: ES Modules, CommonJS and AMD Modules
> - dev-server: bundled modules served via webpack-dev-server using Express.js web server
> - production build: webpack

> Vite
> - supported modules: ES Modules
> - dev-server: native ES Modules served via Vite using Koa web server
> - production build: Rollup

When you start the app in development, Webpack will bundle all of your code, and start the webpack-dev-server, the Express.js web server which will serve the bundled code. Within the bundled js file contains all modules for the app and need to regenerate the entire file when we change a file for HMR. It can often take an long wait to spin up a dev server, and even with HMR, file edits can take a couple seconds to be reflected in the browser.

Vite doesn't set out to be a new bundler. Rather, it's a pre-configured build environment using the Rollup bundler and a tool for local development.
- Vite pre-bundles dependencies (when install vite) using `esbuild` which is written in Go, 10-100x faster than JavaScript-based bundlers.
- Vite serves source code over native ES Modules. It only needs to transform and serve source code on demand, as the browser requests it.

Vite only support ES Modules, and parsing the native ES Modules means it will read the `export` and `import` lines from your code. It will convert those lines into HTTP requests back to the server, where it will again read the `export` and `import` lines and make new requests. Vite also leverages HTTP headers to speed up full page reloads: source code module requests are made conditional via `304 Not Modified`, and dependency module requests are strongly cached via `Cache-Control` header.

https://vitejs.dev/guide/why.html  
https://github.com/originjs/webpack-to-vite   
https://patak.dev/vite/ecosystem.html  

