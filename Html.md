
# 🌐 HTML Guide for Salesforce Lightning Web Components (LWC)

## 📘 Introduction

HTML in the context of Salesforce Lightning Web Components (LWC) development is the foundational language used to define the structure and content of your user interface. It is the declarative part of an LWC component, outlining what the user sees on the screen.

---

## 🔹 1. The Role of HTML in LWC

In standard web development, HTML is the markup language that browsers interpret to render web pages. For LWC, HTML plays a similar but specialized role.

Each LWC component is defined by:

- A `.html` file: The component's visual layout.
- A `.js` file: The business logic.
- Optional `.css` or `.js-meta.xml` files.

The `.html` template is **compiled and rendered efficiently** inside the Lightning runtime and Shadow DOM.

---

## 🔹 2. Key Characteristics of HTML in LWC

| Feature | Description |
|--------|-------------|
| 🧩 **Template File** | Must match the JS file name (e.g., `myComponent.html`). |
| 📦 **Root `<template>` Tag** | All content must be wrapped in a single `<template>` tag. |
| ✅ **HTML5 Compliance** | Use semantic tags like `<div>`, `<h1>`, `<p>`, etc. |
| 🔄 **Reactive Data Binding** | Use `{property}` syntax to bind data from JS to UI. |
| 🛡️ **Shadow DOM** | Enforces style and structure encapsulation. |
| 🔐 **No Inline JavaScript** | Due to CSP, no JavaScript logic inside HTML tags. |
| 💡 **Base Components** | Use `lightning-*` components for inputs, buttons, etc. |
| 🎨 **SLDS Integration** | Use `slds-*` utility classes for styling. |

---

## 🔹 3. How HTML is Used in LWC Development

### ✅ Defining Structure & Layout
Use standard HTML tags like:
```html
<div class="slds-box">
  <h2 class="slds-text-heading_medium">{title}</h2>
  <p>{description}</p>
</div>
````

### 📊 Displaying Data

Bind JS properties like:

```html
<p>Hello, {userName}!</p>
```

### 🖱️ Handling User Events

```html
<lightning-button label="Click Me" onclick={handleClick}></lightning-button>
```

### 🔁 Composing Components

```html
<c-child-component name={userName}></c-child-component>
```

### 👁️ Conditional Rendering

```html
<template if:true={isVisible}>
  <p>This is visible!</p>
</template>
```

### 🔂 List Rendering

```html
<template for:each={items} for:item="item" for:index="index">
  <div key={item.id}>{item.name}</div>
</template>
```

---

## 🔹 4. Important Considerations & Best Practices

| Best Practice              | Why                                            |
| -------------------------- | ---------------------------------------------- |
| ✅ Use Base Components      | Built-in accessibility and SLDS compatibility. |
| ✅ Leverage SLDS            | Avoid custom CSS where possible.               |
| 🚫 Avoid Direct DOM Access | Use data binding/reactivity instead.           |
| 🧠 Consider Accessibility  | Use ARIA attributes and semantic tags.         |
| ✅ Write Semantic HTML      | Improves structure and screen reader support.  |

---

## 🔹 5. Sample HTML Component (myComponent.html)

```html
<template>
  <lightning-card title="User Info">
    <div class="slds-p-around_medium">
      <p class="slds-text-title_bold">Name: {userName}</p>
      <lightning-button label="Greet" onclick={handleGreet}></lightning-button>
    </div>
  </lightning-card>
</template>
```

---

## 🚀 Project Ideas (HTML + LWC)

| Project                           | Description                                                     |
| --------------------------------- | --------------------------------------------------------------- |
| 📋 **User Info Card**             | Display dynamic user details using lightning-card.              |
| 📑 **Record List Viewer**         | List Salesforce records with `for:each` loops.                  |
| 🔄 **Conditional Message Banner** | Show messages only under certain conditions.                    |
| 📬 **Contact Form**               | Use `lightning-input`, `lightning-button`, and form validation. |
| 📦 **Custom Modal Dialog**        | Use slots and event handlers to toggle visibility.              |

---

## 🔗 References

* [LWC Developer Guide](https://developer.salesforce.com/docs/component-library/documentation/en/lwc)
* [SLDS Utility Classes](https://www.lightningdesignsystem.com/utilities/)
* [LWC Recipes GitHub](https://github.com/trailheadapps/lwc-recipes)

---

> ✨ **Pro Tip:** Bookmark this Markdown doc or include it in your repo's `docs/` folder for fast reference while building Lightning Web Components!

```

---

Let me know if you'd like this saved as a `.md` file, or want me to add a **sidebar, table of contents, or interactive demos** using CodeSandbox or GitHub Pages!
```
