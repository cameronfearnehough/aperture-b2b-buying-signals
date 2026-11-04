# Aperture MCP Server — Master Registry Submission Checklist

This checklist governs the distribution and indexing of the **Aperture B2B Buying-Signal & Statutory Enrichment MCP Server** across the top 5 Model Context Protocol registries and directories (`mcp.so`, `pulsemcp.com`, `smithery.ai`, `glama.ai`, and `github.com/modelcontextprotocol/servers`).

Follow each gate sequentially. Every check must pass before completing directory submissions.

---

## Gate 0: Pre-Submission GitHub Repository Configuration (CRITICAL)

Before submitting to any registry (especially `mcp.so`), the public GitHub repository must be configured with exact metadata. Directory scrapers crawl GitHub repo metadata at submission time to index website backlinks.

- [ ] **Repository Name:** Set to `aperture-b2b-buying-signals` (or `aperture-mcp-server`).
- [ ] **Repository Description:** Under 350 characters, containing high-intent keywords:
  > *"Aperture B2B Buying-Signal & Statutory Enrichment Suite connects autonomous AI agents to real-time commercial intent triggers (hiring, funding, tender awards, executive appointments, clinical trials) across 9 markets via hosted Apify Streamable HTTP and stdio."*
- [ ] **GitHub Repository Homepage URL (MANDATORY):** Set to:
  ```text
  https://apify.com/aperture
  ```
  > ⚠️ **CRITICAL DOFOLLOW BACKLINK REQUIREMENT:** `mcp.so` extracts its dofollow website link directly from the GitHub repository **Homepage URL** field at the moment of submission. If this field is empty when paying the $39 verified review fee, the scraper will index an empty link or default to GitHub, forfeiting the DR 70+ dofollow backlink to Apify Store.
- [ ] **Repository Topics:** Set the following 10 discovery tags:
  `model-context-protocol`, `mcp-server`, `apify`, `b2b-sales`, `intent-data`, `lead-generation`, `buying-signals`, `sales-intelligence`, `enrichment`, `claude-desktop`.
- [ ] **License Check:** Verify [LICENSE](./LICENSE) exists and contains the official MIT license with copyright `2026 Aperture Intelligence (apify.com/aperture)`.
- [ ] **Bundle Files Present:** Verify all 5 bundle files exist in the repository root:
  - `README.md`
  - `smithery.yaml`
  - `LICENSE`
  - `SUBMISSION_CHECKLIST.md`
  - `SUBMISSION_GUIDE.md`

---

## Gate 1: Bundle Content & Copywriting Verification

- [ ] **Line 1 Capability Declaration:** `README.md` begins on Line 1 with the exact single-sentence capability declaration stating target intent streams, geographies, and protocol endpoints.
- [ ] **Client Setup Blocks:** Copy-paste configuration blocks for both Streamable HTTP (`https://mcp.apify.com`) and local stdio (`@apify/actors-mcp-server`) are present for:
  - Claude Desktop (`claude_desktop_config.json`)
  - Claude Code CLI (`claude mcp add ...`)
  - Cursor IDE (`.cursor/mcp.json`)
  - VS Code Copilot (`.vscode/mcp.json`)
- [ ] **Unauthenticated Discovery Documented:** Explicitly documents how AI agents query `search-actors` and `fetch-actor-details` without an API token at up to 30 req/s ($0 token cost).
- [ ] **Dynamic Schema Inference Documented:** Explains how `https://mcp.apify.com` dynamically parses `.actor/output_schema.json` and `.actor/dataset_schema.json` to generate strongly typed tool definitions for LLMs.
- [ ] **Complete 10-Actor Manifest Table:** Table lists all 10 Aperture Actors with Actor Slug, Apify Actor ID, Geographies, Signal Dimension, Key Input Parameters, First-10-Key Output Order, and Pay-Per-Event / Bytewells pricing.
- [ ] **Fair Pricing Guarantee (`role_fallback`):** Details the $0.002 base vs. $0.008 enriched ($0.003 vs. $0.009 for Aggregator) pricing rule and guarantees free departmental inboxes (`role_fallback`).
- [ ] **Softened Cloud Execution Claim:** Includes the exact required phrasing:
  > *"Runs in the cloud without requiring your LinkedIn cookies or browser login."*
- [ ] **Empirical Proof Table:** Displays verified output rows cited verbatim from a file that passes scripts/audit/verify-ground-truth-csv.mjs (currently marketing/sample-leads/dach-verified-leads.csv: `OXEA GmbH`, `ElektroPhysik Dr. Steingroever GmbH & Co. KG`, `achelos GmbH`, `Hauff-Technik GmbH & Co. KG`, `Magnet-Schultz GmbH & Co. KG`, `Aktiv Assekuranz Makler GmbH`).
- [ ] **Bytewells Unit Economics Bridge:** Features the 8,300 rows/month break-even comparison between on-demand Apify PPE and Bytewells $49/mo flat rental.
- [ ] **Zero Internal Artifacts Above `<details>`:** Confirmed zero raw internal flags, prompt leaks, or `[cite: ...]` references above the `<details>` block.

---

## Gate 2: Registry Submission Execution

Open [SUBMISSION_GUIDE.md](./SUBMISSION_GUIDE.md) and copy-paste the exact form payloads into each registry:

### 1. `mcp.so/submit` ($39 Instant Verified Tier)
- [ ] Confirm GitHub repo Homepage URL is set to `https://apify.com/aperture`.
- [ ] Navigate to `https://mcp.so/submit`.
- [ ] Select **$39 Instant Verified Review** (enables 24h fast-track indexing + verified badge + high-authority dofollow link).
- [ ] Paste Repository URL and Metadata from Section 2 of `SUBMISSION_GUIDE.md`.
- [ ] Complete payment and record listing URL.
- [ ] Inspect live page HTML to confirm `rel="dofollow"` link targets `https://apify.com/aperture`.

### 2. `pulsemcp.com/submit`
- [ ] Navigate to `https://pulsemcp.com/submit`.
- [ ] Paste GitHub URL, server title, and transport types (`http`, `stdio`).
- [ ] Paste structured description and tags from Section 3 of `SUBMISSION_GUIDE.md`.
- [ ] Submit and verify indexing confirmation.

### 3. `smithery.ai/new`
- [ ] Navigate to `https://smithery.ai/new`.
- [ ] Connect repository `aperture-b2b-buying-signals`.
- [ ] Confirm `smithery.yaml` is detected and schema validation passes with 0 warnings.
- [ ] Test installation command locally:
  ```bash
  npx -y @smithery/cli install vivid_astronaut/aperture-b2b-buying-signals --client claude
  ```
- [ ] Publish listing.

### 4. `glama.ai/mcp/servers`
- [ ] Navigate to `https://glama.ai/mcp/servers`.
- [ ] Click **Submit Server**.
- [ ] Paste repository URL, hosted endpoint (`https://mcp.apify.com`), and documentation link.
- [ ] Paste categories and overview from Section 5 of `SUBMISSION_GUIDE.md`.
- [ ] Confirm listing.

### 5. Official MCP Community Servers PR (`github.com/modelcontextprotocol/servers`)
- [ ] Fork `https://github.com/modelcontextprotocol/servers`.
- [ ] Create branch `add-aperture-b2b-buying-signals`.
- [ ] Apply the exact Markdown diff provided in Section 6 of `SUBMISSION_GUIDE.md` to `README.md` under the Community Servers table.
- [ ] Verify Markdown table aligns properly with surrounding entries.
- [ ] Commit with message:
  ```bash
  git commit -m "Add Aperture B2B Buying-Signal & Statutory Enrichment Suite to community servers"
  ```
- [ ] Open Pull Request using the exact PR Title and Body from `SUBMISSION_GUIDE.md`.

---

## Gate 3: Post-Submission Verification & Telemetry

- [ ] **Link Integrity:** Confirm all registry profile links resolve with HTTP 200.
- [ ] **SEO & Dofollow Audit:** Inspect the backlink on `mcp.so` using Chrome DevTools or `curl` to verify no `rel="nofollow"` or `rel="ugc"` attribute overrides the link to `https://apify.com/aperture`.
- [ ] **Search Indexing:** Submit registry listing URLs to Google Search Console or ping indexers to accelerate crawl frequency.
