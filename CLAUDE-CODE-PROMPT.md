# Claude Code — Master Prompt

Copy everything inside the box below and paste it as your **first message** to Claude Code,
after you've opened a terminal **inside the `sbom4ai-builder` folder** and run `claude`.

It instructs Claude Code to (1) publish the project to your GitHub, (2) verify it works
and the live site is up, and (3) write a user manual.

> One-time setup note: publishing needs the GitHub CLI authenticated. If Claude Code
> reports an auth error, run `gh auth login` once in the terminal, then tell Claude Code
> to continue.

---

```
You are working inside the project folder for "SBOM4AI Builder" — a free, open-source,
fully client-side tool (a single index.html file, no build step) that helps people build
G7-compliant Software Bills of Materials for AI systems. The author is Brahim EL ALLAM
(LinkedIn: https://www.linkedin.com/in/brahim-el-allam-0a7731222/). It is MIT licensed.

Please complete the following three tasks in order. Pause and show me the result of each
task before moving to the next.

=== TASK 1 — PUBLISH TO GITHUB ===

1. Confirm the folder contains: index.html, README.md, PUBLISH.md, LICENSE, .gitignore.
   List anything missing before continuing.
2. Initialise a git repository here if one does not already exist. Set the default
   branch to "main".
3. Check that the GitHub CLI (gh) is installed and authenticated. If it is not
   authenticated, stop and tell me to run `gh auth login`, then wait for me.
4. Create a PUBLIC GitHub repository named "sbom4ai-builder" with this description:
   "Free, open-source, fully local builder for G7-compliant Software Bills of Materials
   for AI systems. Implements the seven clusters of minimum elements."
5. Stage all files, commit with the message "Initial release of SBOM4AI Builder", and
   push to main.
6. Set the repository topics to: sbom, ai-governance, cybersecurity, eu-ai-act, mdr,
   supply-chain-security, open-source, ai-act, samd.
7. Enable GitHub Pages for this repository, served from the root (/) of the main branch.
8. Set the repository "website" field to the GitHub Pages URL once it exists.
9. Report back: the repository URL and the live GitHub Pages URL.

=== TASK 2 — VERIFY ===

Run these checks and give me a short PASS/FAIL report for each:

A. CODE INTEGRITY
   - Confirm index.html is a single self-contained file.
   - Confirm there is NO reference to "cdn.tailwindcss.com" anywhere (it must not use the
     Tailwind runtime CDN — styles are inlined).
   - Confirm there are NO calls to any AI/LLM API (search for "api.anthropic.com",
     "openai", "api_key") — there must be none. This tool makes zero external API calls.
   - Confirm it uses localStorage for persistence (search for "localStorage") and does
     NOT use "window.storage".
   - Extract the JSX from the <script type="text/babel"> block and compile it with Babel
     (@babel/preset-react) to confirm there are ZERO syntax errors. If you find errors,
     fix them, re-commit, and re-push.

B. CONTENT INTEGRITY
   - Confirm all 7 cluster ids are present in the schema: metadata, slp, models, datasets,
     infrastructure, security, kpi.
   - Confirm the author name "Brahim EL ALLAM" and the LinkedIn URL appear in the file.

C. LIVE SITE
   - Wait for GitHub Pages to finish building (it can take 1–2 minutes), then fetch the
     live URL and confirm it returns HTTP 200 and the HTML contains the page <title>
     "SBOM4AI Builder".
   - Confirm the external resources it loads (Google Fonts, React, Babel from unpkg) are
     reachable.

D. LINKS
   - Verify the LinkedIn URL (https://www.linkedin.com/in/brahim-el-allam-0a7731222/)
     is well-formed and used consistently.

If any check FAILS, fix the underlying issue in index.html, commit with a clear message,
push, and re-run the failing check until it passes.

=== TASK 3 — CREATE A USER MANUAL ===

Create a new file in the repo called USER-GUIDE.md — a clear, friendly user manual for
NON-technical users (regulatory affairs, QA/RA, compliance, and engineering staff). Use
plain language and a calm, professional tone. It must cover:

1. What this tool is and who it's for (one short paragraph).
2. What a Software Bill of Materials for AI is, in two or three sentences, and why the
   seven G7 clusters matter — keep it accessible.
3. How to open the tool — three ways:
   (a) Use the hosted link (the GitHub Pages URL — insert the real URL).
   (b) Download index.html and double-click it to run locally with no internet.
   (c) Self-host it on any static web server or company intranet.
   Emphasise that all data stays in the user's own browser and nothing is uploaded
   anywhere.
4. A step-by-step walkthrough:
   - Creating a new SBOM, or clicking "Load demo" to explore a worked medical-AI example.
   - Navigating the seven sections (§1 Metadata through §7 KPIs) using the table of
     contents / the Previous–Next buttons.
   - How fields work: free text, dropdowns, date-time, multi-select chips, and the
     "add multiple entries" sections (Models and Datasets). Mention that each field shows
     its official G7 description inline.
   - That work auto-saves locally as they type.
   - Using the Validation view to see coverage per cluster and jump to gaps.
   - Exporting: Copy JSON or Download .json, and what that file is useful for
     (attaching to technical documentation, feeding CI/CD, sharing with auditors).
5. A short FAQ:
   - "Is it free?" Yes — MIT licensed, free for any use including commercial.
   - "Where is my data stored?" Only in your browser's local storage on your device.
   - "Does it send anything to a server or use AI?" No. It is 100% local, no API calls.
   - "Can I use this for EU MDR / EU AI Act / ISO 42001 work?" It helps you structure an
     SBOM aligned to the G7 minimum elements, but it is not legal advice and not a
     substitute for the binding requirements of those frameworks.
   - "Will my data be lost?" It persists in this browser; clearing browser data or using a
     different browser/device starts fresh. Export to JSON to keep a portable copy.
6. A closing "Feedback & contact" section linking to Brahim EL ALLAM's LinkedIn, inviting
   suggestions, and noting the tool is open source and contributions are welcome.

Keep it well-structured with headings and short paragraphs. When finished, add a link to
USER-GUIDE.md near the top of README.md (e.g., under the badges: "📖 New here? Read the
User Guide"). Then commit both files with the message "Add user guide" and push.

=== FINISH ===

When all three tasks are done, give me a final summary containing:
- The repository URL
- The live GitHub Pages URL
- The PASS/FAIL verification summary
- A one-line confirmation that USER-GUIDE.md was created and linked
```

---

## Optional follow-up prompts

After the master prompt finishes, you can use these one-liners with Claude Code:

**To update the live site after editing `index.html` yourself:**
```
Commit my changes to index.html with a clear message and push to main.
```

**To add a custom domain later:**
```
Help me point a custom domain to this GitHub Pages site. Walk me through the DNS
records I need to add and create the CNAME file in the repo.
```

**To generate a release:**
```
Create a GitHub release tagged v1.0.0 titled "SBOM4AI Builder 1.0.0" with concise
release notes summarising the features, and attach index.html as a downloadable asset.
```
