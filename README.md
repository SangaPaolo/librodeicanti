# Pagina per condividere le liste

WhatsApp rende cliccabili solo i link `https://`. Questa pagina riceve il link
della lista (`https://…/?t=Titolo&s=12.5.33`) e apre l'app con la lista.
La lista viaggia tutta dentro il link: la pagina non salva e non invia nulla.

## Pubblicarla gratis con GitHub Pages

1. Su GitHub crea un repository pubblico, per esempio `librodeicanti-liste`.
2. Caricaci i file di questa cartella: `index.html` (liste condivise),
   `termini.html` e `privacy.html` (richiesti dagli store per l'abbonamento).
3. Settings → Pages → Branch: `main`, cartella `/ (root)` → Save.
4. Dopo un minuto la pagina è su `https://<tuo-utente>.github.io/librodeicanti-liste/`.
5. Metti quell'indirizzo in `.env.local`:
   ```
   EXPO_PUBLIC_SHARE_URL=https://<tuo-utente>.github.io/librodeicanti-liste
   ```
6. Riavvia l'app (`npx expo start --clear`): i link condivisi useranno la pagina.

Senza questa variabile l'app condivide il proprio link (`librodeicanti://…`):
il QR code funziona lo stesso (la fotocamera apre l'app), ma in WhatsApp il
link non è cliccabile.

## Più avanti

Con l'account Apple Developer e un dominio proprio si possono attivare gli
Universal Links / App Links: toccando il link si apre direttamente l'app,
senza passare dalla pagina.
