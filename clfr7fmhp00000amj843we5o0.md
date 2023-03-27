---
title: "Setup ReactJs + TS + Styled-Componets + Redux"
seoTitle: "Setup react js project with typescript, styled-components and redux"
datePublished: Mon Mar 27 2023 19:10:54 GMT+0000 (Coordinated Universal Time)
cuid: clfr7fmhp00000amj843we5o0
slug: setup-reactjs-ts-styled-componets-redux
canonical: https://dev.to/shubhamku044/setup-reactjs-ts-styled-componets-redux-580d
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1679944112289/8ab5d29b-e6ea-4593-b901-1d2ca02708bc.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1679944243724/c4949425-837b-4af9-98d6-1c7cf0e0f7f7.png
tags: web-development, reactjs, redux, project-management, frontend-development

---

## Intro

In this blog tutorial, we will see how we can setup a [ReactJs](https://react.dev/) project with [Typescript](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html), [styled-components](https://styled-components.com/) and [redux toolkit](https://redux-toolkit.js.org/).

## ReactJs

React is a popular open-source JavaScript library for building user interfaces. React allows developers to build reusable UI components that can be used to create complex user interfaces. React uses a declarative syntax and a virtual DOM to efficiently update the UI when data changes. React can be used for both client-side and server-side rendering and can be integrated with other libraries and frameworks.

## Typescript

TypeScript is a programming language and a typed superset of JavaScript that adds optional static type checking, classes, interfaces, enums, and other features to JavaScript. TypeScript can help improve code quality and maintainability, catch errors at compile time rather than at runtime, and provide better tooling and editor support for large codebases. It is widely adopted in the industry for building scalable and maintainable applications.

## Styled-components

Styled Components is a popular open-source library for styling components in React applications. It allows developers to write CSS code as part of their component code using a unique syntax that is similar to regular CSS but is scoped to the specific component. This allows for easy and efficient styling of components and helps to avoid naming conflicts and specificity issues. Styled Components also support dynamic styles based on props and theming.

## Redux-toolkit

Redux Toolkit is an official opinionated collection of utilities and best practices designed to simplify the development of Redux applications. It includes pre-configured tools that help developers write clean, concise, and maintainable Redux code. Redux Toolkit provides an easy-to-use API for creating Redux slices, which are small, self-contained pieces of the Redux store that manage a specific piece of state and associated logic.

---

## Prerequisites

1. Ensure that Node.js is installed on your machine. If it is not installed, you can download and install it by [clicking here](https://nodejs.org/en).
    
2. Now you need a package manager, either `npm` or `yarn`, `npm` comes by default with node installation. You can install yarn by writing this in your bash or shell.
    

```bash
#for windows
npm i -g yarn

# for macOs/linux
sudo npm i -g yarn
```

---

### Creating react app with vite

```bash
npm create vite
#or 
yarn create vite
```

![React Js, typescript, react-redux, styled-components](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/l8kmy1lf629z58blycfs.png align="left")

![React Js, typescript, react-redux, styled-components](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nfqmo8eqvx3t84t7wl7l.png align="left")

![React Js, typescript, react-redux, styled-components](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/g1v8mlr1vnkinyfgg6qo.png align="left")

![React Js, typescript, react-redux, styled-components](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/par0j0z2flh4yy59afb9.jpg align="left")

![React Js, typescript, react-redux, styled-components](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/2m0qfwrylg0a9rqdw0xq.png align="left")

```bash
cd project-name
```

```bash
yarn
yarn dev
```

or

```bash
npm install
npm run dev
```

Now we are done with the installing `ReactJs` with `Typescript`

The folder structure should look like this for now

![Folder structrue](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/stf28rjj2o4fd25g7142.png align="left")

Now We are going to delete `App.css` and `index.css`,

### Installation and setup of styled-components

Now let's install `styled-components`. So to install `styled-components` you need to write.

```bash
yarn add styled-components
```

We will be creating `components`, `pages` and a `styles` folder inside `src`.

`components` will be for writing reusable components. `pages` directory contains the main pages of the application `styles` gonna contain the styles of components and pages

```plaintext
├── src/
│ ├── assets/
│ ├── components/
│ ├── pages/
│ ├── styles/
│ │ ├── global.ts
│ │ └── theme.ts
│ ├── App.tsx
│ └── main.tsx
│ └── vite-env.d.ts
```

`global.ts` is going to contain global styles for web-app and the `theme.ts` will contain the variables that we can use in writing style.

```typescript
// theme.ts

export const theme = {
  colors: {
    primary: '#f1faee',
    secondary: '#457b9d',
    tertiary: '#a8dadc',
    background: '#1d3557',
    text: '#f1faee',
    primaryTextColor: '#594F43',
    secondaryTextColor: '#777777',
    inputPlaceholder: '#C7C7C7',
    darkGrayText: '#303030',
    darkText: '#f1faee',
    black: '#000000',
    white: '#ffffff',
  },
  paddings: {
    container: '15px',
    pageTop: '30px',
  },
  fonts: {
    xs: '0.8rem',
    sm: '0.9rem',
    base: '1rem',
    md: '1.2rem'
  }
};
```

```typescript
// global.ts

import { createGlobalStyle } from 'styled-components';

type ThemeType = {
  colors: Record<string, string>;
}

export const GlobalStyles = createGlobalStyle<{theme: ThemeType}>`
*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  font-size: 100%;
}

body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
  min-height: 100vh;
  text-rendering: optimizeSpeed;
  font-family: 'Lato', sans-serif;
  font-size: 1rem;
  line-height: 1;
  background-color: ${({ theme }) => theme.colors.background};
  color: ${({ theme }) => theme.colors.text};
}

h1,
h2,
h3,
h4,
h5,
h6,
p,
ul,
figure,
blockquote,
dl,
dd {
  padding: 0;
  margin: 0;
}
button {
  border: none;
  background-color: transparent;
  font-family: inherit;
  padding: 0;
  cursor: pointer;
}
/* Remove list styles on ul, ol elements with a list role, which suggests default styling will be removed */
ul[role="list"],
ol[role="list"] {
  list-style: none;
}
li {
  list-style-type: none;
}
/* Set core root defaults */
html:focus-within {
  scroll-behavior: smooth;
}
/* A elements that don't have a class get default styles */
a:not([class]) {
  text-decoration-skip-ink: auto;
}

a {
  text-decoration: none;
}

/* Make images easier to work with */
img,
picture {
  max-width: 100%;
  display: block;
}

/* Inherit fonts for inputs and buttons */
input,
button,
textarea,
select {
  font: inherit;
}
/* Remove all animations, transitions and smooth scroll for people that prefer not to see them */
@media (prefers-reduced-motion: reduce) {
  html:focus-within {
    scroll-behavior: auto;
  }

  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}

#root {
  min-height: 100vh;
}
`;
```

after this, you need to add this to your `main.ts`

```typescript
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import { GlobalStyles } from './styles/global';
import { theme } from './styles/theme';
import { ThemeProvider } from 'styled-components';

ReactDOM.createRoot(document.getElementById('root') as HTMLElement).render(
	<React.StrictMode>
		<ThemeProvider theme={theme}>
			<GlobalStyles />
			<App />
		</ThemeProvider>
	</React.StrictMode>,
);
```

### Installation and setup of redux for state management

Now we need to install redux,

```bash
yarn add @reduxjs/toolkit react-redux
```

We will be creating another folder `store` inside `src`, so our new `src` will look like

```plaintext
├── src/
│ ├── assets/
│ ├── components/
│ ├── pages/
│ ├── styles/
│ │ ├── global.ts
│ │ └── theme.ts
│ ├── store/
│ │ ├── actions/
│ │ ├── reducers/
│ │ └── index.ts
│ ├── App.tsx
│ └── main.tsx
│ └── vite-env.d.ts
```

And this `store` is going to contain the code related to state management of the web application.

`store/index.ts`

```typescript
/* The code is taken from redux toolkit website */
import { configureStore } from '@reduxjs/toolkit';

export const store = configureStore({
  reducer: {
    // reducers.
  },
});

// Infer the `RootState` and `AppDispatch` types from the store itself
export type RootState = ReturnType<typeof store.getState>
// Inferred type: {posts: PostsState, comments: CommentsState, users: UsersState}
export type AppDispatch = typeof store.dispatch
```

`main.tsx`

```typescript
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';
import { GlobalStyles } from './styles/global';
import { theme } from './styles/theme';
import { ThemeProvider } from 'styled-components';
import { store } from './store';
import { Provider } from 'react-redux';

ReactDOM.createRoot(document.getElementById('root') as HTMLElement).render(
  <React.StrictMode>
    <ThemeProvider theme={theme}>
      <GlobalStyles />
	  <Provider store={store}>
		<App />
	  </Provider>
    </ThemeProvider>
  </React.StrictMode>,
);
```

That's all.

If you have any questions, drop a comment below.

[Shubham](https://shubhams.dev)