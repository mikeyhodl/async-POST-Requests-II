# async-POST-Requests-II

Now we’re going to piece together a POST request using async and await.

Feel free to refer to the async/await diagram below at any point while completing this exercise:

![async/await POST diagram](https://content.codecademy.com/courses/intermediate-javascript-requests/diagrams/async%20await%20POST%20diagram.svg)

## Q

At the top of main.js create an async arrow function and save it to a const getData().

The async keyword will ensure that the function returns a promise.


Hint
To create an async arrow function use the following syntax:

const getData = async ()  => {};
2.
In the code block for getData, we should add a try statement with an empty code block.

In case things go wrong, we need some code to handle that. Below the try code block, add a catch statement and pass in error as an argument.

Then, in the catch statement code block, log error to the console.


Hint
The syntax will look something like:

try {
  // Code to handle request
} catch (error)  {
  console.log(error)
}
3.
We now have to consider what we want to do inside of the try code block. Since we are making a POST request, we should start by using the await keyword before calling the fetch() function.

We will have to save the returned promise in a variable called response using the const keyword.


Hint
The syntax will look like:

try {
  const response = await fetch()
} catch (error)  {
  // Code to handle error
}
4.
In the fetch() call that we just made, pass in the following URL to the function as a string for the first argument:

https://api-to-call.com/endpoint
Then as our second argument, let’s pass in an empty object for now.


Hint
Remember to wrap the URL in quotes.

5.
Let’s now fill in the request options in our second argument.

First, add the method property and the value is 'POST'. Then we have to include a body property and the value is JSON.stringify({id: 200}).

Remember to separate the properties with a comma.


Hint
The general syntax to create the properties will be:

const response = await fetch(url, { 
  property1: value1, 
  property2: value2
});
6.
After the code block of response, we should create an if statement that checks the ok property of the response object.

Inside the code block of the conditional statement, await the resolution of calling the .json() method on response. Save the returned object to a variable called jsonResponse using the keyword const.


Hint
The syntax will be:

if (response.ok) {
  const jsonResponse = await response.json()
}
7.
Now that we have what we want, we should return jsonResponse directly below the code written in the previous step.

Like with previous boilerplate exercises, we’re practicing writing code. Normally, we would want to do more beyond this step of returning jsonResponse.

8.
Below the if conditional, throw a new Error() with the message 'Request failed!'

Nice work, didn’t that feel very similar to making a GET request?


Hint
The syntax will look like:

if(response.ok){
  // Previous code
}
throw new Error('Request failed!');
