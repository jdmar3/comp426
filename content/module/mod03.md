---
title: "mod03 JavaScript Functions"
description: "Get started writing and calling basic functions in JavaScript."
draft: false
weight: 30
enableToc: true
tocLevels: ["h2", "h3", "h4"]
---

In [a03](assignment/a03), we're writing some basic JS functions that can be called to return values outside of a web browser. 
This module includes some information and links about JS functions and a walkthrough of creating a very basic set. 
Some of this is covered in the [a03](assignment/a03) instructions as well.
You can use this as a reference to expand on the information presented in the instructions. 

## How do functions work in JavaScript?

Functions in JS work prettymuch the way that functions in any langauge work.
You are defining something that can be invoked to do a specific set of tasks so that you do not have to write instructions for those tasks over and over again. 

> **One weird trick:** if you find yourself doing something more than once, then you should probably rwrite a function instead of doing that thing over and over again.

Functions have a very straightforward definition syntax comprising a few parts:

1. **name**, which invokes the function;
2. **parameters**, which define local variables as arguments when the function is invoked; and
3. code that gets executed by the function.

If we want to get some sort of information out of our function, then we will need our code to include a **return**, which is all the stuff that you expect the function to spit out so you can do something else with it. 

Basic function definition syntax looks like this: 

```javascript
function name(parameter1, parameter2) {
	// some code
	return parameter1 + parameter2;
}
```

As you can see, you can use `//` to comment single lines in your code inside a function.
You can also comment multiple lines by using `*/` and `/*` to wrap whatever you want to comment between them.
These work across the board in JS and you should be using them in order to leave information for your self.
There are tons of examples of comments in [a03](assignment/a03). 

### Export / Import

In addition to writing basic functions, we want to be able to olexport them so that we can call them in other places.
This requires just a simple modification to the basic syntax listed above:

```javascript
export function name(parameter1, parameter2) {
	// some code
	return parameter1 + parameter2;
}
```

Lets's say we have the above code saved in a file called `exports.js`.

To import the same function, you would need the following in another file, we'll call it `main.js`.
We'll also add an invocation of the function. 

```javascript
import {name} from "./exports.js";

name(5,6);
```

In order to get the above to spit out the return value in the terminal, we need to wrap the call in the above block of code with a `console.log()` function. 

```javascript
import {name} from "./exports.js";

console.log(name(5,6));
```

That should spit out `11` if we were to run `main.js` in a terminal with `node`.

## Hello, world.

In this section, we will do a pretty basic walkthrough for creating, exporting, and importing a "Hello, world" function.
This example will sort of mirror what you are doing in [a03](assignment/a03).

### Get set up

First, open a terminal and create a new directory. 

```
$ mkdir helloworld
```

Then, let's create some files to get ourselves started.

```
$ cd helloworld
$ touch helloworld.js
$ touch functions.js
```

Then lets initialize our directory as an *npm* package.
You can just accept the defaults suggested by npm. 

```
$ *npm* init
```

In order to run this, we'll need some help from the *ESM* package, so let's go ahead and install that now.

```
$ *npm* install esm
```

> Normally when you want to run a `.js` file you just use the command line and call `node FileName.js`.
> But because the *es6* import and export syntax is experimental in node, we need to use a package called *ESM*.
> For us, the user, the only difference is that we now run our *node* command as follows: `node -r esm FileName.js`.
> *ESM* will not be required in later versions of node.

### Write some code!

Now we can open `helloworld.js` and we'll put the following code in it.

```javascript
export function helloWorld(message) {
	return `Hello, world ${message}`
}
```

Save that script and let's think about what we just did for a minute. 

In the above script we are defining a function `helloWorld()` and exporting it so that we can import it and then invoke it elsewhere. 
It has one parameter, which we have defined as `message`. 
Whatever value we insert as the message is going to get returned after the words "Hello, world".
If you leave the function empty, it will just return "Hello, world."

So if we want to say "Hello, world and exit", then we would call `helloWorld('and exit').
There are other ways to do this.
The code you see above is one example of how to do this.
You may find other examples that work and that is fine.

Now we need to import our function and call it. 

Open the `main.js` file that we created earlier.
Put the following in it.

```javascript
import {helloWorld} from "./helloworld";

console.log(helloWorld('and exit'));
```

Now, what are we doing here?

We are importing our previously defined and exported function `helloWorld` from the `helloworld.js` script we created earlier.
We are using a path relative to our current working directory: `./` means "this directory."
Since `helloworld.js` is stored in the same directory, `./helloworld.js` means "the hello_world.js script stored in this directory."
You'll notice that you don't have to put the file extension in the script.
*Node* will assume that we are asking for a JS file.

Next, we are invoking our function `helloWorld()`.
If we just invoke that on its own, it will not output anything in the terminal. 
To get it to do that, we need to wrap the function call in `console.log()`.

Save that file and we'll see if it works!

### Run it!

Alright, we've written some scripts and we have our directory set up with *npm*.
We should be ready to run this and see if it works.

To run your script, run the first line in the example below and you should see the output on the second line:

```
$ node -r esm main.js
Hello world, and exit.
```

You can also have *Node* run this interactively so that you can change what the function is saying.

Run:

```
node -i -r esm
>
```

The `>` means that we are in an interactive *node* session and it is expecting us to type something.
So lets type some stuff.
Let's import our function (HINT: we do the same thing that we did in the file, but just live on the command line).

```
> import {helloWorld} from './helloworld.js'
undefined
> 
```

Don't worry about the "undefined" thing.
It's misleading.
It is saying that here was no console output defined, so it echoes "undefined."

We can turn this off, but for now we're not going to worry about it. 

Next let's see what happens if we continue with our interactive *Node* session and call our `helloWorld()` function with different arguments. 

```
> import {helloWorld} from './helloworld.js'
undefined
> helloWorld()
'Hello, world undefined'
> helloWorld('')
'Hello, world '
> helloWorld('.')
'Hello, world .'
> helloWorld('and exit.')
'Hello, world and exit.'
>
```

Press CTRL+C twice or type `.exit` to exit the *Node* interactive session.

And that's it!
We did it!
We defined a function, exported it, imported it, and made it do things!

## *npm* test

If you open up `package.json` you will notice that there is a field for a test. 

We left this undefined earlier, but let's define it so that we have another way of running a test of our function.

Let's put the command that we used to run our `main.js` file in that field as a test. 

To do this, make your `package.js` file look like this:

```json
{
  "name": "helloworld",
  "version": "1.0.0",
  "description": "",
  "main": "main.js",
  "scripts": {
    "test": "node -r esm main.js"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "esm": "^3.2.25"
  }
}
```

Now, we can run the following in the terminal and it will run the command we set as a test and should generate output that looks like the example below. 

```
$ npm test
> helloworld@1.0.0 test
> node -r esm main.js

Hello, world and exit.
```

This all feeds directly into [a03](assignment/a03), which will have you defining a bunch of functions that do different things. 
