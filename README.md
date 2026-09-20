# ComplyNG

**Can a Nigerian SME actually win this federal contract — or is the deadline already gone?**

Six statutory certificates stand between a small Nigerian contractor and a federal tender: CAC, a Tax Clearance Certificate from the NRS, PenCom, ITF, NSITF, and BPP registration. The institutions that demand them do not adequately publish how to obtain or renew them. So the gap is filled by agents, who price it.

ComplyNG tells you, before you spend a naira, whether the tender is reachable at all — and shows you the law behind every requirement, the official fee beside the agent's quote, and a scorecard of which institutions actually publish what they demand.

Built for the Andela × Open Society Foundations invention sprint, September 2026. Track: **Transparency & Accountability**.

The mechanism this documents — institutions demanding compliance they do not publish, and a private market pricing the gap — is not Nigerian. The dataset schema in `data/agencies.json` is country-agnostic; Nigeria is the first instance, not the only one.

---

## Why this exists

This project came out of two things that happened to its author, a construction contractor and product manager in Abuja.

**One.** A payment from a client was blocked because his company's tax ID had lapsed. He had never been notified. At a tax office in Abuja he was told to travel to Lagos — where the company was registered in 2020 — to regularise it. He had no way to check whether that instruction was correct.

*It appears it was not.* The Nigeria Tax Administration Act 2025 s.3 allocates jurisdiction only between the NRS and state authorities; s.3(1)(a) places companies exclusively with the NRS wherever they are. There is no published rule requiring the office of registration — and none permitting any office either. The agency publishes nothing at all on office jurisdiction.

**Two.** To assemble a bid bundle, he paid an agent **₦250,000**, and waited about two weeks. Of the six certificates in that bundle, **two are free**. One of them — the PenCom Pension Clearance Certificate — is not only free and fully online, PenCom has publicly declared that using an agent to obtain it is *illegal* under Pension Reform Act 2014 s.104(b)–(c). Agents advertise up to ₦250,000 for it anyway, because PenCom's own message reaches nobody.

The agent's fee is not payment for work. It is payment for knowing something the state declined to publish. That is the problem this addresses.

---

## What it does

**Eligibility check.** Enter your company's basics — employees, turnover, what you're already remitting, days until the tender closes — and get an honest verdict. Often that verdict is *no*, and the most valuable thing the tool does is say so before you spend money. A PenCom certificate requires evidence of remittance for the last three fiscal years; that evidence cannot be created retroactively, at any price, by any agent. Knowing this in week one instead of week three is the product.

**The law behind every requirement.** Each certificate carries the Act, section and source URL that imposes it. The NRS has **two weeks** to issue a Tax Clearance Certificate or give you written reasons — Nigeria Tax Administration Act 2025, s.72(1). Consultants openly advertise three to five weeks. The statutory right exists; almost nobody knows to assert it.

**True cost of compliance.** Enter your monthly payroll and the tool computes what becoming compliant actually costs, from published statutory rates only: three years of pension back-remittance at 18% of emoluments, NSITF arrears at 1% of monthly payroll over the same period, the ITF levy at 1% of annual payroll. At a ₦1.2m monthly payroll that is **₦8.4 million**, against ₦55,000 of certificate fees and ₦532,500 of agent quotes.

This is the finding that reframes the project. The agent's fee is real, but it is not the barrier — the barrier is a multi-million-naira retroactive liability that no agency discloses until you attempt to comply. A tool that showed only certificate fees would be reproducing the same opacity it exists to expose. Statutory penalties (NSITF 5–10% per month, ITF 5% per month) and the group life premium are left explicitly blank, because no agency publishes them and we will not guess.

**Cost exposure.** Official fees beside openly advertised agent quotes, per certificate.

**Demand letters.** Four generated letters for the moment an official tells you something that is not the published rule: a TCC not issued within the two weeks NTAA 2025 s.72(1) allows; a direction to travel to another tax office, requesting the provision relied on; a fee demanded for a certificate that is published as free; and an agency that will not disclose its own requirements. Each cites the section it stands on, so the official reading it can verify the claim. Fill in your company details, edit freely, download and print. This is the difference between transparency and accountability: informing a contractor is the first; equipping one to ask for the rule in writing is the second.

**Order of operations.** Six certificates presented as a critical path rather than a list — what starts today in parallel, what is gated behind remittance history, and why BPP is always last. Starting at BPP, which most people do because it is free and online, is the most common wasted month in the process.

**The other six documents.** A federal tender demands twelve items, not six. Audited accounts for three years and evidence of three similar jobs in five years are modelled alongside the certificates, because that is where small bids actually die — and the second of those is a structural lock-out: you need public-sector track record to win public-sector work.

**Do it yourself.** Every certificate carries direct links to the official portal that issues it and, where one exists, the free portal that verifies it — so the answer to "you are being overcharged" is immediately followed by the door. Five of the six have a working self-service route. ITF has none: its compliance page currently serves gambling spam, and the certificate is collected in person at the Area Office of registration. That contrast is left visible rather than smoothed over.

**The 31 December cliff.** These certificates do not run for a year from the day you receive them. Almost all expire on 31 December regardless of issue date — PenCom states it outright, and federal tender adverts demand the rest "valid till 31st December". So renewal is not a personal anniversary; it is a single national deadline the whole country walks off together every January, unannounced. ComplyNG counts down to it, works backwards from each agency's own published turnaround to the date you must start, and hands you a calendar file with a reminder fourteen days before each one. Where an agency publishes no turnaround, the bar is labelled a planning estimate — we do not invent a number and attribute it to them.

The reminder deliberately uses a downloaded calendar file rather than accounts and email. A notification service would require sign-up, an address and a stored record of who holds which certificates — precisely the database that must not exist. Your own phone does the reminding; nothing is stored here.

**A public record, not just a private tool.** ComplyNG helps one contractor at a time. The opacity record does something else: it states, with evidence and a date, whether six Nigerian federal institutions publish the requirements they enforce. That claim is citable, contestable, and free to reuse — and it outlives any single bid. `data/agencies.json` is the open dataset behind it: every requirement, fee, timeline, citation and recorded absence, including the official URLs that returned 404, in one machine-readable file. It is written for journalists, procurement-transparency organisations, researchers, and the agencies themselves — every failure recorded here is cheap to fix, and the record will say so the day it changes.

**Anonymous institutional reporting.** A contractor can add what actually happened to them — which office, how long it really took, what an agent charged, what they were told — and send it from their own WhatsApp or email. The form asks only about the institution, never about the person, the company or their documents, and nothing leaves the browser until the contractor chooses to send it. One contractor's experience is an anecdote; two hundred is a dataset nobody in Nigeria currently holds. The record currently contains one report: the author's own, published exactly as given.

**Institutional opacity scorecard.** For each of the six institutions: does it publish its requirements, its fees, its processing times, its forms? Checked against each agency's own website on 19 September 2026. Where an agency publishes nothing, that absence is recorded and scored — not filled in with a plausible-sounding estimate.

---

## What we found while building it

These are not claims. Each is a page that was fetched on 19 September 2026.

- **ITF's compliance-certificate page serves gambling spam.** `itf.gov.ng/itf-compliance/` — the page that should carry the requirements for a certificate you are legally obliged to hold, and the top search result for it — returns Indonesian gambling affiliate content. `/about-us/` returns 404. No archived copy exists. Consequently **no official ITF requirements checklist exists anywhere**; every list circulating online originates with commercial agents.
- **BPP 404s its own governing statute.** The Public Procurement Act 2007 fails on four separate BPP-hosted URLs. The 2014 circular that makes BPP registration a bid condition is listed on bpp.gov.ng and both hosted copies are unreadable. Its main FAQ page at `/faqs/` is unfinished placeholder text about managed IT services. "Interim Registration Report" and "IRR" appear nowhere on BPP's site, though every federal tender demands that document by name.
- **NSITF requires forms it does not distribute.** ECS RE01 and ECS RE03 are both marked "Coming soon" on its own downloads page.
- **PenCom publishes three different processing times** — 72 hours, 7 working days, 15 working days — with no reconciliation. Three official sources give three different employee thresholds: 15 (Pension Reform Act 2014 s.2(2)), 5 (BPP's FAQ), 3 (enforced by PenCom's own portal).
- **CAC serves two conflicting fee schedules simultaneously**, the gazetted one and the one its own site still links, with no notice reconciling them.
- **NRS publishes no TCC checklist, no fee and no validity period.** The FCT state authority publishes a checklist; the federal agency does not.
- **Correction to a common assumption:** BPP does not require NSITF for registration. The five-certificate chain is imposed by procuring entities applying PPA 2007 s.16(6)(d) plus SGF Circular SGF/50/S.52/II of 11 December 2014 — not by BPP's registration form. Same practical outcome, different sequencing.

---

## Designed for real conditions

| Condition | How it's handled |
|---|---|
| **Trust & verification** | Every requirement carries its Act, section and source URL with a date. Nothing asserted without provenance. |
| **Low bandwidth** | One self-contained HTML file, no framework, no runtime data fetches. Text-first; works on 2G. |
| **Privacy** | No accounts, no uploads, no certificates, no RC or tax numbers. Inputs stay in the browser and are never transmitted. A tool that asked contractors for statutory documents would be a tool asking to be impersonated. |
| **Multilingual** | English and Nigerian Pidgin, including the verdict and every action step — not a roadmap item. |
| **Accessibility** | Status encoded by glyph and text as well as colour; palette validated for protan, deutan and tritan separation in both light and dark themes. |
| **Local relevance** | Real Nigerian statutes, real gazetted fees, real tender document lists from UNILAG, NCAT and the Federal Ministry of Works. |

---

## Honest limits

- **Not legal or tax advice.** It reports what published rules say and links to where you can read them yourself.
- **It does not submit anything to any agency on your behalf**, and never will. That boundary is deliberate: a tool that files on your behalf needs your credentials, and a tool that holds contractors' credentials is a target.
- **Some figures cannot be verified because the agency does not publish them.** Those are shown as *not published*, never as an estimate.
- **Below the thresholds, there is no route at all.** A company with fewer than three employees cannot complete a PenCom application, and no agency publishes an exemption letter or waiver. The smallest businesses in Nigeria are locked out of public procurement by a paperwork gap nobody designed and nobody owns.
- **The letters are requests, not legal filings.** They ask an institution to state the rule it is applying. They are not legal advice and do not commence any proceeding.
- **Six agencies, federal contracting only.** State-level procurement has its own requirements and is out of scope for this proof of concept.
- **The dataset is a snapshot** taken on 19 September 2026. Requirements change; the next version needs monitoring rather than a fixed file.

---

## Run it

```bash
git clone <this repo>
cd complyng
python3 -m http.server 8000
# open http://localhost:8000
```

No build step, no dependencies, no framework. `index.html` is the entire application — one file, roughly 80KB, which is deliberate: it loads over 2G, it can be saved and opened offline, and it has no supply chain to audit.

## Deploy it

```bash
npm i -g vercel
vercel          # preview
vercel --prod   # production
```

Vercel serves it as a static site with no configuration. There is no build command and no output directory to set — if the dashboard asks, leave the framework preset as "Other" and both fields empty.

Downloads (the renewal calendar and the demand letters) use an ordinary Blob download on a normal host, and fall back to the platform download API when the page is running inside a sandbox that blocks page-initiated saves. Both paths are exercised in `index.html`; neither requires a server.

## Repository

```
index.html          The application — markup, styles, logic, data
data/agencies.json  Source-of-truth dataset: requirements, fees, timelines,
                    citations and opacity scores for all six institutions
README.md           This file
```

`data/agencies.json` is the canonical research artefact and carries the full citation list, including the broken and inaccessible official URLs recorded as evidence.

## Next, if this is worth developing

1. **Aggregation of the reports.** The reporting flow is deliberately backend-free for the proof of concept — nothing is collected, because collecting it properly means answering who holds it, who can subpoena it, and how a contractor stays unidentifiable in a dataset small enough to deanonymise. That is a governance question before it is an engineering one, and it should be answered with a civil-society partner rather than assumed.
2. **Monitoring instead of a snapshot** — watch each agency's pages and record when requirements, fees or availability change. The opacity scorecard becomes a time series, and a citable public record of which institutions meet their own transparency obligations.
3. **WhatsApp and USSD entry points** — most of the contractors this is for will never open a browser tab to find it. The 31 December reminder is the obvious first thing to deliver over SMS, and the only part that would justify holding a phone number.
4. **Verified community data where agencies publish nothing** — clearly separated from cited official sources, never blended with them.
5. **A generated demand letter** citing the relevant section, for the moment an official improvises. Turning "he said" into "the law says" is most of the value.
