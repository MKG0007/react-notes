# react-notes

### React
it is the javascript liberary use to create and manage the complex frontend(where we are changing variable at multiple positons with one aciton and by using js this thing is very tough to manage)

### advantages of React:-
One-Way Data Binding(Data flows in a single direction, making it easier to debug and understand)
Component-Based Architecture(React breaks the UI into reusable components which we can reuse where we need)
Virtual DOM(React uses a virtual copy of the real DOM, which makes UI updates faster and more efficient)
react Hooks(You can use state and other features without writing classes)
JSX (JavaScript + HTML)--Allows writing UI in a syntax that looks like HTML inside JavaScript — more readable and intuitive.

#### note:- when we use react for making any website then all the variable updation and function calling handled by react by using hooks.We can change anything in the UI without using hooks. 


### custom react code:-
we can make our own react by using pure javascript(because on the other hand react is the libaray of js)

function codeRender(mainContent , reactEle){

A function use to add the created element in the root 
in this function all the characteristic of the element is passed inn form of argument

    let ele = document.createElement(reactEle.type);
    ele.innerHTML = reactEle.Children;
    ele.setAttribute('href', reactEle.props.href);
    ele.setAttribute('target' , reactEle.props.target);
    mainContent.appendChild(ele);
}

const reactEle = {//characteristic object
    type: 'a',
    props:{
        href: "https://google.com",
        target: '_blank'
    },
    Children: "click this to visit google"
};

const mainContent = document.querySelector("#root");// accessing the root element

codeRender(mainContent , reactEle);


### useState hook
it is use to set the state of the variable that we are using in the react because we can not change the values by just using js 
as react manages all the state change and updates

syntax-
header -- import { useState , useCallback } from 'react'
const [value , setvalue] = useState("default value");
value just ast as a variable
setvalue() is function that we use to set the value of the "value" variable

note- we can not change value wihout using the setfunction in react.



