# SBOM4AI Builder — User Guide

A friendly walkthrough for everyone who needs to produce a Software Bill of Materials for an AI system — no coding required.

---

## 1. What this tool is, and who it is for

**SBOM4AI Builder** is a free, open-source web app that guides you through building a Software Bill of Materials (SBOM) for an AI system, aligned with the G7 minimum elements. It is designed for **regulatory affairs, quality assurance, compliance, clinical, and engineering staff** who need a clear, structured way to document an AI product — for an internal review, a technical file, an audit, or a supplier hand-off.

You do not need to install anything, create an account, or share any data. The whole tool is a single web page that runs in your browser.

---

## 2. What an "SBOM for AI" is, in plain language

A **Software Bill of Materials (SBOM)** is the list of ingredients of a piece of software — what is inside, where it came from, and who is responsible for it. An **SBOM for AI** extends that idea to AI systems by adding the things that matter for AI: which models are used, what data they were trained or fine-tuned on, what infrastructure they run on, and what security controls protect them.

The **G7 cybersecurity agencies** grouped those ingredients into **seven clusters**. Together they cover the document itself, the AI system as a whole, every model, every dataset, the infrastructure, the security controls, and the operational KPIs. Filling in all seven gives a reader the full picture of an AI product in one place — which is what auditors, customers, regulators, and your own security team are looking for.

---

## 3. How to open the tool

There are three ways to use it. All three behave identically and **keep every value you type inside your own browser** — nothing is uploaded anywhere.

### Option A — Use the hosted link (easiest)

Open this address in any modern browser (Chrome, Edge, Firefox, Safari):

**https://brahimelallam.github.io/sbom4ai-builder/**

That page is the entire tool. Once it loads, you can disconnect from the internet and keep working — your browser has already cached what it needs.

### Option B — Run it locally with no internet

1. Download the file [`index.html`](https://github.com/brahimelallam/sbom4ai-builder/blob/main/index.html) from the project page.
2. Save it anywhere you like (Desktop, Documents, a USB stick — it does not matter).
3. **Double-click the file.** It opens in your default browser and works the same way as the hosted version.

After the first launch, the small external assets it uses (fonts, the React library) are cached by your browser, and you can work offline.

### Option C — Self-host on your own server or intranet

If your organisation prefers to host the tool internally:

1. Copy `index.html` to any static web server (Apache, nginx, IIS, an S3 bucket, SharePoint, Confluence attachment, GitHub Pages, an internal company portal — anything that can serve a single HTML file).
2. Share the URL with your team. There is no build step, no database, and no configuration to manage.

### A word on privacy (applies to all three options)

Every value you type stays in **your** browser's local storage on **your** device. There is no server collecting your inputs, no analytics, no telemetry, no account, no AI API call, and no third-party tracking. If you close the tab and re-open it later in the same browser, your work is still there.

---

## 4. Step-by-step walkthrough

### 4.1 Start a new SBOM, or explore the demo

When you open the tool you land on the welcome screen. Two buttons:

- **Load demo** — opens a fully filled example for a fictional Class IIa medical-AI imaging triage system. This is the fastest way to see what a complete SBOM looks like. You can edit it freely; you will not break anything.
- **New SBOM** — starts a blank document. Give it a name (for example *MyProduct v1.2 — initial release*) and you are ready to fill it in.

You can keep **several SBOMs side by side** in your browser — for different products, different versions, or different draft attempts.

### 4.2 Navigate the seven sections

The left side of the screen shows a **table of contents** with the seven clusters:

1. **§ 1 Metadata** — the SBOM document itself (author, version, format, signature, timestamps).
2. **§ 2 System Level Properties** — the AI system as a whole (components, data flow, inputs, outputs, intended use).
3. **§ 3 Models** — every AI model the system uses.
4. **§ 4 Datasets Properties** — every dataset the system uses.
5. **§ 5 Infrastructure** — the software and hardware the system runs on.
6. **§ 6 Security Properties** — the controls, policies, and known vulnerabilities.
7. **§ 7 Key Performance Indicators** — operational and security metrics.

You can jump to any section by clicking it in the table of contents, or move sequentially using the **Previous section** and **Next section** buttons at the bottom of each page. On a small screen, the table of contents collapses into a dropdown.

### 4.3 How the fields work

Each section contains a series of fields. Every field shows its **official G7 description inline**, so you understand exactly what is being asked — no need to consult the source document while you work.

You will encounter five kinds of input:

- **Free text** — short answers (names, identifiers, versions) and longer ones (descriptions, intended use, controls).
- **Dropdowns** — for pre-defined choices (for example, SBOM format).
- **Date and time pickers** — for timestamps.
- **Multi-select chips** — click a chip to add or remove an option; you can pick as many as apply.
- **"Add multiple entries" sections** — used in **§ 3 Models** and **§ 4 Datasets**. Each model or dataset gets its own card with its own set of fields. Use the **Add** button to create another card, and the small delete control to remove one.

### 4.4 Your work saves itself

You do not need to press a save button. Every keystroke is **stored locally in your browser as you type**. If you accidentally close the tab, just re-open the page and your work is back exactly as you left it.

### 4.5 Check coverage with the Validation view

When you want to see how complete your SBOM is, open the **Validation** view from the table of contents (or click **Next section** past the last cluster). It shows **coverage by cluster** — what percentage of the G7 minimum elements you have filled in for each of the seven sections, and which fields are still empty.

Click any listed gap to **jump straight to that field**. There is no notion of a passing grade — the G7 minimum elements are recommendations, not a regulation — but the coverage view is a quick way to spot what is still missing before you share or archive your file.

### 4.6 Export your SBOM

When you are ready to share or archive, use the buttons at the top of the page:

- **Copy JSON** — copies the entire SBOM to your clipboard as structured JSON.
- **Download .json** — saves it as a `.json` file on your computer.

That JSON file is what you would typically:

- Attach to a **technical documentation** package (for example, an EU MDR technical file or an EU AI Act high-risk technical documentation file).
- Feed into a **CI/CD pipeline** or internal compliance tooling.
- Send to an **auditor**, a customer's security team, or a notified body as part of a hand-off.
- Keep as a **portable backup** of your work, independent of any browser.

---

## 5. Frequently asked questions

**Is it free?**
Yes. The tool is released under the MIT licence — free for any use, including commercial use, with no restrictions beyond keeping the licence notice.

**Where is my data stored?**
Only in your browser's local storage on your own device. Nothing is uploaded, nothing leaves your machine.

**Does it send anything to a server, or use any AI behind the scenes?**
No. The tool makes zero API calls of any kind, and it does not contact any AI service. The only network requests it makes are to load the page itself (and, once, the fonts and React library it depends on).

**Can I use this for EU MDR, EU AI Act, or ISO/IEC 42001 work?**
The tool helps you **structure** an SBOM aligned with the G7 minimum elements, which is a useful input for those frameworks. It is **not legal advice** and **not a substitute** for the binding requirements of EU MDR, the EU AI Act, ISO/IEC 42001, FDA QSR, ISO 13485, or any other framework that applies to your product. Always consult the actual text of the framework and, where appropriate, your regulatory affairs team or notified body.

**Will my data be lost?**
Your data persists in **that specific browser, on that specific device**. If you clear your browser data, switch browsers, switch computers, or open the tool in a private/incognito window, the new session starts fresh. The safe habit is to **Download .json** whenever you reach a meaningful milestone — that file is your portable, permanent copy.

**Can I work on several SBOMs at once?**
Yes. The tool keeps a list of all SBOMs you have created in this browser. You can switch between them, rename them, or delete the ones you no longer need.

**Can I share my work with a colleague?**
Yes — export it as a `.json` file and send it the same way you would any other document. Your colleague can keep it as a record; importing it back into a different browser to continue editing is a possible future enhancement.

**Does it work offline?**
After the first time the page loads, yes — your browser caches the small external assets it uses, and you can keep working without an internet connection.

---

## 6. Feedback and contact

This tool is open source and improves with use. If you have ideas, suggestions, corrections to field descriptions, or examples from your own field that would help others, please get in touch:

**Brahim EL ALLAM** — TÜV SÜD-certified PRRC (EU MDR Article 15) · QM/RA Manager
[LinkedIn — connect or send feedback](https://www.linkedin.com/in/brahim-el-allam-0a7731222/)

Contributions are warmly welcome. Bug reports, pull requests, and translated UI strings can be submitted via the project repository:
https://github.com/brahimelallam/sbom4ai-builder

Thank you for using SBOM4AI Builder.
