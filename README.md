# React useEffect Hook Infinite Loop

This example demonstrates a common mistake when using the `useEffect` hook in React, leading to an infinite loop. The issue stems from omitting necessary dependencies in the dependency array, which causes the effect to re-run continuously.

## Problem

The `useEffect` hook is used to perform side effects after every render.  However, if a value used inside the effect is not included in the dependency array, React cannot track changes to that value, leading to unexpected behavior.  In this case, the effect runs on every render because `count` is updated within the effect's scope and is not in the dependency array.

## Solution

The solution is to include `count` in the dependency array.  This ensures that the effect only runs when the value of `count` changes.