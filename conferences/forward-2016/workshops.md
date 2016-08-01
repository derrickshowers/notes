# Functional-Light Javascript
_Kyle Simpson_

* First rule of a functional programmer: side effects are bad!
  - "free variables" are defined outside of a function. No bueno.
  - Program is harder to reason due to state changes occurring before non-pure function is executed.
  - Side effects can't be completed avoided. I/O is a side effect (appending to the DOM, outputting to the console, etc.)

### Pure functions

* Best approach as a functional programmer
* What about functions that can't be pure (library, I/O)?
* Wrap impure functions in pure functions!

```js
function bar(x, y, z) {
  foo(x);
  return [y, z];

  function foo(x) {
    y = y * x;
    z = y * x;
  }
}

bar(5, 2, 3);     // [10, 50]
bar(5, 10, 50);   // [50, 250]
```
_Note: prior to this, `y` and `z` where defined outside of foo, making foo unpure_

### Composition
* Value of being able to compose parts of a program from other parts of a program. Building blocks (or LEGOs)
* Functional programming is not about keeping things DRY, it's about abstraction
* Why is abstraction good? It's about focusing on the correct part of the code
* Higher-order functions: take functions as inputs and/or return functions as outputs

**Simple of higher-order functions**
```js
function compose2(fn1, fn2) {
  return function(arg1, arg2, arg3) {
    return fn2(fn1(arg1, arg2), arg3);
  }
}

function sum(a, b) {
  return a + b;
}

function mult(a, b) {
  return a * b;
}

var twoFunctions = compse2(sum, mult);
twoFunctions(1, 2, 3);    // 9
```

### Immutability

* `const` doesn't help with immutability - it prevents _reassignment_, not a change in value.
* A function which changes a value is a side effect - more of an issue than a variable being reassigned.
* But... important part for a functional programmer is not about enforcing immutability, but respecting all things as immutable.

### Closure

* Kyle's definition: Closure is when a function _remembers_ the variables around it even when that function is executed elsewhere.
* If closure is about remembering variables around it, why do functional programmers use it? Doesn't really seem like a pure function anymore. Hmmm.
* Closure works if variables in it cannot be changed from underneath it (`fn1` and `fn2` in the code example above are basically constants).
* Currying vs partial application
  - A function that sets an x number of arguments (but not all) and returns a function to set the rest.
  - Currying is a special from of partial application, a lazy form of partial application. Arguments get applied one at a time.

### Proper Tail Calls (PTC) / Recursion
[Read this](http://benignbemine.github.io/2015/07/19/es6-tail-calls/)

* Recursion is a declarative way of doing things (instead of an imperative as with a loop).
* Only implemented by webkit. Other browsers are suggesting STC (syntactical tail calls). Still a lot up in the air.
* `return sum + recursiveFn(...args)` breaks tail calls because `sum` is being stored on the stack.
* What about doing something like `return recursiveFn(sum, ...args)`?

### Lists

* **Map**: Transformation. Transform all values of a list. Don't mutate, return a new list with values transformed.
* **Filter**: Exclusion. New list with fewer items.
* **Reduce**: Combining. Takes a list, function and an initial value. Returns a result (combo of everything based on func passed in).

### Fusion

* Take multiple maps/filters and compose them together. See Underscore's [compose](http://underscorejs.org/#compose) method.

### Transduce

* Fusing functions with different signatures (map and filter)
* Example: `composeRight(mapReducer(add1), filterReducer(isOdd))(list reduction);`
