# Configuratore Preventivi — Foto & Video Matrimonio

Pagina singola, gira in qualsiasi browser. Nessuna installazione, nessun server obbligatorio:
basta aprire `index.html` con doppio clic (o `Apri.bat`).

## Cosa fa

- Modulo dati evento con controlli veri (email, telefono, data non passata).
- Pacchetto base + extra + operatori aggiuntivi + servizi partner.
- Totale che si aggiorna a ogni clic, con il dettaglio riga per riga.
- Le voci che non c'entrano col pacchetto scelto spariscono da sole
  (es. le riprese drone non compaiono su "Solo Foto").
- La bozza resta salvata nel browser: se chiudi e riapri, ritrovi tutto.
- "Invia il preventivo" apre il riepilogo: email precompilata, copia, `.txt`, stampa/PDF.

## Dove si toccano i prezzi

Tutto in un blocco solo, dentro `index.html`, in cima allo `<script>`:

- `STUDIO` → nome dello studio e email che riceve i preventivi.
- `LISTINO.pacchetti` → i tre pacchetti base.
- `LISTINO.extra` → gli extra. `pacchetti: ["fv","foto","video"]` dice per quali
  pacchetti base la voce ha senso.
- `LISTINO.operatori` → prezzo unitario e massimo.
- `LISTINO.partner` → servizi dei partner esterni.
- `LISTINO.campi` → i campi del modulo dati evento.

Aggiungere una voce nuova = aggiungere una riga a quella lista. Il resto si disegna da solo.

Colori, misure e font stanno tutti nelle variabili `:root` in cima al `<style>`.

## Quello che ancora non c'è

L'invio è lato browser (mailto / copia / file). Per ricevere i preventivi
direttamente in casella senza passare dal programma di posta del cliente serve
un piccolo backend (o un servizio tipo Formspree): mezz'ora di lavoro quando serve.

## Prezzi da confermare

Presi dagli screenshot. Due li ho dedotti:
- **Foto + Video € 2500** — nello screenshot la pillola diceva "da € 1500" ma il totale
  con 2+2 operatori extra faceva € 3500, che torna solo con base 2500.
- **Piattaforma Selfie 360 – 4 ore € 500** — la seconda riga partner era tagliata fuori dalla foto.
