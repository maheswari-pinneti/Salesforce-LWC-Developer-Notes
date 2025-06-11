# ⚙️ JavaScript Guide for Salesforce Lightning Web Components (LWC)

---

## 📘 Introduction

JavaScript (JS) is the backbone of logic in LWC. It controls the behavior of components, handles user interactions, manages data, and facilitates communication between components and Salesforce’s backend (Apex, Lightning Data Service, etc.).

---

## 🔹 1. The Role of JavaScript in LWC

Each LWC component has an associated `.js` file that contains:

- Class declaration (ES6+ syntax)
- Properties and methods
- Event handling logic
- Decorators for reactivity and wiring data

**Example file structure:**

```

myComponent/
├── myComponent.html
├── myComponent.js
└── myComponent.js-meta.xml

````

---

## 🔹 2. Key JavaScript Features in LWC

| Feature               | Description                                             |
|----------------------|---------------------------------------------------------|
| 🧠 **ES6 Classes**     | JS logic is written using modern class syntax           |
| 📛 **Decorators**      | `@track`, `@api`, and `@wire` for reactivity and data   |
| 📦 **Modules**         | Imports from LWC modules, Apex classes, utilities       |
| 🔄 **Reactive Props**  | UI updates when reactive properties change              |
| 🎯 **Event Handlers**  | Used to respond to user actions                         |
| 📡 **Data Services**   | Use `@wire` to fetch Salesforce data                    |
| 🔐 **Encapsulation**   | Use `_property` to mark it as private (convention)      |

---

## 🔹 3. JavaScript Syntax Overview

### 🧱 Component Setup

```js
import { LightningElement, api, track, wire } from 'lwc';

export default class MyComponent extends LightningElement {
  @api userName; // Public property
  @track count = 0; // Reactive state

  handleClick() {
    this.count += 1;
  }
}
````

### 📡 Wiring Salesforce Data

```js
import { LightningElement, wire } from 'lwc';
import getContacts from '@salesforce/apex/ContactController.getContacts';

export default class ContactList extends LightningElement {
  @wire(getContacts) contacts;
}
```

### ⚙️ Lifecycle Hooks

| Hook                     | Purpose                            |
| ------------------------ | ---------------------------------- |
| `constructor()`          | Initialization logic               |
| `connectedCallback()`    | Invoked when component is inserted |
| `renderedCallback()`     | Runs after render                  |
| `disconnectedCallback()` | Called when component is removed   |

---

## 🔹 4. Common Patterns and Examples

### 🎯 Handling Button Click

**HTML**

```html
<lightning-button label="Add" onclick={handleAdd}></lightning-button>
```

**JS**

```js
handleAdd() {
  this.count++;
}
```

---

### 🧩 Composing Child Components

**HTML**

```html
<c-child-component name={userName}></c-child-component>
```

**Child JS**

```js
@api name;
```

---

### 🔁 Loop with Event Handling

**JS**

```js
handleItemClick(event) {
  const itemId = event.currentTarget.dataset.id;
  console.log('Clicked:', itemId);
}
```

**HTML**

```html
<template for:each={items} for:item="item">
  <div key={item.id} data-id={item.id} onclick={handleItemClick}>
    {item.name}
  </div>
</template>
```

---

## 🔹 5. Best Practices for JS in LWC

| Practice                          | Why                                                  |
| --------------------------------- | ---------------------------------------------------- |
| ✅ Use ES6+ Syntax                 | Modern syntax improves readability and compatibility |
| ✅ Keep Components Small           | Easier to maintain and test                          |
| ✅ Separate Logic & Template       | Keep business logic in JS and structure in HTML      |
| 🔐 Use `@api`/`@track` Properly   | Respect public-private boundaries                    |
| 🚫 Don’t Access DOM Directly      | Prefer LWC APIs like `this.template.querySelector()` |
| 📡 Prefer `@wire` over Imperative | Enables auto-refresh and is more declarative         |

---

## 🔹 6. Sample JavaScript Component

**`myComponent.js`**

```js
import { LightningElement, api } from 'lwc';

export default class MyComponent extends LightningElement {
  @api userName = 'Maheswari';
  count = 0;

  handleGreet() {
    alert(`Hello, ${this.userName}! Count is ${++this.count}`);
  }
}
```

**`myComponent.html`**

```html
<template>
  <lightning-button label="Greet" onclick={handleGreet}></lightning-button>
</template>
```

---

## 🚀 Project Ideas (JS + LWC)

| Project                | Description                                          |
| ---------------------- | ---------------------------------------------------- |
| 🧮 **Counter App**     | Track button clicks with reactive updates            |
| 📇 **Contact Viewer**  | Fetch and display contact records using Apex + @wire |
| 🔁 **To-Do List App**  | Add/remove items dynamically, manage state           |
| 📬 **Email Composer**  | Input validation and send via Apex                   |
| 📊 **Live Data Table** | Render and auto-update record list using `@wire`     |

---

## 🔗 References

* [LWC JavaScript Developer Guide](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.js_intro)
* [Apex in LWC](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.apex)
* [Wire Decorator](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_wire)
* [LWC Recipes GitHub](https://github.com/trailheadapps/lwc-recipes)

---

> ✨ **Pro Tip:** Use **VS Code + Salesforce Extensions Pack** for intelligent autocomplete, deploy-on-save, and Lightning-specific debugging tools.
