# Aperture MCP Server — Master Copy-Paste Registry Submission Guide

This guide provides exact, production-ready form field values for submitting the **Aperture B2B Buying-Signal & Statutory Enrichment MCP Server** to all major Model Context Protocol registries and directories:

1. [GitHub Repository Setup (Mandatory Foundation)](#1-github-repository-metadata-setup)
2. [mcp.so ($39 Instant Verified Tier + Dofollow Backlink)](#2-mcpso-submission-guide)
3. [pulsemcp.com](#3-pulsemcpcom-submission-guide)
4. [smithery.ai](#4-smitheryai-submission-guide)
5. [glama.ai](#5-glamaai-submission-guide)
6. [Official MCP Registry PR (`modelcontextprotocol/servers`)](#6-official-mcp-registry-github-pr-guide)

---

## 1. GitHub Repository Metadata Setup

> ⚠️ **DO THIS BEFORE SUBMITTING TO ANY DIRECTORY:**
> Directory scrapers (especially `mcp.so`) scrape your repository settings when indexing. The **Homepage URL** is used to create the live dofollow backlink to your commercial store.

Navigate to **https://github.com/cameronfearnehough/aperture-b2b-buying-signals** -> Click the **⚙️ Settings** icon in the **About** section (top right of the repository homepage):

### Repository Name
```text
aperture-b2b-buying-signals
```

### Description (292 Characters)
```text
Connect autonomous AI agents to real-time B2B buying signals (hiring, funding, public tenders, statutory appointments, clinical trials) across 9 markets via hosted Apify Streamable HTTP and stdio. Runs in the cloud without requiring your LinkedIn cookies or browser login.
```

### Homepage URL (CRITICAL FOR DOFOLLOW BACKLINK)
```text
https://apify.com/aperture
```

### Topics (Paste one by one and press Enter)
```text
model-context-protocol
mcp-server
apify
b2b-sales
intent-data
lead-generation
buying-signals
sales-intelligence
enrichment
claude-desktop
```

---

## 2. `mcp.so` Submission Guide

- **Submission URL:** `https://mcp.so/submit`
- **Recommended Tier:** **$39 Instant Verified Review** (Delivers 24-hour fast-track approval, verified badge, and guarantees that mcp.so's crawler parses the repository Homepage URL as a high-authority DR 70+ dofollow backlink to `https://apify.com/aperture`).

### Form Fields (Copy & Paste)

#### Server Name
```text
Aperture B2B Buying-Signal & Statutory Enrichment Suite
```

#### GitHub Repository URL
```text
https://github.com/cameronfearnehough/aperture-b2b-buying-signals
```

#### Website / Store Homepage URL
```text
https://apify.com/aperture
```

#### Category
```text
Business & Productivity (or Data & Scraping)
```

#### Pricing Model
```text
Freemium (Pay-Per-Event: $0.002 base / $0.008 verified named contact; Free role_fallback)
```

#### Short Tagline (124 Characters)
```text
Autonomous B2B intent signals (hiring, funding, public tenders, clinical trials) across 9 markets via Streamable HTTP & stdio.
```

#### Detailed Description (Markdown)
```markdown
Aperture B2B Buying-Signal & Statutory Enrichment Suite connects autonomous AI agents to real-time commercial intent triggers—active hiring requisitions, venture capital funding rounds, public procurement contract awards, statutory executive changes, and clinical trial pipelines—across 9 global markets via the hosted Apify Streamable HTTP MCP server (https://mcp.apify.com) and local stdio.

Runs in the cloud without requiring your LinkedIn cookies or browser login.

### Key Capabilities
- **Commercial Hiring Intent:** Real-time job requisitions from Stepstone (DE, AT, BE, NL), Seek (AU, NZ), France Travail (FR), and public ATS career boards (Greenhouse, Lever, Ashby, Workable).
- **Public Procurement Awards:** Government contract awards from UK Find a Tender Service (OCDS), EU TED API v3, and French BOAMP.
- **Statutory Corporate Registries:** Executive appointments and corporate incorporations from UK Companies House, French BODACC, and German Handelsregister.
- **Biotech & Life Sciences:** Clinical trial activations and NIH/EU grant awards from ClinicalTrials.gov API v2, EU CTIS, and Horizon Europe CORDIS.
- **Deep Impressum & Contact Enrichment:** Direct HTTP/2 corporate crawling across /sales, /team, and statutory /impressum pages with automatic Cloudflare XOR hex decoding and zero-cost DNS/DoH deliverability checks.

### Fair Pricing Guarantee (`role_fallback`)
- Basic signals billed at $0.002 ($0.003 for Aggregator).
- Verified named contacts (firstname.lastname@) billed at $0.008 ($0.009 for Aggregator).
- Generic department inboxes (info@, contact@, sales@) are delivered for FREE as `role_fallback` at base rates.
- High-volume flat rental available at $49/mo on Bytewells.com (8,300 rows/mo break-even).
```

#### Client Configuration (Claude Desktop)
```json
{
  "mcpServers": {
    "aperture-signals": {
      "url": "https://mcp.apify.com",
      "headers": {
        "Authorization": "Bearer YOUR_APIFY_TOKEN"
      }
    }
  }
}
```

---

## 3. `pulsemcp.com` Submission Guide

- **Submission URL:** `https://pulsemcp.com/submit`

### Form Fields (Copy & Paste)

#### Server Title
```text
Aperture B2B Buying-Signal & Statutory Intelligence
```

#### GitHub Repository URL
```text
https://github.com/cameronfearnehough/aperture-b2b-buying-signals
```

#### Author / Maintainer
```text
Aperture Intelligence (apify.com/aperture)
```

#### Primary Transports
- [x] Streamable HTTP (`https://mcp.apify.com`)
- [x] Local stdio (`@apify/actors-mcp-server`)

#### Category Tags
```text
Sales, Intent Data, Web Scraping, B2B, Lead Generation, Apify, Claude Desktop
```

#### Short Summary
```text
Multi-source B2B intent signals (hiring requisitions, public tender awards, startup funding, statutory executive appointments, clinical trials) across 9 markets for autonomous AI agents.
```

#### Execution Command (stdio)
```text
npx -y @apify/actors-mcp-server --actors vivid_astronaut/stepstone-dach-buying-signal-scraper,vivid_astronaut/seek-anz-buying-signal-scraper,vivid_astronaut/france-buying-signal-scraper,vivid_astronaut/b2b-buying-signal-icp-aggregator,vivid_astronaut/eu-uk-procurement-award-signal-scraper,vivid_astronaut/eu-uk-executive-incorporation-signal-scraper,vivid_astronaut/biotech-clinical-trial-buying-signal-scraper,vivid_astronaut/linkedin-ats-b2b-buying-signal-scraper
```

---

## 4. `smithery.ai` Submission Guide

- **Submission URL:** `https://smithery.ai/new`

### Submission Process

1. **Connect GitHub:** Authorize Smithery to access your public repository `cameronfearnehough/aperture-b2b-buying-signals`.
2. **Configuration Detection:** Smithery automatically reads [`smithery.yaml`](./smithery.yaml) from the repository root.
3. **Verify Settings:**
   - **Command Type:** `stdio`
   - **Package:** `npx -y @apify/actors-mcp-server`
   - **Config Schema:** Confirmed `apifyToken` (required), `defaultActors` (array), and `scraperMode` (enum).
4. **Test CLI Installation:** Verify the Smithery 1-click installation works:
   ```bash
   npx -y @smithery/cli install vivid_astronaut/aperture-b2b-buying-signals --client claude
   ```
5. **Publish:** Click **Publish Server**.

---

## 5. `glama.ai` Submission Guide

- **Submission URL:** `https://glama.ai/mcp/servers`

### Form Fields (Copy & Paste)

#### Server Name
```text
Aperture B2B Buying Signals & Statutory Enrichment
```

#### Repository URL
```text
https://github.com/cameronfearnehough/aperture-b2b-buying-signals
```

#### Server Hosted Endpoint
```text
https://mcp.apify.com
```

#### Standard Stdio Command
```text
npx -y @apify/actors-mcp-server
```

#### Tags
```text
b2b-sales, intent-data, web-scraping, apify, lead-gen
```

#### Documentation URL
```text
https://github.com/cameronfearnehough/aperture-b2b-buying-signals#readme
```

#### Description
```text
Enables AI agents to query 10 commercial intent pipelines across Germany, Austria, Switzerland, France, the UK, the US, Australia, and New Zealand. Access real-time job hiring, public procurement tenders (Find a Tender OCDS / EU TED), statutory executive appointments (Companies House / BODACC), and biotech clinical trials (ClinicalTrials.gov v2 / CTIS). Features the Fair Pricing Guarantee with free role_fallback departmental inboxes.
```

---

## 6. Official MCP Registry GitHub PR Guide

The official repository for community Model Context Protocol servers is hosted at [github.com/modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers).

Follow these exact steps to submit a Pull Request:

### Step 1: Fork and Clone
```bash
git clone https://github.com/<your-username>/servers.git mcp-servers-fork
cd mcp-servers-fork
git checkout -b add-aperture-b2b-buying-signals
```

### Step 2: Update `README.md`
Open `README.md` and navigate to the **Community Servers** table. Insert the Aperture entry alphabetically under **A**:

```markdown
| [Aperture B2B Buying Signals](https://github.com/cameronfearnehough/aperture-b2b-buying-signals) | 🏢 💼 | Real-time B2B buying signals (hiring, funding, public tenders, statutory appointments, clinical trials) across 9 markets via hosted Apify Streamable HTTP or stdio | [Node/npm](https://www.npmjs.com/package/@apify/actors-mcp-server) |
```

### Step 3: Commit and Push
```bash
git add README.md
git commit -m "Add Aperture B2B Buying-Signal & Statutory Enrichment Suite to community servers"
git push origin add-aperture-b2b-buying-signals
```

### Step 4: Open Pull Request

#### PR Title
```text
Add Aperture B2B Buying-Signal & Statutory Enrichment Suite to Community Servers
```

#### PR Body (Copy & Paste Markdown)
```markdown
### Summary
This PR adds the **Aperture B2B Buying-Signal & Statutory Enrichment Suite** to the Community Servers table.

- **Repository:** https://github.com/cameronfearnehough/aperture-b2b-buying-signals
- **Server Documentation:** https://github.com/cameronfearnehough/aperture-b2b-buying-signals/blob/main/README.md
- **Transport Types:** Streamable HTTP (`https://mcp.apify.com`) and local stdio via [`@apify/actors-mcp-server`](https://www.npmjs.com/package/@apify/actors-mcp-server).

### Server Overview
Aperture connects autonomous AI agents to real-time commercial intent triggers across 9 global markets (US, UK, DE, FR, AT, CH, BE, NL, AU, NZ):
- **Hiring Requisitions:** Stepstone DACH/Benelux, Seek ANZ, France Travail, and ATS platforms (Greenhouse, Lever, Ashby, Workable).
- **Public Procurement Awards:** UK Find a Tender Service (OCDS), EU TED (API v3), and French BOAMP.
- **Statutory Corporate Registries:** UK Companies House, French BODACC (DataDila), and German Handelsregister.
- **Life Sciences Clinical Trials:** US ClinicalTrials.gov API v2, EU CTIS, and Horizon Europe CORDIS.
- **Statutory Enrichment:** Corporate website contact discovery with automatic Cloudflare XOR / TYPO3 decoding and zero-cost MX deliverability verification.

### Verification Checklist
- [x] Readme conforms to Community Server format.
- [x] Tested with Claude Desktop, Claude Code, and Cursor.
- [x] Unauthenticated discovery supported via `search-actors` and `fetch-actor-details` up to 30 req/s.
- [x] Open-source MIT license included in repository.
```
