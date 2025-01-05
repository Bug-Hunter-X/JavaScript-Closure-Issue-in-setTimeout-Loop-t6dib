# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common issue in JavaScript related to closures and the use of `setTimeout` within loops.  The problem arises when trying to log the loop iteration variable (`i`) within a `setTimeout` callback. Due to the asynchronous nature of `setTimeout`, the loop completes before the callbacks execute, resulting in all callbacks logging the final value of `i`.

## Bug Description
The provided `bug.js` file contains a function `myFunction` that uses a `for` loop to schedule multiple `setTimeout` calls.  Each callback intended to log the value of `i` at the time it was scheduled. However, because of the closure, all callbacks will log 10 instead of the expected sequence of numbers from 0 to 9.

## Solution
The solution in `bugSolution.js` addresses this issue by using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, thereby capturing the correct value of `i` in each callback.