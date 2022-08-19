## Understanding the React useState Hook

Before understanding what is a react `useState` hook, let us first know what is a hook?

## **What is a hook?**
Hooks are a feature of react which allows us to use state and other React features without writing a class. React hooks can only be used in the functional components.

## **What is `useState` hook?**
useState is a react hook which is used to add a state variable to our components. It means that we can now declare state variables to functional components.


**Syntax to declare `useState` hook**
```javascript
const [state, setState] = useState('Initial Value');
```

**Where to use useState hook**
Let us simply understand this using an example. Let say we are working on a hamburger menu.

```javascript
import React from 'react';

export const MyComponent = () => {
    // BAD ❌ - this way it won't work, We need to use useState hook in such situation
    let openHamburger = false;
    
    const toggle = () => {
        openHamburger = !openHamburger;
    }
    
    return (
        // ...
    )
}
```

Whenever we want to change the value of a variable and then after we want to use that, then we need to use `useState` hook.
```javascript
import React, { useState } from 'react';

export const MyComponent = () => {
    // GOOD ✅
    const [openHamburger, setOpenHamburger] = useState(false);
    
    const toggle = () => {
        setOpenHamburger(!openHamburger);
    }
    
    return (
        // ...
    )
}
```

## **Where we can use `useState` hook?**
- We can use `useState` hook only in functional components, not in class components.
- We want to change the value of a variable and then after we want to use that.
- Every time a components run, the `useState` hook also runs in the exact same order in which it is written.
- We cannot put hooks inside if statements, or inside any functions or inside loops or it should not be nested in any things. It should be present in the top level of the functional components.

## **How to use `useState` hook?**
- `useState` hook always returns an array with two values. The first is state and the second value is a function.
- The function which is `useState` returns is used to change the state.
- Every time we call the update function of the `useState`, it re-renders the components with the updated state value.
- Every time when we need to use the previous value to create the new value, we need to use the function version of setting the state.

```javascript
const [count, setCount] = useState(6);

const inc = () => {
  setCount(prevCount => prevCount + 1); // setCount(6 => 6 + 1)
}
```

- `useState` can also be used in other way by passing function in it. And this will run only once when the component is rendered first time.

```javascript
const [state, setState] = useState(()=> 6); // by doing this way, whenever we update the state value, the component will not re-renders.
```

I hope this blog will help you to understand `useState` hook.
