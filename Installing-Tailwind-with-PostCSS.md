# Installing Tailwind with PostCSS

#### Requirements:

- Node
- NPM

## Guide

### 1. Initialize NPM

```
npm init -y
```

## 2. Installing Tailwind and PostCSS CLI

```
npm install -D tailwindcss postcss-cli autoprefixer
```

## 3. Initialize Tailwind

This will create `tailwind.config.js` file in the working directory.

```
npx tailwindcss init
```

## 4. Add Tailwind to PostCSS Configuration

Add `tailwindcss` and `autoprefixer` to your `postcss.config.js` file or wherever postcss is installed in your project. In this case, we are gonna write our own postcss.config file

`postcss.config.js`

```
module.exports = {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  }
}
```

## 5. Configuring Template Paths

Add the paths to all of your template files in your `tailwind.config.js` file.

`tailwind.config.js`

```
/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./src/**/*.{html,js}"],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

## 6. Add the Tailwind directives to your CSS

Add the `@tailwind` directives for each of Tailwind’s layers to your main CSS file.

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## 7. Adding the Build command to `package.json`

Note make sure to refer to the base tailwind css and the preferred css path

`package.json`

```
"scripts": {
    "dev": "postcss ./src/css/tailwind.css -o ./public/css/main.css --watch",
    "build": "postcss ./src/css/tailwind.css -o ./public/css/main.css"
  },
```

## 8. Run the commands

```
npm run dev
```

## 9. Use some classes on your html files

If the installation went successful, you should now be able to use tailwind classes on your HTML files.

`Important:` link the main.css file to your HTML Files to see the styling

```
<div class="h-dvh bg-blue-500"></div>
```
