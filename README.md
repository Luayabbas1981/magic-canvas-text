# ✨ Magic Text Canvas

**Magic Text Canvas** is a lightweight npm library for rendering animated, interactive particle-based text using the HTML5 canvas.  
It supports mouse and touch interactions over the text, gradients, multiple animation start modes, and mobile-optimized behavior.

Ideal for landing pages, hero sections, and playful UI elements.

---

## 📦 Installation

Install the package via npm:

```bash
npm install magic-text-canvas
````
```bash
yarn add magic-text-canvas
```

## 🚀 Usage
Import
import { initializeText } from "magic-text-canvas";

### HTML

Create a container element where the canvas will be injected:

<div class="text-con"></div>

### JS
initializeText({
  textContainerClass: "text-con",
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
  startMode: "auto",
});

### ## 🔧 Configuration Options

| Option | Type | Required | Notes |
|------|------|----------|-------|
| `textContainerClass` | `string` | ✅ Yes | Must match an existing DOM element and must be an empty element |
| `text` | `string` | ❌ No | Defaults to `"Magic Text"` |
| `fontSize` | `number` | ✅ Yes | Required for proper font rendering |
| `fontSizeMobile` | `number` | ✅ Yes | Required for mobile rendering |
| `textColor` | `string` | ⚠️ Conditional | Defaults to `#000000` |
| `bgColor` | `string` | ❌ No | Defaults to `#ffffff` |
| `effectColorApplied` | `boolean` | ⚠️ Recommended | Enables hover color effect |
| `effectColor` | `string` | ⚠️ Conditional | Required when `effectColorApplied === true` |
| `effectRadius` | `number` | ❌ No | Defaults to `80` (mobile capped at `100`) |
| `duration` | `number` | ❌ No | Defaults internally to `0.05` |
| `gradient` | `boolean` | ⚠️ Recommended | Enables gradient text |
| `colorOne` | `string` | ⚠️ Conditional | Required when `gradient === true` |
| `colorTwo` | `string` | ⚠️ Conditional | Required when `gradient === true` |
| `colorThree` | `string` | ⚠️ Conditional | Required when `gradient === true` |
| `startMode` | `string` | ❌ No | Defaults to `random` |


### 🎬 Start Modes

- random – particles spawn at random positions

- left – particles animate in from the left

- center – particles animate from the center

- bottom – particles animate from below

### 🧹 Cleanup

To remove the canvas, animation loop, and event listeners:

const magicText = initializeText({ ... });

// later
magicText.destroy();


### 📱 Mobile Support

- Touch events supported

- Optimized interaction radius for performance

- Separate mobile font size configuration

### npm

[Magic canvas text...](https://www.npmjs.com/package/magic-canvas-text)

### Portfolio

[Portfolio...](https://luay-portfolio.interflowcode.de/)

### 📄 License

MIT License
