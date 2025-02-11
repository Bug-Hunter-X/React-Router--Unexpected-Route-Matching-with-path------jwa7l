# React Router Unexpected Route Matching
This repository demonstrates a common issue in React Router v6 where a route with path="/*" unintentionally overrides other routes defined earlier.  This can lead to unexpected routing behavior where other routes may never be accessed.

## Problem
The issue arises from the order of routes and how the `path="/*" ` catch-all route works.  Because `path="/*"` is a catch-all, it matches all paths, even those defined earlier.  This means it will always be matched before other routes and effectively render the component it is associated with, regardless of the user's request.

## Solution
The solution is to place the catch-all route (`path="/*"`) as the last route in your `Routes` component.  This ensures that other routes are evaluated first and only the catch-all route is used if no other match is found.