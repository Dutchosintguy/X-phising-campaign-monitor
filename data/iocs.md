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
