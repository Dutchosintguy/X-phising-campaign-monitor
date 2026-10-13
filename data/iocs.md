# IOCs – fake journalist / Calendly → X OAuth phishing (defanged)
## Infrastructure (from blog)
- calendly[.]com/d/d336-3mq-q2z  (routing form: "Collaboration" / "Press Release")
- X OAuth app "Events Portal", claimed site eventsportal[.]com (GoDaddy for-sale page)
- callback/cred-harvest: plugins[.]cal-apis[.]com -> /login "Twitta" page; cal-apis[.]com reg 2026-09-16, Dominet (HK) Ltd, NS bill/paige.ns.cloudflare[.]com, LE wildcard *.cal-apis[.]com
## X accounts (active as of 2026-10-13 lookup)
| handle | display | persona claim | created | followers | blue |
|---|---|---|---|---|---|
| Conviasa | Liv Conviasa | @Bloomberg correspondent | 2018-09-03 | 1824 | yes |
| SeoSamantha | Samantha | correspondent @opinion @bloomberg ex @techcrunch | 2009-08-21 | 2203 | yes |
| Futana6 | Chloe Futana | TechCrunch correspondent | 2019-05-17 | 3924 | yes |
| KylieUncovered | Kylie | @Techcrunch & @opinion, prev @bloomberg @google | 2020-11-13 | 1348 | yes |
| Jaydayritt | Jay Dayrit | @WIRED, prev Bloomberg/Reuters | 2010-02-17 | 138 | yes |
## Related, suspended (from public warnings)
- MiaEsswein (shared same calendly d336-3mq-q2z, per @mdisec 2026-09-17) – suspended
- SimonHill_ (fake WIRED Simon Hill, per @GergelyOrosz/@consumerxai) – suspended
- Personas reported, handles unknown: "Tifafny Wu"/"Keyaki Yuu" (Reuters, @OfirPress 2026-09-28), Reuters persona (@daveg 2026-09-27)
## Lure phrasing
- "I’m writing an article on <topic>[.| and] Would value your insight. DM me if interested, thanks."
- "...would be valuable for an article I’m working on. DM me if you’re interested in a short interview chat."
- "Hey <Name>, just following up on my DM about our annual AI & technology feature."
- "I'm working on something I think you'd be interested in, would love to chat, couldn't send a message so feel free to message when convenient."
- "Hi <Name>, I’d love the chance to connect regarding a potential piece. Would you mind reaching out when convenient?"
- "Shot you a quick DM!" / "Sent you a DM regarding a founder piece!"

## Wider campaign (added 2026-10-13; status per item)
| IOC | type | source | our check 2026-10-13 |
|---|---|---|---|
| invitehandler[.]com | OAuth callback | Nosian (Epi Security) | reg 2026-08-15 Tucows; NS bill/paige Cloudflare (same pair as cal-apis); resolves |
| whitelistportal[.]com | "Booking Pass" OAuth callback | SafeBrowz | reg 2026-08-01 Tucows; NS bill/paige Cloudflare; resolves |
| asteriapanls[.]com | Asteria backend ("CalendarBookings") | Casco | reg 2026-08-02 Tucows; Njalla NS; A 111.90.148.101 |
| 30min-meetings[.]com | Asteria lure host | Casco | reg 2026-08-02 Tucows; Njalla NS; A 111.90.148.101 (same as asteriapanls) |
| bookings[.]caIendly[.]com / caiendly[.]com | capital-I Calendly homograph (app website) | Casco/Cybernews | caiendly.com reg 2026-02-11 Spaceship; no A record |
| x[.]login-api[.]com | credential phishing (Bloomberg-persona bot) | @eversinc33 | login-api.com reg 2026-09-25 **Dominet (HK)** (same registrar as cal-apis/cal-api); Cloudflare felicity/tess; resolves |
| calendly[.]com/30min-calls/interviews | Calendly destination | Casco | HTTP 404 (gone) |
| Apps: CalendarBookings, Booking Pass, Events Portal | X OAuth apps | Casco / SafeBrowz / blog | X app status not publicly queryable |
| Accounts: RamIyer__ (suspended), punk8739 (active, unverified) | X | @nickgraynews / @OG_Mr_Diamond | see operators.csv |
Note: Nosian's 13 accounts are not individually named in the article; only those named publicly elsewhere are added.
