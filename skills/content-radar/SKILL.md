---
name: content-radar
description: >
  Radar settimanale per la content strategy: monitora i post LinkedIn recenti degli autori di
  riferimento (watchlist) + le conversazioni sui temi core (posizionamento B2B, early stage, growth,
  product marketing, GTM), li mappa sui POV del sistema content-flywheel e produce un Google Doc
  con 5-8 angle prioritizzati per post e articoli. Usa quando l'utente dice "content radar",
  "radar settimanale", "lancia il radar", "cosa hanno pubblicato gli autori questa settimana",
  o quando il cron settimanale lo invoca. NON aggiorna la knowledge base: propone solo candidati.
---

# Content Radar — loop settimanale autori + temi

Scopo: alimentare la produzione editoriale di Stefano (post LinkedIn + articoli Substack) con segnali
freschi, già tradotti in angle collegati ai SUOI core argument. Non è rassegna stampa: ogni output
deve superare il test "questo serve a scalare un POV di Stefano?".

**Working directory attesa:** il repo `System-content-flywheel`. Se non ci sei, chiedila o usa
`c:\Users\Utente\Documents\System-content-flywheel`.

**Config:** autori e temi stanno in `references/watchlist.md` (in questa cartella skill).
Modificare quella, non questo workflow.

---

## Fase 0 — Setup contesto

1. `git pull` nel repo System-content-flywheel (il sistema è cross-surface).
2. Leggi da `knowledge/foundation/`: `pov.md` (POV-master + sotto-POV), `content-strategy.md`
   (5 tipi di contenuto, trigger), `audience.md` (buyer, convinzioni, lessico). Questi sono i core
   argument contro cui mappare TUTTO.
3. Leggi `knowledge/hypotheses/active.md` (per la sezione "Segnali per la knowledge").
4. Determina la settimana ISO corrente (`YYYY-Wxx`) e la finestra: ultimi 7 giorni.
5. Leggi `references/watchlist.md` di questa skill: lista autori + temi + query.

## Fase 1 — Radar autori (Chrome MCP)

Per ogni autore della watchlist:

1. Naviga `https://www.linkedin.com/in/[handle]/recent-activity/all/` con Chrome MCP
   (browser dell'utente, già loggato).
2. Estrai i post degli **ultimi 7 giorni**: hook (testo prima del "…altro"), corpo se rilevante,
   formato (testo / carosello / immagine / video), tema trattato, engagement se visibile
   (reactions, commenti).
3. **Regole anti-rumore:** max 3-4 post rilevanti per autore · skip repost senza commento,
   giveaway "commenta per ricevere", post puramente promozionali · se l'autore non ha pubblicato
   nella finestra, scrivilo e passa oltre.
4. **Se un profilo non carica** (rate limit, login scaduto, layout cambiato): annota nel report
   (sezione Note di processo) e continua — mai bloccare il run per un profilo.

## Fase 2 — Radar temi (WebSearch)

Per ognuno dei temi della watchlist: 1-2 ricerche mirate su cosa è uscito negli **ultimi 7-10 giorni**
(newsletter di settore, ricerche/report con dati, dibattiti, take contrarian). Usa le query suggerite
nella watchlist come base, adattandole all'attualità.

**Filtro:** scarta tutto ciò che non è collegabile ai core argument (test del generico: se il segnale
potrebbe interessare qualsiasi marketer, non è un segnale — è rumore).

## Fase 3 — Sintesi editoriale (il cuore del radar)

Per ogni segnale sopravvissuto al filtro, mappa TRE coordinate:

- **Quale POV scala** → POV-master (accumulo) o sotto-POV 1-3 (reframe madre / sequenza invertita /
  moltiplicatori) da `pov.md`. Un segnale che non scala nessun POV si scarta o finisce al massimo
  tra i "Segnali per la knowledge".
- **Quale tipo di contenuto** → Opinion / POV-Framework / Case-Teardown / Backstory
  (da `content-strategy.md`, con lo stadio di awareness che muove).
- **Quale trigger del buyer aggancia** → dai 4 tipi in `audience.md` (dolore / evento positivo /
  esterno / transizione di fase).

Poi produci **5-8 angle prioritizzati** (mai di più — la scarsità è il valore). Per ogni angle:

1. **Titolo/hook proposto** (in italiano, nella voce di Stefano: diretto, specifico, mai guru)
2. **Formato consigliato**: post LinkedIn / articolo Substack / infografica / combinazione hub&spoke
3. **Perché ora**: il segnale che lo rende attuale questa settimana
4. **Le 3 coordinate** (POV · tipo · trigger)
5. **Fonte**: link al post dell'autore o alla risorsa

Ordina per priorità: prima gli angle che (a) scalano il POV-master, (b) hanno un aggancio d'attualità
forte, (c) coprono tipi di contenuto diversi tra loro (variety dentro LinkedIn).

## Fase 4 — Report su Google Doc

Crea un Google Doc via Google Drive MCP, titolo: `Content Radar — Settimana [YYYY-Wxx]`.
(Cartella di destinazione: se l'utente ne ha indicata una, usala; altrimenti root di Drive.)

Struttura fissa del Doc (in italiano):

1. **Executive summary** — 3 righe: il tema della settimana, l'angle più forte, cosa ignorare.
2. **Cosa hanno detto gli autori** — per autore: temi trattati + il post più notevole con perché.
3. **Cosa gira sui temi core** — segnali dalle ricerche, con fonte.
4. **Gli angle pronti per te (5-8, prioritizzati)** — il cuore, formato della Fase 3.
5. **Segnali per la knowledge (solo candidati — nessun file modificato)** — pattern nuovi candidati
   per `references/`, evidenze pro/contro le ipotesi H01-H07. Formato: "CANDIDATO: [cosa] → [dove
   andrebbe] → [perché]". Decide Stefano cosa promuovere.
6. **Note di processo** — profili non raggiunti, limiti dei dati, tempo di run.

## Fase 5 — Log, push e rinnovo del loop

1. Aggiungi una riga a `radar/log.md` nel repo progetto:
   `| [data] | [YYYY-Wxx] | [link al Doc] | [sintesi in 1 riga] |`
2. Commit + push: `chore: content radar — settimana [YYYY-Wxx]` (autorizzato dal CLAUDE.md di progetto).
3. **Rinnova il loop:** registra con CronCreate un job **one-shot** (`recurring: false`) per la
   **domenica successiva alle 10:00** (cron: `0 10 [giorno] [mese] *`), con prompt:
   `Esegui la skill content-radar nella directory c:\Users\Utente\Documents\System-content-flywheel (run settimanale automatico).`
   Se il tool CronCreate non è disponibile nella sessione, caricalo con ToolSearch.
   **Limite noto (essere trasparenti con l'utente):** i cron sono session-only — il rinnovo vale
   solo finché questa sessione di Claude Code resta aperta. Se la sessione si chiude, il fallback
   è il lancio manuale `/content-radar` la domenica (vedi watchlist, "Setup del loop").
4. Chiudi riportando all'utente: link al Doc, i 3 angle top in una riga ciascuno, e conferma del
   rinnovo del cron.

---

## Regole di qualità (non negoziabili)

- **Test del generico:** un angle che potrebbe scrivere qualsiasi consulente si scarta.
- **Ogni angle dichiara il suo POV.** Senza collegamento esplicito, fuori.
- **Mai inventare:** se un dato/post non è verificabile, si omette o si marca come incerto.
- **Voce:** suggerimenti di hook in italiano, mai pomposi, con esempio/numero dove possibile.
- **Scarsità:** meglio 5 angle forti che 12 mediocri.

## Troubleshooting

- **LinkedIn chiede login / blocca:** avvisa l'utente e prosegui con gli autori raggiungibili +
  WebSearch come fallback parziale ("[autore] LinkedIn post [tema] this week").
- **Google Drive MCP non disponibile:** salva il report come `radar/[YYYY-Wxx]-content-radar.md`
  nel repo progetto (fallback), segnala il mancato Doc.
- **Run manuale a metà settimana:** la finestra resta "ultimi 7 giorni" dal giorno del run.
