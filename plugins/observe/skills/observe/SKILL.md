---
name: observe
description: Always on for any work in a website or app. Learn every page the agent visits or is shown (each button, link and field and where it leads), keep that as a map, and on every later request go straight to the destination address instead of starting from the home page.
argument-hint: "[teach | <page or task>, optional]"
---

# Observe

An agent should never have to find the same page twice. While it works, Observe quietly learns every screen it sees: what each button, link, menu, tab and field does and where it leads. Later, when asked for something ("change the hours"), the agent looks up where that task happens and lands on that address directly.

Observe runs all the time during web or app work, not only when someone types `/observe`.

## The memory (kept on the user's own computer)
Keep it in an `observe/` folder in the project, one file per website or app (e.g. `observe/example-store.md`). Each file has two parts:

**1. Task index:** what people ask for, and exactly where it happens.
```
- Change store hours → <direct address of the hours screen> → pencil next to "Hours" → set times → Save
- Edit a product description → <products list address> → Search name → ⋯ → Edit → Description → Save
```

**2. Screens:** one entry per screen.
```
### Products list
- Address: <direct link>
- Reached from: Dashboard → Products
- Elements:
  - Search box → filters the list
  - Row click → opens a preview only (gotcha)
  - ⋯ on a row → menu: Edit (→ Product editor), Send to top, Delete (danger)
  - + (top right) → New product form
- Leads to: Product editor, New product form
```
Record the site's shared menus (top bar, sidebar) once, in a "Shared navigation" entry, not on every screen.

## Every time you land on a screen
1. If it has no entry, read it once as text or elements (the page's element list, not a screenshot) and write the entry: its address, how you got there, every interactive element with what it does and where it leads (use the link's real address when there is one), plus gotchas.
2. If it has an entry, use it and check it briefly. If a button moved or an address changed, fix the entry right away.
3. When you finish a task, add or update its line in the task index with the direct address and the shortest click path.

## Every time you get a request
1. Look in the task index first. If the task is there, open its direct address and follow the path. Don't start from a search engine or the home page.
2. If it isn't there, check the screen entries for the likely screen and go there directly.
3. Only when neither helps, explore. Then record what you find so the next time is direct.
4. If one fact lives in several places (for example hours shown on many pages), keep a "Where this appears" list in the task index. Before starting, say how many places there are.

## Teach mode (`/observe teach`)
The user shows the agent how something is done:
- The agent watches each step the user takes, or the user describes it ("now I click Settings, then Hours…").
- After each step, the agent reads the new screen and records it.
- At the end, the agent writes the task-index line ("To do X: go to <address>, then …"), reads it back to the user, and fixes anything the user corrects.

`/observe <page or task>` reads one page, or traces one task, and records it without changing anything.

## Saving tokens
- A screen gets read in full once. After that the agent reads its entry, which is a few lines, instead of re-reading the page.
- Prefer element and text reads over screenshots. Take a screenshot only to confirm a result.
- Batch the steps of a known path into one sequence.

## Safety
- Exploring and recording are read-only. Never click Save, Publish, Send, Pay, Delete or anything that goes live just to see what it does. Record such buttons from their label and mark them "(danger, not tested)".
- Never write passwords, one-time codes, card or bank numbers, or personal data into the memory. Store addresses and labels only.
- Ask the user before anything goes live or any message is sent.
- The memory stays on the user's computer and is never shared with anyone else.
