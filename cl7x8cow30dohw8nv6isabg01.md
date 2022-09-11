## Solidity - Hello World

## Introduction to Solidity
Solidity is an object-oriented programming language created by _Ethereum_ _Network_ _Team_ for developing `smart contracts` in _Blockchain_.

Solidity is a high-level language that is based on other programming languages, including C++, Java, Python etc. Solidity code should feel familiar if you're familiar with any of those programming languages.

Solidity has very good documentation, you can it out [here](https://docs.soliditylang.org/en/v0.8.17/index.html).

## Prerequisites for learning solidity
+ [Basics of Blockchain](https://docs.soliditylang.org/en/v0.8.17/introduction-to-smart-contracts.html#blockchain-basics)
+ Ethereum basics
+ Basics of any programming language (eg. C, C++, Java, JavaScript, python etc.)

## Where to write solidity code
In this tutorial, we will write our solidity program in remix IDE, an open-source online IDE that provides a solidity compiler.

### Step 1
[Click here](https://remix.ethereum.org/) to open Remix. You will see an interface like this.

![Remix IDE interface](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mt67yiro70fsrf5b75wy.png)

### Step 2
Let's create a `HelloWorld.sol` file, in which we will be writing our first solidity code.

![Create a new file in remix](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9xbrjhpsgzhkctt4dwdu.png)
Then click on this _New File_ button and create a new file, make sure it is ending with `.sol`. You will find this layout a little bit similar to the _visual studio code_.
![Create a HelloWorld.sol file](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/k9u4revct6da44meo5rz.png)

### Step 4
Now we are good to go, let's write some code.

```solidity
// SPDX-Liscense-Identifier: MIT
pragma solidity ^0.8.9;

contract HelloWorld{
	string public greet = "Hello World";
}
```
I will explain every line of the code later in this blog, you just copy this to your remix compiler.

### Step 5
Now let's compile then deploy and then run the code.

- Compile
![Remix compile section to compile solidity code](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/93bdqjke4r6wzvvq0cvt.png)

- Deploy
![Remix deploy section to compile solidity code](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/63qqcnjwd2r6x0vixttm.png)

- Run
![Remix run section to compile solidity code](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hqbjl9s8yn5iv2mfjuvc.png)

## Explanation of the code
```solidity
// SPDX-Liscense-Identifier: MIT
```
The above comment is added to prevent throwing errors and to prevent legal problems regarding copyright, it is important to specify the license of the smart contract, the _MIT license makes the code available as free and open-source_.

```solidity
pragma solidity ^0.8.9;
```
The above line means that the code will compile with a compiler greater than version `0.8.9`.

We are creating a contract named HelloWorld.
```solidity
contract HelloWorld [
	// ...
}
```

```solidity
// Here we have initialised a state variable named greet.
string greet = "Hello World";
```
Above we have created a state variable with name greet, but now we want to create a function name greet which can be called by anyone outside the contract, and it should return a string “Hello World”.

Do not worry if you get confused with this syntax, You will learn everything in deep in the upcoming blog. This blog is just to give you an overview of the smart contract and solidity.

```solidity
// Method 1
string message = "Hello World";
function greet() public view returns(string memory) {
	return message;
}

// Method 2
string public greet = "Hello World";
```

Congrats, You have successfully written your first program in solidity.

Feel free to connect with me on [Twitter](twitter.com/shubhamku044), [LinkedIn](linkedin.com/in/shubhamku044)