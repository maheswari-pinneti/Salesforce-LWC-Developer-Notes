# 📚 Salesforce LWC Developer Notes

---
 Salesforce LWC Developer Notes repository, including installation, code example, run steps, and troubleshooting — all in professional GitHub markdown:

---

This repository contains well-structured, beginner-to-advanced level notes for **Salesforce Lightning Web Components (LWC)** development. It's designed as a quick reference guide and a personal learning tracker to support developers preparing for Salesforce developer roles, certifications, or real-world projects.

---

## ✨ What's Inside

- ✅ HTML5 essentials in LWC context
- ✅ LWC directives and templating syntax (`if:true`, `for:each`, etc.)
- ✅ Base Lightning Components usage (`lightning-button`, `lightning-input`, etc.)
- ✅ SLDS utility classes for consistent Lightning styling
- ✅ Component composition and data binding
- ✅ Event handling and custom event examples
- ✅ Handy markdown documentation for GitHub readability

---

## ⚙️ Installation & Setup: Salesforce LWC Developer Environment

### ✅ Prerequisites

- 📥 [Salesforce CLI](https://developer.salesforce.com/tools/sfdxcli)
- 🧠 [Node.js](https://nodejs.org/)
- 🧩 [VS Code](https://code.visualstudio.com/)
- 🧩 [Salesforce Extension Pack for VS Code](https://marketplace.visualstudio.com/items?itemName=salesforce.salesforcedx-vscode)

---

### 🛠️ Step-by-Step Setup

#### 1️⃣ Install Salesforce CLI

```bash
# Mac
brew install sfdx-cli

# Windows & Linux
# Download manually:
https://developer.salesforce.com/tools/sfdxcli
````

#### 2️⃣ Authenticate to Salesforce Org

```bash
sfdx auth:web:login -a myDevHub
```

> This opens your browser to login. Use a Developer Edition org or Sandbox.

#### 3️⃣ Create a Salesforce DX Project

```bash
sfdx force:project:create -n myLWCProject
cd myLWCProject
```

#### 4️⃣ Enable Dev Hub

```bash
# Login to your org → Setup → Dev Hub → Enable
```

#### 5️⃣ Create a Scratch Org

```bash
sfdx force:org:create -s -f config/project-scratch-def.json -a lwcScratch
```

#### 6️⃣ Push Code to Scratch Org

```bash
sfdx force:source:push
```

#### 7️⃣ Open Scratch Org

```bash
sfdx force:org:open
```

---

## ✨ Create Your First LWC Component

```bash
sfdx force:lightning:component:create \
  --type lwc \
  --componentname helloWorld \
  --outputdir force-app/main/default/lwc
```

### 📄 helloWorld.html

```html
<template>
  <div class="slds-box slds-theme_default">
    <h1>Hello, {name} 👋</h1>
    <lightning-input label="Your Name" onchange={handleChange}></lightning-input>
  </div>
</template>
```

### 📄 helloWorld.js

```javascript
import { LightningElement } from 'lwc';

export default class HelloWorld extends LightningElement {
  name = 'Trailblazer';

  handleChange(event) {
    this.name = event.target.value;
  }
}
```

### 📄 helloWorld.js-meta.xml

```xml
<?xml version="1.0" encoding="UTF-8"?>
<LightningComponentBundle xmlns="http://soap.sforce.com/2006/04/metadata">
  <apiVersion>60.0</apiVersion>
  <isExposed>true</isExposed>
  <targets>
    <target>lightning__AppPage</target>
    <target>lightning__HomePage</target>
  </targets>
</LightningComponentBundle>
```

---

## 🚀 Running the App

* Open your scratch org:

  ```bash
  sfdx force:org:open
  ```

* In the org UI, go to **App Builder**

* Add `helloWorld` to a Lightning Page

* Save and **Activate** the page

* Preview it live!

---

## 🐞 Debugging & Troubleshooting

| ❌ Error                 | ✅ Reason                           | 🛠️ Fix                                           |
| ----------------------- | ---------------------------------- | ------------------------------------------------- |
| Component not visible   | Missing `isExposed` or `targets`   | Add `<isExposed>true</isExposed>` + valid targets |
| `undefined` input value | Missing `event.target.value`       | Use `this.name = event.target.value;`             |
| Push fails              | Invalid folder path or file format | Use correct folder: `force-app/main/default/lwc`  |
| Not loading styles      | Missing SLDS class or static CSS   | Use official SLDS utility classes                 |
| Component not reactive  | No tracked/public decorators used  | Add `@track` or expose properties with `@api`     |

---

## 💡 Helpful CLI Commands

```bash
sfdx force:org:list                     # List all connected orgs
sfdx force:source:status                # View local vs org changes
sfdx force:source:pull                  # Pull updates from org
sfdx force:source:deploy -p force-app   # Deploy to any org
```

---

## 🤝 Contribution

🙌 Contributions are welcome!
Feel free to submit issues, ideas, or PRs to expand this reference for fellow Trailblazers.

---

## 📌 License

[MIT License](LICENSE) – Use freely, just give credit where due!

---

> Made with 💙 by [Maheswari Pinneti](https://www.linkedin.com/in/maheswari-pinneti)
> ✨ Fork it, star it, and make it your own Salesforce dev vault!

