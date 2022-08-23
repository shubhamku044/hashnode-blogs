## Best folder structure for SCSS/SASS

## Why I am using `SASS/SCSS`?
After writing code for lots of websites in `vanilla CSS`, I understood that I am doing something wrong. I was given a lot of time to debug a very simple problem.

Then after I discovered `sass/scss` way back in 2019, and for the last 3 years, I am writing styles in `scss`. Because this solved a lot of my problems. And, debugging code is also much easier in it and it saves my time. I can create re-useable components in it. Which is also a very lifesaver thing for a programmer.

**_NOTE:_ ** I hope you all know how to initialize a 
 `sass/scss` project, If you want to learn it then please do let me know in the comment.

## Folder structure which I personally use.
So basically when I start a project, I create a root directory with the name `sass/scss`. Inside it, I create 5 folders, and 1 file main.scss.


![Screenshot of the folder structure which I use with my project.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hwgujbw1tpdxt8xdg617.png)

I will talk about each folder and file one by one below.

**`main.scss `** : In `main.scss` I used to import all the `sass/scss` files.
```scss
@import 'abstracts/variables';
@import 'abstracts/functions';
@import 'abstracts/mixins';

@import 'base/reset';
@import 'base/typography';

@import 'components/card';
@import 'components/button';
@import 'components/form';
@import 'components/carousel';

@import 'layout/grid';
@import 'layout/header';
@import 'layout/navigation';
@import 'layout/sidebar';

@import 'pages/about';
@import 'pages/auth';
@import 'pages/contact';
```

**abstracts** : This folder contains all the sass helpers you can create for your project. We create variables, functions and mixins etc. in it.

**base** : This folder contains code for reset and typography. `_reset.scss` is responsible to reset `CSS` styles. eg. text decoration for `a` tag and list style for `ul` or `ol`.

**components** : This folder contains some re-useable UI components like we need buttons on almost every page and also in the header and footer.  So we create files like buttons, cards, carousels, forms and modals etc.

**layout** : This folder contains all styles necessary for the layout of the site, eg. header, footer, sidebar.

**pages** : This folder contains styles for individual pages, like the about page, contact page, auth page etc.


---



Thanks for reading this article. Feel free to contact me on <u>[Twitter](https://twitter.com/shubhamku044)</u>, <u>[Linkedin](https://www.linkedin.com/in/shubhamku044/)</u>, <u>[Github](https://github.com/shubhamku044)</u>