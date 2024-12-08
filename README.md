# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React applications involving the `useEffect` hook: creating an infinite loop. The `useEffect` hook, while powerful, requires careful consideration of its dependency array to prevent unintended side effects.

## Bug Description

The `bug.js` file contains a component that uses `useEffect` to increment a counter on every render.  This happens because the `setCount` function depends on the `count` variable which changes inside the effect, therefore causing an infinite loop. The dependency array `[]` indicates that the effect should run only once after the component mounts; however, updating `count` inside the effect triggers a re-render, which again runs the effect, leading to an infinite loop.

## Solution

The `bugSolution.js` file provides the corrected code. The issue is resolved by ensuring that the effect only runs when the value of count changes, but it also shows an example on how to run only after mount.