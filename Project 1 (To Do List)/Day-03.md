# Day 3

## What I Built
Upgraded my to-do app into a full CRUD app with task completion, editing, deletion, and duplicate prevention.

## Features Implemented
- Delete tasks and persist changes
- Mark tasks complete/incomplete (checkbox) with visual feedback
- Edit tasks with Save/Cancel (Enter to save, Escape to cancel)
- Prevent duplicate tasks (case-insensitive)
- Refactored to a single renderTasks() and helper functions
- Persist full task state (text + completed) in localStorage

## Challenges
Fixing syntax errors caused by missing braces and keeping state consistent while editing/deleting.

## What I Learned
- Managing UI state (editingIndex) alongside application state (tasks)
- Converting data models from strings to objects
- Why clean structure (one render function + helpers) reduces bugs
- How to debug browser errors quickly using the console and network panel