# React 19 useEffect Bug: Unexpected Multiple Executions on Mount

This repository demonstrates a seemingly unusual issue where a `useEffect` hook with an empty dependency array runs twice during the initial mount in React 19.  This is counter to the expected behavior, which is only one execution after initial render.

## Reproduction

The `bug.js` file contains a simple component that uses `useEffect` to log a message. Despite having an empty dependency array, the effect runs twice on the first render.

## Solution

The solution involves understanding the root cause and implementing a fix that ensures `useEffect` runs only once, as intended. This is detailed in the `bugSolution.js` file. The issue is often linked to unexpected state updates or other side-effects in the component that trigger re-renders before the first render cycle concludes.