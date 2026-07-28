Sei un agente che monitora settimanalmente i finanziamenti di startup italiane. Oggi è lunedì — esegui il radar settimanale.

STEP 1 — LEGGI LE FONTI (ultimi 7 giorni)

EMAIL (Gmail MCP):
1. Cerca email da mittente contenente "f6s.com" degli ultimi 7 giorni.
   - Leggi il corpo completo del thread
   - Estrai SOLO le startup con sede in Italia o founder italiani — filtra per keyword: "Italy", "Italian", "Milano", "Roma", "Torino", "Firenze", "Bologna", "italian founders", ".it"
   - Ignora tutti gli altri deal internazionali

2. Cerca email con subject "TWIS" da mittente "dealflowit@substack.com" degli ultimi 7 giorni — leggi il corpo completo

WEBSEARCH (fonte principale — eseguita sempre):
3. Cerca: startup italiana seed finanziamento 2026
4. Cerca: `site:bebeez.it startup seed OR pre-seed round finanziamento`
5. Cerca: `site:startupbusiness.it startup seed OR pre-seed funding`
6. Cerca: `site:startupitalia.eu round seed OR pre-seed`
7. Cerca: `site:economyup.it startup seed OR pre-seed round`
8. Cerca: `site:tech.eu italy startup seed OR pre-seed OR "series a" funding`
9. Cerca: `site:sifted.eu italy startup funding seed`
10. Cerca: `site:eu-startups.com italy startup seed funding`

WEB (WebFetch — solo come fallback se WebSearch non restituisce abbastanza risultati):
11. https://dealflowit.niccolosanarico.com — leggi il post più recente (Substack TWIS)
12. https://www.borsaitaliana.it/borsa/notizie/teleborsa/economia

CRITERI DI SELEZIONE — includi SOLO se:
- Startup con sede in Italia o founder italiani
- Round: Pre-seed - Seed - Serie A
- Importo dichiarato tra €200.000 e €10.000.000
- Annuncio degli ultimi 7 giorni

STEP 2 — DEDUPLICAZIONE
Leggi il Google Sheet https://docs.google.com/spreadsheets/d/1dO1fiHyKYrRn1tk_n8hyCPW3zt0rGkVUNozc4tuqCBU/edit?gid=1754620588 via Google Drive MCP e prendi nota di tutti i nomi già presenti nella colonna "Nome Startup".

STEP 3 — SCRIVI I NUOVI DEAL
Per ogni startup trovata NON già presente nello sheet, esegui una chiamata HTTP POST con Bash/curl a:
https://stefano1479.app.n8n.cloud/webhook/startup-radar

Con questo JSON body (una chiamata per startup):
{
  "Nome Startup": "nome della startup",
  "Capitale Ottenuto": "importo in € come stringa (es. 500000)",
  "ARR": "solo se menzionato esplicitamente, altrimenti stringa vuota",
  "Capitale Richiesto": "solo se menzionato esplicitamente, altrimenti stringa vuota",
  "Contatti": "sito web ufficiale o LinkedIn della startup (cerca con WebSearch se non presente nell'articolo)"
}

Esempio curl:
curl -s -X POST https://stefano1479.app.n8n.cloud/webhook/startup-radar -H "Content-Type: application/json" -d '{"Nome Startup": "...", ...}'

Se non trovi nuovi deal che rispettano tutti i criteri, non fare nessuna chiamata POST.
