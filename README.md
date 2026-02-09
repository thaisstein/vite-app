# Atech portal
This is a small interface built to showcase a Vue + TS + Vite application
## How to run
1. Navegate to the app directory
`cd vite-app`
2. Install dependencies:
`npm i`
3. Run server:
`npm run dev`

## On the projec

I created this project using the `npm create vite@latest` command, which sets up the "skeleton" of a website using vite so that we can build on top of it. Vite is a tool that allows us to serve our code while writing it (testing and iterating with npm run dev) and bundles it up when we're ready to launch (npm run build). In here we have

- The core config files (`vite.config.ts, package.json, package-lock.json`): they specify plugins, dependencies, scripts...
- `index.html`: serves as the front door of the ap; it contains the '<div id="app">' where your site will appear and tells the browser where to start loading the JavaScript.
- `public` that is
- `src`: actual source code of the app. We have `assets/` which stores images and icons used, `main.ts` which takes the code and "mounts" it into index.html, `App.vue` which is the main component, `/components/HelloWorld.vue` that is son of App.vue and `style.css  **