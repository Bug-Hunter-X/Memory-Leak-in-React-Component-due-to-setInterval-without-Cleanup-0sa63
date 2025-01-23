# React setInterval Memory Leak

This repository demonstrates a common mistake in React components: using `setInterval` within `useEffect` without proper cleanup. This leads to memory leaks and potential performance issues.

The `bug.js` file contains the buggy code. The `bugSolution.js` file demonstrates the correct way to use `setInterval` with cleanup.

## Problem

The original component uses `setInterval` to update the count every second. However, the interval is never cleared. This means that even if the component unmounts, the interval continues to run, consuming resources and potentially causing memory leaks.

## Solution

The solution is to use the cleanup function provided by `useEffect` to clear the interval when the component unmounts or when dependencies change.  This ensures that the interval is stopped when it is no longer needed.