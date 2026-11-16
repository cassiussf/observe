# Observe

By Cassius Tekin

A Claude Code plugin that adds `/observe`.

While Claude works on any website or app, Observe quietly learns every screen it sees: what each button, link, menu and field does and where it leads. It keeps that as a map on your own computer, with a task index ("change the hours" → the exact address and clicks). The next time you ask for something, Claude goes straight to the right page instead of starting from the home page. That's faster and uses fewer tokens.

## Install
```
/plugin marketplace add cassiussf/observe
/plugin install observe@observe
```

## Use
- It's always on during web and app work. You don't have to type anything.
- `/observe teach`: show Claude how you do something, step by step, and it remembers the path.
- `/observe <page or task>`: Claude reads that page or traces that task once, changes nothing, and adds it to the map.

## Privacy
The plugin contains instructions only: no links, logins or data. Each person's map is created and kept on their own computer. Claude is told never to store passwords, codes, card numbers or personal data in it, and never to click Save, Send, Pay or Delete just to see what a button does. Installing it gives no one access to anyone else's accounts.
