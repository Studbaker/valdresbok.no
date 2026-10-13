# valdresbok.no

Forlagssiden for humorromanene fra Valdresbok.no. Siden er én fil, `index.html`, pluss omslagsbildene i mappa `img/`. Den publiseres automatisk med GitHub Pages på https://valdresbok.no hver gang noe lagres i `main`.

## Redigere tekst rett i GitHub

1. Åpne `index.html` her i repoet og trykk på blyanten (**Edit this file**) øverst til høyre.
2. Nesten alt innhold ligger i to lister øverst i `<script>`-delen:
   - `FORLAG` – forlagsnavn, e-post, pris og lenka til påmeldingsskjemaet (Google Sheets).
   - `BOKER` – én blokk per bok.
   Tekstene om forfatteren, signerte bøker og bokhandlere står som vanlig HTML lenger opp i fila (søk etter `id="forfatteren"` og `id="signert"`).
3. Endre teksten mellom anførselstegnene. Pass på at hver linje fortsatt slutter med komma, og at anførselstegn inne i en tekst skrives som «» i stedet for ".
4. Trykk **Commit changes…**, skriv en kort melding og trykk **Commit changes** igjen. Siden er oppdatert etter et minutt eller to.

## Legge til en ny bok

1. Last opp omslaget først: åpne mappa `img/`, trykk **Add file → Upload files**. Lag to versjoner med samme navn, for eksempel `img/elefanten.jpg` (vanlig, ca. 600 px bred) og `img/elefanten-stor.jpg` (stor, vises når man klikker på omslaget).
2. Åpne `index.html`, finn `const BOKER = [` og kopier en eksisterende bokblokk, fra `{` til og med `},`. Lim den inn der boka skal stå.
3. Fyll inn feltene:
   - `id` – kort navn uten mellomrom og æøå, for eksempel `"elefanten"`.
   - `tittel` (og eventuelt `undertittel`), `humorlinje`.
   - `status` – `"ute"` (til salgs), `"kommer"` (vises under «Kommer» med påmeldingsfelt) eller `"skjult"` (ligger klar, vises ikke).
   - For bøker som kommer: `lanseres: "Måned ÅÅÅÅ"` og `kort` (omtalen).
   - For bøker som er ute: `utgitt`, `isbn`, `hook`, `tekst` (liste med avsnitt), `sluttlinje` og `lenker` (BoD, Ark, Norli, Adlibris, lydbok – `null` skjules).
   - `omslag: "img/elefanten.jpg"`, eller `null` hvis omslaget ikke er klart (da vises et tekstomslag).
4. Commit som over. Den nyeste boka med status `"ute"` vises automatisk øverst på forsiden.

Bøkene som allerede ligger med status `"skjult"` blir synlige ved å endre status til `"kommer"` og legge inn omslag.

## Ikke rør

- `CNAME` – må inneholde `valdresbok.no`, ellers slutter domenet å virke.
