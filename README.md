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

- **Tredje kort** (Ladakh / Jakob Rømer Barfod) er en placeholder-eksempel — byt ud med den faktiske 3. relaterede rejse
- **Sprite'en** `rejsetyper.svg` har seks 40×40 tiles (kultur, safari, familie, bjerg, maler, trekking) og bruges via `background-position`
- **JavaScript:** ingen (statisk mockup)
- **Responsivt:** 3 kort → 2 kort → 1 kort ved 900px og 620px
