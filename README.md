# SBOM4AI Builder

> **Free and open source. For anyone, for anything. Runs locally — self-hosted on your own laptop or server. No cloud, no accounts, no API keys, no tracking.**

![License: MIT](https://img.shields.io/badge/License-MIT-7a1f1f.svg)
![100% Client-Side](https://img.shields.io/badge/runs-100%25%20local-2d5e3f.svg)
![No tracking](https://img.shields.io/badge/tracking-none-444.svg)
![Single file](https://img.shields.io/badge/deploy-single%20HTML%20file-444.svg)

A guided builder for **G7-compliant Software Bills of Materials for AI systems**, implementing the seven clusters of minimum elements published by G7 cybersecurity agencies.

**Developed by [Brahim EL ALLAM](https://www.linkedin.com/in/brahim-el-allam-0a7731222/)** — TÜV SÜD-certified PRRC (EU MDR Art. 15) · QM/RA Manager

[💼 Connect on LinkedIn](https://www.linkedin.com/in/brahim-el-allam-0a7731222/)  ·  [📝 Send feedback](https://www.linkedin.com/in/brahim-el-allam-0a7731222/)

---

## License & freedom of use — in plain words

- ✅ **Free** — costs nothing, ever.
- ✅ **Open source** — all the code is in one readable `index.html`. Nothing hidden.
- ✅ **Use it for anything** — personal, commercial, internal corporate tooling, teaching, research. No restrictions beyond keeping the MIT notice.
- ✅ **Local & self-hosted** — the whole app runs on *your* machine. Double-click the file and it works in your browser, even offline. Your data never leaves your laptop (it's saved in your browser's local storage only).
- ✅ **No backend, no server, no cloud account, no API key, no sign-up, no telemetry.**

You can fork it, rename it, restyle it, embed it in your company's intranet, or ship it to your own domain. The MIT License is about as permissive as software licenses get.

Built on the G7 Cybersecurity Working Group document
**"Software Bill of Materials for AI — Minimum Elements"** (February 2026),
jointly published by BSI (Germany), ACN (Italy), ANSSI (France), CSE (Canada),
CISA (USA), NCSC (UK), and NCO (Japan), with the EU Commission.

---

## What it does

Walks you through the **seven clusters** of minimum elements from the G7 guidance:

1. **Metadata** — the SBOM document itself (author, version, format, signature, timestamps)
2. **System Level Properties** — the AI system as a whole (components, data flow, I/O, intended use)
3. **Models** — every AI model used (identifier, version, hash, properties, training, license)
4. **Datasets Properties** — every dataset used (provenance, sensitivity, statistics, license)
5. **Infrastructure** — software and hardware dependencies (HBOM link)
6. **Security Properties** — controls, compliance, policy, vulnerability references
7. **Key Performance Indicators** — security metrics and operational KPIs

For each field, the G7 description is shown inline so users **learn the standard while filling it**.

---

## Features

- ✅ All seven G7 clusters, 50+ minimum elements
- ✅ Add multiple Models and Datasets (proper structured arrays)
- ✅ Multiple SBOMs saved side-by-side in your browser
- ✅ Auto-save (zero clicks)
- ✅ Validation view — coverage % per cluster, jump to gaps
- ✅ JSON export — copy to clipboard or download
- ✅ Pre-loaded medical-AI demo (Class IIa imaging triage)
- ✅ Mobile-friendly responsive layout
- ✅ **100% client-side** — no servers, no tracking, no AI/API calls

---

## Privacy

Everything stays on the user's device.

- Data is stored in the browser's `localStorage` only
- No analytics, no telemetry, no third-party tracking
- No accounts, no sign-up
- No backend — the entire app is one HTML file
- No AI / LLM API calls of any kind

Loaded from public CDNs at startup: React, Tailwind CSS (Play CDN), Babel Standalone, Google Fonts. No user data is sent to those CDNs.

---

## Try it locally (zero setup)

Download `index.html` and **double-click it**. It opens in your browser and works offline (after the first load that caches the CDN assets).

---

## Deploy your own (free, choose one)

### Option A — Netlify drop (easiest, 30 seconds, no Git required)

1. Go to https://app.netlify.com/drop
2. Drag the folder containing `index.html` onto the page
3. You get a free `https://<random>.netlify.app` URL instantly
4. (Optional) Sign up to rename or connect a domain

### Option B — GitHub Pages (free, custom URL)

1. Create a new GitHub repository (e.g., `sbom4ai-builder`)
2. Upload `index.html`, `README.md`, `LICENSE`
3. Settings → **Pages** → Source: `Deploy from a branch` → Branch: `main` → folder: `/ (root)` → Save
4. Wait ~1 minute → visit `https://<your-username>.github.io/sbom4ai-builder/`

### Option C — Cloudflare Pages (free, fast CDN)

1. Push the files to a GitHub repository
2. https://pages.cloudflare.com → Create project → Connect to your repo
3. Build command: *(leave empty)* · Build output directory: `/` → Save & Deploy
4. You get a free `https://<project>.pages.dev` URL

### Option D — Vercel (free)

1. Push the files to a GitHub repository
2. https://vercel.com/new → Import the repo
3. Framework preset: `Other` → Deploy
4. You get a free `https://<project>.vercel.app` URL

### Option E — Any static web host

Drop `index.html` on any web server (Apache, nginx, S3, even a USB stick served via `python -m http.server`).

---

## Customising

The entire app is in one `index.html` file. Open it in any editor.

- The **schema** (all clusters, field labels, descriptions, examples) is the `CLUSTERS` array near the top of the inline `<script>` block. Edit field text, add fields, or add whole new clusters there.
- The **demo data** is in the `makeDemoDoc()` function — change it to your own example.
- The **styling** uses Tailwind utility classes inline. Colors are the `stone-*` and `lime-*` Tailwind palettes.
- The **storage keys** are `sbom4ai:index` and `sbom4ai:doc:*` in `localStorage`.

### Going to a real build system

For production deployment with a build step (faster load, no Babel-in-browser):

1. Create a Vite + React project: `npm create vite@latest -- --template react`
2. Copy the JSX from inside the `<script type="text/babel">` block into `src/App.jsx`
3. Adjust imports (use `import` statements instead of globals, add `lucide-react` for icons)
4. `npm run build` → deploy the `dist/` folder

---

## Roadmap ideas (PRs welcome)

- Native SPDX 3.0 / CycloneDX 1.6 export (currently exports clean cluster-structured JSON)
- Regulatory-mapping overlay (EU MDR Annex II.6, EU AI Act Articles 11–15, ISO/IEC 42001)
- Import existing SBOMs to extend with the AI-specific clusters
- Multi-language UI
- Signature verification helpers (Sigstore, PKCS#7)
- Diff view between SBOM versions

---

## Disclaimer

This tool helps structure SBOMs aligned with the **G7 minimum elements**, which are
**not mandatory** and **do not create requirements, standards, or legislation**
(as stated in the source document). In some jurisdictions, certain elements may
already be addressed through legal requirements, obligations, or existing/forthcoming
standards. Always consult your applicable frameworks (EU MDR, EU AI Act, FDA 21 CFR
Part 820 / QSR, ISO/IEC 42001, ISO 13485, etc.) for binding obligations.

This tool is provided **as-is**, without warranty of any kind. It is not legal,
regulatory, or cybersecurity advice.

---

## Sources

- **G7 Cybersecurity Working Group — "Software Bill of Materials for AI: Minimum Elements"** (February 2026), jointly published by BSI, ACN, ANSSI, CSE, CISA, NCSC, NCO, with the EU Commission
- **G7 Cybersecurity Working Group — "A Shared G7 Vision on SBOM for AI"** (June 2025)
- NCSC — *Guidelines for Secure AI System Development*
- NCSC — *SBOMs and the importance of inventory*

---

## License

[MIT](./LICENSE) — do what you want with it. Attribution appreciated but not required.

---

## Author

**Brahim EL ALLAM**
TÜV SÜD-certified PRRC (EU MDR Article 15) · QM/RA Manager
Bridging regulatory rigor, engineering, and AI innovation.

🔗 [LinkedIn](https://www.linkedin.com/in/brahim-el-allam-0a7731222/) — feedback, questions, and collaboration welcome.

### Suggested Citation

```
EL ALLAM, B. (2026). SBOM4AI Builder: An interactive tool for
G7-compliant Software Bills of Materials for AI systems.
[Software]. MIT License.
```

---

## Contributing

Issues and pull requests welcome. If you find a field description that drifts from the
G7 source, please open an issue with the page reference.
