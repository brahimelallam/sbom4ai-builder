# START HERE

This folder is **SBOM4AI Builder** — a free, open-source, fully local tool for building
G7-compliant Software Bills of Materials for AI systems. Developed by Brahim EL ALLAM.

You've chosen **Route B: publish with Claude Code.** Follow the five steps below in order.

---

## What's in this folder

| File | What it is |
|------|------------|
| `index.html` | **The tool itself.** A single self-contained file. This is what the world loads. |
| `README.md` | Project description, license, deployment notes (shown on the GitHub repo page). |
| `PUBLISH.md` | Publishing playbook + the LinkedIn announcement posts (Part 2). |
| `CLAUDE-CODE-PROMPT.md` | The master prompt you paste into Claude Code. |
| `LICENSE` | MIT license — free for any use. |
| `.gitignore` | Housekeeping for the git repository. |
| `START-HERE.md` | This file. |

---

## Step 1 — Test it locally first (2 minutes)

Double-click `index.html`. It opens in your browser.

- Click **"Load demo"** to see all seven sections filled with a worked example.
- Click through the sections; try **Export** to confirm the JSON downloads.

If that works, the tool is good. Nothing left your computer — this is the "local /
self-hosted on your laptop" proof.

---

## Step 2 — Install Claude Code (one time)

If you don't already have it, install Claude Code (Anthropic's terminal tool). You'll also
need Git and the GitHub CLI (`gh`) — Claude Code can check for these and tell you what's
missing.

You need a free **GitHub account**. If you don't have one yet, create it first at
github.com.

---

## Step 3 — Open Claude Code inside this folder

1. Open a terminal (Terminal on macOS, PowerShell or Windows Terminal on Windows).
2. Navigate **into this folder**. For example:
   - macOS/Linux: `cd ~/Downloads/sbom4ai-builder`
   - Windows: `cd %USERPROFILE%\Downloads\sbom4ai-builder`
3. Type `claude` and press Enter.

> If publishing later fails with an authentication error, run `gh auth login` once in the
> terminal, follow the browser prompts, then tell Claude Code to continue.

---

## Step 4 — Paste the master prompt

Open `CLAUDE-CODE-PROMPT.md`, copy the entire block inside the code fence, and paste it as
your first message to Claude Code.

It will, pausing for your review between each task:
1. **Publish** — create the public GitHub repo, commit, push, and enable GitHub Pages.
2. **Verify** — check the code is clean, compiles, makes no external API calls, and that
   the live site returns HTTP 200.
3. **Document** — write `USER-GUIDE.md` (a manual for non-technical users) and link it
   from the README.

When it finishes, it gives you:
- your repository URL
- your **live site URL** (looks like `https://<your-username>.github.io/sbom4ai-builder/`)
- a PASS/FAIL verification summary

Open the live URL in a fresh browser tab and confirm it loads and "Load demo" works.

---

## Step 5 — Announce on LinkedIn

Open `PUBLISH.md` → **Part 2**. Copy **Draft 1** (the professional version).

- Post the text **without** links in the body.
- Put your live URL and repo URL in the **first comment** instead.
- Reply to comments in the first hour, briefly and in your own words.

The "What to avoid" list at the end of Part 2 keeps your writing from looking generated.

---

## Reminders about what this tool is

- **Free** — costs nothing, MIT licensed, free for any use including commercial.
- **Open source** — all code is in one readable `index.html`.
- **Local & self-hosted** — runs in the browser; data is saved only in the user's own
  browser storage. No server, no cloud, no account, no API, no tracking.

---

When your live URL is ready, that's the moment to share it. Good luck with the launch.
