# Relaterede rejser — mockup

Design-mockup til refresh af "Relaterede rejser"-sektionen på kiplingtravel.dk.

## Preview

- **Live:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/relaterede-rejser-mockup.html
- **Landing:** https://ssleadtime.github.io/Rejseoversigt-Kiplingtravel/

Alt CSS er inline i `relaterede-rejser-mockup.html` — ingen build-step, ingen eksterne stylesheets. Åbn direkte i browser.

## Filer

- `relaterede-rejser-mockup.html` — sektionsmockup
- `Billeder/` — 3 rejsebilleder, 3 rejseleder-portrætter, `rejsetyper.svg` (tema-ikon-sprite)

## Noter

- Layoutet skal genbruges bredt — hele indholdet (rejser, ledere, datoer, temaer) er eksempeldata. Selve mockup'en viser blot komponent-mønsteret, som fyldes dynamisk ind i `.search__results--container` med relevante rejser for den enkelte side.
- **Sprite'en** `rejsetyper.svg` har seks 40×40 tiles (kultur, safari, familie, bjerg, maler, trekking) og bruges via `background-position`
- **JavaScript:** ingen (statisk mockup)
- **Responsivt:** 3 kort → 2 kort → 1 kort ved 900px og 620px
