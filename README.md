<div align="center">

# Frontend Vue + Tailwind Study

**A Vue + Tailwind frontend case**

</div>

## Overview

This project contains the frontend for a porfolio website. It uses Vue and Vite, with Tailwind CSS for styling, AOS for scroll animations, and Lucide icons for Vue.

## Prerequisites

- Node.js (LTS recommended)
- npm
- Git

## Clone and run

Replace `<repository-url>` and `<repository-folder>` with the actual repository URL and folder name.

```bash
git clone <repository-url>
cd <repository-folder>/frontendVue
npm install
npm run dev
```

## Install UI packages

From the `frontendVue` directory, install Tailwind CSS, AOS, and Lucide icons:

```bash
npm install -D tailwindcss @tailwindcss/vite
npm install aos lucide-vue-next
```

### Tailwind CSS

For Tailwind CSS v4 with Vite, add its plugin in `vite.config.js` (or `vite.config.ts`):

```js
import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'
import tailwindcss from '@tailwindcss/vite'

export default defineConfig({
	plugins: [vue(), tailwindcss()],
})
```

Add Tailwind to the main stylesheet, such as `src/style.css`:

```css
@import "tailwindcss";
```

Import that stylesheet from the app entry point (`src/main.js` or `src/main.ts`). If this project uses Tailwind v3, use the v3 installation and configuration instructions instead.

### AOS animations

Import AOS and its stylesheet in the app entry point, then initialize it:

```js
import AOS from 'aos'
import 'aos/dist/aos.css'

AOS.init({ duration: 700, once: true })
```

Set an animation on an element with a `data-aos` attribute:

```html
<section data-aos="fade-up">Case study content</section>
```

### Lucide icons

Import icons from `lucide-vue-next` and use them as Vue components:

```vue
<script setup>
import { ArrowRight } from 'lucide-vue-next'
</script>

<template>
	<ArrowRight :size="20" aria-hidden="true" />
</template>
```

## Common commands

Use `npm run` to see the scripts defined by this project. Typical Vite scripts include:

```bash
npm run dev       # Start the development server
```

The production build is generated in `dist/`, which can be deployed to a static hosting service.
