# ⚛️ React.js Complete Notes

[![React](https://img.shields.io/badge/React-18.0+-blue?logo=react)](https://react.dev/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![JavaScript](https://img.shields.io/badge/Language-JavaScript-yellow.svg)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

React is a **JavaScript library** used to create and manage **complex frontends** with multiple states.  
It helps developers build **Single Page Applications (SPAs)** efficiently using its **Virtual DOM** feature.

> 🧠 Developed and maintained by **Facebook (Meta)**.

---

## 🚀 Ways to Create a React Project

### 1️⃣ Using Create React App
```bash
npx create-react-app my_project_name
```

### 2️⃣ Using Vite (Faster)
```bash
npm create vite@latest
```
> During setup, you’ll be asked some configuration questions.

---

## 🧩 Key Notes

- Component names **must start with a capital letter**.  
- JSX = **JavaScript XML** (or **JavaScript Syntax Extension**).  
- TSX = **TypeScript XML** (used when working with TypeScript).  
- `index.html` is the **first file that loads** in a React project.  

---

## 📁 React Project Structure

### 📦 `package.json`
Contains project metadata, dependencies, devDependencies, and package versions.

### 🗂️ `src/` Folder
Contains all source code files — components, hooks, and main entry file (`main.jsx` or `index.js`).

### 🖼️ `assets/` and `public/` Folders
Contain images and static files.  
> 🔒 Use **assets** instead of **public** for better security.

---

## 🧱 Components in React

A **Component** is a reusable, independent piece of UI that defines how part of the app looks and behaves.  
It can include **HTML (JSX)**, **CSS**, and **JavaScript logic** together.

---

## 📦 Import and Export in React

### ➕ Import

#### 1. Named Import
```js
import { add, PI } from './utils.js';
```

#### 2. Default Import
```js
import multiply from './math.js';
```

#### 3. Import Everything
```js
import * as mathUtils from './math.js';
```

---

### ➤ Export

#### 1. Named Export
```js
export function add(a, b) {
  return a + b;
}
```

#### 2. Default Export
```js
function App() {
  return <h1>Hello World</h1>;
}
export default App;
```

#### 3. Export Everything
```js
export * from './utils.js';
```

---

## 🧠 JSX in React

JSX allows writing HTML-like syntax inside JavaScript.

Example:
```jsx
<img src={imageUrl} alt="profile" />
```

> ⚙️ Always use **camelCase** for event handlers and attributes.

---

## 🖱️ Events and Function Calls

- Use **camelCase** event names (`onClick`, `onChange`, etc.).
- Always pass a **function definition**, not a function call.

```jsx
<button onClick={handleClick}>Click Me</button>
```

---

## ⚙️ Node Modules Note

> ❗ Never push the `node_modules` folder to GitHub.  
> Anyone cloning your project can reinstall dependencies using:
```bash
npm install
```

---

## 🪝 Hooks in React

Hooks let you **use React features** (like state, lifecycle, and side effects) in **functional components**.

Common Hooks:
- `useState` — Manage component state.
- `useEffect` — Handle side effects.
- `useRef` — Access DOM elements.
- `useMemo`, `useContext`, etc.

---

## 📤 Props in React

**Props** (short for “properties”) are used to **pass data between components**.

```jsx
<MyComponent title="React Notes" />
```

---

## 🧾 Controlled Components

A **controlled component** is a form input whose value is managed by React state.

### 💡 How It Works
1. Store input value in state.  
2. Use `onChange` handler to update the state.  
3. Bind `value` attribute to that state.

Example:
```jsx
const [name, setName] = useState('');

<input
  type="text"
  value={name}
  onChange={(e) => setName(e.target.value)}
/>
```

**Benefits:**
- Single source of truth  
- Easy validation and manipulation  
- Dynamic UI updates

---

## 🔁 Looping in JSX

Use the **`map()`** function to loop through lists.

```jsx
{users.map((user) => (
  <li key={user.id}>{user.name}</li>
))}
```

> 🧩 Always use a **unique key** prop for each item to help React track updates efficiently.

---

## ⚡ useEffect Hook

`useEffect` is used to handle **side effects** like fetching data, timers, or manual DOM manipulation.

### Syntax:
```jsx
useEffect(() => {
  // side effect code
}, [dependencies]);
```

### Variations:
| Type | Description |
|------|--------------|
| `useEffect(()=>{})` | Runs on every render. |
| `useEffect(()=>{}, [])` | Runs only once (on mount). |
| `useEffect(()=>{}, [state])` | Runs when a specific state changes. |

---

## 🧬 Component Lifecycle in React

| Phase | Description |
|--------|--------------|
| **Mounting** | Component is created and added to the DOM. |
| **Updating** | State/props changes trigger re-render. |
| **Unmounting** | Component is removed from the DOM. |
| **Error Handling** | Catches errors during rendering. |

---

## 🎨 Styling in React

There are **five main ways** to style components:

### 1️⃣ Inline Style
```jsx
<h1 style={{ color: "red", backgroundColor: "yellow" }}>Hello</h1>
```

### 2️⃣ External CSS
```jsx
import './style.css';
<div className="container"></div>
```

### 3️⃣ CSS Modules
```jsx
import styles from './Button.module.css';
<button className={styles.primaryBtn}>Click</button>
```

### 4️⃣ Styled Components (Library)
```bash
npm install styled-components
```
```jsx
import styled from "styled-components";

const Heading = styled.h1`
  color: red;
  border: 2px solid green;
  text-align: center;
`;
```

### 5️⃣ External CSS Libraries / Frameworks
Example: **Tailwind CSS**, **Bootstrap**, etc.

---

## 🎭 Dynamic and Conditional Styling

```jsx
<div style={{ color: isActive ? "green" : "gray" }}>Status</div>
```

---

## 💅 External CSS in React

Create and import an external CSS file:
```jsx
import './css/style.css';
```
Usage:
```jsx
className="myStyle"
```

---

## 🎨 CSS Modules

To prevent style leakage to parent components, use **module-specific styling**:

- File format: `ComponentName.module.css`

```jsx
import styles from './App.module.css';
<div className={styles.wrapper}></div>
```

---

## 🌈 Styled Components

**Installation:**
```bash
npm i styled-components
```

Example:
```jsx
import styled from "styled-components";

const Button = styled.button`
  background-color: blue;
  color: white;
  border-radius: 8px;
`;
```

---

## 🧱 Bootstrap in React

**Installation:**
```bash
npm install react-bootstrap bootstrap
```

Add Bootstrap CSS in your main file:
```jsx
import 'bootstrap/dist/css/bootstrap.min.css';
```

Then, import and use Bootstrap components:
```jsx
import { Button } from 'react-bootstrap';
<Button variant="primary">Click Me</Button>
```

---

## 🏁 Summary

| Feature | Description |
|----------|--------------|
| React | JavaScript library for building UI |
| JSX | JavaScript XML syntax |
| Props | Pass data between components |
| Hooks | Use React features in functional components |
| useEffect | Handle side effects |
| Styling | Inline, external, modules, or styled-components |

---

> ✨ **React makes UI development simple, modular, and scalable.**  
> Master components, hooks, and state management to build modern front-end applications.

---

## 📚 Author

**👨‍💻 Mayank Kumar Gupta**  
> Passionate about Frontend Development & Modern JavaScript Frameworks.  
> 🚀 [Follow me on GitHub](https://github.com/) | [LinkedIn](https://linkedin.com/)
