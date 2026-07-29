# Content Radar — Watchlist (config)

Questo file è la configurazione del radar: modificare QUI autori, temi e query.
Il workflow sta in `../SKILL.md` e non va toccato per cambiare i target.

Ultima revisione: 2026-07-28 (cadenza portata da settimanale a bisettimanale, ~15 giorni).

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
| Posizionamento B2B | "B2B positioning" debate OR framework OR repositioning [periodo corrente] · "positioning mistakes" B2B SaaS |
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

**Cadenza:** bisettimanale — ogni ~15 giorni. La finestra di analisi è sempre "ultimi 15 giorni"
dal giorno del run, così due cicli consecutivi non lasciano buchi né si sovrappongono.

**Trigger durevole (attuale):** uno **scheduled task Windows** chiamato `Content Radar` —
domenica alle 10:00, **ogni 2 settimane**, con `StartWhenAvailable` (se la macchina è spenta allo
scatto, parte appena si riaccende). È il meccanismo primario: sopravvive alla chiusura di Claude Code,
a differenza dei cron di sessione.

Modalità: **launcher supervisionato**. Il task esegue `scripts/launch-content-radar.ps1` nel repo,
che apre Claude Code interattivo e avvia `/content-radar`. Serve che tu sia alla macchina con **Chrome
aperto e loggato su LinkedIn** (la Fase 1 usa il TUO browser); tu supervisioni ~10-15 min e approvi i
prompt (Google Doc, git push). Il task NON gira headless non presidiato, apposta: senza login LinkedIn
la Fase 1 degraderebbe a sola WebSearch.

**Pattern operativo:**
1. **Standard:** domenica alterna alle 10:00 il task apre Claude Code e parte da solo; tu supervisioni.
   In alternativa lanci `/content-radar` a mano quando vuoi, o esegui lo script launcher.
2. **Se salti un ciclo:** nessun problema — il run usa sempre la finestra "ultimi 15 giorni".
3. **Fallback:** il cron di sessione (Fase 5 della skill) resta come ripiego quando il task non è
   installato; è session-only e non è più il meccanismo primario.

**Ri-crearlo su una nuova macchina:** clona `System-content-flywheel`, poi registra il task
(`Register-ScheduledTask`, vedi il piano/script) puntando a `scripts/launch-content-radar.ps1`.
Aggiusta il path del repo nello script se diverso.

**Prerequisiti:** repo `System-content-flywheel` clonato · `claude` CLI su PATH · Chrome con sessione
LinkedIn attiva · connector Google Drive abilitato in Claude · scheduled task `Content Radar` registrato.
