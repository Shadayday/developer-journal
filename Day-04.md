# Day 4

## What I Built
Added bulk actions and task reordering to my to-do app.

## Features Implemented
- Clear All button with confirmation
- Move Up / Move Down controls to reorder tasks
- Persisted ordering via localStorage (order is stored in the tasks array)

## What I Learned
- UI bugs often come from missing DOM elements (null getElementById)
- Keeping state updates centralized (swap helper) makes features safer
- Re-rendering from state keeps the UI consistent after every change