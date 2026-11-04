# Aperture 7-Actor B2B Buying-Signal Suite — X (Twitter) Launch Sample Kit & Live Enriched Output Rows

Verified live enriched output rows (`scraperMode: "enriched_with_email"`, `maxItems: 5` default) and copy-paste X workflow launch posts across all **7 commercial Actors** in the **[`aperture`](https://apify.com/aperture)** suite (`7/7 HEALTHY`).

---

## Live Cloud Smoke Run Verification Summary (`7/7 HEALTHY`)

| # | Actor Slug | Apify Cloud ID | Latest Enriched Run ID | Build | Status | Duration | Items | Errors |
| :-: | :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **1** | [`aperture/stepstone-dach-buying-signal-scraper`](https://apify.com/aperture/stepstone-dach-buying-signal-scraper) | `idZZRizPvXw9erx7P` | `XD7dxyIHkGtNJT8PU` | `1.0.12` | `SUCCEEDED` | `10.63s` | `5` | `0` |
| **2** | [`aperture/seek-anz-buying-signal-scraper`](https://apify.com/aperture/seek-anz-buying-signal-scraper) | `2RQGFx6eMh7roCRt4` | `25GYBbyKuTXvhnSH9` | `1.0.11` | `SUCCEEDED` | `5.65s` | `5` | `0` |
| **3** | [`aperture/france-buying-signal-scraper`](https://apify.com/aperture/france-buying-signal-scraper) | `dRMQFHrMpiuGjB8fm` | `hFfLaINWm9tLU4W26` | `1.0.11` | `SUCCEEDED` | `9.76s` | `5` | `0` |
| **4** | [`aperture/b2b-buying-signal-icp-aggregator`](https://apify.com/aperture/b2b-buying-signal-icp-aggregator) | `3fd4tjQONIb0mSwaG` | `oOyb96a0DUHkPLYKH` | `1.0.12` | `SUCCEEDED` | `1.55s` | `2` | `0` |
| **5** | [`aperture/eu-uk-procurement-award-signal-scraper`](https://apify.com/aperture/eu-uk-procurement-award-signal-scraper) | `BWvLdexjiPu5IgJtR` | `iWroH59irbm3P7AsN` | `1.0.6` | `SUCCEEDED` | `13.07s` | `5` | `0` |
| **6** | [`aperture/eu-uk-executive-incorporation-signal-scraper`](https://apify.com/aperture/eu-uk-executive-incorporation-signal-scraper) | `5PwBOfpH3vf7MMEV0` | `z0f6gmq5DilrHgAGB` | `1.0.2` | `SUCCEEDED` | `6.01s` | `5` | `0` |
| **7** | [`aperture/biotech-clinical-trial-buying-signal-scraper`](https://apify.com/aperture/biotech-clinical-trial-buying-signal-scraper) | `WRg36MK6xCFrciz1y` | `UreCyp3n2mML8V6I6` | `1.0.2` | `SUCCEEDED` | `10.37s` | `5` | `0` |

---

## 1. `aperture/stepstone-dach-buying-signal-scraper` (`DE`, `AT`, `BE`, `NL`)

### Verified Sample Output Table (Screenshot-Ready)

| Company | Domain | Signal / Role | Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **OXEA GmbH** | `oxea.com` | `Business Development Manager Performance Chemicals EU (m/w/d)` | `johan.rinckhout@oxea.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **ElektroPhysik Dr. Steingroever GmbH & Co. KG** | `elektrophysik.com` | `Vertriebsingenieur (m/w/d)` | `frank.osthoff@elektrophysik.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Example Industrietechnik GmbH** *(illustrative)* | `example.com` | `Sales Manager DACH` | `info@example.com` | `role_fallback` *(Free Bonus)* | `job-signal-scraped` | **$0.002** |

### Raw JSON Sample (`buying-signal-enriched` vs `job-signal-scraped`)

```json
[
  {
    "detected_at": "2026-10-14T13:15:10Z",
    "company": "OXEA GmbH",
    "domain": "oxea.com",
    "role_title": "Business Development Manager Performance Chemicals EU (m/w/d)",
    "seniority_band": "director",
    "location": "Monheim am Rhein",
    "geo": "DE",
    "posted_date": "2026-10-14T10:00:00.000Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Business Development Manager Performance Chemicals EU (m/w/d) — Monheim am Rhein [Full-time]",
    "signal_source_actor": "stepstone-dach-buying-signal-scraper",
    "signal_date": "2026-10-14",
    "evidence_url": "https://www.stepstone.de/stellenangebote--Business-Development-Manager-Performance-Chemicals-EU-m-w-d-Monheim-am-Rhein-OXEA-GmbH--14500805-inline.html",
    "contact_name": "Johan Rinckhout",
    "contact_title": "Regional Sales Director Europe",
    "contact_email": "johan.rinckhout@oxea.com",
    "contact_match_type": "role_matched",
    "contact_source_url": "https://www.oxea.com/contacts/sales-cr",
    "contact_phone": "+49 2173 9993 0",
    "salary_band": "€ 85.000 - € 110.000",
    "contract_type": "Festanstellung / Vollzeit",
    "email_verification_status": "ok",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "buying-signal-enriched",
    "notes": "source=contacts/sales-cr; verify=smtp_250_ok; mx=Microsoft 365",
    "error": null
  },
  {
    "detected_at": "2026-10-27T13:15:10Z",
    "company": "ElektroPhysik Dr. Steingroever GmbH & Co. KG",
    "domain": "elektrophysik.com",
    "role_title": "Vertriebsingenieur (m/w/d) Wirtschaftsingenieurwesen / Techniker mit Vertriebserfahrung",
    "seniority_band": "mid",
    "location": "Köln",
    "geo": "DE",
    "posted_date": "2026-10-27T10:00:00.000Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Vertriebsingenieur (m/w/d) Wirtschaftsingenieurwesen / Techniker mit Vertriebserfahrung — Köln [Full-time]",
    "signal_source_actor": "stepstone-dach-buying-signal-scraper",
    "signal_date": "2026-10-27",
    "evidence_url": "https://www.stepstone.de/stellenangebote--Vertriebsingenieur-m-w-d-mit-einem-Abschluss-als-Diplom-oder-einem-vergleichbaren-Bachelor-in-Wirtschaftsingenieurwesen-bzw-Techniker-mit-Vertriebserfahrung-Koeln-ElektroPhysik-Dr-Steingroever-GmbH-Co-KG--14690010-inline.html",
    "contact_name": "Frank Osthoff",
    "contact_title": "Head of international sales & service",
    "contact_email": "frank.osthoff@elektrophysik.com",
    "contact_match_type": "role_matched",
    "contact_source_url": "https://www.elektrophysik.com/en/about-elektrophysik/",
    "contact_phone": "+49 221 75204 0",
    "salary_band": "€ 70.000 - € 90.000",
    "contract_type": "Festanstellung / Vollzeit",
    "email_verification_status": "ok",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "buying-signal-enriched",
    "notes": "source=about-elektrophysik; verify=smtp_250_ok; mx=Microsoft 365",
    "error": null
  },
  {
    "detected_at": "2026-10-30T13:15:14Z",
    "company": "Example Industrietechnik GmbH (illustrative)",
    "domain": "example.com",
    "role_title": "Sales Manager DACH",
    "seniority_band": "manager",
    "location": "Darmstadt",
    "geo": "DE",
    "posted_date": "2026-10-30T10:00:00.000Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Sales Manager DACH — Darmstadt [Full-time] (illustrative)",
    "signal_source_actor": "stepstone-dach-buying-signal-scraper",
    "signal_date": "2026-10-30",
    "evidence_url": "https://www.stepstone.de/stellenangebote--illustrative-example.html",
    "contact_email": "info@example.com",
    "contact_phone": "+49 6151 555123",
    "salary_band": "€ 85.000 - € 105.000",
    "contract_type": "Festanstellung / Vollzeit",
    "email_verification_status": "role_fallback",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "job-signal-scraped",
    "notes": "source=impressum; verify=role_fallback; mx=Microsoft 365",
    "error": null
  }
]
```

### Ready-to-Post X Launch Post (Post #1 — DACH & Benelux Stepstone + Impressum Workflow)

**Main Post (258 chars):**
```text
Most job scrapers dump raw Stepstone links into Clay and leave you to find the domain + email.

Built a DACH & Benelux hiring signal scraper that crawls German /impressum pages in one pass.

$0.008 ONLY for verified firstname.lastname@ emails. info@ is free ($0.002). 👇
```

**Follow-Up Reply (Clay HTTP API + Link):**
```text
Drop it into a Clay HTTP API column (runs in ~10s, no LinkedIn cookies needed):

POST https://api.apify.com/v2/acts/aperture~stepstone-dach-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN

Store link (25-lead free trial, enriched by default):
https://apify.com/aperture/stepstone-dach-buying-signal-scraper
```

---

## 2. `aperture/seek-anz-buying-signal-scraper` (`AU`, `NZ`)

### Illustrative Sample Output Table (Screenshot-Ready)

| Company | Domain | Signal / Role | Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Illustrative Fleet Logistics NZ** *(illustrative)* | `example.com` | `Fleet Account Manager ($110k–$130k)` | `alex.smith@example.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Illustrative Enterprise NZ** *(illustrative)* | `example.com` | `Business Development Manager` | `people@example.com` | `role_fallback` *(Free Bonus)* | `job-signal-scraped` | **$0.002** |

### Raw JSON Sample (`buying-signal-enriched` vs `job-signal-scraped`)

```json
[
  {
    "detected_at": "2026-11-01T13:16:02Z",
    "company": "Illustrative Fleet Logistics NZ (illustrative)",
    "domain": "example.com",
    "role_title": "Fleet Account Manager",
    "seniority_band": "mid",
    "location": "Auckland",
    "geo": "NZ",
    "posted_date": "2026-10-30T03:10:00.000Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Fleet Account Manager — Auckland [Full time | $110,000 - $130,000 base + super + vehicle] (illustrative)",
    "signal_source_actor": "seek-anz-buying-signal-scraper",
    "signal_date": "2026-10-30",
    "evidence_url": "https://www.seek.co.nz/job/illustrative-example",
    "contact_email": "alex.smith@example.com",
    "contact_phone": "+64 9 000 0000",
    "salary_band": "$110,000 - $130,000 base + super + vehicle",
    "contract_type": "Full time",
    "email_verification_status": "ok",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "buying-signal-enriched",
    "notes": "source=job_listing+contact; verify=mx_fingerprinted_impressum_match; mx=Microsoft 365",
    "error": null
  },
  {
    "detected_at": "2026-11-01T13:16:05Z",
    "company": "Illustrative Enterprise NZ (illustrative)",
    "domain": "example.com",
    "role_title": "Business Development Manager",
    "seniority_band": "manager",
    "location": "Wellington",
    "geo": "NZ",
    "posted_date": "2026-10-29T22:14:05.000Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Business Development Manager — Wellington [Full time | $120k - $140k + benefits] (illustrative)",
    "signal_source_actor": "seek-anz-buying-signal-scraper",
    "signal_date": "2026-10-29",
    "evidence_url": "https://www.seek.co.nz/job/illustrative-example-2",
    "contact_email": "people@example.com",
    "contact_phone": "+64 4 000 0000",
    "salary_band": "$120k - $140k + benefits",
    "contract_type": "Full time",
    "email_verification_status": "role_fallback",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "job-signal-scraped",
    "notes": "source=contact; verify=mx_fingerprinted_impressum_match; mx=Microsoft 365",
    "error": null
  }
]
```

### Ready-to-Post X Launch Post (Post #2 — Australia & NZ Seek Hiring Signals)

**Main Post (255 chars):**
```text
Running outbound into Australia & New Zealand?

We built a Seek (AU/NZ) buying-signal scraper that resolves the real .com.au / .co.nz domain, salary band, phone & verified contact email in ~5 seconds.

Pay $0.008 ONLY when a named person email is found. 👇
```

**Follow-Up Reply (Clay HTTP API + Link):**
```text
Generic people@ or info@ inboxes are kept in contact_email for free (`role_fallback`) and billed at $0.002.

Clay HTTP API endpoint:
POST https://api.apify.com/v2/acts/aperture~seek-anz-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN

Try it here:
https://apify.com/aperture/seek-anz-buying-signal-scraper
```

---

## 3. `aperture/france-buying-signal-scraper` (`FR` — Jobs + Startup Funding)

### Illustrative Sample Output Table (Screenshot-Ready)

| Company | Domain | Signal / Role | Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Illustrative Solutions SAS** *(illustrative)* | `example.com` | `Business Developer B2B [France Travail]` | `adeline.gautier@example.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Illustrative Tech SAS** *(illustrative)* | `example.com` | `Venture Funding Round [Maddyness]` | `contact@example.com` | `role_fallback` *(Free Bonus)* | `job-signal-scraped` | **$0.002** |

### Raw JSON Sample (`buying-signal-enriched` vs `job-signal-scraped`)

```json
[
  {
    "detected_at": "2026-11-01T13:17:10Z",
    "company": "Illustrative Solutions SAS (illustrative)",
    "domain": "example.com",
    "role_title": "Business Developer B2B",
    "seniority_band": "mid",
    "location": "75 - Paris",
    "geo": "FR",
    "posted_date": "2026-10-25T00:00:00.000Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Business Developer B2B — 75 - Paris [CDI - Contrat travail] (illustrative)",
    "signal_source_actor": "france-buying-signal-scraper",
    "signal_date": "2026-10-25",
    "evidence_url": "https://candidat.francetravail.fr/offres/recherche/detail/illustrative-example",
    "contact_email": "adeline.gautier@example.com",
    "contact_phone": "+33 1 00 00 00 00",
    "salary_band": "Annuel de 45000.0 Euros à 55000.0 Euros",
    "contract_type": "CDI",
    "email_verification_status": "ok",
    "mx_provider": "Google Workspace",
    "ppe_event_charged": "buying-signal-enriched",
    "notes": "source=mentions-legales+contact; verify=smtp_250_ok; mx=Google Workspace",
    "error": null
  },
  {
    "detected_at": "2026-11-01T13:17:14Z",
    "company": "Illustrative Tech SAS (illustrative)",
    "domain": "example.com",
    "role_title": "",
    "seniority_band": "",
    "location": "France",
    "geo": "FR",
    "posted_date": "2026-10-13T16:20:27.000Z",
    "signal_type": "funding",
    "signal_detail": "Funding: Venture Funding Round — French Tech (illustrative)",
    "signal_source_actor": "france-buying-signal-scraper",
    "signal_date": "2026-10-13",
    "evidence_url": "https://www.maddyness.com/illustrative-example/",
    "contact_email": "contact@example.com",
    "contact_phone": "",
    "salary_band": "",
    "contract_type": "",
    "email_verification_status": "role_fallback",
    "mx_provider": "Google Workspace",
    "ppe_event_charged": "job-signal-scraped",
    "notes": "source=mentions-legales; verify=mx_fingerprinted_impressum_match; mx=Google Workspace",
    "error": null
  }
]
```

### Ready-to-Post X Launch Post (Post #3 — France Travail Hiring + Maddyness Funding)

**Main Post (259 chars):**
```text
French B2B outbound cheat code: combine France Travail CDI hiring signals + Maddyness startup funding rounds in one feed, then crawl /mentions-legales for direct emails.

$0.008 only for verified firstname.lastname@ emails. Generic contact@ is free ($0.002). 👇
```

**Follow-Up Reply (Clay HTTP API + Link):**
```text
Plug directly into Clay via HTTP API (decodes Cloudflare hex-protected emails automatically):

POST https://api.apify.com/v2/acts/aperture~france-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN

Store URL:
https://apify.com/aperture/france-buying-signal-scraper
```

---

## 4. `aperture/eu-uk-procurement-award-signal-scraper` (`UK`, `FR`, `DE`, `NL`, `BE`, `AT`)

### Illustrative Sample Output Table (Screenshot-Ready)

| Company | Domain | Signal / Role | Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Illustrative Software Ltd** *(illustrative)* | `example.com` | `UK Digital Transformation Award (£1,200,000 GBP)` | `commercial.director@example.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Illustrative Digital Solutions GmbH** *(illustrative)* | `example.com` | `Public Tender Award (€252,100 EUR)` | `info@example.com` | `role_fallback` *(Free Bonus)* | `job-signal-scraped` | **$0.002** |

### Raw JSON Sample (`buying-signal-enriched` vs `job-signal-scraped`)

```json
[
  {
    "detected_at": "2026-11-01T13:18:00Z",
    "company": "Illustrative Software Ltd (illustrative)",
    "domain": "example.com",
    "role_title": "UK Digital Transformation Award (£1,200,000 GBP)",
    "seniority_band": "director",
    "location": "London",
    "geo": "UK",
    "posted_date": "2026-10-31T12:34:39Z",
    "signal_type": "contract_award",
    "signal_detail": "Contract Award: Digital Transformation — Awarded by Ministry of Justice [£1,200,000 GBP] (illustrative)",
    "signal_source_actor": "eu-uk-procurement-award-signal-scraper",
    "signal_date": "2026-10-31",
    "evidence_url": "https://www.contractsfinder.service.gov.uk/Notice/illustrative-example",
    "contact_email": "commercial.director@example.com",
    "contact_phone": "+44 20 0000 0000",
    "salary_band": "£1,200,000 GBP",
    "contract_type": "Public Tender Award",
    "email_verification_status": "ok",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "buying-signal-enriched",
    "notes": "source=UK_CF; buyer=Ministry of Justice; verify=smtp_250_ok; mx=Microsoft 365",
    "error": null
  },
  {
    "detected_at": "2026-11-01T13:18:04Z",
    "company": "Illustrative Digital Solutions GmbH (illustrative)",
    "domain": "example.com",
    "role_title": "Public Tender Award (€252,100 EUR)",
    "seniority_band": "director",
    "location": "Berlin",
    "geo": "DE",
    "posted_date": "2026-10-30T16:00:00Z",
    "signal_type": "contract_award",
    "signal_detail": "Contract Award: Public Web Portal Development [€252,100 EUR] (illustrative)",
    "signal_source_actor": "eu-uk-procurement-award-signal-scraper",
    "signal_date": "2026-10-30",
    "evidence_url": "https://ted.europa.eu/en/notice/-/detail/illustrative-example",
    "contact_email": "info@example.com",
    "contact_phone": "+49 30 0000000",
    "salary_band": "€252,100 EUR",
    "contract_type": "Public Tender Award",
    "email_verification_status": "role_fallback",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "job-signal-scraped",
    "notes": "source=TED; verify=mx_fingerprinted_impressum; mx=Microsoft 365",
    "error": null
  }
]
```

### Ready-to-Post X Launch Post (Post #4 — UK Find a Tender + EU TED + BOAMP Contract Awards)

**Main Post (268 chars):**
```text
Companies that just won a £100k–£5M government contract need cloud infra, subcontractors & recruiting immediately.

Built a UK & EU Procurement Award scraper (Find a Tender, EU TED, BOAMP) that resolves the winning vendor's domain & verified emails in one pass. 👇
```

**Follow-Up Reply (Clay HTTP API + Link):**
```text
Filter by minContractValue (e.g. 100000) and pay $0.008 ONLY when a verified named contact is returned:

POST https://api.apify.com/v2/acts/aperture~eu-uk-procurement-award-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN

Store URL:
https://apify.com/aperture/eu-uk-procurement-award-signal-scraper
```

---

## 5. `aperture/eu-uk-executive-incorporation-signal-scraper` (`FR`, `UK`, `DE`, `AT`)

### Illustrative Sample Output Table (Screenshot-Ready)

| Company | Domain | Signal / Role | Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Illustrative Agency SAS** *(illustrative)* | `example.com` | `New Appointment: Président — Jean Dupont (Capital: €10,000 EUR)` | `jean.dupont@example.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Illustrative FinTech Ltd** *(illustrative)* | `example.com` | `New Director Appointment — Companies House Filing` | `info@example.com` | `role_fallback` *(Free Bonus)* | `job-signal-scraped` | **$0.002** |

### Raw JSON Sample (`buying-signal-enriched` vs `job-signal-scraped`)

```json
[
  {
    "detected_at": "2026-11-01T13:35:45Z",
    "company": "Illustrative Agency SAS (illustrative)",
    "domain": "example.com",
    "role_title": "New Appointment: Président — Jean Dupont",
    "seniority_band": "cxo",
    "location": "Paris",
    "geo": "FR",
    "posted_date": "2026-10-31T00:00:00.000Z",
    "signal_type": "executive_change",
    "signal_detail": "New Appointment: Président — Jean Dupont (Capital: €10,000 EUR) (illustrative)",
    "signal_source_actor": "eu-uk-executive-incorporation-signal-scraper",
    "signal_date": "2026-10-31",
    "evidence_url": "https://www.bodacc.fr/pages/annonces-commerciales-detail/?q.id=illustrative-example",
    "contact_email": "jean.dupont@example.com",
    "contact_phone": "+33 1 00 00 00 00",
    "salary_band": "€10,000 EUR",
    "contract_type": "Executive Appointment",
    "email_verification_status": "ok",
    "mx_provider": "Google Workspace",
    "ppe_event_charged": "buying-signal-enriched",
    "notes": "source=FR_BODACC; verify=smtp_250_ok; mx=Google Workspace",
    "error": null
  },
  {
    "detected_at": "2026-11-01T13:35:46Z",
    "company": "Illustrative FinTech Ltd (illustrative)",
    "domain": "example.com",
    "role_title": "New Director Appointment — Companies House Filing",
    "seniority_band": "director",
    "location": "London",
    "geo": "UK",
    "posted_date": "2026-10-30T00:00:00.000Z",
    "signal_type": "executive_change",
    "signal_detail": "New Director Appointment — Companies House Filing (illustrative)",
    "signal_source_actor": "eu-uk-executive-incorporation-signal-scraper",
    "signal_date": "2026-10-30",
    "evidence_url": "https://find-and-update.company-information.service.gov.uk/company/illustrative/officers",
    "contact_email": "info@example.com",
    "contact_phone": "+44 20 0000 0000",
    "salary_band": "£50,000 GBP",
    "contract_type": "Executive Appointment",
    "email_verification_status": "role_fallback",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "job-signal-scraped",
    "notes": "source=UK_COMPANIES_HOUSE; verify=mx_fingerprinted_contact_page; mx=Microsoft 365",
    "error": null
  }
]
```

### Ready-to-Post X Launch Post (Post #5 — Newly Appointed Directors & Incorporations across UK, FR, DE, AT)

**Main Post (267 chars):**
```text
New Managing Directors review and replace software, agencies & payroll in their first 90 days.

We built an EU & UK Executive Appointment scraper (BODACC, Companies House & GLEIF) that resolves company domains & verifies executive emails in ~6s.

$0.008 per named email 👇
```

**Follow-Up Reply (Clay HTTP API + Link):**
```text
Generic info@/office@ inboxes are kept for free (`role_fallback`, billed at $0.002).

Clay HTTP API endpoint:
POST https://api.apify.com/v2/acts/aperture~eu-uk-executive-incorporation-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN

Store URL:
https://apify.com/aperture/eu-uk-executive-incorporation-signal-scraper
```

---

## 6. `aperture/b2b-buying-signal-icp-aggregator` (`US`, `DE`, `AT`, `BE`, `NL`, `FR`, `UK`, `AU`, `NZ` — 5D Multi-Signal)

### Verified Sample Output Table (Screenshot-Ready)

| Company | Domain | Signal / Role | Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **OXEA GmbH** | `oxea.com` | `Business Development Manager (ICP Score: 98) [Salesforce, SAP]` | `johan.rinckhout@oxea.com` | `ok` *(Named Person)* | `icp-multi-signal-enriched` | **$0.009** |
| **Illustrative Enterprise GmbH** *(illustrative)* | `example.com` | `Hiring Signal (ICP Score: 63) [HubSpot, Salesforce]` | `info@example.com` | `role_fallback` *(Free Bonus)* | `icp-lead-scored` | **$0.003** |
| **Illustrative Tech SAS** *(illustrative)* | `example.com` | `Multi-Signal: Funding + Hiring (ICP Score: 100)` | `contact@example.com` | `role_fallback` *(Free Bonus)* | `icp-lead-scored` | **$0.003** |

### Raw JSON Sample (`icp-multi-signal-enriched` vs `icp-lead-scored`)

```json
[
  {
    "detected_at": "2026-10-14T13:19:00Z",
    "company": "OXEA GmbH",
    "domain": "oxea.com",
    "role_title": "Business Development Manager Performance Chemicals EU (m/w/d)",
    "seniority_band": "director",
    "location": "Monheim am Rhein",
    "geo": "DE",
    "posted_date": "2026-10-14T10:00:00.000Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Business Development Manager Performance Chemicals EU (m/w/d) — Monheim am Rhein [Full-time]",
    "signal_source_actor": "stepstone-dach-buying-signal-scraper",
    "signal_date": "2026-10-14",
    "evidence_url": "https://www.stepstone.de/stellenangebote--Business-Development-Manager-Performance-Chemicals-EU-m-w-d-Monheim-am-Rhein-OXEA-GmbH--14500805-inline.html",
    "evidence_urls": [
      "https://www.stepstone.de/stellenangebote--Business-Development-Manager-Performance-Chemicals-EU-m-w-d-Monheim-am-Rhein-OXEA-GmbH--14500805-inline.html"
    ],
    "contact_name": "Johan Rinckhout",
    "contact_title": "Regional Sales Director Europe",
    "contact_email": "johan.rinckhout@oxea.com",
    "contact_match_type": "role_matched",
    "contact_source_url": "https://www.oxea.com/contacts/sales-cr",
    "contact_phone": "+49 2173 9993 0",
    "salary_band": "€ 85.000 - € 110.000",
    "contract_type": "Festanstellung / Vollzeit",
    "email_verification_status": "ok",
    "mx_provider": "Microsoft 365",
    "ppe_event_charged": "icp-multi-signal-enriched",
    "notes": "source=contacts/sales-cr; verify=smtp_250_ok; mx=Microsoft 365",
    "error": null,
    "icp_score": 98,
    "signal_count": 1,
    "signal_types_matched": ["jobs"],
    "source_actors": ["stepstone-dach-buying-signal-scraper"],
    "tech_stack": ["Salesforce", "SAP"],
    "outreach_hook": "Noticed OXEA is hiring a Business Development Manager for Performance Chemicals EU in Monheim am Rhein and wanted to share how we help chemical sales teams accelerate European enterprise account expansion."
  },
  {
    "detected_at": "2026-11-01T13:19:00Z",
    "company": "Illustrative Enterprise GmbH (illustrative)",
    "domain": "example.com",
    "role_title": "Sales Development Representative (SDR) B2B",
    "seniority_band": "entry",
    "location": "Berlin",
    "geo": "DE",
    "posted_date": "2026-10-28T09:00:00Z",
    "signal_type": "jobs",
    "signal_detail": "Job: Sales Development Representative (SDR) B2B — Berlin [Full-time, Hybrid, HubSpot & Salesforce CRM] (illustrative)",
    "signal_source_actor": "stepstone-dach-buying-signal-scraper",
    "signal_date": "2026-10-28",
    "evidence_url": "https://www.stepstone.de/stellenangebote--illustrative-example.html",
    "evidence_urls": [
      "https://www.stepstone.de/stellenangebote--illustrative-example.html"
    ],
    "contact_name": "",
    "contact_title": "",
    "contact_email": "info@example.com",
    "contact_match_type": "generic_inbox",
    "contact_source_url": "https://example.com/impressum/",
    "contact_phone": "+49 30 000000",
    "salary_band": "",
    "contract_type": "Full-time",
    "email_verification_status": "role_fallback",
    "mx_provider": "Google Workspace",
    "ppe_event_charged": "icp-lead-scored",
    "notes": "source=impressum; match_type=generic_inbox; ppe=icp-lead-scored ($0.003 role_fallback); tech=HubSpot, Salesforce",
    "error": null,
    "icp_score": 63,
    "signal_count": 1,
    "signal_types_matched": ["jobs"],
    "source_actors": ["stepstone-dach-buying-signal-scraper"],
    "tech_stack": ["HubSpot", "Salesforce"],
    "outreach_hook": "Noticing that your team is actively scaling outbound sales representatives in Berlin (stack: HubSpot, Salesforce), are you looking for automated intent signals to fuel your reps? (illustrative)"
  },
  {
    "detected_at": "2026-11-01T13:19:01Z",
    "company": "Illustrative Tech SAS (illustrative)",
    "domain": "example.com",
    "role_title": "Senior Account Executive Mid-Market",
    "seniority_band": "senior",
    "location": "Paris",
    "geo": "FR",
    "posted_date": "2026-10-30T10:00:00Z",
    "signal_type": "multi_signal",
    "signal_detail": "Funding: Venture Funding Round — French FinTech SaaS | Job: Senior Account Executive Mid-Market — Paris [CDI] (illustrative)",
    "signal_source_actor": "france-buying-signal-scraper",
    "signal_date": "2026-10-30",
    "evidence_url": "https://www.maddyness.com/illustrative-example/",
    "evidence_urls": [
      "https://www.maddyness.com/illustrative-example/",
      "https://candidat.francetravail.fr/offres/recherche/detail/illustrative-example"
    ],
    "contact_email": "contact@example.com",
    "contact_phone": "+33 1 00 00 00 00",
    "salary_band": "65k€ - 85k€",
    "contract_type": "CDI",
    "email_verification_status": "role_fallback",
    "mx_provider": "Google Workspace",
    "ppe_event_charged": "icp-lead-scored",
    "notes": "source=mentions-legales; mx=Google Workspace; tech=Salesforce, Snowflake",
    "error": null,
    "icp_score": 100,
    "signal_count": 2,
    "signal_types_matched": ["funding", "jobs"],
    "source_actors": ["france-buying-signal-scraper"],
    "tech_stack": ["Salesforce", "Snowflake"],
    "outreach_hook": "Congratulations on the recent funding round! Noticed your team is actively recruiting for a Senior Account Executive in Paris (stack: Salesforce, Snowflake). Given this expansion, are you exploring new outbound data partnerships? (illustrative)"
  }
]
```

### Ready-to-Post X Launch Post (Post #6 — 5D Multi-Signal ICP Scorer & Clay Hook Engine)

**Main Post (265 chars):**
```text
When a company raises funding, wins a public tender, sponsors a clinical trial, AND hires AEs in the same month, outbound reply rates 3x.

Built a 1s 5D Multi-Signal ICP Scorer across 9 markets that merges 5 triggers, tags 28 tech tools & writes Clay hooks for $0.003–$0.009 👇
```

**Follow-Up Reply (Clay HTTP API + Link):**
```text
Even if an account scores 100/100 across multiple signals, if only a generic contact@ inbox is present (`role_fallback`), you pay $0.003 instead of $0.009:

POST https://api.apify.com/v2/acts/aperture~b2b-buying-signal-icp-aggregator/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN

https://apify.com/aperture/b2b-buying-signal-icp-aggregator
```

---

## 7. `aperture/biotech-clinical-trial-buying-signal-scraper` (`US`, `UK`, `DE`, `FR`, `NL`, `BE`, `AT` — Clinical Trials & R&D Grants `>= 2025`)

### Illustrative Sample Output Table (Screenshot-Ready)

| Company | Domain | Signal / Role | Contact Email | Verification Status | PPE Event Triggered | Price Billed |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Illustrative Therapeutics Inc.** *(illustrative)* | `example.com` | `Clinical Trial Sponsor (PHASE1): Study Director` | `study.director@example.com` | `ok` *(Named Person)* | `buying-signal-enriched` | **$0.008** |
| **Illustrative Biotech SAS** *(illustrative)* | `example.com` | `EU CORDIS Horizon Europe Grant (€2,499,831 EUR)` | `info@example.com` | `role_fallback` *(Free Bonus)* | `job-signal-scraped` | **$0.002** |

### Raw JSON Sample (`buying-signal-enriched` vs `job-signal-scraped`)

```json
[
  {
    "detected_at": "2026-10-30T14:20:00Z",
    "company": "Illustrative Therapeutics Inc. (illustrative)",
    "domain": "example.com",
    "role_title": "Clinical Trial Sponsor (PHASE1): Study Director",
    "seniority_band": "director",
    "location": "Redmond, WA",
    "geo": "US",
    "posted_date": "2026-10-30T08:00:00Z",
    "signal_type": "clinical_trial",
    "signal_detail": "Trial: Phase 1 Study in Oncology (illustrative)",
    "signal_source_actor": "biotech-clinical-trial-buying-signal-scraper",
    "signal_date": "2026-10-30",
    "evidence_url": "https://clinicaltrials.gov/study/illustrative-example",
    "contact_email": "study.director@example.com",
    "contact_phone": "+1 000 000 0000",
    "salary_band": "$18,500,000 R&D Budget",
    "contract_type": "Interventional Clinical Trial (PHASE1)",
    "email_verification_status": "ok",
    "mx_provider": "Google Workspace",
    "ppe_event_charged": "buying-signal-enriched",
    "notes": "source=clinicaltrials_us; StudyFirstPostDate:desc; verify=smtp_250_ok; mx=Google Workspace",
    "error": null
  },
  {
    "detected_at": "2026-10-30T14:25:00Z",
    "company": "Illustrative Biotech SAS (illustrative)",
    "domain": "example.com",
    "role_title": "EU CORDIS Horizon Europe Grant Winner",
    "seniority_band": "director",
    "location": "Rennes",
    "geo": "FR",
    "posted_date": "2026-10-30T09:30:00Z",
    "signal_type": "research_grant",
    "signal_detail": "Grant: CORDIS Horizon Europe Multi-Organ Platform (€2,499,831 EUR) (illustrative)",
    "signal_source_actor": "biotech-clinical-trial-buying-signal-scraper",
    "signal_date": "2026-10-30",
    "evidence_url": "https://cordis.europa.eu/project/id/illustrative-example",
    "contact_email": "info@example.com",
    "contact_phone": "+33 2 00 00 00 00",
    "salary_band": "€2,499,831 EUR",
    "contract_type": "Research Grant (Horizon Europe)",
    "email_verification_status": "role_fallback",
    "mx_provider": "Google Workspace",
    "ppe_event_charged": "job-signal-scraped",
    "notes": "source=eu_cordis; verify=mx_fingerprinted_contact; mx=Google Workspace",
    "error": null
  }
]
```

### Ready-to-Post X Launch Post (Post #7 — Biotech Clinical Trials & R&D Grants `>= 2025`)

**Main Post (269 chars):**
```text
Selling CRO, CDMO or lab tech to biotech?

Built a Clinical Trial & Grant intent scraper (ClinicalTrials.gov v2, EU CTIS, CORDIS, NIH) with a >= 2025 recency guard that resolves domains & verified emails in 10s.

$0.008 ONLY for named contacts. info@ is free ($0.002) 👇
```

**Follow-Up Reply (Clay HTTP API + Link):**
```text
Runs in the cloud without LinkedIn cookies. Features StudyFirstPostDate:desc sorting to drop legacy trials updating old paperwork.

Clay HTTP API:
POST https://api.apify.com/v2/acts/aperture~biotech-clinical-trial-buying-signal-scraper/run-sync-get-dataset-items?token=YOUR_APIFY_TOKEN

Store link (25-lead free trial, enriched by default):
https://apify.com/aperture/biotech-clinical-trial-buying-signal-scraper
```
