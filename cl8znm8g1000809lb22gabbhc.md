# JavaScript array method -map()

Hello Developers,

While coding you definitely arrays somewhere in your code. and if you have used arrays then must need to know how to work loop over arrays.
So, basically in this blog, we are going to learn about the most used javascript array method. Yes, you have guessed it correctly, it's the `map()` method.

## map()

%[https://www.youtube.com/watch?v=ldQ4wHy0I_8&t=13s]

Remember all the points which are written below, so that you will never confuse about when and where to use the `map()` method.

1. It is used to iterate over an array, it's just like forEach() and for of loop.
2. It does not mutate the original array.
3. It returns a new array.

## Syntax
```javascript
const array = [2, 4, 5, 6]

// it takes a callback function
// array.map(callbackFn())

// parameters of callback function
// 1. callbackFn(element)
// 2. callbackFn(element, index)
// 3. callbackFn(element, index, arrary)    the 3rd one is the original array where we are using map()

```

We are going to learn javascript `map()` with 3 questions.

### Question 1
```javascript
// Create a new array based on the given array with twice every element.
// double [2, 6, 4, 16, 18, 10, 2, 14]

const myArray = [1, 3, 2, 8, 9, 5, 1, 7]

const doubledArray = myArray.map((el) => el * 2)

```

### Question 2
```javascript
// Create a new array based on the given array with the sum of index + element at that index.
// double [1, 4, 4, 11, 18, 10, 2, 14]

const myArray = [1, 3, 2, 8, 9, 5, 1, 7]
```

### Question 3
```javascript
// create a new array based on the given array object, the new array should contain 

const items = [
	{
		id: 1,
		fName: 'John',
		lName: 'Doe',
	},
	{
		id: 2,
		fName: 'Julia',
		lName: 'Green',
	},
	{
		id: 3,
		fName: 'Thomas',
		lName: 'Freguson',
	},
	{
		id: 4,
		fName: 'Jane',
		lName: 'Smith',
	},
	{
		id: 5,
		fName: 'Maria',
		lName: 'Reese',
	},
]

const newItems = items.map((el) => `${el.fName} ${el.lName}`)
// ['John Doe', 'Julia Green', 'Thomas Freguson', 'Jane Smith', 'Maria Reese']
```

Hope you have understood when to use the `map()` method in javascript

If you have any queries you can post in the comment.

You can also connect with me on [LinkedIn](https://www.linkedin.com/in/shubhamku044) and [Twitter](https://twitter.com/shubhamku044)