# Configuratore Preventivi — Foto & Video Matrimonio

### ▶ [Aprilo qui: cammo22.github.io/trisconfig](https://cammo22.github.io/trisconfig/)

Pagina singola, gira in qualsiasi browser. Il cliente compone il servizio del suo
matrimonio e vede il totale aggiornarsi a ogni clic.

In locale funziona uguale: doppio clic su `index.html` (o su `Apri.bat`).
Nessuna installazione, nessun server.

## Cosa fa

- Modulo dati evento con controlli veri (email, telefono, data non passata).
- Pacchetto base + extra + operatori aggiuntivi + servizi partner.
- Totale in tempo reale, con il dettaglio riga per riga.
- Le voci che non c'entrano col pacchetto scelto spariscono da sole
  (es. le riprese drone non compaiono su "Solo Foto").
- La bozza resta salvata nel browser: se chiudi e riapri, ritrovi tutto.
- "Invia il preventivo" apre il riepilogo: email precompilata, copia, `.txt`, stampa/PDF.

## Dove si toccano i prezzi

Tutto in un blocco solo, dentro `index.html`, in cima allo `<script>`:

| | |
|---|---|
| `STUDIO` | nome dello studio ed email che riceve i preventivi |
| `LISTINO.pacchetti` | i tre pacchetti base |
| `LISTINO.extra` | gli extra — `pacchetti: ["fv","foto","video"]` dice per quali pacchetti base la voce ha senso |
| `LISTINO.operatori` | prezzo unitario e numero massimo |
| `LISTINO.partner` | servizi dei partner esterni |
| `LISTINO.campi` | i campi del modulo dati evento |

Aggiungere una voce nuova = aggiungere una riga a quella lista. Il resto si disegna da solo.
Colori, misure e font stanno nelle variabili `:root` in cima allo `<style>`.

## Quello che ancora non c'è

L'invio è lato browser (mailto / copia / file). Per ricevere i preventivi
direttamente in casella, senza passare dal programma di posta del cliente,
serve un piccolo backend (o un servizio tipo Formspree).

## Prezzi da confermare

Presi dagli screenshot del configuratore esistente. Due sono dedotti:

- **Foto + Video € 2500** — la pillola diceva "da € 1500", ma il totale mostrato
  (€ 3500 con 2+2 operatori extra a € 250) torna solo con base 2500.
- **Piattaforma Selfie 360 – 4 ore € 500** — quella riga era tagliata fuori dalla foto.

## Pubblicazione

Il sito esce da `main` tramite il workflow [`.github/workflows/pages.yml`](.github/workflows/pages.yml):
ogni push su `main` ripubblica la pagina.
