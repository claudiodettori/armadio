# Il mio Armadio: webapp

App per organizzare l'armadio: capi con foto, outfit pronti e calendario della settimana.
Funziona su telefono e computer, si installa come un'app e va anche senza connessione.

## Novità della versione 2

- **Assistente:** nella sezione Settimana, sotto il giorno scelto, trovi tre outfit proposti. Si basano sui capi che metti più spesso, sugli abbinamenti che hai già fatto, sulla stagione e su cosa hai messo ieri. Puoi scegliere l'occasione (lavoro, casual, sera…) e chiedere altre proposte.
- **Diario:** per oggi e per i giorni passati puoi registrare cosa hai indossato, scegliendo i capi uno per uno o da un outfit salvato. Più giorni registri, più le proposte ti somigliano.
- **Capi:** ogni capo mostra quante volte l'hai indossato; puoi ordinare per "Più indossati" o "Meno indossati".

## Dove è pubblicata

Il codice sta su **GitHub** e il sito è servito da **Cloudflare Pages**, collegato al repository:
ogni volta che i file su GitHub cambiano, Cloudflare ripubblica il sito da solo in un minuto circa.

**Collegare Cloudflare la prima volta**
1. Accedi a https://dash.cloudflare.com (account gratuito).
2. Vai su **Workers e Pages** → **Crea** → scheda **Pages** → **Importa un repository Git** (o "Connect to Git").
3. Autorizza GitHub e scegli il repository `armadio`.
4. Impostazioni di build: preset **Nessuno**, comando di build **vuoto**, directory di output **/**.
5. **Salva e distribuisci**. L'indirizzo sarà del tipo `https://armadio.pages.dev`.

**Aggiornare l'app**: basta sostituire i file nel repository GitHub (anche dal sito, con "Add file → Upload files").
Quando cambi i file, cambia anche `VERSIONE` in `sw.js` (es. da `armadio-v2` a `armadio-v3`), così il telefono scarica subito la nuova versione.

**Passare da un altro indirizzo (es. Netlify)**: i dati sono legati all'indirizzo del sito.
Prima di cambiare, dall'app vecchia apri ⚙ → **Esporta backup**; poi nella nuova apri ⚙ → **Importa backup**.

## Installarla sul telefono

- **iPhone (Safari):** apri l'indirizzo → tasto Condividi → "Aggiungi alla schermata Home".
- **Android (Chrome):** apri l'indirizzo → menu ⋮ → "Installa app" (o "Aggiungi a schermata Home").

## Dove finiscono i dati

Capi, foto, outfit e calendario sono salvati **solo sul dispositivo e nel browser** in cui usi l'app.
Non vengono inviati a nessun server.

- Dall'icona ⚙ in alto: **Esporta backup** crea un file `.json` con tutto, foto comprese.
- **Importa backup** lo ricarica, anche su un altro telefono o computer.
- Fai un backup ogni tanto: se cancelli i dati del browser o disinstalli l'app, l'armadio si svuota.

## File

- `index.html`: l'app
- `manifest.webmanifest`, `icons/`: nome e icona per l'installazione
- `sw.js`: funzionamento offline. Se modifichi i file, cambia `VERSIONE` in `sw.js` così i telefoni scaricano la nuova versione.
