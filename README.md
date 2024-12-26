# React Memory Leak: Uncleared setInterval in useEffect Hook

This repository demonstrates a common React memory leak caused by the improper use of `setInterval` within the `useEffect` hook.  The issue arises from a missing cleanup function to clear the interval when the component unmounts, resulting in multiple timers running and eventually causing performance issues or application crashes.

## Bug Description
The provided `MyComponent` uses `setInterval` to update a counter every second.  However, the `useEffect` hook lacks a cleanup function to stop the interval when the component is unmounted.  This leads to a memory leak because the interval continues to run in the background even after the component is no longer rendered.

## Bug Solution
The solution involves adding a cleanup function within the `useEffect` hook's return statement to use `clearInterval`. This ensures the interval is cleared when the component unmounts, preventing the memory leak.