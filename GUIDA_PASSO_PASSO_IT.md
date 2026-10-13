# Astra Phoenix Basketball Stats — Kit v6

## Struttura
- `index.html`: compilatore locale. Aprilo con Edge/Chrome.
- `uisp/index.html`: sito pubblico UISP.
- `fip/index.html`: sito pubblico FIP.
- `uisp/data/partite/manifest.json` e `fip/data/partite/manifest.json`: elenchi dei file partita pubblicati.
- Ogni partita viene esportata come un singolo JSON. Non esiste un file giocatori globale.

## Parte 1 — Compilatore
1. Estrai lo ZIP in una cartella.
2. Apri `index.html` con Edge o Chrome.
3. Crea/seleziona una partita e inserisci giocatori ed eventi.
4. Vai in `Archivio e backup`.
5. Usa **Esporta JSON della partita selezionata** per ottenere un file per quella partita.
6. Conserva anche un backup completo dell'archivio locale usando le funzioni di backup esistenti.

I dati inseriti nell'app restano nel browser/dispositivo: esporta i JSON prima di cambiare dispositivo o cancellare i dati del browser.

## Parte 2 — Pubblicare i siti su GitHub Pages
1. Crea un repository GitHub pubblico (es. `astra-phoenix-stats`).
2. Carica il contenuto della cartella `Astra_Phoenix_Basketball_Stats` nella radice del repository.
3. In `Settings → Pages`, scegli la pubblicazione da `main` e cartella `/(root)`.
4. I siti saranno:
   - `https://TUO-USERNAME.github.io/astra-phoenix-stats/uisp/`
   - `https://TUO-USERNAME.github.io/astra-phoenix-stats/fip/`

## Parte 3 — Aggiungere una partita al sito
1. Esporta il JSON della singola partita.
2. Controlla che la competizione sia UISP o FIP.
3. Carica il JSON nella cartella corretta:
   - `uisp/data/partite/` oppure
   - `fip/data/partite/`
4. Apri il corrispondente `manifest.json` e aggiungi un elemento all'array `games`, indicando il nome del file. Esempio:
   `{"file":"2026-10-18_astra_vs_squadraa_UISP.json"}`
5. Salva entrambe le modifiche. Dopo la pubblicazione GitHub Pages, il sito legge la partita dal manifest.

**Importante:** ogni file deve avere un nome univoco. Non caricare una partita UISP nella cartella FIP o viceversa. Se due collaboratori esportano la stessa partita, controlla gli ID e non aggiungere due volte lo stesso incontro.

## Limiti di questa prima versione
- I siti sono statici e pubblici: chiunque abbia il link può consultare i dati pubblicati.
- L'app non invia automaticamente i JSON a GitHub; l'upload e l'aggiornamento del manifest sono manuali.
- Il sito è una prima base di consultazione. Alcune statistiche avanzate e filtri potranno essere migliorati dopo il test con JSON reali.
- Il compilatore esistente usa un formato dati specifico; prova l'esportazione di una partita prima di pubblicare dati reali.
