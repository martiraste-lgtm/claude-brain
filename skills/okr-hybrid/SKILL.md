---
name: okr-hybrid
description: Facilita la definizione, strutturazione e validazione di OKR con il framework ibrido OKR+NCT. Usarlo quando devi costruire goal trimestrali da zero, validare OKR esistenti, o declinare Company OKR in Team OKR. Trigger: "aiutami a definire gli OKR", "crea gli OKR per", "valida questi OKR", "costruiamo i key results", "OKR per il Q[x]", "definisci i goal per", "costruiamo i Commitments", "framework NCT", "review degli OKR", "aiutami con gli obiettivi del team".
license: MIT
metadata:
  author: Utente
  version: 1.0.0
---

## Overview

Framework ibrido che unisce la precisione tecnica degli OKR con il contesto strategico degli NCT (Narrative, Commitments, Tasks) di Ravi Mehta. Aggiunge due layer mancanti a entrambi i framework originali: **Health Metrics** (guardrail sistematici) e la distinzione **Leading/Lagging + Frontier Stage** nei Commitments.

Tre modalità operative:
- **A — Creazione**: costruisci il framework completo da zero
- **B — Validazione**: analisi e diagnosi di OKR esistenti
- **C — Cascata**: declina Company OKR in Team OKR

Leggi sempre `references/framework-ibrido.md` e `references/formule-e-template.md` prima di procedere.

---

## Instructions

### Avvio — Identificare la Modalità

All'attivazione, chiedi:

> "In che modalità vuoi lavorare?
> **A — Creazione**: costruiamo il framework da zero
> **B — Validazione**: analizzo OKR già scritti
> **C — Cascata**: declinare Company OKR in Team OKR"

Se il contesto è già chiaro dal messaggio dell'utente, identifica la modalità senza chiedere.

---

### Modalità A — Creazione da Zero

**Step 1 — Intake contesto**

Raccogli conversazionalmente (non come questionario):
- Chi sta definendo questi OKR? (azienda, team, ruolo)
- A quale livello? (Company / BU / Team / Individuale)
- Quale ciclo? (quarter, semestre)
- Esistono Annual Strategic Goals? Se sì, quali?
- Esistono Company OKR di riferimento da cui derivare?

**Step 2 — Annual Strategic Goals (se mancano)**

Se non esistono strategic goals annuali, definiscili prima degli OKR trimestrali. Gli OKR sono ispirati dalla strategia, non la sostituiscono. Chiedi: "Quali sono i 3-5 obiettivi che questa organizzazione deve raggiungere entro fine anno?"

**Step 3 — Narrative**

Guida la costruzione con queste domande:
1. Cosa vuole ottenere questo team nel ciclo?
2. Perché è prioritario ADESSO? (WHY NOW — non solo perché è importante, ma perché questo quarter)
3. Cosa abbiamo imparato di recente che ci ha portato a questa priorità?
4. Come si inserisce nella strategia annuale o nella Company vision?

Output atteso: 2-4 frasi che coprono tutti e 4 i punti. Se la Narrative non risponde al WHY NOW, non è completa.

**Step 4 — Objective**

Formula: **Verbo + area di miglioramento + (deadline) + (persona accountable)**

Vedi `references/formule-e-template.md` per i verbi per categoria e la sintassi rapida.

L'Objective deve essere derivabile dalla Narrative. Se non lo è, o la Narrative è incompleta o l'Objective è arbitrario.

**Step 5 — Health Metrics**

2-3 metriche che NON devono peggiorare mentre si inseguono i Commitments.

Chiedi: "Quali metriche critiche potrebbero deteriorarsi se il team si focalizza troppo sui Commitments? Cosa non deve rompersi?"

Formato: `[Metrica] deve rimanere [≥/≤] [soglia] per tutta la durata del ciclo`

Violate una Health Metric = equivale a mancare un Commitment. Non sono traguardi — sono guardrail.

**Step 6 — Commitments**

3-4 goal al 100% completion target (non 50-70%). Per ogni Commitment:

1. Assegna etichetta **Leading** o **Lagging** (vedi `references/framework-ibrido.md`)
2. Identifica il **Frontier Stage**: Understanding / Dependency / Execution / Strategic (vedi `references/frontier-stages.md`)
3. Applica la formula: `KPI + direzione + baseline → target + deadline + persona`
4. Verifica la prova causale: "se raggiungo questo Commitment, so con certezza che mi avvicino all'Objective?"

Un set bilanciato ha almeno 1 Leading e 1 Lagging. Se sono tutti Lagging, si misura solo il passato.

**Moonshot opzionale**: 1 solo Commitment al 60-70%, etichettato `[Moonshot]`. Non obbligatorio.

**Step 7 — Initiatives (con ipotesi causale)**

Per ogni Commitment, 2-4 iniziative nel formato:
`[Iniziativa] → ipotesi: [meccanismo causale atteso]`

Se non si riesce a formulare l'ipotesi causale, è una Task, non un'Iniziativa.

**Step 8 — Tasks (warm start)**

Lista di partenza per ogni Iniziativa. Fluide — possono cambiare durante il ciclo. Non sono goal. Completare Tasks ma mancare Commitments = il team ha fallito sull'obiettivo.

**Step 9 — Validation Check**

Esegui automaticamente prima di consegnare il documento finale:

```
[ ] La Narrative risponde a WHY + WHY NOW?
[ ] L'Objective è derivabile dalla Narrative?
[ ] Ci sono almeno 2 Health Metrics definite?
[ ] Ogni Commitment ha etichetta Leading/Lagging?
[ ] Ogni Commitment ha un Frontier Stage assegnato?
[ ] Ci sono almeno 1 Leading e 1 Lagging tra i Commitments?
[ ] I Commitments sono al 100% target?
[ ] Ogni Commitment ha una prova causale verificabile?
[ ] Ogni Iniziativa ha un'ipotesi causale esplicita?
[ ] Le Tasks danno un warm start credibile?
```

Segnala ogni item mancante con il problema specifico e una proposta di correzione.

---

### Modalità B — Validazione OKR Esistenti

Ricevi gli OKR e analizza layer per layer.

**Schema diagnosi** — usa ✅ (corretto) / ⚠️ (migliorabile) / ❌ (problema critico):

1. **Narrative / Contesto strategico**: c'è un WHY? C'è un WHY NOW?
2. **Objective**: è qualitativo? Usa verbo di direzione? È derivato da strategia?
3. **Health Metrics**: esistono guardrail? (Se assenti → ⚠️ sempre)
4. **Key Results / Commitments**: sono outcome o output? Hanno baseline e target? Target al 100% o 50-70%? Distinzione Leading/Lagging presente?
5. **Initiatives**: hanno ipotesi causale o sono solo attività?
6. **Tasks**: danno un warm start?

**Output diagnosi**:
- Valutazione layer per layer
- I 3 problemi più critici da risolvere
- Riscrittura degli elementi con ❌
- Elementi da spostare (es. KR che sono Task, Initiative che è una Task)

---

### Modalità C — Cascata Company → Team

**Principio guida**: non cascadare OKR meccanicamente. Allineare i goal.

Il Company Commitment non diventa automaticamente il Team Objective — lo alimenta.

**Step**:
1. Ricevi i Company OKR
2. Identifica quale Company Commitment è più rilevante per questo team
3. Usa il Company Commitment come INPUT per costruire la Narrative del team
4. Costruisci il Team Objective derivato dalla Narrative
5. Definisci Team Commitments con almeno 1 Leading che predice il Company Lagging

**Weighting Matrix (opzionale — per contesti multi-team)**:
Se ci sono più team da allineare, costruisci una matrice Company Objectives × Core Processes. Punteggio 0-5 per impatto. I nodi 4-5 sono dove costruire OKR; i nodi 0-1 non necessitano goal specifici. Vedi `references/formule-e-template.md` per il template.

---

## Examples

### Esempio A — Creazione Completa (Startup SaaS B2B, Team Marketing, Q2)

**Annual Strategic Goal**: raggiungere 1M ARR entro fine anno (attuale: 500K)

**Narrative**:
"Il team Marketing punta ad accelerare la pipeline qualificata nel Q2 perché l'attuale conversion rate (8% SQL-to-deal) non è sufficiente per raggiungere l'ARR target con il volume corrente di lead. L'analisi delle deal chiuse negli ultimi 60 giorni mostra che i clienti con NPS > 8 hanno un tasso di referral 3x superiore alla media. Priorità adesso perché i 2 nuovi SDR entrano in onboarding a inizio Q2 e serve una pipeline qualificata su cui lavorare dal giorno 1."

**Objective**: Accelerare la generazione di pipeline qualificata entro fine Q2 [Head of Marketing]

**Health Metrics**:
- CAC deve rimanere ≤ €180 per tutta la durata del Q2
- Tasso di disqualifica lead deve rimanere ≤ 40%

**Commitments**:
- C1 `[Leading][Execution]`: MQL generati deve crescere da 45 → 90/mese entro 30 aprile [Head of Marketing]
- C2 `[Lagging][Strategic]`: SQL-to-deal conversion rate deve crescere da 8% → 14% entro fine Q2 [Head of Marketing]
- C3 `[Leading][Dependency]`: Lead scoring operativo entro 30 aprile — binario [RevOps]

**Initiatives**:
- "Attivare canale referral strutturato → ipotesi: clienti NPS>8 convertono referral con tasso 3x, un programma strutturato aumenta MQL qualificati a costo inferiore al paid"
- "Segmentare e riscrivere sequenze nurturing per ICP → ipotesi: messaging generico è il principale driver di bassa conversion SQL, messaging ICP-specifico la migliora del 30-40%"

**Tasks (warm start)**:
- Identificare i 20 clienti NPS>8 e mappare le loro reti
- Scrivere 3 varianti email referral da testare
- Analizzare le 15 deal chiuse negli ultimi 60 giorni e identificare pattern ICP

---

### Esempio B — Validazione (OKR mal scritti)

**Input**:
- Objective: "Migliorare il prodotto per i clienti"
- KR1: "Lanciare 3 nuove feature entro Q2"
- KR2: "Ridurre i bug del 20%"
- KR3: "Fare 10 customer interview"

**Diagnosi**:

Narrative: ❌ Non esiste. Non si capisce perché il prodotto deve migliorare, per quali clienti, in quale direzione strategica.

Objective: ❌ Nessun verbo di direzione. Nessuna deadline. "Migliorare" non è misurabile. Potrebbe significare qualsiasi cosa.

Health Metrics: ⚠️ Assenti. Se il team si focalizza su nuove feature, potrebbe aumentare technical debt o peggiorare la stabilità.

KR1: ❌ Output puro. Non dice se le feature vengono usate, se risolvono un problema, se migliorano una metrica. È una to-do list.

KR2: ⚠️ Lagging, ma manca baseline. "20% di riduzione" rispetto a cosa? Inverificabile senza baseline.

KR3: ❌ Task travestita da KR. Non specifica cosa si vuole imparare né come si misura il successo delle interviste.

**3 problemi critici**: (1) KR1 e KR3 sono output/task, non outcome. (2) Manca il WHY — non si capisce perché questa sia la priorità ora. (3) KR2 non ha baseline — inverificabile.

**Riscrittura KR1**: C1 `[Leading][Execution]`: Tasso di adozione nuove feature (% utenti attivi che usano almeno 1 nuova feature/settimana) deve crescere da 0% → 25% entro fine Q2.

**KR3** → diventa Task sotto Iniziativa "Ricerca qualitativa per identificare top 3 job-to-be-done non coperti dal prodotto".

---

## Troubleshooting

**"I KR sembrano giusti ma qualcosa non funziona"**
Test: chiedi "se raggiungo questo KR, so con certezza che il business è migliorato?" Se la risposta è no o dipende da molti altri fattori, è probabilmente un output travestito da outcome. Vedi `references/anti-patterns.md`.

**"Non riusciamo a trovare la Narrative"**
Causa: si sta cercando di scrivere OKR senza avere strategia. Soluzione: prima definisci gli Annual Strategic Goals. OKR senza strategia sono arbitrari per definizione.

**"Tutti i Commitments vengono Lagging"**
Aggiungi almeno 1 Leading che predice il Lagging principale. Se il Lagging è "aumenta revenue", il Leading potrebbe essere "aumenta conversion rate trial-to-paid" o "riduci sales cycle".

**"Non sappiamo in che Frontier Stage siamo"**
Guida rapida: stai ancora discutendo su cosa misurare → Understanding. Sai cosa misurare ma non hai ancora gli strumenti → Dependency. Hai gli strumenti e stai eseguendo → Execution. Hai prove che la tua ipotesi funziona → Strategic.

**"Le Health Metrics sembrano OKR in più"**
Differenza chiave: i Commitments sono traguardi da raggiungere (target positivo). Le Health Metrics sono soglie da non violare (floor/ceiling). Non hai un target di miglioramento sulla Health Metric — hai solo un limite da non sfondare.

**"Il team vuole mettere tutto al 50-70% come negli OKR classici"**
Il 50-70% crea una zone of confusion: nessuno sa cosa sarà fatto a fine quarter. I Commitments al 100% creano un contratto chiaro e permettono di fare course correction durante il ciclo quando qualcosa non sta andando. Vedi `references/framework-ibrido.md` per l'argomento completo.
