# React useEffect setInterval Memory Leak
This example demonstrates a common mistake in React's `useEffect` hook when using `setInterval`.  Forgetting to include a cleanup function to `clearInterval` results in a memory leak, as the interval continues to run even after the component unmounts. This repository shows the problematic code and the corrected version.

## Bug
The `bug.js` file contains the code with the memory leak. The `setInterval` is started, but the returned interval ID is not used for cleanup in the `useEffect` hook's return statement. 

## Solution
The `bugSolution.js` demonstrates the corrected code.  The `clearInterval` function is called within the return function of the `useEffect` hook to clear the interval when the component unmounts or the effect is updated preventing the memory leak.