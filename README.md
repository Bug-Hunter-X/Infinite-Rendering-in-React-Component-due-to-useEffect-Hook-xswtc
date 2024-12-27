# Infinite Rendering Bug in React

This repository demonstrates a common React bug: infinite rendering caused by an improperly used `useEffect` hook. The `useEffect` hook, without a dependency array, re-renders the component continuously, leading to an infinite loop and crashing the application.

## Bug Description
The `MyComponent` component uses `useState` to manage a count and `useEffect` to log a message.  Because the `useEffect` hook lacks a dependency array (`[]`), it runs after every render, causing the component to re-render infinitely. 

## Solution
The solution involves adding a dependency array to the `useEffect` hook. This array specifies the values the hook should monitor.  When any of these values change, the effect runs.  If the array is empty (`[]`), the effect runs only once after the initial render.