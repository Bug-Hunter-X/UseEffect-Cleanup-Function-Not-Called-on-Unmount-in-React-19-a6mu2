# React 19 useEffect Cleanup Function Not Called on Unmount

This repository demonstrates a subtle bug related to the `useEffect` hook's cleanup function in React 19.  The cleanup function, intended to run when the component unmounts, is not always being called as expected.

## Bug Description

The provided `MyComponent` uses `useEffect` with an empty dependency array (`[]`).  The expectation is that the cleanup function (`console.log('Unmounted!')`) should execute when the component is unmounted. However, under certain conditions (such as rapid component switching or errors during rendering), this cleanup function may not be executed, leading to potential memory leaks or unexpected behavior.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console logs.  You may need to rapidly switch between components or cause an error to reliably reproduce the bug.

## Solution

The solution is to ensure that the component is always properly unmounted. This may involve addressing root issues in the component's lifecycle management or surrounding context.  This example shows alternative approaches to manage cleanup within the component's lifecycle.