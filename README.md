# React Memory Leak: Unclosed setInterval in useEffect

This repository demonstrates a common React memory leak scenario caused by the improper use of `setInterval` within a `useEffect` hook.  The `setInterval` function, without cleanup, continues to run even after the component unmounts leading to memory leaks and performance issues.

## Problem
The provided `MyComponent` uses `setInterval` to update a counter every second. However, it fails to clear the interval using `clearInterval` in the cleanup function of `useEffect`.  This causes the interval to persist even after the component is unmounted from the DOM.

## Solution
The solution demonstrates how to properly clear the `setInterval` in the cleanup function of `useEffect` to prevent memory leaks.  The cleanup function is essential to ensure that any resources allocated by the effect are released when the component unmounts.