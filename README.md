Weekend Challenge 2 - FizzBuzz JS
=================================


## Functionality of the program
The program checks the divisibility of the input number. If the number is divisible by three, the word "Fizz" is returned, if the number is divisible by five, the word "Buzz" is returned. If the number is divisible by fifteen, the word "FizzBuzz" is returned.

## Dependencies
The project is written in plain JavaScript.  
Testing is performed with [e2e_training_wheels](https://www.npmjs.com/package/e2e_training_wheels).

## Setup
Instructions can be found on [e2e_training_wheels' npm website](https://www.npmjs.com/package/e2e_training_wheels#installation).


## Answers to course material questions:

### Question 1: 
_"... explain what the following lines of code do"_
* `global.browser = new BrowserHelpers()` 
  * Creates a new instance of a class called `BrowserHelpers` and assigns it to the `global.browser` variable.
* `global.expect = chai.expect;`
  * Assigns Chai's _Expect_ library, to the `global.expect` variable. It is a set of tools to make assertions in tests. Example: `expect(foo).to.equal('bar');`.

### Question 2:
_"... explain why we are placing the_ `let fizzBuzz = new FizzBuzz` _outside the it block?"_
* It will create a new instance of FizzBuzz for tests inside the `describe` block. 

### Question 3:  
_"... explain the difference between using === and == in JS?"_
* `===` strictly compares the types and values of variables without any type correction while `==` first tries to type correct the variables before comparing them. A good example of possible negative side effects of using `==` can be seen in this meme : 
![](https://www.freecodecamp.org/news/content/images/2019/07/best-js-meme-to-date-2.png)

* When choosing whether to use `===` or `==` this meme can come in handy and should always be within line of sight: ![](https://www.freecodecamp.org/news/content/images/2019/07/just-use-triple-equals.jpeg)

  
### Question 4: 
_"... explain why we are moving (number % 5 === 0) to the top?"_
* It is unneccessary to place this code at the top and it would be more efficient to leave it at the bottom. If we consider the fact that more numbers are divisible by 3, and given that the end result will place 15 as the initial divider, in my opinion, the logical placement of 5 as a divider is at the bottom. That would result in fewer calculations. 

### Question 5: 
_"... explain the difference between feature and unit test"_
* Unit tests test individiual aspects such as functions and whether they return expected values. 
* Feature tests test whole features, which can include multiple units.

### Question 6: 
```javaScript 
describe('User can input a value and get FizzBuzz results', () => {
    before(async () => {
        await  browser.init()
        await  browser.visitPage('http://localhost:8080/')
    });

    beforeEach(async () => {
        await  browser.page.reload();
    })

    after(async ()=> {
        await  browser.close();
    })
})
```
_"... explain what this code does"_
* This code opens a browser window and points it to port 8080 on the localhost (path). Before each test we reload the page to start with a fresh FizzBuzz. After the tests are finished we close the browser window. 

### Question 7: 
_"... explain what expectations in the context of testing are"_
* It refers to the expected return value and allows us to compare it to what we want to be returned. 

### Question 8: 
_"... write a line to line explanation of what is happening in this code"_

```javaScript 

<script src="js/fizzbuzz.js"></script>
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            let button = document.getElementById('button')
            let displayDiv = document.getElementById('display_answer')
            button.addEventListener('click', () =>{
                let value = document.getElementById('value').value
                let fizzBuzz = new FizzBuzz
                let result = fizzBuzz.check(value)
                displayDiv.innerHTML = result;
            })
        })
    </script>
```
1. Points the html file to an external javaScript file located in a folder one higher from the html file. 
2. Opens a script tag
3. Adds an event listener to the document that waits for the page to be loaded. It has a callback function.
4. Declares the `button` variable and assigns to it the element from the document that has the id `button`. 
5. Declares the `displayDiv` variable and assigns to it the element from the document that has the id `display_answer`. 
6. Adds an event listener to the button element (from step 4) that listens for a `click`. This listener has a callback function. 
7. Declares the `value` variable and assigns to it the value from the document element that has the id `value`. 
8. Declares the `fizzBuzz` variable as a new instance of the FizzBuzz function.
9. Declares the `result` variable as the return value of calling the FizzBuzz `check` funtion with the variable `value` as an argument. 
10. Writes to the value of `result` to the element that `displayDiv` points to (see step 5). 



### Question 9: 
_"... explain what a CDN (Content Delivery Network) is?"_
* A CDN is a set of servers that aim to deliver some kind content to users. There are many types of CDN's, one example of which is the one used in this project to create styling for the FizzBuzz program. By using a CDN we can avoid having to host the content on our own. 


