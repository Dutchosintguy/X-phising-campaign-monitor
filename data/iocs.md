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
| Futana6 | Chloe Futana | TechCrunch correspondent | 2019-05-17 | 3930 | yes — SUSPENDED (detected 2026-10-24) |
| KylieUncovered | Kylie | @Techcrunch & @opinion, prev @bloomberg @google | 2020-11-13 | 1348 | yes |
| Jaydayritt | Jay Dayrit | @WIRED, prev Bloomberg/Reuters | 2010-02-17 | 138 | yes |
| PetersonCouto | Peterson Couto | @Reuters tech & AI correspondent (fake; added 2026-10-17, named by victim @lordx64 with cal-api[.]com redirect) | 2009-10-05 | 3315 | yes |
| DobosDorina4 | Phoenix | covering AI/startups @TechCrunch (SUSPECTED; added 2026-10-18 – exact Futana6 'couldn't send a message' lure, not victim-named) | 2014-09-14 | 1604 | no (blue check lost, detected 2026-10-24) |
| nam_isay | Isaac Namm | Sr correspondent @bloomberg (fake; added 2026-10-17, likely – same template, not victim-named) | 2018-04-15 | 1691 | yes |

## Related, suspended (from public warnings)
- MiaEsswein (shared same calendly d336-3mq-q2z, per @mdisec 2026-09-17) – suspended
- SimonHill_ (fake WIRED Simon Hill, per @GergelyOrosz/@consumerxai) – suspended
- Personas reported, handles unknown: "Tifafny Wu"/"Keyaki Yuu" (Reuters, @OfirPress 2026-09-28), Reuters persona (@daveg 2026-09-27)
## Lure phrasing
- (2026-10-17) "I'd love to work with you on a piece but I can't send you a message. Please send me a dm whenever you're free" / "I'd love to write about this and feature your team in an article. Please send me a DM" (PetersonCouto, nam_isay)
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
| Accounts: RamIyer__ (suspended), punk8739 (renamed to @punk9962 on or before 2026-10-26, same id 893162896259198977, bio now "GP @0xBlockwire"; unverified) | X | @nickgraynews / @OG_Mr_Diamond | see operators.csv |
Note: Nosian's 13 accounts are not individually named in the article; only those named publicly elsewhere are added.

## Infrastructure clusters (added 2026-10-16; credit @orlof_v https://x.com/orlof_v/status/2111081475277811880)
All 7 domains below served the page title "Sign in — Twitta" on / and /login and the identical /static/css/panel.css (sha256 prefix 2ce123a1a60f, ?v=1787890490) on our passive GET 2026-10-16, and all use Cloudflare NS bill/paige → same phishing panel/operator infrastructure (high confidence).
- Cluster B (Tucows; Njalla privacy per @orlof_v WHOIS screenshot, Saint Kitts & Nevis; RDAP redacted): xredirecting[.]com (reg 2026-07-28), petrilabs[.]app (2026-07-30), whitelistportal[.]com (2026-08-01), invitehandler[.]com (2026-08-15), hyperball[.]one (2026-08-25)
- Cluster A (Dominet (HK)): cal-apis[.]com (2026-09-16), cal-api[.]com (2026-10-08); possibly login-api[.]com (2026-09-25, Dominet but NS felicity/tess, no Twitta page → medium)
- Cluster C (Asteria, Casco): asteriapanls[.]com, 30min-meetings[.]com — Tucows but Njalla NS + IP 111.90.148.101, no Twitta page → separate cluster, link to A/B unproven.
Panel class names seen by @orlof_v (oauth-app-form, account-grid, activity log badges) suggest an operator panel managing multiple X OAuth apps and hijacked accounts.

## Calendly routing forms
| Link | Status (last check) | Form | Owner | Options | Source |
|---|---|---|---|---|---|
| calendly[.]com/d/d336-3mq-q2z | 404 (removed by 2026-10-14) | (was Collaboration / Press Release → Events Portal OAuth) | — | Collaboration, Press Release | Nico blog / @mdisec |
| calendly[.]com/d/d3sm-ypg-s4w | 200 live (2026-10-17); **404 since 2026-10-22 ~20:26 CEST (last 200 at 18:20) — taken down/removed** | FormBuilder "F30" uuid 48ea958b-…; scheduling_link uid d3sm-ypg-s4w | org owner display name "MM" (id 54480394) | Name + Meeting type radios: Collaboration, Press Release | shared by targeted victim @ConstanceWaing via Nico Dekens (17 Oct) |
Identical public form options to the old lure. Downstream OAuth app/callback not visible without submitting the form (not done). No public X or urlscan hits for the new slug as of 2026-10-17.

- 2026-10-20 20:25 CEST: cal-apis.com nameservers switched by registrar to NS1/NS2.NONVERIFIEDDOMAIN.COM at 17:37Z (Verisign RDAP 'last changed'); domain no longer resolves (REFUSED), /login unreachable. Pattern consistent with a registrar hold for unverified registrant contact data (likely suspension; not confirmed by registrar). cal-api.com and invitehandler.com still on Cloudflare bill/paige.

- 2026-10-20 22:22 CEST: cal-apis.com REACTIVATED — NS back on Cloudflare bill/paige at 18:38:51Z (hold from 17:37Z lasted ~1h), status active, /login 200 with same Twitta kit (panel.css 2ce123a1a60f). Verified by us.
