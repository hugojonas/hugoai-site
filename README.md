# HugoAI — website

De marketing-site van HugoAI: één self-contained pagina (`index.html`) met de iriserende WebGL stem-orb, cinematic scroll en een werkend contactformulier (Formspree).

Dit is een **losse, schone repo met alléén de website** — bewust los van het privé HugoAI-project (server/prompts), zodat je dit veilig publiek kunt hosten.

## Bestanden
| Bestand | Wat |
|---|---|
| `index.html` | De hele website (CSS + JS inline; Three.js/GSAP/Lenis via CDN) |
| `og-image.png` | Preview-afbeelding bij delen (1200×630) |
| `robots.txt` | Zoekmachine-instructies + sitemap-verwijzing |
| `sitemap.xml` | Sitemap (één pagina) |

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
1. Pas `index.html` aan.
2. ```bash
   git add -A && git commit -m "beschrijving" && git push
   ```
3. De site update vanzelf binnen ~1 minuut.

## Nog te doen voor complete SEO
- [ ] `REPLACE-MET-JE-DOMEIN` vervangen in `robots.txt` en `sitemap.xml` door je echte domein.
- [ ] `og:image` en `twitter:image` in `index.html` op de **volledige** URL zetten (bv. `https://hugoai.nl/og-image.png`) — sommige platforms eisen een absolute URL.
- [ ] Site aanmelden bij [Google Search Console](https://search.google.com/search-console) en je sitemap indienen.
