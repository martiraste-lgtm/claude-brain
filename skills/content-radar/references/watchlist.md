# Content Radar — Watchlist (config)

Questo file è la configurazione del radar: modificare QUI autori, temi e query.
Il workflow sta in `../SKILL.md` e non va toccato per cambiare i target.

Ultima revisione: 2026-07.

---

## Autori da monitorare (LinkedIn)

| Autore | URL profilo | Focus | Perché nel radar |
|--------|-------------|-------|------------------|
| Maja Voje | https://www.linkedin.com/in/majavoje/ | GTM strategy, early stage | Segmento vicino; pattern hook + framework |
| April Dunford | https://www.linkedin.com/in/aprildunford/ | Positioning B2B, architetture multi-product | Fonte primaria del metodo (Obviously Awesome); il pillar architetture deriva da lei |
| Alex Estner | https://www.linkedin.com/in/alexander-estner/ | GTM execution, anchor framework | Fonte del framework anchor; reframe diagnostico |
| Douwe Wester | https://www.linkedin.com/in/douwewester/ | GTM assessment, positioning early stage | Top performer sul reframe; dialoghi con reazione emotiva |
| Rob Kaminski | https://www.linkedin.com/in/heyrobk/ | Positioning & messaging B2B (Fletch) | Fonte del framework H1/homepage; contenuti visual |
| Anthony Pierri | https://www.linkedin.com/in/anthonypierri/ | Homepage messaging B2B (Fletch) | Fonte H1; registro sarcastico su AI hype |
| Pierre Herubel | https://www.linkedin.com/in/pierre-herubel-540b3949/ | Content strategy B2B | Pattern di struttura post + caroselli; engagement alto |

**Percorso post recenti:** `[URL profilo]recent-activity/all/`

## Temi da monitorare (WebSearch)

| Tema | Query base (adattare all'attualità) |
|------|--------------------------------------|
| Posizionamento B2B | "B2B positioning" debate OR framework OR repositioning [settimana corrente] · "positioning mistakes" B2B SaaS |
| Startup early stage | early stage startup GTM OR traction OR first customers [mese corrente] · pre-PMF founder mistakes |
| Startup growth | startup growth stage scaling GTM OR product marketing [mese corrente] · post-PMF growth plateau |
| Product marketing | product marketing trends OR PMM role OR product marketing AI [mese corrente] |
| Go-to-market | go-to-market strategy B2B SaaS [mese corrente] · GTM motion PLG SLG founder-led |

**Lente sempre attiva:** privilegiare segnali collegabili al concept "Accumulo"
(feature bloat, prodotti confusi, tesi di prodotto, architettura di brand, homepage che non converte,
founder bottleneck) — sono i core argument del sistema.

---

## Setup del loop su una nuova macchina (portabilità)

Il radar gira in locale (serve Chrome loggato su LinkedIn + i connector Google Drive).

**Come funziona il trigger (limite reale, documentato):** i cron di Claude Code vivono nella
sessione — se Claude Code è aperto domenica alle 10, il radar parte da solo; se è chiuso, il cron
muore con la sessione. Quindi il pattern operativo è:

1. **Cadenza standard:** domenica mattina apri Claude Code nel repo System-content-flywheel e
   lanci `/content-radar` (10-15 minuti, tutto automatico: LinkedIn → ricerche → Doc → log → push).
2. **Se tieni Claude Code aperto:** ogni run registra il cron della domenica successiva alle 10:00
   (Fase 5 della skill) — parte da solo finché la sessione vive.
3. **Se salti una domenica:** nessun problema — il run manuale usa sempre la finestra "ultimi 7 giorni".

**Prerequisiti:** repo `System-content-flywheel` clonato · Chrome con sessione LinkedIn attiva ·
connector Google Drive abilitato in Claude.
