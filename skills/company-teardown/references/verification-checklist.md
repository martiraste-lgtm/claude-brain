# Checklist di verifica — Company Teardown

Cosa verificare, come verificarlo, e come gestire l'incertezza nel testo.

---

## Stack di strumenti (usare in ordine progressivo)

### Step 1 — WebSearch
Primo tentativo per qualsiasi dato. Priorità alle fonti primarie:
- Sito ufficiale dell'azienda
- Comunicati stampa
- Blog ufficiale
- Interviste al CEO / fondatori su testate note (TechCrunch, Il Sole 24 Ore, Corriere, Wired)
- Announce dei round (spesso su LinkedIn + press release)

### Step 2 — WebFetch
Quando WebSearch restituisce titoli ma non dati: fetch della pagina per leggere il contenuto completo.
Utile per:
- Pagine di bilanci pubblici
- Articoli paywall parzialmente leggibili
- Press release con numeri dettagliati

### Step 3 — Apify actors
Quando i dati non emergono da ricerca semplice. Cercare actor adatti per:

| Dato cercato | Actor consigliato |
|---|---|
| Funding rounds, valutazioni | Actor per Crunchbase |
| Profilo aziendale, dipendenti | Actor per LinkedIn Company Pages |
| Traffico web, ranking | Actor per SimilarWeb |
| Recensioni prodotto, rating | Actor per G2, Capterra, Trustpilot |
| Metriche App Store | Actor per App Store / Play Store |

Per trovare actor: usa `mcp__apify__search-actors` con query pertinente (es. "crunchbase funding", "linkedin company").

---

## Categorie di dati e cosa verificare

### Founding team
- Nome corretto di tutti i co-fondatori
- Ruoli al momento della fondazione (non quelli attuali)
- Background rilevante (precedenti esperienze, università, settore)
- Data e luogo di fondazione (città, non solo paese)
- Fonte: Crunchbase, LinkedIn personale, interviste fondatori

### Fundraising
Per ogni round:
- Importo (EUR o USD, specificare)
- Tipologia (pre-seed, seed, Series A, B, C...)
- Data di chiusura (non di annuncio)
- Lead investor
- Investitori partecipanti
- Valutazione post-money (se dichiarata)
- Fonte: Crunchbase, comunicato ufficiale, TechCrunch/dealroom

**Attenzione:** gli importi dei round spesso vengono annunciati in tranche. Distingui tra il round totale e la tranche specifica.

### Milestones di prodotto
- Data di lancio del prodotto (versione pubblica, non beta)
- Data di lancio di funzionalità chiave
- Raggiungimento di milestone utenti (100k, 1M, etc.)
- Pivot o cambi di nome/brand
- Espansioni geografiche (paese + data)
- Fonte: blog aziendale, comunicati stampa, archivi di TechCrunch/articoli storici

### Revenue e metriche finanziarie
- Revenue annuale (non ARR stimato se non dichiarato)
- Gross margin
- EBITDA
- Perdita netta
- Cassa e runway
- Fonte: **solo** bilanci depositati (per aziende italiane: MISE/Registro Imprese), dichiarazioni ufficiali del management, investor report pubblici

**Attenzione al livello di certezza:**
- Bilancio depositato → ✅ verificato
- Dichiarazione CEO in intervista → ⚠️ dichiarato, cita la fonte
- Stima di terzi (analisti, media) → ⚠️ segnala come stima
- Numero che non trovi da nessuna parte → ❌ o `[DA VERIFICARE]`

### Metriche operative
- Utenti registrati vs. utenti attivi (distinzione critica — le aziende comunicano quasi sempre registrati)
- GMV / volume transato
- Numero di merchant / clienti B2B
- Churn rate
- Fonte: comunicati, interviste, report pubblici

**Nota:** Le metriche operative sono spesso non verificabili in modo indipendente. Usa sempre l'attribuzione ("come dichiarato dall'azienda").

### Team e struttura organizzativa
- Numero di dipendenti (range o dato esatto)
- Sede principale e uffici secondari
- Acquisizioni (aziende acquisite, anno, importo se dichiarato)
- CEO attuale e storia delle leadership (se ci sono stati cambi)
- Fonte: LinkedIn Company Page, comunicati

---

## Come classificare ogni claim

| Simbolo | Significato | Come trattare nel testo |
|---------|-------------|-------------------------|
| ✅ | Verificato con fonte primaria | Scrivi il dato con fonte inline |
| ⚠️ | Non verificabile pubblicamente | Usa attribuzione: "come dichiarato da..." o "secondo..." |
| ❌ | Contraddice le fonti trovate | Segnala all'utente, non usare il dato senza chiarimento |

---

## Come segnalare l'incertezza nel draft

### Nel corpo del testo
Durante il draft, usa tag `[DA VERIFICARE]` accanto al dato da controllare:

> "Il GMV totale ha raggiunto 1,2 miliardi nel 2021 [DA VERIFICARE]."

### Nella tabella di verifica (Fase 1)
Presenta una tabella prima di procedere:

| Claim | Fonte trovata | Status |
|-------|---------------|--------|
| Fondati nel 2013 a Torino | Crunchbase + sito | ✅ |
| Series C da 93M a nov 2020 | Comunicato ufficiale | ✅ |
| 5 milioni di utenti fine 2024 | Dichiarazione CEO Corriere | ⚠️ dichiarato |
| Gross margin del 75% | Non trovato | ⚠️ non verificabile |
| Revenue 2023 di 30M | Contraddice bilancio che mostra 28.4M | ❌ |

---

## Dati che non si trovano quasi mai (e come comportarsi)

| Dato | Situazione tipica | Come comportarsi |
|------|-------------------|------------------|
| CAC, LTV, payback period | Non pubblici per default | Non includerli a meno di citazione diretta del CEO |
| Gross margin esatto | Solo se in bilancio o dichiarato | Usa il dato se disponibile, altrimenti ometti |
| NPS, retention rate | Non pubblici per default | Stessa regola del CAC |
| Valutazione pre-money | Raramente dichiarata | Usa solo se è in documenti ufficiali |
| Runway residuo | Calcola da cassa + burn — dichiara che è un tuo calcolo | "Con X di cassa e Y di perdita annua, il runway stimato è Z mesi" |

---

## Fonti italiane utili per aziende italiane

- **Registro Imprese / MISE**: bilanci depositati, struttura societaria, sede legale
- **startup.registroimprese.it**: schede startup innovative
- **Spaghetti Startups**: database funding italiano
- **Dealroom**: round europei con dati strutturati
- **Il Sole 24 Ore / Corriere della Sera economia**: archivio interviste CEO italiani
- **Startupbusiness.it**: news funding Italia
