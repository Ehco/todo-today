# Today — a to-do list for right now

A single-file to-do list that opens instantly, works offline, and looks right on a phone.

**Live:** https://ehco.github.io/todo-today/

## What it does

- **Add** a task — the Add button and the Enter key both work
- **Check off** a task by tapping anywhere on the row (the whole row is a 48px target)
- **Delete** a task with the ✕ on the right
- **Remaining count** in the footer and a progress bar above the list
- **Blank tasks are ignored** — spaces, tabs, newlines and empty submits never create a row
- **Clear done** removes everything you've finished, once you have something finished

## Details worth knowing

- **Everything is local.** Tasks live in `localStorage` under `todo-today.v1`. No account, no server, no network calls.
- **Scoped to today.** The list is stored with its date. Open it tomorrow and it's empty — but any unfinished tasks from the previous day are offered back in a banner ("Bring them over" / "Discard") instead of vanishing.
- **Phone-first.** 390px viewport tested, no horizontal scroll, 16px input font (stops iOS zoom-on-focus), `viewport-fit=cover` plus safe-area padding for notched screens, and 44px+ touch targets.
- **Dark and light** follow `prefers-color-scheme`. Reduced-motion is respected.
- **Safe by default.** Task text is rendered with `textContent`, so HTML in a task is shown as text, never executed.
- **Accessible.** Checkboxes are real buttons with `role="checkbox"` and `aria-checked`; the remaining count is an `aria-live` region; every control has an accessible name.

## Run it

```sh
python3 -m http.server 8099   # then open http://127.0.0.1:8099
```

Or just double-click `index.html` — it needs no build step and no dependencies.

## Deploy

The site is served straight from the `main` branch by GitHub Pages. Push to `main` and it updates.
