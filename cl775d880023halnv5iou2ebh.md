## How to use .ttf fonts with Tailwind CSS

If you are a frontend developer, you might face some problems while searching for good and unique fonts. If you want to use some special fonts which are not available in [Google fonts](https://fonts.google.com/), but it is available in `.ttf` or `.woff` or any other formats like these. Then I will show you how to use these with **Tailwind CSS**.

I will show you step by step process for it. I have initialized a blank project on [NextJs](https://www.nextjs.org), So I am going to talk in reference to the [NextJs](https://www.nextjs.org) folder structure but you can follow the same process for **any framework or for vanilla JS project**.

**Step 1**. Create a folder **font** (you can use any name) inside **styles** folder.
**Step 1**. Add the `.ttf` or `.woff` fonts inside the **font** folder.
**Step 3**. Create a new CSS file inside the **font** folder, I am creating stylesheet.css
**Step 4**. Now use `@font-face` CSS rule which allows us to import our own font in CSS.
```CSS
@font-face{
	font-family: 'Pixellari'; // Write the name of your custom font.


	// Below you need to give the path of the font, If you have only one format no problem
	// but if you have more then one format, you can add all those, you just need to
	// separate these with commas.
	src: url('Pixellari.woff2') format('woff2'), url('Pixellari.woff') format('woff');
}
```
**Step 5**. Now you need to import the previous CSS file on your global CSS, in my case I need to import `stylesheet.css` to my `globals.css`
```CSS
@import url('./fonts/stylesheet.css');
```
**Step 6**. Now lastly, you need to inform `tailwind CSS` that you need to extend a font-family, So for this, you need to add a few lines in `tailwind.config.js`.
```javascript
module.exports = {
	//.... All the initial code
	theme: {
		extend: {
			fontFamily: {
				'pixellari' : ['Pixellari', 'sans-serif'],  // after you font, add some fonts separated by commas to handle fallback.
			}
		}
	}
	//.... All the initial code
}
```

Now you are good to go, you can now use `font-pixellari` property in your `html class` or `jsx className`.

### Thanks for your time
Hope you like this blog, and it adds some value to your skills. Feel free to connect with me on [Twitter](https://www.twitter.com/shubhamku044) or [LinkedIn](https://www.linkedin.com/in/shubhamku044).