---
name: b2b-h1-writer
description: Expert system for writing and evaluating H1 headlines for B2B software homepages using the Fletch framework (Pierri + Kaminsky). Two formulas: H1 = Category + Differentiation, or H1 = JTBD + Differentiation. Trigger when: user wants to write, improve or evaluate an H1 or homepage headline for a software product. Phrases: "scrivi l'H1 per", "come faccio l'headline della homepage", "migliora questa headline", "H1 per B2B", "headline homepage", "valuta questo H1", "non so come formulare il titolo della homepage", "la mia headline non funziona", "come scrivo l'headline", "H1 homepage software".
license: MIT
metadata:
  author: User
  version: 1.0.0
  category: marketing
  tags: [copywriting, homepage, H1, B2B, positioning, Fletch]
---

# B2B H1 Writer

## Overview

Framework Fletch (Pierri + Kaminsky) per scrivere o valutare l'H1 di una homepage B2B software. Due sole formule valide: **Category + Differentiation** oppure **JTBD + Differentiation**. Tutto il resto è fluff che non dice niente a nessuno.

Posizione nella catena: `b2b-positioning-diagnostic` → **`b2b-h1-writer`** → `saas-homepage-analyzer`

---

## Instructions

### Modalità

- **Modo A — Scrittura**: dato un prodotto (con o senza positioning già fatto), genera H1
- **Modo B — Valutazione**: dato un H1 esistente, diagnostica e suggerisci fix

Rileva il modo dal contesto. Se l'utente porta un H1 esistente → Modo B. Se vuole scriverne uno → Modo A. Se non è chiaro, chiedi.

---

### Modo A — Scrittura H1 da zero

**Step 1 — Raccolta input**

Se il Positioning Canvas di Dunford è già disponibile (output di b2b-positioning-diagnostic), estrailo direttamente. Altrimenti, fai queste domande in sequenza (una alla volta):

1. "Cosa fa il prodotto e a chi è destinato?"
2. "Esiste una categoria di prodotto riconoscibile dall'ICP? (es. CRM, project management software, analytics tool...) Oppure il prodotto fa qualcosa di nuovo che non rientra in una categoria esistente?"
3. "Qual è la differenziazione principale rispetto alle alternative che l'ICP userebbe senza di voi?"

**Step 2 — Diagnosi reference point**

Decidi quale formula usare con criterio esplicito:

Usa **Category + Differentiation** se:
- Il prodotto rientra in una categoria che l'ICP conosce già (CRM, browser, accounting software, ecc.)
- Nominare la categoria crea immediatamente contesto nel visitatore

Usa **JTBD + Differentiation** se:
- Il prodotto fa qualcosa di nuovo che non rientra in una categoria esistente
- La categoria è troppo generica per differenziare ("platform", "solution", "tool")
- L'ICP non cerca una categoria ma un obiettivo specifico da raggiungere

Comunica sempre la scelta all'utente e spiega perché.

**Step 3 — Applicazione formula**

Genera 3–5 varianti di H1. Per ogni variante, identifica chiaramente:
- Quale componente è il reference point (Category o JTBD)
- Quale componente è la differenziazione

Leggi `references/formulas-and-examples.md` per esempi reali annotati.

**Step 4 — Valutazione**

Valuta ogni variante contro i 4 criteri (vedi sezione Criteri qui sotto).

**Step 5 — Output**

```
REFERENCE POINT: [Category / JTBD]
FORMULA: [Formula 1 / Formula 2]

H1 CONSIGLIATO:
"[H1]"
→ Reference point: [componente]
→ Differenziazione: [componente]
→ Perché funziona: [2 righe max]

ALTERNATIVE:
"[H1 alternativa 1]" — [breve nota]
"[H1 alternativa 2]" — [breve nota]

NOTE: [eventuali dipendenze con subheadline o kicker per chiarire il contesto]
```

---

### Modo B — Valutazione H1 esistente

**Step 1 — Analisi**

Classifica l'H1 in una di queste categorie (vedi `references/bad-h1-patterns.md` per esempi):

- **Fluff puro**: nessun reference point, applicabile a qualsiasi azienda ("Shape What Comes Next")
- **Category senza differenziazione**: dice cos'è ma non perché sceglierlo ("Project Management Software")
- **JTBD troppo vago**: il job non è identificabile ("automate your systems")
- **JTBD troppo lofty**: il job è troppo grande per essere credibile ("drive revenue")
- **H1 decente con fix minori**: reference point c'è, differenziazione migliorabile
- **H1 forte**: rispetta entrambi i criteri, passa i 4 criteri

**Step 2 — Diagnosis**

Spiega il problema specifico in 2–3 righe. Sii diretto: se è fluff, dillo.

**Step 3 — Fix**

Proponi 2–3 H1 alternativi con il framework corretto. Usa lo stesso format dell'output del Modo A.

---

### Criteri di valutazione H1

1. **Reference point chiaro** in max 8–10 parole — senza leggere il subheadline
2. **5-second test**: un visitatore capisce in 5 secondi cosa fa il prodotto
3. **Differenziazione specifica** — non interscambiabile con un competitor della stessa categoria
4. **Livello gerarchico giusto** — il JTBD o la categoria parla all'ICP che il marketing raggiunge effettivamente (individuale vs VP vs C-suite)

---

### Anti-pattern da evitare

**Fluff puro** — headline senza reference point:
- "Shape What Comes Next"
- "Connect Everything. Achieve Anything."
- "One Platform. Endless Solutions."

Questi potrebbero appartenere a qualsiasi azienda tech. Non creano contesto.

**JTBD troppo vago**:
- "Automate your systems" — non identifica nessun job specifico
- "Streamline your operations" — stessa cosa

**JTBD troppo lofty**:
- "Drive revenue" — nessun singolo software guida il revenue; è l'intero business che lo fa
- "Transform your business" — non believable, non specifico

Leggi `references/bad-h1-patterns.md` per case study completi con diagnosi.

---

### Multi-product

Se il prodotto è multi-product, ci sono tre opzioni. Leggi `references/multi-product.md` per esempi e criteri di scelta:

- **Opzione 1**: H1 sul prodotto più importante
- **Opzione 2**: JTBD condiviso che copre tutti i prodotti
- **Opzione 3**: dichiarare esplicitamente di essere una suite

---

## Examples

### Esempio 1 — Modo A, product con category nota

Utente: "Ho un tool di website analytics pensato per marketer B2B non tecnici. La nostra differenziazione è che è molto più semplice da usare di Google Analytics."

→ Reference point: Category (website analytics)
→ Formula: Category + Differentiation
→ H1 consigliato: "Website analytics that finally make sense"
→ Alternative: "Website analytics without the data science degree" / "The analytics tool your marketing team will actually use"

### Esempio 2 — Modo A, product senza category

Utente: "Il nostro prodotto permette alle piattaforme SaaS di offrire finanziamenti integrati ai loro utenti finali, direttamente dentro la loro UI."

→ Reference point: JTBD ("offer loans to your customers")
→ Formula: JTBD + Differentiation ("inside your platform")
→ H1 consigliato: "Offer loans to your customers — inside your platform"

### Esempio 3 — Modo B, valutazione

Utente: "Il nostro H1 è: 'Innovate faster with AI-powered insights'"

→ Diagnosi: fluff puro. Nessun reference point. "Innovate faster" non è né una categoria né un JTBD identificabile. "AI-powered insights" è una feature, non un job.
→ Fix: richiedo categoria o JTBD + differenziazione per proporre alternative.

---

## Troubleshooting

**Problema: non riesco a decidere tra Category e JTBD**
→ Chiedi: "Il tuo ICP, quando inizia a cercare una soluzione come la tua, cosa cerca? Cerca 'CRM' o cerca 'come gestire i contratti dei clienti'?" La risposta ti dice quale reference point usare.

**Problema: la Category è troppo generica ("platform", "solution")**
→ Vai diretto al JTBD. Se anche il JTBD è vago, il problema è a monte nel positioning — suggerisci di usare b2b-positioning-diagnostic prima.

**Problema: l'utente vuole un H1 aspirazionale/brand**
→ Spiega il rischio: un H1 aspirazionale funziona solo se il brand è già abbastanza noto da non aver bisogno di un reference point (Apple, Slack quando già affermati). Per startup e scale-up, la chiarezza batte sempre l'aspirazione. Proponi comunque le varianti richieste, ma flagga il tradeoff.

**Problema: multi-product senza un prodotto chiaramente dominante**
→ Usa `references/multi-product.md` per guidare la scelta. Se nessuna delle tre opzioni funziona, è probabile che il problema sia più profondo nel positioning.
