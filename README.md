# ✨ Magic Canvas Text

**Magic Canvas Text** is a lightweight npm library for rendering animated, interactive particle-based text using the HTML5 canvas.
It supports mouse and touch interactions, gradients, multiple animation start modes, and mobile‑optimized behavior.

Perfect for landing pages, hero sections, and playful UI elements.

---

## 📦 Installation

Install the package via npm or yarn:

```bash
npm install magic-canvas-text
```

```bash
yarn add magic-canvas-text
```

---

## 🚀 Usage

### HTML

Create a container element where the canvas will be injected:

```html
<div class="text-con"></div>
```

> ⚠️ The container should be empty and have a defined width & height.

---

### JavaScript

```js
import { initializeText } from "magic-canvas-text";

const element = document.querySelector(".text-con");

const magicText = initializeText({
  element,
  text: "Magic Text",
  fontSize: 100,
  fontSizeMobile: 30,
  textColor: "#ffffff",
  bgColor: "#000000",
  effectColorApplied: true,
  effectColor: "#ff0000",
  effectRadius: 85,
  duration: 0.03,
  gradient: false,
  colorOne: "#ff0000",
  colorTwo: "#00ff00",
  colorThree: "#0000ff",
  startMode: "random",
});
```

### ✅ Important API Change

Magic Canvas Text now **expects a DOM element**, not a class name or selector string.

This makes the API:

* more predictable
* framework‑friendly (React, Vue, Svelte)
* safer against double initialization

---

## 🔧 Configuration Options

| Option               | Type          | Required       | Description                                          |
| -------------------- | ------------- | -------------- | ---------------------------------------------------- |
| `element`            | `HTMLElement` | ✅ Yes          | Target element where the canvas will be mounted      |
| `text`               | `string`      | ❌ No           | Text to render (default: `"Magic Text"`)             |
| `fontSize`           | `number`      | ❌ No           | Desktop font size (default: `100`)                   |
| `fontSizeMobile`     | `number`      | ❌ No           | Mobile font size (default: `30`)                     |
| `textColor`          | `string`      | ❌ No           | Solid text color (default: `#000000`)                |
| `bgColor`            | `string`      | ❌ No           | Canvas background color (default: `#ffffff`)         |
| `effectColorApplied` | `boolean`     | ❌ No           | Enables hover color effect                           |
| `effectColor`        | `string`      | ⚠️ Conditional | Required if `effectColorApplied === true`            |
| `effectRadius`       | `number`      | ❌ No           | Interaction radius (default: `80`, mobile max `100`) |
| `duration`           | `number`      | ❌ No           | Particle easing speed (default: `0.05`)              |
| `gradient`           | `boolean`     | ❌ No           | Enables gradient text                                |
| `colorOne`           | `string`      | ⚠️ Conditional | Required when `gradient === true`                    |
| `colorTwo`           | `string`      | ⚠️ Conditional | Required when `gradient === true`                    |
| `colorThree`         | `string`      | ⚠️ Conditional | Required when `gradient === true`                    |
| `startMode`          | `string`      | ❌ No           | Particle start animation mode (default: `random`)    |

---

## 🎬 Start Modes

* `random` – particles spawn at random positions
* `left` – particles animate in from the left
* `center` – particles animate from the center
* `bottom` – particles animate in from below

---

## 🧹 Cleanup

Each initialization returns an instance with a `destroy()` method.

```js
const magicText = initializeText({ element, text: "Hello" });

// later
magicText.destroy();
```

This removes:

* the canvas
* animation loop
* event listeners
* internal instance reference

---

## 📱 Mobile Support

* Touch interaction support
* Optimized interaction radius
* Separate mobile font sizing

---

## 🧩 Framework Usage

### React

```js
const ref = useRef(null);

useEffect(() => {
  const instance = initializeText({
    element: ref.current,
    text: "React Magic",
  });

  return () => instance?.destroy();
}, []);
```

### Vue

```js
const title = ref(null);

onMounted(() => {
  initializeText({
    element: title.value,
    text: "Vue Magic",
  });
});
```

---

## 🌐 Demo

[Magic Canvas Text Demo](https://luayabbas1981.github.io/magic-text/)

---

## 📦 npm

[magic-canvas-text on npm](https://www.npmjs.com/package/magic-canvas-text)

---

## 👤 Portfolio

[Portfolio](https://luay-portfolio.interflowcode.de/)

---

## 📄 License

MIT License
