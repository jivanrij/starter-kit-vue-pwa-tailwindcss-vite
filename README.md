# Bootstrap Vue 3 / PWA / Tailwind CSS / Vite

This template should help get you started developing a PWA with Vue 3 and Tailwind CSS in Vite.

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
yarn dev
```

### Compile and Minify for Production

```sh
yarn build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
yarn test:unit
```

### Run production compiled version
```
cd dist && php -S 127.0.0.1:8000
```

## Steps done to create this starter package.

#### Create project
```
npm create vite my-project
cd my-project
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
yarn add vite-plugin-pwa -D
```

####  Install Tailwind CSS
```
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Specify the paths to template files in the content array of tailwind.config.js
```js
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: [
    "./index.html",
    "./src/**/*.{vue,js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

Include Tailwind directives in ./src/assets/base.css
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Note: Vite detects what css file to include based on it being included in ./src/main.js

####  Vite PWA plugin
```
yarn add vite-plugin-pwa -D
```

Edit your vite.config.js / vite.config.ts file and add the vite-plugin-pwa:
```js
export default mergeConfig(
    viteConfig,
    defineConfig({
        test: {
            environment: 'jsdom',
            exclude: [...configDefaults.exclude, 'e2e/*'],
            root: fileURLToPath(new URL('./', import.meta.url))
        }
    })
)
```
