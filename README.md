Weekend Challenge 2 - FizzBuzz JS
=================================

## Question 1: "explain what the following lines of code do"
* `global.browser = new BrowserHelpers()` 
  * Creates a new instance of a class called `BrowserHelpers` and assigns it to the `global.browser` variable.
* `global.expect = chai.expect;`
  * Assigns Chai's _Expect_ library, to the `global.expect` variable. It is a set of tools to make assertions in tests. Example: `expect(foo).to.equal('bar');`.

## Question 2:
* _"... explain why we are placing the_ `let fizzBuzz = new FizzBuzz` _outside the it block?"_
  * It will create a new instance of FizzBuzz for all tests inside that `describe` block.

