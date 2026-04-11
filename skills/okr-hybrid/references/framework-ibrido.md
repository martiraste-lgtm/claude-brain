# Framework Ibrido OKR + NCT — Struttura Completa

## Origine e Logica del Framework

Il framework nasce da due limiti complementari:

**OKR classici (mancano di):**
- Contesto strategico (il WHY è assente o opzionale)
- Determinismo: il target 50-70% crea ambiguità su cosa sarà fatto
- Guardrail sistematici (il Backstop KR è puntuale, non strutturale)
- Distinzione esplicita Leading/Lagging
- Warm start: i team iniziano il ciclo "a freddo"

**NCT di Ravi Mehta (mancano di):**
- Meccanismo di cascata / allineamento multi-team
- Guardrail metrici sistematici (Health Metrics)
- Formula tecnica precisa per i Commitments (baseline → target)
- Distinzione Leading/Lagging
- Strumento per l'ambizione (Moonshot)

**Il framework ibrido risolve entrambi** aggiungendo Health Metrics come layer dedicato e rendendo esplicita la distinzione Leading/Lagging + Frontier Stage in ogni Commitment.

---

## I 6 Layer del Framework

### Layer 0 — Narrative
*Origine: NCT, potenziata con WHY + WHY NOW degli OKR*

Viene PRIMA dell'Objective. Definisce il WHY prima del DOVE.

**Cosa deve contenere:**
1. Cosa vuole ottenere il team in questo ciclo
2. Perché è prioritario ADESSO (WHY NOW — non solo importante, ma urgente in questo momento)
3. Cosa abbiamo imparato di recente che ci ha portato qui
4. Come si inserisce nella strategia annuale o nella Company vision

**Lunghezza**: 2-4 frasi. Non un paragrafo di marketing, non un bullet list.

**Test**: se qualcuno legge la Narrative senza conoscere l'azienda, capisce la priorità strategica e il motivo della scelta temporale? Se no, manca qualcosa.

---

### Layer 1 — Objective
*Origine: OKR classici*

Sintesi qualitativa della Narrative. Deve essere **derivabile** dalla Narrative — se non lo è, o la Narrative è incompleta o l'Objective è arbitrario.

**Formula**: Verbo + area di miglioramento + (deadline) + (persona accountable)

**Verbi per categoria**:
- Crescita: aumentare, sviluppare, potenziare, accrescere, raggiungere, accelerare, espandere
- Stabilità: mantenere, stabilizzare, consolidare, rientrare, preservare
- Riduzione: diminuire, ridurre, contenere, abbassare, limitare

**Aggiungere sempre WHY e WHY NOW**:
```
Objective: [formula]
WHY: [perché questo obiettivo è necessario — ragionamento causale]
WHY NOW: [perché questo quarter e non il prossimo]
```

---

### Layer 2 — Health Metrics *(layer nuovo — mancante in entrambi i framework originali)*

Metriche che NON devono peggiorare mentre si inseguono i Commitments.

**Differenza critica rispetto ai Commitments**:
- Commitments = traguardi da raggiungere (target positivo, si vuole muovere la metrica)
- Health Metrics = soglie da non violare (floor o ceiling, non si vuole muoverle in senso negativo)

**Quante**: 2-3. Non di più — diventano burocrazia.

**Formato**: `[Metrica] deve rimanere [≥/≤] [soglia] per tutta la durata del ciclo`

**Come sceglierle**: chiedi "quali metriche potrebbero deteriorarsi se ottimizziamo i Commitments in modo aggressivo?" Le Health Metrics proteggono quelle vulnerabilità.

**Esempi pratici**:
- `CAC deve rimanere ≤ €180 per tutto Q2` (protegge la profittabilità mentre si scala la pipeline)
- `NPS deve rimanere ≥ 40` (protegge la customer experience mentre si spinge la crescita)
- `Tasso di churn mensile deve rimanere ≤ 2,5%` (protegge la retention mentre si acquisisce)
- `Burn rate mensile deve rimanere ≤ €85K` (protegge la runway mentre si investe in growth)

**Conseguenza se violata**: equivale a mancare un Commitment. Non è un warning, è un fail del ciclo.

---

### Layer 3 — Commitments
*Origine: NCT, con formula OKR + etichette Leading/Lagging + Frontier Stage*

**3-4 goal, target 100% completion** (non 50-70%).

Il termine "Commitment" è deliberato: le persone prendono sul serio i propri impegni. "OKR ambiziosi" incoraggia il wishful thinking. "Commitment" riporta al pragmatico e all'achievable.

#### Perché 100% e non 50-70%

Il target 50-70% degli OKR crea una "zone of confusion":
- Leadership e team non sanno mai cosa sarà fatto a fine quarter
- Quando si manca a 60%, non è chiaro se è un successo (si stava mirando alto) o un fallimento
- Rende difficile il course correction durante il ciclo

Con i Commitments al 100%: se il team è al 40% a metà ciclo, è un segnale chiaro che qualcosa non va e va corretto ora, non a fine quarter.

#### Etichetta Leading/Lagging

**Leading** (predittivi):
- Misurano input o comportamenti che causano il risultato
- Azionabili nel ciclo corrente
- Esempi: conversion rate, adoption rate, numero di esperimenti lanciati, tempo al valore

**Lagging** (risultati):
- Misurano l'output o l'impatto finale
- Spesso ritardati rispetto alle azioni
- Esempi: revenue, ARR, retention, churn, NPS

**Regola**: un set di soli Lagging misura il passato. Un set di soli Leading non dimostra impatto business. Il bilanciamento target: 1-2 Leading + 1-2 Lagging.

#### Frontier Stage (da Ravi Mehta)

Il tipo di Commitment giusto dipende da dove si trova il team nel ciclo di comprensione del problema. Vedi `frontier-stages.md` per la guida completa.

Sintesi rapida:
- `[Understanding]` → non sai quali leve muovere → goal qualitativo o ricerca
- `[Dependency]` → sai le leve, devi validare risorse/capabilities → goal di setup/deliverable
- `[Execution]` → hai le risorse, devi dimostrare esecuzione → goal di output
- `[Strategic]` → hai prove causali → goal di outcome con metriche

**Errore frequente**: mettere goal di outcome (Strategic) quando si è in realtà a Understanding o Execution. Genera frustrazione e manca il Commitment per ragioni strutturali, non di execution.

#### Moonshot (opzionale)

1 solo Commitment al 60-70%, etichettato `[Moonshot]`. Funzione: restituire l'ambizione come leva motivazionale senza inquinare il determinismo dei Commitments core. Se si manca il Moonshot, non è un fallimento — è informazione.

---

### Layer 4 — Initiatives
*Origine: OKR classici, con aggiunta di ipotesi causale esplicita*

Gruppi di attività che secondo le migliori ipotesi del team porteranno al raggiungimento di un Commitment.

**Formato con ipotesi causale**:
`[Iniziativa] → ipotesi: [meccanismo causale atteso]`

La formulazione dell'ipotesi causale serve a due cose:
1. Verifica che l'iniziativa sia davvero collegata al Commitment (non è un'attività random)
2. Crea una struttura di apprendimento: se si esegue l'iniziativa e il Commitment non si muove, l'ipotesi era sbagliata

Se non si riesce a formulare l'ipotesi causale, è una Task, non un'Iniziativa.

---

### Layer 5 — Tasks
*Origine: NCT (warm start) + OKR*

Lista di partenza delle attività concrete per ogni Iniziativa.

**Tre regole**:
1. Sono fluide — possono cambiare durante il ciclo senza che sia un problema
2. Non sono goal in sé — completarle non equivale a raggiungere i Commitments
3. Danno un warm start — il team non inizia il ciclo a freddo

**Test**: se il team non riesce a listare nemmeno 3-4 Tasks per un Commitment, probabilmente il Commitment è troppo vago o il Frontier Stage è sbagliato.

---

## Struttura Cascata

### Principio: Align, don't cascade

Gli OKR non definiscono la strategia aziendale — ne sono ispirati. Non cascadare OKR meccanicamente (Company KR → Team Objective). Allineare i goal.

**Meccanismo corretto**:
```
Company Narrative + Company Commitments (Lagging)
         ↓
Alimentano la Narrative del Team
         ↓
Team costruisce il proprio Objective dalla propria Narrative
         ↓
Team definisce Commitments con almeno 1 Leading
che predice il Company Lagging
```

**Perché non cascadare direttamente**: il Company KR è spesso un Lagging (revenue, retention). Se diventa automaticamente l'Objective del team, il team non ha spazio per ragionare su quali leve azionare. La Narrative del team deve rispondere alla domanda "come contribuiamo noi a quel risultato?" — e questa risposta richiede ragionamento, non traduzione meccanica.

### Livelli temporali

```
Mission & Vision (5-10 anni)
         ↓
Annual Strategic Goals (annuale)
         ↓
OKR / NCT Trimestrali
         ↓
Tasks & Initiatives (settimanale/giornaliero)
```

I Commitments trimestrali non si derivano direttamente dalla Vision — si derivano dagli Annual Strategic Goals. Senza questo layer intermedio, i goal trimestrali tendono a essere troppo astratti o troppo operativi.

---

## Il Ciclo Virtuoso (vs Vizioso)

**Ciclo vizioso degli OKR mal fatti**:
Over Plan → Over Commit → Under Execute → Under Track → Under Perform → Raise the Bar (ancora) → riparte

**Ciclo virtuoso degli NCT/OKR ibridi**:
Plan (capendo come il lavoro scala a risultati strategici) → Commit (goal ambiziosi ma achievable) → Execute (su un piano credibile) → Track (e aggiustare durante il ciclo) → Perform (il team si sente empowered) → Raise the Bar (spontaneamente)

Il cambiamento chiave: dal "set it and forget it" al tracking attivo + course correction durante il ciclo.
