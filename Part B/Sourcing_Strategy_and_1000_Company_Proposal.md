# Part B: Sourcing Strategy + 1000-Company Scale-Up Proposal
### DeepThought Business Analytics Internship | Bengaluru Precision Auto & Aerospace | May 2026

---

## Question 1: Sourcing Methods — How Else Would You Find Federer Companies Across India?

Beyond Google search, here are the specific sources I would use, why they work for this ICP, and their limitations:

---

### Source 1: DSIR-Recognized R&D Units List (dsir.gov.in)

**What it is:** The Department of Scientific and Industrial Research maintains a public list of ~3,000+ companies with government-recognized in-house R&D units. Available as a downloadable Excel/PDF.

**Why it works for this ICP:**
DSIR recognition is a direct pre-filter for two Federer criteria:
- **C3 (Differentiation):** A company that invested in setting up a recognized R&D unit is not a commodity manufacturer.
- **C4 (Technical DM):** Someone had to conceptualize, set up, and maintain the R&D unit — signals systems thinking.

It is also self-qualifying: traders and distributors are ineligible for DSIR recognition.

**How to use:** Download from dsir.gov.in, filter by state (Karnataka, Maharashtra, Gujarat, Tamil Nadu), filter by NIC code (manufacturing sub-sectors), and segment by city.

**Limitation:** Skews toward established companies (10+ years old). Misses newer precision engineering startups that haven't applied. Also available as a static snapshot — needs to be cross-referenced with MCA for current operational status.

**Expected yield from Bengaluru aerospace/auto segment:** ~50–80 companies.

---

### Source 2: BIS (Bureau of Indian Standards) Certified Manufacturers List

**What it is:** BIS maintains a public database of companies that have obtained ISI/BIS product certification for specific product categories.

**Why it works:**
BIS product certification for a manufacturing category (e.g., IS: standards for auto components, aerospace fasteners, hydraulic components) directly evidences:
- **E1 (Producer):** Must have a physical plant to earn product certification.
- **C3 (Differentiation):** A company that invested in BIS certification for a specialty product is not a generic commodity player.

Unlike ISO 9001 (which is a management system certification), BIS product certification requires the actual product to meet technical standards — it's harder to fake.

**How to use:** BIS public portal (bis.gov.in) has a manufacturer search. Filter by product type (auto components, precision parts, etc.) and city.

**Limitation:** BIS certification is not mandatory for all products — many specialty manufacturers export under international standards (IATF, AS9100) and don't bother with BIS. This source underrepresents exporters.

---

### Source 3: Trade Expo Exhibitor Directories

**Target expos:**
- **Auto Expo Components (New Delhi):** Tier-1 and Tier-2 auto component exhibitors
- **IMTEX (Bengaluru):** Machine tool and precision engineering manufacturers — directly in our segment
- **Aero India (Bengaluru):** Aerospace component manufacturers, defence systems suppliers
- **Defexpo India:** Defence manufacturing — overlaps with aerospace segment
- **India International Engineering Sourcing Show (IESS):** Engineering component exporters

**Why it works:**
Expo exhibitors self-select for growth intent. Paying Rs.2–10L for a booth signals C6 (Growth Signals) — a stagnant company doesn't invest in exhibitions. Exhibitor directories include company names, product categories, city, contact person, and website — everything needed to build the initial universe.

**How to use:**
- Past expo websites retain exhibitor directories (IMTEX, Aero India publish full lists)
- Wayback Machine for archived directories from 2022–2024 editions
- Scrape with Python + BeautifulSoup; most expo sites have structured exhibitor pages

**Limitation:** Biased toward companies large enough to afford booths. Small-to-mid MSMEs (<Rs.30Cr) often absent. Deduplication needed across expos.

**Expected yield:** 300–500 companies across 5 expos for auto/aerospace segments.

---

### Source 4: USFDA Facility Database (fda.gov) + EU-GMP Lists

**What it is:** USFDA maintains a public searchable database of all approved foreign manufacturing establishments. EU EMA maintains a similar database for EU-GMP certified sites. WHO publishes a prequalification list.

**Why it works:**
Regulatory approval is the strongest single signal for C3 (Differentiation) and C1 (Producer) simultaneously. A company cannot get USFDA or EU-GMP approval without:
- A physical facility (E1)
- Documented manufacturing processes (C7 Systems — mandatory for approval)
- Demonstrated product quality differentiation (C3)
- Export orientation (C5 Tailwind — export = growing sector)

This source was designed for pharma/chem but also applies to precision components (medical devices, aerospace parts requiring FDA approval for US export).

**How to use:** Filter fda.gov/industry/facilities-registration to India, then filter by product category. Cross-reference with WHO prequalification for pharma.

**Limitation:** Heavy pharma/chemical bias. Doesn't cover pure auto-component or aerospace-only manufacturers.

---

### Source 5: MSME Udyam Registration Portal

**What it is:** Government of India's MSME registration database (udyamregistration.gov.in) with 4Cr+ registered MSMEs. Filterable by NIC code (manufacturing sub-sector), state, district.

**Why it works:**
- Captures the long tail of MSMEs that never appear in expo lists, BSE, or media
- NIC codes like 2812 (manufacture of industrial and agricultural machinery), 2591 (metal forging), 2910 (motor vehicles) are direct segment proxies
- Free, government data — no subscription needed

**How to use:** NIC-code search by state and district. Pair with Google search for each company name + city to find website. Automate with Python.

**Limitation:** Very noisy. Millions of records. NIC codes are self-declared and frequently wrong (a trader will declare as manufacturer). Requires heavy filtering. Does not indicate company size or revenue.

---

### Source 6: ACMA (Automotive Component Manufacturers Association of India) Member Directory

**What it is:** ACMA is the apex auto components industry body. Members include Tier-1 and Tier-2 suppliers across India. ACMA publishes an annual member directory with company names, locations, product categories, and key contacts.

**Why it works:**
ACMA membership signals:
- Active participation in the auto component supply chain (E1, active producer)
- Industry engagement and growth intent (C6 signal)
- Geographical filter available (Bengaluru/Karnataka chapter)

ACMA also hosts the India International Engineering Sourcing Show (IESS) — cross-reference with expo lists.

**Limitation:** Membership is self-selected and fee-based. Some ACMA members may be traders or large-group subsidiaries (Tata, Mahindra Tier-1s) that don't fit the ICP. Revenue filter needed post-extraction.

---

### Source 7: LinkedIn Sales Navigator (Inverted Search)

**What it is:** LinkedIn's premium search tool filters by company size, industry, geography, and seniority.

**Why it works — inverted approach:**
Instead of finding companies and checking if the DM is technical, find technical DMs and check if their company is a manufacturer.

**Search filter:** Industry = Manufacturing (sub-sectors: aerospace, automotive, industrial machinery), Company headcount = 50–500, Geography = target cities, Seniority = Owner / Founder / MD / CXO.

This is the only source that directly pre-filters for C4 (Technical Decision-Maker). If the top result for a company is an IIT/IISc/BITS alumni or ex-DRDO/ISRO founder, C4 is pre-qualified.

**Limitation:** Self-reported data — company headcount and industry category are frequently wrong for Indian MSMEs. Many founders are not on LinkedIn. Exports names but requires website discovery separately.

---

### Source 8: State Industrial Development Corporation Directories

**Specific bodies:**
- **KIADB (Karnataka Industrial Areas Development Board):** Maintains a database of industrial plot allottees across its industrial areas (Peenya, Bommasandra, Jigani, Devanahalli Aerospace Park)
- **MIDC (Maharashtra):** Similar for Pune/Nashik
- **GIDC (Gujarat):** For Ahmedabad/Vadodara/Surat

**Why it works:**
Allottee lists contain company names, industrial area, and plot size — all confirming physical manufacturing presence. The Aerospace SEZ (Devanahalli, Bengaluru) allottee list is a direct pre-filter for aerospace manufacturers.

**How to obtain:** RTI request to KIADB, or from published KIADB annual reports and meeting minutes (some available publicly).

**Limitation:** Requires RTI filing for full data. Published lists may be outdated. Does not include revenue or DM details.

---

### Source 9: Google Maps Industrial Cluster Scraping

**What it is:** Google Maps scraping of industrial areas (Peenya Industrial Area, Bommasandra, KIADB Jigani) to extract business names, ratings, and contact information.

**Why it works:**
Many precision engineering MSMEs are discoverable via Google Maps (they list their business with category "manufacturer" or "precision machined components") but don't have websites or aren't on directories. This source captures the invisible long tail.

**How to use:** Use Python + googlemaps API or SerpAPI to scrape business listings by latitude/longitude radius. Filter by business category (manufacturer, engineering, precision parts).

**Limitation:** Noisy. Includes retailers, contractors, services companies. Requires heavy filtering. Category tags are self-declared and often wrong.

---

## Question 2: The 1000-Company Proposal — Building a Verified Federer List in One Month

---

## Goal

1,000 genuinely ICP-qualified companies — Federer profile, scored on all 6 criteria with evidence, ready for outreach — within 30 calendar days.

---

## Core Constraint

**~30% yield.** Based on Part A research, roughly 3 in 10 companies investigated pass. To get 1,000 passes, the sourcing universe needs to be ~3,500–4,000 companies.

The challenge is not finding 3,500 company names — that's achievable in 3 days. The challenge is qualifying them at scale without sacrificing evidence quality.

---

## The Funnel

```
Universe: 3,500–4,000 company names
       ↓ Pre-filter: Remove traders, PSUs, <10 employees, no website (auto-reject)
Screened pool: 2,000–2,500
       ↓ Automated ICP scoring: AI-assisted (Claude Haiku first pass)
First-pass qualified: 1,200–1,400
       ↓ Human QA: Verify borderlines, check auto-QA flags
Final verified list: 1,000
```

---

## Week 1: Build the Universe (Days 1–7)

**Goal:** 3,500–4,000 unique companies with name, city, segment tag, and website URL.

**Day 1–2:** Structured data sources (fastest to process)
- DSIR recognized R&D units list (download + filter by state + segment)
- BSE SME / NSE Emerge listed companies (manufacturing sectors, revenue band filter)
- USFDA facility list for India (filter pharma/medtech segments)
- Expected: ~800–1,000 companies from these three sources

**Day 2–3:** Expo exhibitor directories
- Build Python scrapers for IMTEX, Aero India, Auto Expo Components, IESS, Defexpo exhibitor pages
- Use BeautifulSoup / Playwright (for JS-rendered pages)
- Expected: ~500–700 companies after deduplication

**Day 3–4:** Industry association member directories
- ACMA member directory (auto components)
- ELCINA (electronics manufacturers)
- BDMA (bulk drugs and API — for adjacent pharma segment)
- Seed Association of India (for agri-input segment in other cities)
- Expected: ~400–600 companies

**Day 4–5:** MCA / MSME data
- Query Antigravity (or Tofler) for NIC codes matching target manufacturing sub-sectors across target cities
- NIC codes: 2811 (engines/turbines), 2812 (industrial machinery), 2591 (forging/stamping), 2910 (motor vehicles), 2652 (watches/instruments), 2660 (medical equipment), 3030 (air/spacecraft)
- Expected: ~1,000–1,500 companies (very noisy — many will be dormant, tiny, or misfiled)

**Day 5–6:** LinkedIn Sales Navigator
- Filter: Manufacturing industry, 50–500 headcount, target cities, Founder/Owner/MD seniority
- Export list of 400–600 profiles → map to company names
- Expected: ~300–400 unique companies

**Day 6–7:** Deduplication + website discovery
- Fuzzy match company names across all 6 sources (Levenshtein distance threshold 0.85)
- For companies without website URLs: Google search "{company name} {city}" to find website or IndiaMart listing
- Final universe after dedup: 3,500–4,000 unique companies

**Week 1 output:** Master CSV with: company name, city, segment tag, website URL, source tag. Approximately 60–65% will have a confirmed website URL.

---

## Week 2–3: Automated ICP Scoring (Days 8–19)

**Goal:** Score all 3,500 companies against the 6 Federer criteria using an AI-assisted pipeline.

### Step A: Website Scraping

For each company with a website:
- Scrape: homepage, /about, /leadership, /products, /news, /careers, /contact
- Concatenate to ~8K tokens maximum
- Use Playwright (handles JavaScript-rendered sites) with 10-second timeout per page
- Respect robots.txt; add 2-second politeness delay between requests
- Run 4 parallel scrapers to cover 3,500 companies in ~8 hours

### Step B: Hard Pre-Filter (Before AI Scoring)

Auto-reject before sending to AI:
- No website found (after 2 Google search attempts)
- Single-page placeholder site (page count < 2, total text < 500 characters)
- Company name contains "Trading", "Traders", "Imports", "Distributors", "Exports Pvt Ltd" — strong trader signal
- Revenue confirmed > Rs.500Cr from BSE/NSE data

This eliminates ~500–800 companies before AI scoring.

### Step C: AI Scoring Pipeline

**Tool:** Claude Haiku for first pass, Claude Sonnet for borderline re-scoring.

**Prompt structure:**
```
You are an ICP analyst for DeepThought, a B2B company that helps Indian specialty manufacturers structure their operations.

Evaluate the company below against 6 criteria. Output ONLY valid JSON.

Company website content:
{SCRAPED_CONTENT}

Criteria to score (Weak/Moderate/Strong + numeric score + one-line evidence):
- C3: Differentiation (20 pts) — Is this a specialty/technical product or a commodity?
- C4: Technical Decision-Maker (15 pts) — Does the founder/MD have science/engineering background or demonstrate systems thinking?
- C5: Growing Sector (15 pts) — Is this segment benefiting from PLI, China+1, Make-in-India, or export tailwinds?
- C6: Growth Signals (15 pts) — Any 2+ of: hiring, facility expansion, new certifications, active website, revenue growth?
- C7: Systems Maturity (20 pts) — Evidence of ERP, structured processes, digital infrastructure?
- C8: Leadership Succession (15 pts) — Gen-2 involvement, professional management, or leadership depth?

Also output:
- E1_pass: true/false (is this a manufacturer, not a trader/service company?)
- confidence: high/medium/low for each criterion
- auto_disqualify: true/false + reason if true

JSON format: {"E1_pass": true, "C3": {"score": "Strong", "points": 20, "evidence": "...", "confidence": "high"}, ...}
```

**Scoring pipeline:**
1. Scrape website (5–8 pages)
2. Send to Claude Haiku → receive JSON scores
3. If total 40–60 (borderline zone): re-score with Claude Sonnet
4. If any criterion has `confidence: "low"`: flag for human QA
5. Store result in master spreadsheet (one row per company)

**Cost estimate:**
- Haiku first pass: ~Rs.0.40/company × 3,500 = Rs.1,400
- Sonnet re-score on ~20% borderline: ~Rs.3.50/company × 700 = Rs.2,450
- Scraping compute: negligible on local machine or cloud VM
- **Total AI cost: ~Rs.4,000**

**Speed estimate:**
- Scraping: ~30 seconds/company × 3,500 / 4 parallel workers = ~7–8 hours
- Haiku scoring: ~3 seconds/company = ~3 hours
- Sonnet re-scoring: ~5 seconds × 700 = ~1 hour
- **Total compute time: ~12–14 hours spread across 2–3 days**

---

## Week 3–4: Human QA + Final Assembly (Days 19–30)

**Goal:** Validate borderline companies, eliminate false positives, assemble final 1,000.

### Known AI Failure Modes to Check

| Failure Mode | Description | Detection Method |
|---|---|---|
| C3 inflation | LLM reads "ISO 9001" and scores differentiation Moderate, when ISO 9001 is a baseline, not a differentiator | Flag C3 evidence mentioning only ISO 9001/14001 |
| C4 false positive | LLM reads any engineering degree as "Strong" — but tier-3 college + commodity business ≠ IIT + specialty manufacturer | Flag C4 evidence that doesn't mention specific institution, publication, or ISRO/DRDO/IIT connection |
| C6 false positive | LLM reads 2019 press article and scores growth Moderate — old news is not current activity | Flag C6 evidence referencing news older than 2023 |
| C1 false negative | Company says "solutions" and "services" but actually manufactures — LLM takes website language too literally | Flag E1=false for companies in manufacturing NIC codes |
| Revenue error | Website doesn't show revenue; LLM scores "Unknown" but company is clearly a large group subsidiary | Flag companies with parent group branding or "a division of" language |

### Auto-QA (Programmatic — Day 19–20)

```python
flags = []
for company in scored_companies:
    # Flag inflated borderlines
    if 40 <= company.total_score <= 42 and all c.confidence == "high":
        flags.append((company, "possible_inflation"))
    # Flag baseline-only C3
    if "ISO 9001" in company.C3.evidence and "DSIR" not in company.C3.evidence \
       and "USFDA" not in company.C3.evidence and "patent" not in company.C3.evidence.lower():
        flags.append((company, "C3_baseline_only"))
    # Flag stale C6 evidence
    if any(str(year) in company.C6.evidence for year in [2018, 2019, 2020]):
        flags.append((company, "C6_stale_evidence"))
```

Expected: ~300–400 flagged companies.

### Human QA (Days 20–26)

For each flagged company:
1. Open website, verify 2–3 key claims in the AI evidence
2. Check LinkedIn for recent hiring (last 6 months)
3. Check MCA/Tofler for latest revenue filing and director list
4. Adjust scores, accept or reject
5. Spot-check 50 random "Strong Pass" (A-band) companies to verify pipeline accuracy

**Time estimate:** 3–4 minutes/company × 400 companies = ~25–30 hours. Spread over 4 days, 2 hours/day.

### Final Assembly (Days 26–30)

- Merge clean strong_pass (A-band) companies: ~600–700 expected
- Add QA-verified companies: ~300–400
- Remove duplicates (fuzzy match on company name + city)
- Verify total ≥ 1,000
- Add personalization hooks for top 200 priority outreach tier
- Format final deliverable (master CSV + summary dashboard)
- Write methodology document
- Buffer day for overruns

---

## Weekly Summary

| Week | Focus | Output |
|------|-------|--------|
| **1** | Sourcing | 3,500–4,000 company universe with names, cities, segment tags, websites |
| **2** | Scraping + Haiku scoring | All companies scraped and scored. First-pass results: ~1,200–1,400 passes |
| **3** | Sonnet re-scoring + QA start | Borderlines re-scored. Human QA begins on ~400 flagged companies |
| **4** | QA completion + assembly | 1,000 verified companies in final CSV. Top 200 with personalization hooks |

---

## Realistic Yield Expectations

| Stage | Input | Output | Yield |
|-------|-------|--------|-------|
| Pre-filter (trader/no website) | 3,500 | 2,600 | 74% |
| Hard pre-filter (confirmed fails) | 2,600 | 2,100 | 81% |
| Haiku first-pass scoring | 2,100 | 1,200 pass / 500 borderline / 400 fail | 57% of screened |
| Sonnet re-scoring (borderlines) | 500 | 300 pass / 200 fail | 60% of borderlines |
| Human QA (flagged) | 400 | 250 confirmed pass / 150 reject | 63% of flagged |
| **Final verified** | **—** | **~1,000–1,050** | **~30% of universe** |

---

## Risk Mitigation

| Risk | Mitigation |
|------|-----------|
| Yield < 25% | Expand universe with Google Maps industrial cluster scraping (Peenya, Bommasandra, Jigani) + KIADB allottee list |
| Scraper blocked | Rotate user agents, add politeness delays, use residential proxies for critical sites. Fall back to manual for high-priority blocks |
| AI accuracy < 80% | Tune prompt on 20-company calibration set before full run. Split scoring: Haiku for factual criteria (C1, C2, C5), Sonnet for judgment criteria (C3, C4, C7) |
| QA bottleneck | Tighten auto-QA rules to reduce human load. Add second reviewer for overflow |
| Dedup errors | Use CIN number matching (from MCA) for all listed companies — CIN is globally unique |

---

## Tools and Budget

| Tool | Purpose | Cost |
|------|---------|------|
| Claude Haiku API | First-pass scoring (3,500 companies) | ~Rs.1,400 |
| Claude Sonnet API | Borderline re-scoring (700 companies) | ~Rs.2,450 |
| Antigravity | MCA data extraction (NIC code + city queries) | Licence provided |
| Playwright + Python | Website scraping | Free (open source) |
| GitHub Copilot | Scraper and pipeline code assistance | Licence provided |
| LinkedIn Sales Navigator | DM discovery, company enrichment | Licence provided |
| Google Sheets / PostgreSQL | Master data storage | Free |
| **Total AI + data cost** | | **~Rs.4,000** |

---

## Final Deliverable

1. **Master CSV** — 1,000 companies, each with: name, website, city, segment, products, revenue band, decision-maker, C1–C8 scores with evidence, verdict, confidence flags
2. **Priority-200 list** — Top 200 A-band companies with personalization hooks ready for outreach
3. **Methodology document** — Sources, scraper architecture, scoring prompt, QA process, yield rates at each stage
4. **Code repository** — All scraping scripts, scoring pipeline, data processing notebooks, reproducible end-to-end
5. **Source breakdown** — Which sources contributed how many final companies (to inform future sourcing investment)

---

*DeepThought Business Analytics Internship | Part B Proposal | May 2026*
