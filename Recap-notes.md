1) Your workflow and tools
VS Code

Where you edit files (index.html, style.css, script.js)

Terminal inside VS Code is for Git commands, not for “running” browser JavaScript.

Browser (Chrome/Edge)

Your HTML/CSS/JS runs in the browser

Use DevTools to debug:

Console: errors + console.log()

Network: check files actually load (CSS/JS)

2) Git + GitHub basics
What Git is

Version control: saves snapshots of your project over time.

Local vs Remote

Local repo: on your PC

Remote repo: on GitHub

Core commands (the daily loop)
git status       # see what changed
git diff         # see exactly what changed
git add .        # stage changes
git commit -m "message"   # save snapshot
git push         # send to GitHub
Clone a repo

“Clone” = copy repo from GitHub to your computer.

git clone https://github.com/yourusername/repo.git
3) How your app runs (important)
For this project:

You do not run JavaScript in the terminal.

You run it by opening index.html (or Live Server).

Live Server

Serves your files at something like http://127.0.0.1:5500/

Useful because it auto-refreshes.

4) DOM + DOM manipulation
DOM (Document Object Model)

The browser converts your HTML into a “live” object tree the JS can interact with.

DOM manipulation means

Using JavaScript to:

Select elements

Read values

Change text/styles

Create/remove elements

Respond to user actions

Selecting elements
document.getElementById("taskInput");
Creating and adding elements
const li = document.createElement("li");
li.textContent = "Task";
list.appendChild(li);
5) Events (how the page reacts)
Button click
button.addEventListener("click", () => {
  // do something
});
Enter key support
input.addEventListener("keydown", (event) => {
  if (event.key === "Enter") button.click();
});

Key detail: "Enter" is case-sensitive.

6) Debugging essentials
console.log()

Used to inspect what your code is doing.

console.log(taskText);
console.log(tasks);
Reading errors

Errors tell you:

the file: script.js

the line number

the cause

Common beginner errors you hit

Case sensitivity: value ✅ vs Value ❌

null usually means JS couldn’t find an element:

wrong id

script running before HTML loads

you opened the wrong file/folder

7) State (how apps work)
State = your data

Instead of “the UI is the truth”, you store the truth in JS:

let tasks = [];

Then the UI is rebuilt from that state.

Why it matters

Easier to change features

Less bugs

Closer to how React apps work

8) renderTasks() pattern
The idea

UI should reflect state:

Change the array (tasks)

Save if needed

Call renderTasks() to update the page

What renderTasks() does

Clears the list (list.innerHTML = "")

Loops through tasks

Rebuilds all list items from scratch

This is a clean “data → UI” approach.

9) localStorage + JSON
localStorage

Browser storage that persists after refresh.

It stores strings only.

JSON

A text format for structured data.

JSON.stringify

Converts JS data → JSON string

JSON.stringify(tasks)
JSON.parse

Converts JSON string → JS data

JSON.parse(savedTasks)
The full loop
localStorage.setItem("tasks", JSON.stringify(tasks));
tasks = JSON.parse(localStorage.getItem("tasks"));
10) Features you built into the To-Do app
Add a task

Read input

Block empty values

Push into tasks

Save

Render

Clear input

Prevent empty tasks

Use .trim() then check ""

Prevent duplicates

Compare case-insensitively:

tasks.some(t => t.text.toLowerCase() === taskText.toLowerCase())
Delete a task

Use .splice(index, 1)

Save + render

Mark complete

Tasks became objects:

{ text: "lunch", completed: false }

Checkbox toggles completed

Edit tasks

You introduced UI state:

editingIndex

editingText

You added Save/Cancel, Enter/Escape support

You prevented editing into duplicates

Upgrade old saved data

You handled old string-only saved tasks by converting them to objects on load.

11) “Why we’re doing this” (the bigger picture)

Everything you’ve done is teaching real software patterns:

Single source of truth (the tasks array)

Derived views (filters later)

Separation of concerns

state (data)

UI state (editing/filter)

rendering

This is basically the foundation for moving into React / full-stack / real apps.

12) Quick glossary (cheat sheet)

DOM: browser’s live model of HTML

Event listener: reacts to clicks/keys/etc

State: data your app uses (tasks)

UI state: current view/editing mode

localStorage: persistent browser key/value storage

JSON: structured data as text

stringify: JS → JSON string

parse: JSON string → JS

CRUD: Create, Read, Update, Delete (your app does this)

13) Common “fix it fast” checklist

If something doesn’t work:

Open Console (DevTools) and read the error.

Add console.log("loaded") at top of script.

Confirm element selectors aren’t null:

console.log({ input, button, list });

Hard refresh: Ctrl + F5

Confirm you opened the right project folder/file.