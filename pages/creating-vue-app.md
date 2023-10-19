---
layout: section
transition: 'slide-up'
---

# Creando una Vue App

---
layout: big-points
---

- CDN (Content Delivery Network)
- SFC (Single File Component)

---
layout: big-points
---

# CDN (Compilación Global)

```html {1|1-3|1-6,16|1-8,15,16|1-9,14-16|1-10,14-16|all}
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>

<div id="app">{{ message }}</div>

<script>
  const { createApp, ref } = Vue

  createApp({
    setup() {
      const message = ref('Hello vue!')
      return {
        message
      }
    }
  }).mount('#app')
</script>
```

---
layout: big-points
---

# CDN (Compilación ES Modules)

```html {3,4|all}
<div id="app">{{ message }}</div>

<script type="module">
  import { createApp, ref } from 'https://unpkg.com/vue@3/dist/vue.esm-browser.js'

  createApp({
    setup() {
      const message = ref('Hello Vue!')
      return {
        message
      }
    }
  }).mount('#app')
</script>
```

---
layout: big-points
transition: 'slide-up'
---

# CDN (ES Modules con Import Maps)

```html {1-7,12|all}
<script type="importmap">
  {
    "imports": {
      "vue": "https://unpkg.com/vue@3/dist/vue.esm-browser.js"
    }
  }
</script>

<div id="app">{{ message }}</div>

<script type="module">
  import { createApp, ref } from 'vue'

  createApp({
    setup() {
      const message = ref('Hello Vue!')
      return {
        message
      }
    }
  }).mount('#app')
</script>
```

---
layout: big-points
---

# SFC (Instalación)

```powershell {1|1-3|1-4|1-5|1-6|1-7|1-8|1-9|1-10|all}
> npm create vue@latest

✔ Project name: … <your-project-name>
✔ Add TypeScript? … No / Yes
✔ Add JSX Support? … No / Yes
✔ Add Vue Router for Single Page Application development? … No / Yes
✔ Add Pinia for state management? … No / Yes
✔ Add Vitest for Unit testing? … No / Yes
✔ Add an End-to-End Testing Solution? … No / Cypress / Playwright
✔ Add ESLint for code quality? … No / Yes
✔ Add Prettier for code formatting? … No / Yes

Scaffolding project in ./<your-project-name>...
Done.
```


---
layout: big-points
transition: fade
---


<h1 style="text-align:center">SFC (Ejecutar la aplicación)</h1>

<div grid="~ cols-2 gap-12" mb="14">

  ```powershell
  > cd <your-project-name>
  > npm install
  > npm run dev
  ```
  <h4>
    Es recomendable usar como editor <br> VSCode + la extensión Volar.
  </h4>
</div>

<h1 style="text-align:center">Hacer build</h1>

```powershell
  > npm run build
```
