# JavaScript Closure Issue in setTimeout Loop

This example demonstrates a common issue in JavaScript involving closures and the `setTimeout` function within loops.  The expected behavior is to print numbers 0-9 with a one-second delay between each number. However, due to how closures work, this code will print the number 10 ten times.

## Bug
The `setTimeout` function uses a closure that captures the variable `i` by reference, not by value. By the time `setTimeout` finally executes, the loop has already completed, and `i` has its final value of 10.

## Solution
The solution uses an immediately invoked function expression (IIFE) to create a new scope for each iteration, thus capturing the value of `i` at each step.

This repository contains two files: `bug.js` (demonstrates the bug) and `bugSolution.js` (provides the corrected code).