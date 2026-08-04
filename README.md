# Kipling Travel — Relaterede rejser mockup

Design-mockup til refresh af "Relaterede rejser"-sektionen på [kiplingtravel.dk](https://www.kiplingtravel.dk).

## Live preview

- **Landing:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/
- **Mockup:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/relaterede-rejser-mockup.html

## Filer

| Fil | Formål |
|---|---|
| `index.html` | Landing-side med link til mockup + designtokens |
| `relaterede-rejser-mockup.html` | Selve sektionsmockup'en — 3 kort + toolbar |
| `Billeder/` | 6 billeder (rejser + rejseledere) + `rejsetyper.svg` (tema-ikon sprite) |

## Sådan bruger du filerne

HTML-filen er **selvstændig** — al CSS er inline i toppen, og der er ingen build-step. Bare åbn den i en browser:

```bash
open relaterede-rejser-mockup.html
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
| Accent (primær-CTA, pil) | `#FF9900` |
| Tekst | `#2c2c2c` |
| Sekundær tekst | `#6c6258` |
| Baggrund (creme) | `#f5f0e6` |
| Baggrund (kort) | `#ffffff` |
| Kultur- og rundrejser | `#CC6600` |
| Safari- og naturrejser | `#70763F` |
| Familierejser | `#6BC9DD` |
| Bjergbestigning | `#A59184` |
| Trekking og vandreferie | `#83663D` |
| PDF-knap (grå) | `#D0D0D0` |

### Border-radius

- Kort og knapper: `8px`
- Piller (badges, status, meta): `50px`
- Cirkulære elementer (avatar, tema-ikon i pill): `50%`

### Skygger

- Kort default: `0 1px 3px rgba(0,0,0,0.06)`
- Kort hover: `0 8px 20px rgba(0,0,0,0.12)` + `translateY(-2px)`

## Sektionens struktur

```
┌────────────────────────────────────────────────────────┐
│ Relaterede rejser                    [Hent som PDF]    │  ← toolbar
│ Andre kultur- og oplevelsesrejser...                   │
├────────────────────────────────────────────────────────┤
│ [Kort 1]   [Kort 2]   [Kort 3]                         │  ← 3-kolonne grid
├────────────────────────────────────────────────────────┤
│                [Se alle rejser →]                      │  ← primær CTA
└────────────────────────────────────────────────────────┘
```

### Kort-struktur (fra top til bund)

1. **Billede** (4:3 aspect-ratio) med tre overlejrede elementer:
   - **Land-pill** (top-venstre): tema-farvet med tema-ikon fra sprite
   - **Dansk rejseleder-pill** (under land-pillen): transparent hvid, blur bagved
   - **Status-pill** (top-højre): hvid med farvet prik ("Ledige pladser" grøn, "Få pladser tilbage" orange)
2. **Titel** — stor, fed
3. **Meta-piller** — dato, varighed, pris (samme grå style)
4. **Rejseleder** — lille avatar + "Rejseleder: [Navn]" (adskilt fra resten med tynd creme-linje)
5. **CTA** — "Se rejsen ›" (kun pilen orange)

## Ikoner

Tema-ikonerne (kultur/safari/familie/bjerg/trekking) er ét SVG-sprite:

- Fil: `Billeder/rejsetyper.svg`
- Struktur: seks 40×40 tiles side om side (samlet viewBox `0 0 440 40`)
- Bruges som `background-image` med `background-position` per tema

Øvrige ikoner (kalender, ur, prismærke, "Dansk rejseleder"-personer, download) er inline SVG i HTML.

## Responsivt

- **Desktop (≥ 900px):** 3 kort i én række
- **Tablet (620-899px):** 2 kort i række (3. wrapper til næste)
- **Mobil (< 620px):** 1 kort per række

## Placeholder-data

Det tredje kort ("Ladakh — det lille Tibet i Indien" med Jakob Rømer Barfod) er et **placeholder-eksempel**. Byt ud med den faktiske 3. relaterede rejse når data er klar.

## Ansvarlig

Design af Stine Marie Simonsen. Fri til at kontakte hvis noget mangler eller skal forklares nærmere.
