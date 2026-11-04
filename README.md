![Aperture — Global B2B Buying-Signal & Statutory Enrichment Suite](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/aperture-suite-banner.png)

![Strict Named-Contact $0.008](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/badge-strict-named-contact.svg) ![Zero-Proxy HTTP/2 <5s](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/badge-zero-proxy-http2.svg) ![LIMITED_PERMISSIONS • MCP Ready](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/badge-mcp-skyfire-ready.svg)

# Aperture — Global B2B Buying-Signal & Enrichment Suite

Official public integration showcase, n8n workflows, Clay HTTP API recipes, and MCP configurations for **[Aperture — Data Aggregation Solutions](https://apify.com/aperture)** on the Apify Store and **[Bytewells](https://bytewells.com)**.

A unified 10-Actor portfolio of commercial B2B intent-signal scrapers, bulk statutory enrichment tools, and 5D ICP post-processing engines engineered for Sales-Ops, RevOps, and growth teams running outbound campaigns in Clay, n8n, Make, or custom CRMs across **10 markets: the United States (`US`), Germany (`DE`), Austria (`AT`), Belgium (`BE`), the Netherlands (`NL`), France (`FR`), the UK (`UK`), Australia (`AU`), New Zealand (`NZ`), and the European Union (`EU`)**. Every tool resolves the company's real website domain, crawls legal/contact pages (`/impressum`, `/mentions-legales`, `/kontakt`), and extracts verified decision-maker emails and direct phone numbers in one pass. Runs in the cloud without requiring your LinkedIn cookies or browser login.

---

## Quick Links: 1-Click n8n Workflows, Clay HTTP API Recipes & Claude Desktop MCP

Ready-to-import integration assets for zero-code and low-code outbound data pipelines:

* **[Global 4-Actor Fan-In n8n Workflow](./examples/n8n-global-4-actor-fan-in-to-clay.json)**: Scheduled multi-region pipeline running Stepstone DACH, Seek ANZ, France Multi-Signal, and EU/UK Procurement in parallel, streaming into the ICP Aggregator, and syncing to Clay.
* **[Stepstone DACH to Clay n8n Workflow](./examples/stepstone-dach-buying-signals-to-clay.json)**: Dedicated DACH buying signal scraper running on hourly/daily cron with automatic Clay webhook dispatch.
* **[Clay HTTP API Recipes & Webhook Guides](./examples/clay-http-api-recipes.md)**: Copy-paste cURL, HTTP API request bodies, and Clay action configurations for webhook-based automated enrichment.
* **[Claude Desktop & Cursor MCP Server Config](./examples/claude_desktop_config.json)**: One-click configuration to orchestrate all 6 Aperture Actors directly inside Claude Desktop, Cursor, or any MCP client.
* **[Smithery.ai 1-Click MCP Install](https://smithery.ai)**:
  ```bash
  npx -y @smithery/cli install vivid_astronaut/aperture-b2b-buying-signals --client claude
  ```
* **[X (Twitter) Launch Samples & Verified Live Rows](./X_LAUNCH_SAMPLES.md)**: Real output payloads, screenshot-ready Markdown tables, and campaign launch templates across all 6 commercial Actors.

---

## Fair Pricing Guarantee: Only Pay for Named People

All Aperture Actors enforce a transparent, cost-protective Pay-Per-Event (PPE) pricing policy on Apify Store and support zero-fork flat rentals & HTTP 402 agentic passes on Bytewells:

* **Regional & Vertical Signal Scrapers (`$0.002` / `$0.008`)**:
  * **`$0.002` per company signal (`$2.00 / 1,000`) — `job-signal-scraped`:** Includes full company profile, resolved website domain, verified phone number, salary/contract/grant details, and statutory role inbox if found.
  * **`$0.008` per named contact (`$8.00 / 1,000`) — `buying-signal-enriched`:** Charged strictly when a verified named decision-maker email (`firstname.lastname@company.com`, `email_verification_status: "ok"`) is delivered.
  * **Generic Inboxes Are Free (`role_fallback`):** Generic role inboxes (`info@`, `contact@`, `sales@`, `jobs@`) are provided at no extra charge (`email_verification_status: "role_fallback"`) and billed at the basic `$0.002` rate.
  * **`$0.00` Pre-Fetch Exclusion Shield (`excludeCompanyKeywords` / `excludeLocations`):** Excluded companies, universities/hospitals (`commercialSponsorsOnly`), and geographies are dropped before domain resolution or PPE charging.
* **B2B Buying-Signal 5D ICP Aggregator & Whale Suite (`$0.003` / `$0.009`)**:
  * **`$0.003` per scored lead (`$3.00 / 1,000`) — `icp-lead-scored`:** Cross-dataset deduplication, 0–100 5D ICP score (`jobs`, `funding`, `contract_award`, `executive_change`, `clinical_trial`, `research_grant`), 28 tech-stack tags, ready-to-send outreach hook, and free role fallback inboxes (`role_fallback`).
  * **`$0.009` per named contact (`$9.00 / 1,000`) — `icp-multi-signal-enriched`:** Charged only when the lead includes a verified named contact (`firstname.lastname@`, `email_verification_status: "ok"`).
  * **`$0.00` for Blacklisted Accounts:** Current customers, competitors, and agencies filtered via `blacklistDomains` are excluded before scoring and billing at zero cost.
* **European Impressum Contact Bulk Enricher (`$0.001` / `$0.006`)**:
  * **`$0.001` per crawled domain (`$1.00 / 1,000`) — `domain-crawled`:** Domain normalization, statutory register IDs (HRB, SIREN, FN, CHE, KvK), VAT identification, phone numbers, and 28 tech stack tags.
  * **`$0.006` per named contact (`$6.00 / 1,000`) — `impressum-contact-enriched`:** Charged strictly for verified named individuals. Generic `info@` inboxes stay free (`role_fallback`) at `$0.001`.

---

## Complete 10-Actor Suite

![Aperture Multi-Region Buying-Signal & ICP Aggregation Architecture](https://api.apify.com/v2/key-value-stores/j5l13XT1d0O0NQmTI/records/aperture-architecture.png)

| # | Actor | Markets (`geo`) | Signal Types | Primary Data Sources | Price (Basic / Named) | Bytewells Flat Rental |
| :-: | :--- | :---: | :--- | :--- | :--- | :--- |
| **1** | **[`aperture/stepstone-dach-buying-signal-scraper`](https://apify.com/aperture/stepstone-dach-buying-signal-scraper)** | `DE`, `AT`, `BE`, `NL` | `jobs` | Stepstone Germany, Austria, Belgium & Netherlands + Impressum email discovery | `$0.002` / **`$0.008`** | `$49/mo` Unlimited |
| **2** | **[`aperture/seek-anz-buying-signal-scraper`](https://apify.com/aperture/seek-anz-buying-signal-scraper)** | `AU`, `NZ` | `jobs` | Seek Australia & New Zealand live job postings + corporate email discovery | `$0.002` / **`$0.008`** | `$49/mo` Unlimited |
| **3** | **[`aperture/france-buying-signal-scraper`](https://apify.com/aperture/france-buying-signal-scraper)** | `FR` | `jobs`, `funding` | France Travail job postings + Maddyness startup funding rounds + mentions-légales emails | `$0.002` / **`$0.008`** | `$49/mo` Unlimited |
| **4** | **[`aperture/b2b-buying-signal-icp-aggregator`](https://apify.com/aperture/b2b-buying-signal-icp-aggregator)** | `All 9 Geos` | `5D Multi-Signal` | Cross-dataset deduplicator, 28-tool tech scanner, 0–100 5D ICP scoring & outreach hooks | `$0.003` / **`$0.009`** | `$49/mo` Unlimited |
| **5** | **[`aperture/eu-uk-procurement-award-signal-scraper`](https://apify.com/aperture/eu-uk-procurement-award-signal-scraper)** | `UK`, `FR`, `DE`, `NL`, `BE`, `AT` | `contract_award` | UK Find a Tender / Contracts Finder + France BOAMP + EU TED public contract awards | `$0.002` / **`$0.008`** | `$49/mo` Unlimited |
| **6** | **[`aperture/eu-uk-executive-incorporation-signal-scraper`](https://apify.com/aperture/eu-uk-executive-incorporation-signal-scraper)** | `FR`, `UK`, `DE`, `AT` | `executive_change` | France BODACC & Recherche d'Entreprises + UK Companies House + GLEIF Level-1 v1 | `$0.002` / **`$0.008`** | `$49/mo` Unlimited |
| **7** | **[`aperture/biotech-clinical-trial-buying-signal-scraper`](https://apify.com/aperture/biotech-clinical-trial-buying-signal-scraper)** | `US`, `UK`, `DE`, `FR`, `NL`, `BE`, `AT` | `clinical_trial`, `research_grant` | US ClinicalTrials.gov v2 + EU EMA CTIS + EU CORDIS Horizon Europe + US NIH SBIR/STTR | `$0.002` / **`$0.008`** | `$49/mo` Unlimited |
| **8** | **[`aperture/linkedin-ats-b2b-buying-signal-scraper`](https://apify.com/aperture/linkedin-ats-b2b-buying-signal-scraper)** | `All 9 Geos` | `jobs` | Zero-Cookie LinkedIn Guest Jobs + Greenhouse, Lever & Personio + City-Split 1k bypass | `$0.002` / **`$0.008`** | `$49/mo` Unlimited |
| **9** | **[`aperture/european-impressum-contact-bulk-enricher`](https://apify.com/aperture/european-impressum-contact-bulk-enricher)** | `DE`, `AT`, `CH`, `FR`, `UK`, `NL`, `BE` | `impressum_enrichment` | Pure HTTP/2 bulk domain-to-contact extraction, statutory register IDs & B2B SaaS tech stack | `$0.001` / **`$0.006`** | `$49/mo` Unlimited |
| **10** | **[`aperture/global-b2b-signal-suite-unlimited`](https://apify.com/aperture/global-b2b-signal-suite-unlimited)** | `All 10 Geos` | `All 5D Signals` | All-in-one whale orchestrator (Jobs, Tenders, Directors, Trials & Grants) | `$0.003` / **`$0.009`** | `$199–$249/mo` Agency Pass |

---

## Documentation, GTM Copywriting & Verification Index

* [`docs/APERTURE_B2B_GTM_COPYWRITER.md`](./docs/APERTURE_B2B_GTM_COPYWRITER.md) (B2B GTM Copywriter Specification)
* [`GTM_10_ACTOR_DISTRIBUTION_KIT.md`](./GTM_10_ACTOR_DISTRIBUTION_KIT.md) (10-Actor Launch Calendar & Agency Whale Outreach Kit)
* [`BRAND_KIT_MANIFEST.md`](./BRAND_KIT_MANIFEST.md) (Brand Kit & Public CDN Asset Manifest)
* [`EXAMPLE_DATASETS_VERIFICATION_REPORT.md`](./EXAMPLE_DATASETS_VERIFICATION_REPORT.md) (Sample Datasets & PNG Datatable Telemetry Report)
* [`examples/clay-http-api-recipes.md`](./examples/clay-http-api-recipes.md) (Clay HTTP API Integration Recipes)
* [`examples/n8n-global-10-actor-fan-in.json`](./examples/n8n-global-10-actor-fan-in.json) (10-Actor Monday Fan-In n8n Workflow)
* [`X_LAUNCH_SAMPLES.md`](./X_LAUNCH_SAMPLES.md) (Live Cloud Verification & Launch Samples)

---

## High-Volume & Agentic Execution: Apify Store (PPE) vs. Bytewells Flat Rental (`8,300 rows/mo` Break-Even)

| Execution Tier | Best For | Pricing Model | Monthly Break-Even Volume | Autonomous Agent / MCP Support |
| :--- | :--- | :--- | :--- | :--- |
| **Apify Store (Pay-Per-Event)** | On-demand Clay tables, weekly delta schedules & low-to-mid volume | `$0.002` basic / `$0.008` verified named email (`$0.003` / `$0.009` on ICP Aggregator) | **`< 8,300 enriched rows/mo`** | Native `@apify/actors-mcp-server` |
| **Bytewells (`bytewells.com`)** | High-volume agency pipelines, enterprise revops & multi-client agency teams | **`$49/mo` Flat Rental** or **`$199–$249/mo` Agency License** (`$0.00` per-event fee) | **`>= 8,300 enriched rows/mo`** | Native **HTTP 402 Agentic Auto-Buy** (`x402` / Bytewells MCP) |

---

## Sample Output Overview (Live-Verified Ground-Truth Leads)

The following table displays live-verified StepStone DACH job signals paired with verified company contacts from `marketing/sample-leads/dach-verified-leads.csv`:

| Company | Market | Signal / Role | Discovered Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :---: | :--- | :--- | :--- | :--- | :--- |
| **OXEA GmbH** | `DE` | `Business Development Manager Performance Chemicals EU (m/w/d)` | `johan.rinckhout@oxea.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **ElektroPhysik Dr. Steingroever GmbH & Co. KG** | `DE` | `Vertriebsingenieur (m/w/d) Wirtschaftsingenieurwesen` | `frank.osthoff@elektrophysik.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **achelos GmbH** | `DE` | `Sales Manager Cybersecurity (m|w|d)` | `carola.schwarzenberg@achelos.de` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Hauff-Technik GmbH & Co. KG** | `DE` | `Area Sales Manager (w/m/d) Vertriebsregion: westliches NRW` | `michal.rink@hauff-technik.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Magnet-Schultz GmbH & Co. KG** | `DE` | `Vertriebsingenieur Truck (gn*)` | `marco.barton@magnet-schultz.de` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Aktiv Assekuranz Makler GmbH** | `DE` | `Key Account Manager (m/w/d) industrielle Versicherung` | `michael.schreier@aktiv-assekuranz.de` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |

---

## Public Showcase: Apify MCP Server Configuration

Configure Claude Desktop (`claude_desktop_config.json`) or Cursor (`mcp.json`) to invoke all Aperture Actors autonomously:

```json
{
  "mcpServers": {
    "apify": {
      "command": "npx",
      "args": [
        "-y",
        "@apify/actors-mcp-server",
        "--actors",
        "aperture/stepstone-dach-buying-signal-scraper,aperture/seek-anz-buying-signal-scraper,aperture/france-buying-signal-scraper,aperture/eu-uk-procurement-award-signal-scraper,aperture/eu-uk-executive-incorporation-signal-scraper,aperture/b2b-buying-signal-icp-aggregator"
      ],
      "env": {
        "APIFY_TOKEN": "YOUR_APIFY_TOKEN"
      }
    }
  }
}
```
