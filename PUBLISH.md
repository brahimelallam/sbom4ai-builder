# 🚀 Publishing Playbook

Everything you need to put **SBOM4AI Builder** live on the internet — for free — and announce it on LinkedIn.

This is a personal checklist. Follow it once and you're done.

---

## Part 1 · Publish the tool (choose ONE path)

You have two solid free options. **My recommendation: do Path B (GitHub Pages).** It gives you a permanent URL, a public repo as a credibility asset, and lets people star/fork your work — all of which help on LinkedIn.

If you just want it live in 2 minutes for testing, do Path A first, then move to Path B once you're ready to share.

---

### 🅰️ PATH A — Netlify Drop (fastest, ~2 minutes, no Git)

Use this to get a working URL immediately.

1. Open https://app.netlify.com/drop in your browser.
2. In a separate window, locate the `sbom4ai-builder` folder on your computer.
3. **Drag the entire folder** onto the Netlify Drop page (the area that says "Drag and drop your site folder here").
4. Wait ~10 seconds. Netlify gives you a URL like `https://<random-name>.netlify.app`.
5. **Click the URL — your tool is live.**

**Optional polish (free, ~3 minutes):**
- Create a free Netlify account (sign in with GitHub or email)
- Claim the site you just deployed
- Site settings → Change site name → e.g., `sbom4ai-builder` → URL becomes `https://sbom4ai-builder.netlify.app`
- Domain management → add a custom domain if you own one

**When to use this path:** You want it live RIGHT NOW for a quick LinkedIn announcement and don't need a GitHub repo yet.

---

### 🅱️ PATH B — GitHub Pages (recommended for sharing)

This gives you:
- A permanent URL like `https://<your-username>.github.io/sbom4ai-builder/`
- A public repository people can star ⭐ and fork 🍴 (visible engagement)
- A code-credit asset for your CV, LinkedIn, job applications (Siemens, GE, etc.)
- Easy updates: edit → commit → live in 60 seconds

**Step-by-step:**

#### 1. Create a GitHub account (skip if you already have one)
- Go to https://github.com/join
- Pick a username — ideally `brahim-el-allam` or close to your LinkedIn handle for consistency
- Verify email

#### 2. Create the repository
- Top right → click the **+** → **New repository**
- Repository name: `sbom4ai-builder`
- Description (optional): `Free, open-source tool to build G7-compliant Software Bills of Materials for AI systems`
- **Public** ✅
- Do NOT check "Add a README" / "Add .gitignore" / "Choose a license" (we already have those files)
- Click **Create repository**

#### 3. Upload your files
On the empty repository page, you'll see a link **"uploading an existing file"** (or click **"Add file"** → **"Upload files"**).

- Open the `sbom4ai-builder` folder on your computer
- Select **all 4 files**: `index.html`, `README.md`, `LICENSE`, `.gitignore`
- Drag them onto the GitHub upload area
- Scroll down — under "Commit changes":
  - Commit message: `Initial release of SBOM4AI Builder`
- Click **Commit changes**

#### 4. Enable GitHub Pages
- In your repo, click **Settings** (top-right tab)
- Left sidebar → **Pages**
- Under "Build and deployment":
  - Source: **Deploy from a branch**
  - Branch: **main**, folder: **/ (root)**
  - Click **Save**
- Wait ~1–2 minutes.
- Refresh the Pages settings page — a green banner appears:
  > "Your site is live at `https://<your-username>.github.io/sbom4ai-builder/`"

**That's your shareable URL.** ✅

#### 5. (Optional but worth 30 seconds) Polish the repo page
Back on the main repo page, click the ⚙️ next to "About" (top right of the file list):
- Description: `Free, open-source tool to build G7-compliant Software Bills of Materials for AI systems. Runs entirely in your browser.`
- Website: paste your GitHub Pages URL
- Topics: `sbom`, `ai-governance`, `cybersecurity`, `eu-ai-act`, `mdr`, `supply-chain-security`, `open-source`
- Save changes

This makes your repo show up in GitHub topic searches.

#### 6. Future updates
Edit any file directly in the GitHub web editor (pencil icon → edit → commit) and the live site updates within 60 seconds.

---

### 🅲️ PATH C — Ship to GitHub with Claude Code (developer route)

If you have Claude Code installed, this is the cleanest way to version-control and publish in one flow. Open a terminal **inside the `sbom4ai-builder` folder** and run `claude`, then give it instructions like:

**Step 1 — initialise and create the repo**
```
Initialise a git repository here. Create a public GitHub repository called
"sbom4ai-builder" with the description "Free, open-source, fully local builder
for G7-compliant Software Bills of Materials for AI systems." Commit all files
with the message "Initial release of SBOM4AI Builder" and push to main.
```
(Claude Code uses the GitHub CLI `gh` under the hood — if you're not authenticated it will prompt you to run `gh auth login` once.)

**Step 2 — enable GitHub Pages**
```
Enable GitHub Pages for this repository, serving from the root of the main
branch, and tell me the live URL.
```

**Step 3 — set repository metadata (optional polish)**
```
Set the repository topics to: sbom, ai-governance, cybersecurity, eu-ai-act,
mdr, supply-chain-security, open-source. Set the repository website to the
GitHub Pages URL.
```

**Future updates** — whenever you change `index.html`:
```
Commit my changes with a clear message and push to main.
```

> 💡 Claude Code is for developers comfortable with a terminal. If that's not you today, **Path B (the GitHub web upload) does exactly the same thing with no command line.** Both end with an identical live site.

---

## Part 2 · Announce on LinkedIn

Two post drafts below. **Pick one, customize the URLs, then post.**

> 📌 **Before posting:** replace `[YOUR-LIVE-URL]` and `[YOUR-GITHUB-REPO-URL]` with your actual URLs.

---

A note on voice: these are written to sound like *you* — a regulatory professional — not
like a product launch. No emoji headers, no rows of checkmarks, no hashtag walls. Keep it
that way; it's what makes it read as credible rather than generated. Put the links in the
**first comment**, not the post body (LinkedIn favours posts that keep people on-platform).

### Draft 1 — The friction story (recommended)

> The G7 cybersecurity agencies published their minimum elements for a Software Bill of
> Materials for AI in February: seven clusters, just over fifty fields, covering everything
> from model provenance to dataset sensitivity and deployment infrastructure.
>
> It's useful guidance. But there's a real gap between reading a specification and actually
> producing a conformant SBOM for a system you ship.
>
> So I built a small tool to close it. You work through the seven clusters one at a time,
> each field annotated with the relevant text from the G7 document, and export a structured
> JSON file at the end. It runs entirely in the browser — nothing is uploaded, no account,
> no cost.
>
> It's free and open source under the MIT licence. Use it, fork it, or host it on your own
> infrastructure.
>
> I'd value feedback from anyone working on AI supply-chain transparency, EU AI Act
> technical documentation, or ISO/IEC 42001 — particularly on which fields are missing for
> your context.
>
> Link in the comments.
>
> #AIGovernance #Cybersecurity #EUAIAct

*First comment:*
> Tool: [YOUR-LIVE-URL] · Source: [YOUR-GITHUB-REPO-URL] · Built on the G7 Cybersecurity Working Group document "Software Bill of Materials for AI: Minimum Elements" (February 2026).

---

### Draft 2 — Brief

> In February the G7 cybersecurity agencies set out the minimum elements for a Software Bill
> of Materials for AI: seven clusters, around fifty fields.
>
> Reading the specification is one thing; producing a conformant SBOM is another. I built a
> tool for the second part — a guided builder that walks through each cluster with the
> official descriptions inline and exports clean JSON. Browser-only, nothing uploaded, free
> and open source.
>
> If you work in AI supply-chain security, EU AI Act documentation, or ISO/IEC 42001, I'd
> genuinely like your view on what's missing.
>
> Link below.
>
> #AIGovernance #SBOM #Cybersecurity

*First comment:*
> Tool: [YOUR-LIVE-URL] · Source: [YOUR-GITHUB-REPO-URL]

---

### Draft 3 — One paragraph (for a follow-up, weeks later)

> A quick follow-up on the SBOM-for-AI builder I shared earlier: I've had useful feedback on
> the dataset-provenance and security-control fields and folded some of it in. Still free,
> still open source, still runs entirely in your browser. If you've a few minutes and work
> anywhere near AI governance, I'd welcome your read on it.
>
> Link in the comments.

---

### What to avoid (the tells that make writing look generated)

Cut these on sight — they're the difference between "a professional wrote this" and "this came out of a tool":

- Emoji as section markers (🟢, 🔗, 📦, 👇) and emoji in headers
- Rows of ✅ checkmark bullets listing features
- Openers like "Just shipped", "Excited to announce", "Thrilled to share"
- Filler superlatives: "game-changer", "no strings attached", "powerful", "seamless"
- "Whether you're X or Y…" and other over-balanced constructions
- A wall of 8–12 hashtags (use three or four, lowercase the niche ones if you like)
- Perfectly symmetrical paragraphs of identical length

Human professional writing has uneven sentence lengths, one concrete reason the thing
exists, and a specific ask. Keep it plain.

## Part 3 · Maximize the LinkedIn post

A few tactical tips that work on LinkedIn in 2026:

1. **Post on a Tuesday, Wednesday, or Thursday, 8–10 AM CET.** Highest engagement for B2B audiences in Europe.
2. **First line matters most.** LinkedIn shows ~3 lines before "see more". Open with the hook, not a greeting.
3. **No external links in the FIRST version of the post.** LinkedIn deprioritizes posts that send users off-platform. Trick: post the URLs in the **first comment** instead, and write "🔗 Link in the first comment ↓" at the bottom of the post.
4. **Tag 2–3 relevant people** if you have working relationships — e.g., colleagues in regulatory affairs, your PhD supervisor, contacts at ACN/BSI/ANSSI if you know any. Don't spam-tag.
5. **Engage with comments within the first hour.** LinkedIn's algorithm heavily weights early engagement.
6. **Re-share after 1 week** with a new framing (e.g., "1 week in: 47 people tried it, here's what they asked for…"). LinkedIn rewards consistent storytelling around the same project.

---

## Part 4 · After it's live

A few small things that compound over time:

- **Add the live URL** to your LinkedIn featured section (top of your profile)
- **Add it to your LinkedIn experience** as a "Project"
- **Reference the GitHub repo** in your CV under "Open Source Contributions"
- **Mention it in interviews** (Siemens, GE, etc.) — concrete proof that you operationalize regulatory guidance, not just analyze it
- **Track engagement**: GitHub stars + Pages traffic (Insights tab in your repo) are quiet credibility signals

---

## Quick reference — Your URLs

After publishing, fill these in for your records:

```
Live URL:       https://________________________
GitHub repo:    https://github.com/_____________
LinkedIn post:  https://www.linkedin.com/posts/_____________
```

---

Good luck with the launch. 🟢
