# React.js Notes:

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
- index.html (first file executed by the react)
- 

