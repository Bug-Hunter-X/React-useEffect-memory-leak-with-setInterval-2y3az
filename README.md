# React useEffect Memory Leak with setInterval

This example demonstrates a common error in React's `useEffect` hook:  forgetting to clear an interval or timeout within the cleanup function. This leads to memory leaks and potentially unexpected behavior.

The `bug.js` file contains the erroneous code. The `bugSolution.js` file provides the corrected implementation.

## How to reproduce:

1.  Run the code in `bug.js`.
2.  Observe the continuously incrementing counter.
3.  Notice that even when the component unmounts, the counter continues to increment in the background (memory leak).

## Solution:

The corrected code is in `bugSolution.js`. The key change is including the `clearInterval` function in the cleanup function to stop the interval when the component unmounts.