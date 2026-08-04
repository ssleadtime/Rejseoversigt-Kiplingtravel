# Kipling Travel — design-mockups

Design-mockups til refresh af rejseoversigt og relaterede-rejser-sektionen på [kiplingtravel.dk](https://www.kiplingtravel.dk).

## Live preview

- **Landing:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/
- **Rejseoversigt (Marokko):** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/rejseoversigt-mockup.html
- **Relaterede rejser:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/relaterede-rejser-mockup.html

## Filer

| Fil | Formål |
|---|---|
| `index.html` | Landing-side med links til begge mockups + designtokens |
| `rejseoversigt-mockup.html` | Landeoversigt med 11 rejsekort + filter-piller + info-panel |
| `relaterede-rejser-mockup.html` | Sektion med 3 kort til bunden af en rejseside |
| `Billeder/` | Alle billeder + `rejsetyper.svg` (tema-ikon sprite) |

## Sådan bruger du filerne

Hver HTML-fil er **selvstændig** — al CSS er inline i toppen, og der er ingen build-step. Bare åbn dem i en browser:

```bash
open rejseoversigt-mockup.html
```

…eller serve hele mappen:

```bash
python3 -m http.server 8080
# Åbn så http://localhost:8080
```

## Designtokens

### Skrifttype

**Open Sans** i 400/600/700/800, hentes fra Google Fonts:

```css
@import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;500;600;700;800&display=swap');
```

### Farver

| Rolle | Hex |
|---|---|
| Accent (CTA, pil) | `#FF9900` |
| Tekst | `#2c2c2c` |
| Sekundær tekst | `#6c6258` |
| Baggrund (creme) | `#f5f0e6` |
| Baggrund (kort) | `#ffffff` |
| Kultur- og rundrejser | `#CC6600` |
| Safari- og naturrejser | `#70763F` |
| Familierejser | `#6BC9DD` |
| Bjergbestigning | `#A59184` |
| Trekking og vandreferie | `#83663D` |
| Dansk rejseleder-pill (baggrund) | `rgba(74,69,67,0.9)` eller transparent hvid |

### Border-radius

- Kort og knapper: `8px`
- Piller (badges, filter, status): `50px`
- Cirkulære elementer (avatar, tema-ikon i pill): `50%`

### Skygger

- Kort default: `0 1px 3px rgba(0,0,0,0.06)`
- Kort hover: `0 8-10px 20-28px rgba(0,0,0,0.12-0.14)` + `translateY(-2 til -3px)`

## Ikoner

Tema-ikonerne (kultur/safari/familie/bjerg/trekking) er ét SVG-sprite:

- Fil: `Billeder/rejsetyper.svg`
- Struktur: seks 40×40 tiles side om side (samlet viewBox `0 0 440 40`)
- Bruges som `background-image` med `background-position` per tema

Øvrige ikoner (kalender, ur, prismærke, "Dansk rejseleder"-personer, download) er inline SVG i HTML.

## Filter-logik (kun rejseoversigt-mockup)

- Klik på en filter-pill toggle'er den mellem aktiv/inaktiv (multi-select)
- Når mindst én pill er aktiv, tones de øvrige ned til `opacity: 0.4`
- Kortene filtreres på:
  - `.theme-icon.[kultur|safari|familie|bjerg|trekking]` inde i kortet
  - En separat "leader"-tag når kortet indeholder en `.pill-detail` med teksten "Dansk rejseleder"
- CTA-kortet ("Skræddersy din rejse") vises altid
- Info-panelet toggles ved klik på "læs hvad de enkelte temaer dækker →"-linket

JavaScript ligger i bunden af HTML-filen som en IIFE — ingen eksterne dependencies.

## Ansvarlig

Design af Stine Marie Simonsen. Fri til at kontakte hvis noget mangler eller skal forklares nærmere.
