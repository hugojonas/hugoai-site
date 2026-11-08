# HugoAI — website

De marketing-site van HugoAI: een homepage met live demo (`index.html`), een Over-pagina (`over.html`) en een werkend contactformulier (Formspree). Geen build-stap, geen frameworks.

Dit is een **losse, schone repo met alléén de website** — bewust los van het privé HugoAI-project (server/prompts), zodat je dit veilig publiek kunt hosten.

## Bestanden
| Bestand | Wat |
|---|---|
| `index.html` | Homepage: demo-blok, samenvatting, branches, aanvraagformulier (JS inline) |
| `over.html` | Over HugoAI en de werkwijze |
| `privacy.html` | Privacyverklaring (diensten per soort genoemd, zonder bedrijfsnamen) |
| `stijl.css` | Gedeelde stijl voor beide pagina's (fonts via Google Fonts) |
| `kunstbeeld.png` | Kunstbeeld van het telefoonsnoer, alleen bovenaan de homepage |
| `vlak-zand.png` | Geschilderd korrelvlak achter de samenvatting (`vlak-petrol.png` is niet meer in gebruik) |
| `og-image.jpg` | Deelplaatje (1200×630): slogan + telefoonsnoer, zoals de bovenkant van de site |
| `favicon.svg`, `favicon-48.png`, `apple-touch-icon.png` | Icoontje: de petrol stip uit het logo op een crème tegel |
| `robots.txt` | Zoekmachine-instructies + sitemap-verwijzing |
| `sitemap.xml` | Sitemap (homepage, over, privacy) |

> De Garage-, Restaurant- en Kapsalon-demo bellen echt: ze verbinden via WebSocket met de HugoAI-server (nu nog via ngrok op Hugo's laptop). Andere branches komen pas op de site als hun demo af is. Links onder de keuzes staat dat gesprekken worden opgenomen, met een link naar `privacy.html`.

> Contactformulier post naar Formspree: `https://formspree.io/f/xrewjzvl`.

---

## Eenmalig live zetten met auto-deploy (aanrader)

### Stap 1 — Zet deze repo op GitHub
```bash
# in deze map:
git remote add origin https://github.com/<jouw-gebruikersnaam>/hugoai-site.git
git branch -M main
git push -u origin main
```
(Maak eerst een lege repo `hugoai-site` aan op github.com — **public** mag, hier staan geen secrets in.)

### Stap 2 — Koppel aan Vercel of Netlify
- **Vercel:** ga naar vercel.com → *Add New → Project* → kies je `hugoai-site` repo → Deploy. Klaar.
- **Netlify:** app.netlify.com → *Add new site → Import an existing project* → kies de repo → Deploy.

Vanaf nu: **elke `git push` = de site update automatisch live.** Nooit meer handmatig slepen.

### Stap 3 — Eigen domein
1. Koop een domein (bijv. bij TransIP, Versio of Cloudflare voor `.nl`; ~€10/jaar).
2. In Vercel/Netlify: *Domains → Add domain* → volg de DNS-stappen (een CNAME/A-record instellen bij je domeinprovider).
3. HTTPS (het slotje) komt automatisch en gratis.

---

## Iets wijzigen op de site
1. Pas `index.html`, `over.html` of `stijl.css` aan.
2. ```bash
   git add -A && git commit -m "beschrijving" && git push
   ```
3. De site update vanzelf binnen ~1 minuut.

## SEO — status
Live op **https://hugoai.nl** (Vercel, auto-deploy).
- [x] `robots.txt` + `sitemap.xml` op `https://www.hugoai.nl/` (hugoai.nl stuurt door naar www).
- [x] `canonical`, `og:`/`twitter:`-tags en favicon op alle pagina's; Organization-schema op de homepage (1 nov 2026).
- [x] Privacyverklaring (`privacy.html`) + melding "Het gesprek wordt opgenomen" bij de Garage-demo (31 okt 2026).
- [ ] Site aanmelden bij [Google Search Console](https://search.google.com/search-console) en sitemap indienen.
- [ ] (optioneel) Google Bedrijfsprofiel aanmaken voor branded search.
- [ ] (optioneel) `www.hugoai.nl` toevoegen in Vercel.
