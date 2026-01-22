# React.js Notes:

## library:
- A library is a collection of pre-written functions or methods that help perform specific tasks.
- The developer is in control and decides when and how to use the library functions in the program.
- example: react , Axios(it is a library use to make http calls)

## frameworks:
- A framework is a complete structure that provides rules and guidelines to build an application.
- The framework controls the flow of the program and calls the developer’s code at the required time.
- example: Django , angular

## React Environment Set-Up:
### There are Two ways to start working with react.js-
#### 1) Normal React

#### 2) React with Vite
- step-1- npm create vite@latest (to install all required react package and structure)
- step-2- cd project_name (to go inside the react project)
- step-3- npm install (to install all the dependencies according to the package.json file)
- step is complete.
- **npm run dev(to the run the react project)**





## about React.js:
- it is an open-source JavaScript library used to build fast, scalable, and interactive user interfaces.
- use to create Single page application.
- follows component based architecture.
- uses virtual dom.
(Virtual DOM is a lightweight copy of the real DOM that React uses to efficiently update only the changed parts of the UI by comparring both real and virtual dom)

#### working of virtual dom
- react create both virtual and real dom from the start
- when user interact with the pages and make changes that changes is applied to virtual dom and real dom remain untouched.
- after that , react starts comparing both real and virtual dom by using diffing algorithem.
- after that , react deciedes which changes should apply on the real dom that process is called reconciliation.
- finally, react updates only changed parts in the real dom(efficient and fast)


## Intro of Vite with react file structure:
- **index.html** first file executed by the react)
- **package.json**(it is a configuration file used in JavaScript / Node.js projects that stores project information, dependencies, scripts, and settings are used)
- **package.local.json**(auto generated files that contains nested dependenices.)
- **vite.config.js**(stores the vite configuration)
- **gitignore**(contain the file and folder names that developer don't want to push on github)
- **scr folder**(all code files must created inside the src folder)
- **public**(images and data that you want to keep it publically acesseble)
- **scr/assests**(contains images and data that you want to keep hidden)
- **node_modules**(contain all libraries and nested libraries used in the project)


## components in react:
- A component in React is a reusable, independent piece of UI that defines how a part of the user interface should look and behave.
- a components can contain multiple nested components.
- component name should always start with uppercase letter.
- example:
```javaScript
import React from 'react'
const Comp = () => {
  return (
    <div>component</div>
  )
}
export default Comp1

```



## import and export components:
- there are two ways of import and export.
### export:
- **1)named export**(Can have multiple named exports in one file , import name must be same)
- **2)default export**(Only one default export per file and can be imported by anyname)

### import:
- **1)for named import**(name should be same and wrapped up in {})
- **2)for default import**(name can be different and import only one comp)
 

## JSX in react:
- it is a syntax extension of JavaScript used in React that lets you write HTML code inside JavaScript.
- It is converted into JavaScript by tools like Babel at the end.


## JSX with curly braces:
```javaScript
function sumoftwo(a , b){
    return a+b;
}
const Comp2 = () => {
  return (
    <>
<h1>{obj.name}</h1>
<h2>{obj.Age} years old</h2>
<h3>{obj.sirname}</h3>
<img src={url} alt="" />
<p>sum of two element: {sumoftwo(20 , 30)}</p>
    </>
  )
}

```
- as we can create variables, functions and objects both outside or inside and still use it inside the component(because jsx allows you to use any JavaScript expression that is in scope)
- but for constant values, create outside 
- and for variable values, create inside the components as they may be depend on the props



## state in react:
- State is a built-in object in React used to store data that can change over time and directly affects what is rendered on the UI.
- we have to import the state to use it(useState hook)
### why not normal variables
- they don't trigger re-renders , updates and also lose value on re-renders.
- **in react, values will only updates when the component re-renders** 

```javaScript
import {useState } from "react";
function comp(){
const [name , setname] = useState("jon");

//name (variable)
//setname(function to update that variable)

  return(
    <>
  <h1>{name}<h1/>

</>
)
}

```
### hide and show in react:
- in normal js, we use the style property to hide and show the element
- but in react, we use state for this purpose.

```javaScript
import {useState } from "react";
function comp(){
const [visible , setvisible] = useState(true);

//name (variable)
//setname(function to update that variable)

  return(
    <>
  {
    visible ? <h1> see me <h1/> : "nothing";

}
</>
)
}


```

