# React Unhandled Error in Async useEffect

This repository demonstrates a common error in React applications involving unhandled errors within asynchronous functions in the `useEffect` hook. The code includes an example of how this can lead to unexpected behavior, specifically an infinite loading state if the fetch call fails.  The solution highlights proper error handling and cleanup.

## The Problem

The original `MyComponent` incorrectly handles errors during the asynchronous fetch operation. If the fetch fails, the `error` state is updated, but there's no mechanism to indicate that the loading operation is complete. This results in the application remaining stuck in a loading state indefinitely.

## The Solution

The provided solution improves the error handling by using a `finally` block within the `useEffect`'s asynchronous function. This `finally` block guarantees that `setLoading(false)` is always called, regardless of whether the fetch operation is successful or encounters an error. This prevents the infinite loading state, providing a more user-friendly and robust experience.
