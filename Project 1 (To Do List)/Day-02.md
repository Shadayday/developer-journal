# Day 2

## What I Built
Upgraded my JavaScript to-do app to persist tasks using localStorage. Tasks now remain after refreshing the page.

## Features Implemented
- Introduced application state using an array (`tasks`)
- Stored tasks in localStorage using JSON.stringify
- Retrieved tasks using JSON.parse
- Rendered UI from state instead of directly manipulating the DOM
- Ensured tasks persist across page reloads

## Challenges
Understanding how JSON conversion works and why localStorage only stores strings.

## What I Learned
- The concept of application state
- How localStorage works in the browser
- Why JSON is required for storing arrays and objects
- The importance of rendering UI from data rather than manually updating elements

## Reflection
Today felt like a shift from writing simple scripts to building a real application. Understanding state and persistence made the app feel significantly more powerful.