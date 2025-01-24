# React useEffect Infinite Loop

This repository demonstrates a common React bug: an infinite loop caused by incorrect usage of the `useEffect` hook.  The `useEffect` hook's dependency array is incorrectly including the state variable, causing it to re-render continuously and triggering an infinite loop.

## Bug Description

The `MyComponent` component uses `useState` to manage a count.  The `useEffect` hook attempts to increment the count on every render. However, because `count` is included in the dependency array, the effect runs after every state update, leading to an infinite loop. The browser will likely crash or become unresponsive.

## Solution

The solution involves correctly managing dependencies in the useEffect hook. By removing the count variable from the dependency array, the useEffect runs only once after the initial render. Alternatively, one can use a conditional to prevent this infinite loop.