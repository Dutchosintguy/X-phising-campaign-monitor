# X phishing campaign monitor — fake journalist interview → Calendly → X OAuth

**Live dashboard:** https://dutchosintguy.github.io/X-phising-campaign-monitor/
**Last updated:** 2026-10-13 09:26 CEST

Monitoring of an ongoing phishing campaign on X in which accounts posing as Bloomberg / TechCrunch / WIRED journalists publicly reply to people in AI, tech and OSINT ("I'm writing an article on … DM me"), move to DMs and send a **genuine Calendly link** (`calendly[.]com/d/d336-3mq-q2z`) that leads into an X OAuth app ("Events Portal") with callback on `plugins[.]cal-apis[.]com` — a fake "Twitta" credential-harvesting login.

Background write-up: [Phishing Campaign Identified: How OSINT Exposed a Real Calendly Link in a Fake Bloomberg Interview invite](https://www.dutchosintguy.com/post/phishing-campaign-identified-how-osint-exposed-a-real-calendly-link-in-a-fake-bloomberg-interview-i) — Nico Dekens (dutch_osintguy).

![dashboard](dashboard.png)

## Important caveats
- **Targets listed are publicly *approached* accounts, NOT confirmed victims.** A public reply from an operator account does not mean the person received a DM, clicked a link or was compromised. Do not label anyone a victim.
- Handle lists include accounts co-mentioned in operator replies.
- Data gaps: no DM content or Calendly URLs in the public reply data; operator profile fields are a single snapshot (X API); suspended accounts have no profile data; collection coverage starts 2026-09-16 (earliest known reply 2026-08-19 is not in the dataset); passive DNS/CT history not included.
- Attribution: nothing here identifies who operates the accounts.
- Indicators are defanged. Do not submit the Calendly form, authorize the app or enter credentials.

## Data (`data/`)
`posts_clean.csv` operator replies · `operators.csv` operator profiles/status · `warnings.csv` public victim warnings · `targets_publicly_approached.csv` · `iocs.md`.

Times are Europe/Amsterdam. Updated by an automated monitor run.
