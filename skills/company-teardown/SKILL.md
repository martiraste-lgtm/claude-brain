---
name: company-teardown
description: Produce analisi giornalistiche long-form di aziende reali (startup, scale-up, unicorni) per la rubrica Company Teardown della newsletter "da 0 al PMF". Copre origini, acquisizione primi clienti, positioning, GTM evolution, e — opzionalmente — unit economics e salute finanziaria. Usa quando l'utente dice "fai il teardown di [azienda]", "analisi company teardown", "scrivi il teardown di [azienda]", "rubrica teardown", "analisi [azienda] per la newsletter".
license: MIT
metadata:
  author: Stefano Martiradonna
  version: 1.0.0
---

# Company Teardown

## Overview

Skill per la rubrica "Company Teardown" della newsletter "da 0 al PMF". Produce analisi editoriali di aziende reali basate su fatti verificati: origini, acquisizione primi clienti, positioning, GTM evolution, e — quando i dati lo permettono — unit economics e salute finanziaria.

Non è un case study per outreach (usa `case-study-creator`). Non è un'analisi strategica in astratto (usa `strategic-advisor`). Non è un'analisi del vettore di crescita di un brand consumer (usa `how-small-brands-growth`). È un pezzo editoriale lungo-form costruito su ricerca verificata, con una narrativa ad atti cronologici e un angolo editoriale dichiarato.

**Prima di procedere:** leggi tutti i file in `references/`.

---

## Instructions

### Fase 1 — Intake & Verifica

1. Leggi tutto il materiale condiviso dall'utente (articoli, note, appunti, dati grezzi, link)
2. Identifica i claim che richiedono verifica attiva: round di funding, date chiave, revenue dichiarate, milestones di prodotto, composizione del team fondatore, acquisizioni
3. Esegui ricerche attive con stack progressivo:
   - **WebSearch + WebFetch**: fonti primarie (sito ufficiale, blog, comunicati stampa, articoli di stampa)
   - **Apify actors** se WebSearch non è sufficiente: cerca actor per Crunchbase, LinkedIn company pages, SimilarWeb, PitchBook, G2 — per dati strutturati che non emergono da ricerca semplice
4. Per ogni claim critico, classifica:
   - ✅ Verificato con fonte citata
   - ⚠️ Non verificabile pubblicamente — segnalato, andrà dichiarato nel testo
   - ❌ Contraddice le fonti trovate — richiede chiarimento dall'utente
5. Mostra la tabella di verifica all'utente
6. Se ci sono ❌ chiedi all'utente di risolvere prima di procedere

Consulta `references/verification-checklist.md` per i dettagli su cosa verificare per ogni categoria di dato.

### Fase 2 — Domande di sviluppo

Fai massimo 5 domande, divise in tre blocchi:

**Focus narrativo:**
- Quale arco temporale vuoi enfatizzare? (0→PMF / PMF→growth / full arc / un momento specifico)
- Ci sono episodi, scelte o turning point che vuoi approfondire e che non sono nelle fonti pubbliche?

**Angolo editoriale:**
- Che POV vuoi adottare? (neutro investigativo / ammirazione / critico / "cosa avrei fatto diversamente")
- C'è qualcosa di non ovvio o contro-intuitivo sull'azienda che vuoi portare in primo piano?

**Sezione finanziaria:**
- Includi l'analisi dei numeri (revenue, EBITDA, gross margin, unit economics, scenari)?
- Se sì: quali metriche e con che profondità?

### Fase 3 — Outline

Proponi la struttura basata sulle risposte della Fase 2. Struttura default:

1. **Hook** — 3-5 righe: numero singolo, paradosso o contraddizione che crea tensione immediata
2. **Frame investigativo** — 1 paragrafo: come hai raccolto le informazioni e cosa risponde il pezzo
3. **Atti cronologici** — da 4 a 8 atti con titolo + anni nel titolo (es. "ATTO 2 — Il network (2016–2019)"), ognuno con: narrative dei fatti chiave + interpretazione strategica del momento
4. **[Opzionale] Facciamo i conti** — sezione separata con: assunzioni esplicite, 3 scenari con implicazioni pratiche
5. **[Opzionale] Opportunità adiacenti** — mercati non esplorati ma accessibili con il network esistente
6. **Closing synthesis** — ritorna alla domanda o paradosso dell'apertura, verdict, apertura verso il futuro

Attendi la conferma dell'utente prima di scrivere il draft.

Consulta `references/structure.md` per le specifiche di ogni sezione.

### Fase 4 — Draft completo

1. Segui le linee guida in `references/narrative-guide.md`
2. Rispetta lo stile in `~/.claude/skills/newsletter-writer/references/style-guide.md`
3. Lunghezza target: 3500–5000 parole
4. Segna i dati incerti con `[DA VERIFICARE]` nel testo
5. Dati finanziari: sempre con fonte inline es. "secondo il bilancio 2023 depositato al MISE" o "come dichiarato dal CEO in un'intervista a Il Sole 24 Ore"
6. Salva il file in `articoli/Company-Teardown-[NomeAzienda]-[Anno].md` nel progetto System-content-flywheel

### Fase 5 — Revisione editoriale

1. Proponi 3-5 titoli alternativi + sottotitolo per ciascuno
2. Breve analisi strutturale:
   - Cosa funziona bene
   - Cosa è debole o da sviluppare
   - Un suggerimento editoriale finale

---

## Examples

### Example 1: Teardown full arc con analisi finanziaria

**User says:** "fai il teardown di Satispay per la mia newsletter"

**Actions:**
1. Fase 1 — Verifica: WebSearch su round di funding, bilanci, date lancio, fondatori → tabella ✅/⚠️/❌
2. Fase 2 — Domande: arco temporale? (full arc), POV? (neutro investigativo), finanza? (sì, con scenari)
3. Fase 3 — Outline: 7 atti cronologici (2013–2026) + sezione "Facciamo i conti" + closing synthesis
4. Fase 4 — Draft: ~4500 parole, salvato in `articoli/Company-Teardown-Satispay-2026-05.md`
5. Fase 5 — Revisione: 4 titoli alternativi + analisi strutturale

**Result:** Articolo completo, verificato, con sezione finanziaria e verdict finale

### Example 2: Teardown focalizzato su 0→PMF, no finanza

**User says:** "scrivi il teardown di Figma — focus su come hanno acquisito i primi clienti, senza la parte numeri"

**Actions:**
1. Fase 1 — Verifica: founding story, key hires, beta timeline, prime partnership, product milestones
2. Fase 2 — Domande: conferma foco su 0→PMF, salta la sezione finanziaria
3. Fase 3 — Outline: 5 atti (2012–2020 circa) + no "Facciamo i conti"
4. Fase 4 — Draft: ~3500 parole, focus su community-led growth e PLG motion
5. Fase 5 — Revisione: 3 titoli + analisi

**Result:** Articolo narrativo senza analisi finanziaria

---

## Troubleshooting

### I dati finanziari non sono verificabili

**Causa:** L'azienda è privata e non deposita bilanci pubblici accessibili
**Soluzione:** Segna nella tabella ⚠️. Usa fonti secondarie: interviste al CEO, press release, stime di settore con fonte dichiarata. Dichiara nel testo l'incertezza con attributione ("secondo quanto dichiarato dal CEO in un'intervista a..."). Non inventare mai numeri.

### Il materiale condiviso è troppo scarso per un articolo completo

**Causa:** L'utente ha fornito solo appunti iniziali senza ricerca strutturata
**Soluzione:** Usa la Fase 1 per fare ricerca attiva autonoma (WebSearch + Apify). In Fase 2 chiedi se ci sono episodi o conoscenze dirette che non emergono dalle fonti pubbliche.

### L'azienda è internazionale e ha poca coverage in italiano

**Causa:** Startup straniera con documentazione solo in inglese
**Soluzione:** Scrivi l'articolo in italiano, cita le fonti in lingua originale. Include quote in inglese se rilevanti, con traduzione contestuale nel testo.

### Non riesco a distinguere questo teardown da un article di `how-small-brands-growth`

**Criterio:** `company-teardown` parte dai fatti verificati e costruisce una narrativa editoriale su una singola azienda reale. `how-small-brands-growth` applica il framework dei 5 vettori di disruption (Kinner) per diagnosticare o valutare la strategia di crescita di un brand consumer. Non si sovrappongono.
