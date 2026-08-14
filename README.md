# Kipling Travel — design-mockups

Selvstændige HTML-mockups til refresh af sektioner på [kiplingtravel.dk](https://www.kiplingtravel.dk).

## Live preview

- **Landing:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/
- **Relaterede rejser:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/relaterede-rejser-mockup.html
- **Hoteloversigt + popup:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/hoteloversigt-mockup.html

## Filer

| Fil | Formål |
|---|---|
| `index.html` | Landing-side med links til alle mockups |
| `relaterede-rejser-mockup.html` | 3-kort sektion til bunden af en rejseside |
| `hoteloversigt-mockup.html` | 4-kolonners hotel-grid med popup-detaljevisning |
| `Billeder/` | Billeder brugt af relaterede-rejser-mockup |

## Sådan bruger du filerne

HTML-filerne er **selvstændige** — al CSS er inline i toppen, ingen build-step:

```bash
open hoteloversigt-mockup.html
```

…eller server hele mappen:

```bash
python3 -m http.server 8080
```

## Noter til hoteloversigt-mockup

- **Popup i stedet for URL:** klik på et hotelkort åbner en modal med billedgalleri, beskrivelse og alternative hoteller. Ingen sideskift, nem at lukke (X-knap, backdrop-klik eller ESC).
- **Kategori-ikoner** (Classic/Plus/Premium) bruger allerede eksisterende `sprout.svg`, `plus.svg`, `star.svg` fra `/theme/Kiplingtravel/img/icons/`.
- **Billeder** i mockup'en hentes direkte fra kiplingtravel.dk's CDN via absolut URL — udskiftes med normale relative stier i produktion.
- **Alternative hoteller** i popup'en er samme kort-komponent i mindre format, med horisontal scroll.
- **Filtrering** på kategori (Classic/Plus/Premium) demonstreret som optional feature — kan udelades hvis ikke ønsket.
- **Alle klik åbner samme popup** (Langi Langi's data) i mockup'en for demo. I produktion henter popup'en det klikkede hotels egne data.

## Noter til relaterede-rejser-mockup

- Layoutet skal genbruges bredt — indholdet er eksempeldata. Selve kort-komponenten populeres dynamisk i `.search__results--container`
- Tema-ikoner bruger den eksisterende sprite (`rejsetyper.svg`) og klasser (`.kultur`, `.safari`, `.familie`, `.bjerg`, `.trekking`) — intet nyt at bygge
- Ingen JavaScript
- Responsivt: 3 → 2 → 1 kort ved 900px og 620px
