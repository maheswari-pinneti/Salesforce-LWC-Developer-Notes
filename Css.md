# 🌐 CSS Guide for Salesforce Lightning Web Components (LWC)

---

## 📘 Introduction

CSS in the context of Lightning Web Components (LWC) defines the appearance and layout of your component’s UI. Each component can include a single stylesheet that’s automatically scoped to the component via Shadow DOM, ensuring modular and encapsulated styles.

---

## 🔹 1. The Role of CSS in LWC

Like traditional web development, CSS in LWC is used to style HTML templates. However, the styles are encapsulated at the component level, preventing leakage across components.

Each component includes:

* `.html` — Template structure
* `.js` — Business logic
* `.css` *(optional)* — Styling
* `.js-meta.xml` — Metadata/configuration

---

## 🔹 2. Key Characteristics of CSS in LWC

| Feature                           | Description                                                           |
| --------------------------------- | --------------------------------------------------------------------- |
| 🧩 **Component CSS File**         | Named `componentName.css`, auto-applied to the component              |
| 📦 **File Size Limit**            | Max size: 128 KB (131,072 bytes)                                      |
| 🎨 **Standard CSS Syntax**        | Supports normal selectors (classes, elements, pseudo-classes)         |
| 🔒 **Scoped by Shadow DOM**       | Styles are isolated to the component                                  |
| 🚫 **ID Selectors Not Supported** | `#id` is transformed at runtime; avoid using                          |
| 🔗 **CSS Modules**                | Import shared `.css` modules using `@import`                          |
| 💎 **SLDS Integration**           | Use `slds-*` utility classes and styling hooks for best compatibility |

---

## 🔹 3. How CSS is Used in LWC Development

### ✅ Component Styling Example

```css
/* myComponent.css */
.myContainer {
  background-color: #f4f6f9;
  padding: 1rem;
}
.title {
  font-weight: bold;
  font-size: 1.25rem;
  color: #16325c;
}
```

```html
<!-- myComponent.html -->
<template>
  <div class="myContainer">
    <p class="title">{text}</p>
  </div>
</template>
```

### 🎨 SLDS Utility Classes

```html
<div class="slds-box slds-p-around_medium">
  <p class="slds-text-color_default">Hello, {userName}!</p>
  <lightning-button class="slds-m-top_small" label="Click Me" onclick={handleClick}></lightning-button>
</div>
```

### 🕹️ Styling the Root with `:host`

```css
:host {
  display: block;
  border: 1px solid #d8dde6;
  border-radius: 0.25rem;
}
```

### 🔄 Importing Shared CSS Modules

```css
/* myComponent.css */
@import "cssLibrary/myCssLibrary";
```

---

## 🔹 4. Important Considerations & Best Practices

| Best Practice                | Why                                                 |
| ---------------------------- | --------------------------------------------------- |
| ✅ Use SLDS & Base Components | Ensures consistent UI and accessibility             |
| ✅ Use Styling Hooks          | Customize safely without breaking updates           |
| 🚫 Don’t Override Internals  | Avoid targeting internal `.slds-*` classes directly |
| 🚫 Avoid ID Selectors        | LWC transforms IDs, so `#id` selectors won’t work   |
| ✅ Style Host with `:host`    | Proper way to target the component’s root element   |
| 🛡️ Respect Shadow DOM       | Styles are scoped and do not leak in/out            |
| 🧠 Mind Accessibility        | Ensure color contrast and WCAG compliance           |

---

## 🔹 5. Sample CSS Component (myComponent.css)

```css
:host {
  display: block;
  margin-bottom: 1rem;
}
.container {
  background-color: #f4f6f9;
  padding: 1rem;
  border-radius: 0.25rem;
}
.header {
  font-weight: bold;
  color: #16325c;
  margin-bottom: 0.5rem;
}
```

---

## 🚀 Project Ideas (CSS + LWC)

| Project                       | Description                                                         |
| ----------------------------- | ------------------------------------------------------------------- |
| 📋 **Themed Components**      | Toggle between light/dark mode using SLDS classes or CSS variables. |
| 📐 **Responsive Layout**      | Build a dashboard using SLDS grid and media queries.                |
| 🖌️ **Shared Style Library**  | Create reusable style modules via CSS-only components.              |
| 🌗 **Dark Mode Toggle**       | Use `:host(.dark-mode)` or class toggles for theme switching.       |
| 🎨 **Animated Button Styles** | Add hover/transition effects with CSS keyframes.                    |

---

## 🔗 References

* [Style Components with CSS Stylesheets – LWC Docs](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.create_components_css)
* [Lightning Design System – Utility Classes](https://www.lightningdesignsystem.com/utilities/)
* [LWC Recipes GitHub](https://github.com/trailheadapps/lwc-recipes)
* [MDN – CSS `@import` Rule](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)

---

> ✨ **Pro Tip:** Store this doc in your project’s `docs/` folder or bookmark it for quick reference while styling Lightning Web Components.

---



# 🌐 CSS Guide for Salesforce Lightning Web Components (LWC)

## 📘 Introduction

CSS in the context of Lightning Web Components (LWC) defines the appearance and layout of your component’s UI. Each component can include a single stylesheet that’s automatically scoped to the component via Shadow DOM, ensuring modular and encapsulated styles.

---

## 🔹 1. The Role of CSS in LWC

Like traditional web development, CSS in LWC is used to style HTML templates. However, the styles are encapsulated at the component level, preventing leakage across components.

Each component includes:

* `.html` — Template structure
* `.js` — Business logic
* `.css` *(optional)* — Styling
* `.js-meta.xml` — Metadata/configuration

---

## 🔹 2. Key Characteristics of CSS in LWC

| Feature                           | Description                                                           |
| --------------------------------- | --------------------------------------------------------------------- |
| 🧩 **Component CSS File**         | Named `componentName.css`, auto-applied to the component              |
| 📦 **File Size Limit**            | Max size: 128 KB (131,072 bytes)                                      |
| 🎨 **Standard CSS Syntax**        | Supports normal selectors (classes, elements, pseudo-classes)         |
| 🔒 **Scoped by Shadow DOM**       | Styles are isolated to the component                                  |
| 🚫 **ID Selectors Not Supported** | `#id` is transformed at runtime; avoid using                          |
| 🔗 **CSS Modules**                | Import shared `.css` modules using `@import`                          |
| 💎 **SLDS Integration**           | Use `slds-*` utility classes and styling hooks for best compatibility |

---

## 🔹 3. How CSS is Used in LWC Development

### ✅ Component Styling Example

```css
/* myComponent.css */
.myContainer {
  background-color: #f4f6f9;
  padding: 1rem;
}
.title {
  font-weight: bold;
  font-size: 1.25rem;
  color: #16325c;
}
```

```html
<!-- myComponent.html -->
<template>
  <div class="myContainer">
    <p class="title">{text}</p>
  </div>
</template>
```

### 🎨 SLDS Utility Classes

```html
<div class="slds-box slds-p-around_medium">
  <p class="slds-text-color_default">Hello, {userName}!</p>
  <lightning-button class="slds-m-top_small" label="Click Me" onclick={handleClick}></lightning-button>
</div>
```

### 🕹️ Styling the Root with `:host`

```css
:host {
  display: block;
  border: 1px solid #d8dde6;
  border-radius: 0.25rem;
}
```

### 🔄 Importing Shared CSS Modules

```css
/* myComponent.css */
@import "cssLibrary/myCssLibrary";
```

---

## 🔹 4. Important Considerations & Best Practices

| Best Practice                | Why                                                 |
| ---------------------------- | --------------------------------------------------- |
| ✅ Use SLDS & Base Components | Ensures consistent UI and accessibility             |
| ✅ Use Styling Hooks          | Customize safely without breaking updates           |
| 🚫 Don’t Override Internals  | Avoid targeting internal `.slds-*` classes directly |
| 🚫 Avoid ID Selectors        | LWC transforms IDs, so `#id` selectors won’t work   |
| ✅ Style Host with `:host`    | Proper way to target the component’s root element   |
| 🛡️ Respect Shadow DOM       | Styles are scoped and do not leak in/out            |
| 🧠 Mind Accessibility        | Ensure color contrast and WCAG compliance           |

---

## 🔹 5. Sample CSS Component (myComponent.css)

```css
:host {
  display: block;
  margin-bottom: 1rem;
}
.container {
  background-color: #f4f6f9;
  padding: 1rem;
  border-radius: 0.25rem;
}
.header {
  font-weight: bold;
  color: #16325c;
  margin-bottom: 0.5rem;
}
```

---

## 🚀 Project Ideas (CSS + LWC)

| Project                       | Description                                                         |
| ----------------------------- | ------------------------------------------------------------------- |
| 📋 **Themed Components**      | Toggle between light/dark mode using SLDS classes or CSS variables. |
| 📐 **Responsive Layout**      | Build a dashboard using SLDS grid and media queries.                |
| 🖌️ **Shared Style Library**  | Create reusable style modules via CSS-only components.              |
| 🌗 **Dark Mode Toggle**       | Use `:host(.dark-mode)` or class toggles for theme switching.       |
| 🎨 **Animated Button Styles** | Add hover/transition effects with CSS keyframes.                    |

---

## 🔗 References

* [Style Components with CSS Stylesheets – LWC Docs](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.create_components_css)
* [Lightning Design System – Utility Classes](https://www.lightningdesignsystem.com/utilities/)
* [LWC Recipes GitHub](https://github.com/trailheadapps/lwc-recipes)
* [MDN – CSS `@import` Rule](https://developer.mozilla.org/en-US/docs/Web/CSS/@import)

---

> ✨ **Pro Tip:** Store this doc in your project’s `docs/` folder or bookmark it for quick reference while styling Lightning Web Components.
