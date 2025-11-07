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

# ⚛️ React.js Advanced Notes (Part 2)

[![React](https://img.shields.io/badge/React-18+-blue?logo=react)](https://react.dev/)
[![Hooks](https://img.shields.io/badge/Hooks-Advanced-orange)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

This document contains **intermediate to advanced React.js concepts** — covering advanced hooks, state handling, component purity, context API, routing, and API integration.

---

## 🔍 useRef Hook

The **useRef** hook returns a **mutable object** with a `.current` property that persists for the **entire lifetime of the component**.

### 💡 Key Points
- Updating `ref.current` **does not trigger re-render**.  
- Commonly used to **access DOM elements** directly.  
- Best for elements that you **don’t want to cause re-renders**.  

### 🧩 Example
```jsx
import React, { useRef } from "react";

function TextInput() {
  const inputRef = useRef(null);

  function focusInput() {
    inputRef.current?.focus();
  }

  return (
    <>
      <input ref={inputRef} />
      <button onClick={focusInput}>Focus</button>
    </>
  );
}
```

> ⚠️ Note: `useRef` can also be used to hide/show elements, but this approach is **not recommended** in React (use state instead).

---

## 🧾 Uncontrolled Components

An **Uncontrolled Component** is a form input whose values are handled directly through **DOM manipulation** rather than React state.

### Characteristics
- Accessed via `document.querySelector` or `useRef()`.  
- Do not rely on `useState` for value management.  
- Best for quick forms or when integrating non-React libraries.

```jsx
import React, { useRef } from "react";

function FormExample() {
  const nameRef = useRef();

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Name: ${nameRef.current.value}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input ref={nameRef} placeholder="Enter name" />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

## 🔁 Passing Functions as Props

When a function is defined **inside a component**, it is recreated each time the component re-renders.

To avoid unnecessary re-creation:
- Define the function in the **parent component**.
- Pass it as a **prop** to the child.
- This helps in **optimization** and cleaner architecture.

```jsx
function Parent() {
  const handleClick = () => alert("Button clicked!");
  return <Child onClick={handleClick} />;
}

function Child({ onClick }) {
  return <button onClick={onClick}>Click Me</button>;
}
```

---

## 🧭 forwardRef in React

`forwardRef` allows you to **pass a ref from a parent component** to a child component.

### Old Way
```jsx
import React, { forwardRef } from "react";

function User(props, ref) {
  return <input type="text" placeholder="Enter name" ref={ref} />;
}

export default forwardRef(User);
```

### New Way (React 19+)
In newer React versions, refs can be passed through `props` directly — simpler syntax, same behavior.

---

## 🧾 useFormStatus Hook

The **useFormStatus** hook is used to manage **form submission states**.  
It allows React to **wait for form submission completion** — useful for disabling buttons during submission.

Works **only with forms**.

---

## ⚙️ useTransition Hook

The **useTransition** hook is used for **managing concurrent UI updates**.  
It lets you mark some state updates as **non-blocking** (e.g., background updates).

### Example
```jsx
import { useTransition } from "react";

function UseStatus() {
  const [isPending, startTransition] = useTransition();

  const handler = () => {
    startTransition(async () => {
      await new Promise(res => setTimeout(res, 2000));
    });
  };

  return (
    <>
      <h1>useTransition Hook Demo</h1>
      <button disabled={isPending} onClick={handler}>
        {isPending ? "Clicked..." : "Click"}
      </button>
    </>
  );
}
```

---

## 🧼 Keep Components Pure

### 🧠 Pure Function in JavaScript
A **pure function** always returns the same output for the same input and causes **no side effects**.

### ⚛️ Pure Component in React
A **pure component**:
- Does not modify external variables.
- Renders predictable output.
- Helps in debugging and optimizing re-renders.

---

## 🧮 Derived State

A **derived state** is when you store a **computed value** (based on other states) in a variable instead of state.

```jsx
const [count, setCount] = useState(0);
const doubled = count * 2; // derived state
```

> ⚙️ Derived values update automatically when their dependent state changes.

---

## 🔼 Lifting State Up

“Lifting State Up” means **sharing state between components** by moving it up to their **common parent**.

```
Parent
 ├── Child 1
 └── Child 2
```

The parent manages the state and passes data and functions down via props.

---

## 🧱 Updating Objects in State

When updating **nested objects** in React, always use the **spread operator** to maintain immutability.

```jsx
const [data, setData] = useState({
  name: "Mayank",
  class: 10,
  detail: { city: "Agra", state: "UP" },
});

function updateObj(e) {
  setData({
    ...data,
    detail: { ...data.detail, city: e.target.value },
  });
}
```

---

## 📋 Updating Arrays in State

Use the spread operator to add, update, or remove items.

```jsx
setUsers([...users, newUser]); // add
setUsers(users.filter(u => u.id !== id)); // remove
```

---

## 🧾 useActionState Hook

Used to handle **form submissions** and track form data + pending states.

```jsx
const handleSubmit = async (prevData, formData) => {
  let name = formData.get('name');
  let password = formData.get('password');

  await new Promise(res => setTimeout(res, 2000));
  console.log("Submitted:", name, password);
};

const { data, action, pending } = useActionState(handleSubmit, undefined);

<button disabled={pending}>
  {pending ? "Submitting..." : "Submit"}
</button>
```

---

## 🆔 useId Hook

- Introduced in React 18.  
- Generates a **unique and stable ID** for client and server.
- Ideal for labeling form fields.

```jsx
const id = useId();
<label htmlFor={id}>Name</label>
<input id={id} />
```

---

## 🧩 Fragments in React

Fragments allow returning **multiple elements** without adding extra DOM nodes.

```jsx
<Fragment></Fragment>
```
or shorthand:
```jsx
<></>
```

---

## ⚙️ Rules for Hooks

✅ Hooks must:
1. **Start with “use”** (e.g., `useState`, `useEffect`).  
2. Be used **at the top level** of the component.  
3. Be used only inside **React components or custom hooks**.

---

## 🧰 Custom Hooks

You can create your own hooks to **reuse logic** across multiple components.

Example:
```jsx
function useWindowWidth() {
  const [width, setWidth] = useState(window.innerWidth);

  useEffect(() => {
    const handleResize = () => setWidth(window.innerWidth);
    window.addEventListener('resize', handleResize);
    return () => window.removeEventListener('resize', handleResize);
  }, []);

  return width;
}
```

---

## 🌍 Context API

The **Context API** allows you to share data between components **without prop drilling**.

### Key Components
- `createContext()` — Initializes the context.
- `Provider` — Provides data.
- `useContext()` — Consumes data.

Example:
```jsx
const UserContext = createContext();

function App() {
  return (
    <UserContext.Provider value="Mayank">
      <Profile />
    </UserContext.Provider>
  );
}

function Profile() {
  const user = useContext(UserContext);
  return <h2>Hello {user}</h2>;
}
```

---

## 🧭 React Router

React Router is used to **create routes for different pages** in a React app.

### Installation
```bash
npm install react-router-dom
```

### Example Setup
```jsx
import { BrowserRouter, Routes, Route, Link } from "react-router-dom";

function App() {
  return (
    <BrowserRouter>
      <Link to="/">Home</Link>
      <Routes>
        <Route path="/" element={<Home />} />
      </Routes>
    </BrowserRouter>
  );
}
```

### Components
| Component | Purpose |
|------------|----------|
| **BrowserRouter** | Enables client-side routing. |
| **Routes** | Defines route group. |
| **Route** | Maps path to component. |
| **Link** | Navigates between routes. |

---

## ⚙️ 404 Page and Redirection

```jsx
<Route path="/*" element={<PageNotFound />} />
<Route path="/*" element={<Navigate to="/" />} />
```

---

## 🧩 Nested Routes

Use `<Outlet />` to render **child components** inside parent routes.

```jsx
<Route path="products" element={<Products />}>
  <Route path=":productId" element={<ProductDetail />} />
</Route>
```

---

## 🧱 Layout and Index Routes

Layout routes let you share common UI (like a navbar).

```jsx
<Route element={<Navbar />}>
  <Route index element={<Home />} />
  <Route path="about" element={<About />} />
</Route>
```

---

## ⚙️ Route Prefixes and Dynamic Routes

### Prefix Example
```jsx
<Route path="/in">
  <Route path="user">
    <Route path="mayank" />
  </Route>
</Route>
```

### Dynamic Route
```jsx
<Route path="/user/:id" element={<User />} />
```

Access dynamic data:
```jsx
const { id } = useParams();
```

---

## 🧭 NavLink and Active Class

`NavLink` provides automatic **active class** for current routes.

```jsx
<NavLink
  to="/home"
  className={({ isActive }) => (isActive ? "active link" : "link")}
>
  Home
</NavLink>
```

---

## 🎨 Installing Tailwind CSS in React

Visit [TailwindCSS Docs](https://tailwindcss.com/docs/guides/create-react-app)  
Run the setup commands and configure `tailwind.config.js`.

---

## 🌐 API Handling in React

APIs (Application Programming Interfaces) are used for backend communication.

### Common Methods
| Method | Purpose |
|--------|----------|
| `GET` | Fetch data |
| `POST` | Add data |
| `PUT/PATCH` | Update data |
| `DELETE` | Remove data |

### Example
```jsx
async function getUsers() {
  const res = await fetch("https://dummyjson.com/users");
  const data = await res.json();
  console.log(data);
}
```

---

## 💻 Create Your Own API (JSON Server)

**Installation:**
```bash
npm install json-server
```

Create a `db.json` file and run:
```bash
npx json-server --watch db.json --port 3000
```

### Example (Fetch Local Data)
```jsx
import { useEffect, useState } from "react";

function GetData() {
  const [users, setUsers] = useState([]);
  const [loading, setLoading] = useState(false);

  useEffect(() => {
    getUserData();
    setTimeout(() => setLoading(true), 4000);
  }, []);

  async function getUserData() {
    let res = await fetch("http://localhost:3000/users");
    res = await res.json();
    setUsers(res);
  }

  return (
    <>
      <table border={5} style={{ textAlign: "center", padding: "5px" }}>
        <thead>
          <tr><th>Name</th><th>Age</th><th>Email</th></tr>
        </thead>
        {loading ? (
          <tbody>
            {users.map((u, i) => (
              <tr key={i}>
                <td>{u.name}</td>
                <td>{u.age}</td>
                <td>{u.email}</td>
              </tr>
            ))}
          </tbody>
        ) : (
          <h3>Data loading...</h3>
        )}
      </table>
    </>
  );
}

export default GetData;
```

---

> ✨ **React Hooks and Routing together create the backbone of dynamic, scalable web apps.**
> Mastering these concepts helps you become a true front-end engineer.

---

## 📚 Author

**👨‍💻 Mayank Kumar Gupta**  
Frontend Developer | React Enthusiast | JavaScript Lover  
🌐 [GitHub](https://github.com/) | [LinkedIn](https://linkedin.com/)

