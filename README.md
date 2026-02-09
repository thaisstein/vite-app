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
- `index.html`: serves as the front door of the ap; it contains the `<div id="app">` where your site will appear and tells the browser where to start loading the JavaScript.
- `public` : a folder for static assets that don't need to be processed by vite (i.e. they are served exactly as they are and can be accessed directly by the browser).
- `src`: actual source code of the app and what I modified. 
    - We have `assets/` which stores images and icons used that vite *will* process during the build
    - `main.ts` which takes the code and "mounts" it into `index.html`
    - `App.vue` which is the root component
    - `/components/HelloWorld.vue` is a **child component** of `App.vue` (this is important because with Vue we can pass data from parent to children with [**props**](https://v2.vuejs.org/v2/guide/components-props) and from child to parent using **events**). 
    - `style.css`: global stylesheet, where we define the general looks of the project that all components inherit (fonts, colors, all that good stuff)

### Vue code
Before explaining my code, it’s important to understand the anatomy of a .vue file. Unlike traditional development where HTML, JS, and CSS are separate, Vue uses SFCs (Single File Components). This means a single file contains:

- `script setup`: The logic (defining variables, functions, and props).

- `template`: The HTML structure.

- `style`: The CSS design.

With that out of the way, let’s walk through the actual code.

### App.vue

- `script`: I’m bringing in the HelloWorld component so I can use it as a custom HTML tag inside my template. later on I call <HelloWorld /> and use props to pass the specific string: "Inovação em Defesa e Tecnologia". This makes the child component display this message;
- `html`: contains a main-layout which reffers to the root container that uses Flexbox to center all content. I added a grid-background to give the site a tech feel that covers the entire viewport. Also added a clickable logo that linkt to the atech website- I chose to do that do that with a with a standard <a> tag, but I could’ve done it with **@click** (v-on), which is a cool Vue aspect that lets us trigger js functions directly from the HTML (I use it in HelloWorld.vue);
- `style`
    - I chose to turn the mouse pointer into a plane icon (plane-icon.svg). I did this by using the cursor property with the !important rule on the universal selector (*), ensuring the plane stays visible even when hovering over other elements;
    - The grid-background uses a linear-gradient to create a 40px digital grid overlay;
    - I added a transition to the logo. When you hover over it, it scales up, rotates, and glows using `drop-shadow`. 

### HelloWorld.vue

- `script`: I use defineProps to catch the msg variable sent by the parent (App.vue). I also created a function called goToSite using TypeScript; it uses window.open method to launch the atech website in a new tab;
- `html`: I have a container that displays the msg inside a h1 tag using interpolation (how vue binds data into the html: `({{ msg }}`). My button uses the @click to trigger the goToSite function. Inside the button, I added an empty div called `btn-glow`, which is an element used for an animation effect;
- `style`: I used the *scoped* attribute here, that ensures these styles only affect the target component. Some details of the choices made are:
    - The title uses text-transform: uppercase and a text-shadow;
    - I styled the button to look transparent with a border; on hover, I used `transform: translateY(-3px)` to make it lift up and added a strong `box-shadow` for a neon glow;
    - Opted for a created a shine effect using btn-glow: by setting its position to left: -100% and moving it to left: 100% when the button is hovered, a white gradient "sweeps" across the button to create this cool effect.