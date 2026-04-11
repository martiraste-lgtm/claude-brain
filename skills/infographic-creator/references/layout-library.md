# Layout Library - 18 Layout Types

Questa libreria contiene tutti i layout disponibili per la creazione di infografiche. Ogni layout include: quando usarlo, struttura visiva, numero ideale di elementi, e note di implementazione.

---

## Layout 1: Piramide a Zone

**Quando usarlo:** Gerarchie di importanza/priorità dove la base è fondamentale e il vertice è superficiale o vice versa.

**Struttura:**
```
        /  Zona 3  \          ← Top (meno importante o più aspirazionale)
       / 3-4 elementi \
      /________________\
     /    Zona 2        \      ← Middle
    /   4-6 elementi     \
   /______________________\
  /       Zona 1           \   ← Base (fondamenta)
 /      5-8 elementi        \
/____________________________\
```

**Elementi ideali:** 12-18 distribuiti su 3 zone
**Colori:** Ogni zona con colore diverso dalla palette (progressione caldo→freddo o chiaro→scuro)
**Note implementazione React:**
- Usa div con clip-path o bordi angolati per la forma piramidale
- Ogni zona è un div con sfondo colorato
- Elementi interni come chip/badge con sfondo bianco e border-radius
- Label per ogni zona sul lato (es. "What Never Changes", "What Will Really Matter")

**Riferimento:** "2026 Marketing Priorities" di Pierre Herubel

---

## Layout 2: Cascade Verticale (Top-Down Flow)

**Quando usarlo:** Processi sequenziali dove ogni fase alimenta la successiva, con progressione logica dall'alto verso il basso.

**Struttura:**
```
[Fase 1: Nome]  →  elementi associati
      ↓
[Fase 2: Nome]  →  elementi associati
      ↓
[Fase 3: Nome]  →  elementi associati
      ↓
[Fase 4: Nome]  →  elementi associati
      ↓
[Fase 5: Nome]  →  elementi associati
```

**Elementi ideali:** 4-6 fasi, ciascuna con 3-6 sotto-elementi
**Colori:** Ogni fase con colore progressivo dalla palette, sotto-elementi come chip colorati
**Note implementazione React:**
- Colonna sinistra: box fase con bordo colorato e freccia verso il basso
- Colonna destra: chip/tag con gli elementi associati
- Frecce come div con border o carattere Unicode ↓
- Linee tratteggiate con border-dashed

**Riferimento:** "The Marketing Cascade" di Pierre Herubel

---

## Layout 3: Griglia Categorizzata

**Quando usarlo:** Confronto di tipi/categorie con sotto-elementi, specialmente quando ci sono 2 macro-categorie con molti elementi ciascuna.

**Struttura:**
```
┌─────────────────────┬──────────────────────┐
│   Categoria A       │    Categoria B       │
│   (descrizione)     │    (descrizione)     │
├─────────────────────┼──────────────────────┤
│ ┌───┐ ┌───┐ ┌───┐  │ ┌───┐ ┌───┐ ┌───┐   │
│ │el1│ │el2│ │el3│  │ │el1│ │el2│ │el3│   │
│ └───┘ └───┘ └───┘  │ └───┘ └───┘ └───┘   │
│ ┌───┐ ┌───┐ ┌───┐  │ ┌───┐ ┌───┐ ┌───┐   │
│ │el4│ │el5│ │el6│  │ │el4│ │el5│ │el6│   │
│ └───┘ └───┘ └───┘  │ └───┘ └───┘ └───┘   │
└─────────────────────┴──────────────────────┘
```

**Elementi ideali:** 2-3 categorie, 6-12 elementi ciascuna
**Colori:** Sfondo diverso per ogni categoria (rosa vs verde leggero), elementi come card bianche con icone
**Note implementazione React:**
- Grid a 2 colonne con gap
- Header colorato per ogni categoria
- Sotto-grid per gli elementi interni
- Icone come emoji Unicode sopra ogni label

**Riferimento:** "Create 2 Types of B2B Content" di Pierre Herubel

---

## Layout 4: Equazione Visiva

**Quando usarlo:** Formule concettuali dove A + B = C, o relazioni causa-effetto lineari.

**Struttura:**
```
┌──────────┐     ┌──────────────┐     ┌──────────────────┐
│ Elemento A│  +  │ Elemento B   │  =  │ Risultato C      │
│           │     │              │     │                  │
│ - attr 1  │     │ - attr 1     │     │ (Homepage        │
│ - attr 2  │     │ - attr 2     │     │  Representation) │
│ - attr 3  │     │ - attr 3     │     │                  │
└──────────┘     └──────────────┘     └──────────────────┘

[Esempio 1: Riga con A | + | B | = | C]
[Esempio 2: Riga con A | + | B | = | C]
```

**Elementi ideali:** 2-3 componenti dell'equazione + 3-5 esempi in righe
**Colori:** Colonne con sfondo pastello diverso, operatori (+, =) in colore accento
**Note implementazione React:**
- Struttura a griglia con colonne per ogni componente
- Operatori matematici grandi e centrali
- Ogni riga esempio con sfondo alternato
- Bordi arrotondati per le card

**Riferimento:** "The World's Simplest Positioning Equation" di Fletch

---

## Layout 5: Timeline Numerata (Day-by-Day)

**Quando usarlo:** Processi con timeline definita, piano giorno per giorno o fase per fase con progressione temporale.

**Struttura:**
```
Day 1  ●━━→  [Titolo] + bullet points
              ↓
Day 2  ●━━→  [Titolo] + bullet points
              ↓
Day 3  ●━━→  [Titolo] + bullet points
              ...
Day 7  ●━━→  [Titolo] + bullet points
              ↓
         [Analisi/Risultato]
```

**Elementi ideali:** 5-10 step temporali, ciascuno con 2-4 bullet
**Colori:** Badge numerati in colore accento, card con sfondo che si schiarisce progressivamente
**Note implementazione React:**
- Colonna sinistra: badge Day N con pallino colorato
- Colonna destra: card con titolo bold + bullet concisi
- Frecce/connettori tra le fasi
- Icona/emoji opzionale per ogni fase

**Riferimento:** "7-Day Idea Validation Framework" di Maja Voje

---

## Layout 6: Card Numerate a Sezioni

**Quando usarlo:** Framework complessi con multiple aree tematiche, ciascuna contenente card numerate con dettagli.

**Struttura:**
```
═══════════════════════════════════
         TITOLO PRINCIPALE
═══════════════════════════════════

┌─── SEZIONE A ──────────────────┐
│ ┌──1──┐ ┌──2──┐ ┌──3──┐ ┌──4──┐│
│ │Title│ │Title│ │Title│ │Title││
│ │text │ │text │ │text │ │text ││
│ └─────┘ └─────┘ └─────┘ └─────┘│
└────────────────────────────────┘

┌─── SEZIONE B ──────────────────┐
│ ┌──5──┐ ┌──6──┐ ┌──7──┐ ┌──8──┐│
│ ...                             │
└────────────────────────────────┘

┌─── SEZIONE C ──────────────────┐
│ ...                             │
└────────────────────────────────┘
```

**Elementi ideali:** 2-4 sezioni, 3-4 card per sezione, 8-16 card totali
**Colori:** Ogni sezione con colore sfondo diverso dalla palette, card bianche con ombra, numeri in badge circolare accento
**Note implementazione React:**
- Header scuro per titolo principale
- Sezioni come div con sfondo pastello e bordo arrotondato
- Card bianche con shadow-sm, border-radius
- Badge numerici circolari in arancione accento (top-right della card)
- Grid 4 colonne per le card dentro ogni sezione

**Riferimento:** "GTM Power System" (il tuo brand)

---

## Layout 7: Diagramma con Formula

**Quando usarlo:** Definizioni strutturate di un concetto (es. value proposition) con componenti e formula riassuntiva.

**Struttura:**
```
        [Titolo Concetto]
    "Definizione in una riga"

    ┌──────────────────────┐
    │   Componente A       │
    │   - elem 1           │
    │   - elem 2           │
    └──────────────────────┘
              ↕
    ┌──────────────────────┐
    │   Formula:           │
    │   "We help [X] solve │
    │    [Y] to achieve [Z]│
    │    because [W]"      │
    └──────────────────────┘
              ↕
    ┌─────┐ ┌─────┐ ┌─────┐
    │Box 1│ │Box 2│ │Box 3│
    └─────┘ └─────┘ └─────┘
```

**Elementi ideali:** 1 formula centrale + 3-6 componenti intorno
**Colori:** Formula in box con bordo verde/accento, componenti in card pastello
**Note implementazione React:**
- Layout verticale centrato
- Box formula con bordo colorato e sfondo leggero
- Componenti come card distribuite intorno alla formula
- Frecce bidirezionali tra gli elementi

**Riferimento:** "Value Proposition" di Joris van Kappen

---

## Layout 8: Flowchart con Fasi (Processo Multi-Output)

**Quando usarlo:** Processi che partono da un input e producono multipli output attraverso fasi definite.

**Struttura:**
```
[Input/Preparazione]
        ↓
[Fase Core: step 1-8 dettagliati]
        ↓
┌────┐ ┌────┐ ┌────┐ ┌────┐
│Out1│ │Out2│ │Out3│ │Out4│
└────┘ └────┘ └────┘ └────┘
```

**Elementi ideali:** 2-3 fasi macro, 5-8 step nella fase core, 3-7 output
**Colori:** Barra colorata orizzontale per le fasi, card per gli output
**Note implementazione React:**
- Timeline orizzontale in alto con le fasi
- Sezione centrale dettagliata con step numerati
- Sezione output in basso come grid di card
- Frecce direzionali tra le sezioni

**Riferimento:** "How I Turn Customer Interviews into GTM Layer" di Douwe Wester

---

## Layout 9: Confronto Side-by-Side

**Quando usarlo:** Due approcci, modelli o strategie a confronto diretto.

**Struttura:**
```
┌──────────────┐     ┌──────────────┐
│  Approccio A │     │  Approccio B │
│  (subtitle)  │     │  (subtitle)  │
│              │     │              │
│  - Punto 1   │     │  - Punto 1   │
│  - Punto 2   │     │  - Punto 2   │
│  - Punto 3   │     │  - Punto 3   │
│              │     │              │
│  [Esempio]   │     │  [Esempio]   │
│              │     │              │
│  USE: dove   │     │  USE: dove   │
└──────────────┘     └──────────────┘
```

**Elementi ideali:** 2 opzioni con 3-6 punti ciascuna
**Colori:** Colore A vs Colore B dalla palette, sfondo neutro
**Note implementazione React:**
- Grid 2 colonne equal-width
- Header colorato per ogni lato
- Punti corrispondenti allineati
- CTA/conclusione in fondo

**Riferimento:** "Market Positioning vs Segment Positioning"

---

## Layout 10: Funnel / Processo Lineare

**Quando usarlo:** Conversioni, pipeline, processi che si restringono progressivamente.

**Struttura:**
```
╔══════════════════════════════╗
║        FASE 1 (ampia)       ║
╠════════════════════════════╣
║      FASE 2 (media)        ║
╠══════════════════════════╣
║    FASE 3 (stretta)      ║
╠════════════════════════╣
║  FASE 4 (output)     ║
╚══════════════════════╝
```

**Elementi ideali:** 3-6 fasi
**Colori:** Progressione di colore dall'ampio al ristretto
**Note implementazione React:**
- Div con width decrescente o clip-path trapezoidale
- Ogni fascia con colore dalla palette
- Testo centrato in ogni fascia
- Metriche/numeri opzionali sul lato

---

## Layout 11: Fasi a Bande Colorate con Progress Bar

**Quando usarlo:** Processi con fasi ben definite dove ogni fase ha contenuto ricco (mini-tabelle, checklist, case study). Ideale per framework completi.

**Struttura:**
```
┌─── Fase 1 ─── [████░░░░░░ 20%] ───────────┐
│ ┌─────┐ ┌─────┐ ┌─────┐ ┌─────────────┐   │
│ │Card │ │Card │ │Card │ │  Insight    │   │
│ └─────┘ └─────┘ └─────┘ └─────────────┘   │
└────────────────────────────────────────────┘
┌─── Fase 2 ─── [████████░░ 40%] ───────────┐
│ ┌──────────────────┐ ┌─────────────────┐   │
│ │ Mini-tabella      │ │   Nota chiave   │   │
│ └──────────────────┘ └─────────────────┘   │
└────────────────────────────────────────────┘
...
```

**Elementi ideali:** 3-6 fasi, contenuto variabile per fase
**Colori:** Ogni fase un colore diverso (rosso, arancio, giallo, verde, blu), progress bar in grigio
**Note implementazione React:**
- Ogni fase come div full-width con sfondo colorato
- Header fase con nome + progress bar
- Contenuto interno come grid di mini-card
- Bordi arrotondati per tutto

**Riferimento:** "The 5 Phases of AI Product Strategy"

---

## Layout 12: Lista Errori/Problemi a Righe

**Quando usarlo:** Elenco di errori comuni, problemi, cose da evitare, con sintomi o conseguenze.

**Struttura:**
```
    TITOLO: "N Errori che..."
    
│ # │ Problema          │ ✕ Sintomo 1        │ ✕ Sintomo 2        │
│ 1 │ [descrizione]     │ [conseguenza]       │ [conseguenza]       │
│ 2 │ [descrizione]     │ [conseguenza]       │ [conseguenza]       │
│ 3 │ [descrizione]     │ [conseguenza]       │ [conseguenza]       │
...
```

**Elementi ideali:** 4-8 errori, 2-3 sintomi ciascuno
**Colori:** Numeri in badge colore accento degradante (dal rosso al giallo), sfondo righe alternato grigio chiaro
**Note implementazione React:**
- Titolo grande in alto
- Righe con 3 colonne: numero+problema | sintomo 1 | sintomo 2
- ✕ in rosso prima di ogni sintomo
- Sfondo righe alternato per leggibilità

**Riferimento:** "6 GTM mistakes that kill momentum" di Alex Estner

---

## Layout 13: Checklist/Audit Multi-Colonna

**Quando usarlo:** Audit completi, checklist con molte categorie, framework di valutazione con elementi da spuntare.

**Struttura:**
```
    [Timeline/Milestone in alto]
    
┌──── Col 1 ────┐ ┌──── Col 2 ────┐ ┌──── Col 3 ────┐
│ Categoria A    │ │ Categoria D    │ │ Categoria G    │
│ □ item 1       │ │ □ item 1       │ │ □ item 1       │
│ □ item 2       │ │ □ item 2       │ │ □ item 2       │
│                │ │                │ │                │
│ Categoria B    │ │ Categoria E    │ │                │
│ □ item 1       │ │ □ item 1       │ │                │
│ □ item 2       │ │ □ item 2       │ │                │
└────────────────┘ └────────────────┘ └────────────────┘
```

**Elementi ideali:** 3 colonne, 2-4 categorie per colonna, 3-8 item per categoria
**Colori:** Header categorie in colori pastello diversi, checkbox in grigio, milestone line in colore brand
**Note implementazione React:**
- Milestone bar orizzontale in alto con punti
- Grid 3 colonne
- Sezioni con header colorato
- Checkbox come ☐ Unicode

**Riferimento:** "GTM Foundations from 0 to €1m ARR" di Alex Estner

---

## Layout 14: Tabella con Icone ed Esempi

**Quando usarlo:** Confronto di modelli/approcci con attributi e esempi concreti (loghi, brand, aziende).

**Struttura:**
```
│ 🏷 Modello      │ Come funziona          │ Esempi         │
│─────────────────│───────────────────────│───────────────│
│ 🎯 [Nome 1]     │ [descrizione breve]   │ Logo A, Logo B│
│ 💰 [Nome 2]     │ [descrizione breve]   │ Logo C, Logo D│
│ 🔧 [Nome 3]     │ [descrizione breve]   │ Logo E, Logo F│
```

**Elementi ideali:** 4-8 righe, 3 colonne
**Colori:** Header giallo/accento forte, righe con sfondo bianco, separatori leggeri
**Note implementazione React:**
- Header tabella con sfondo accento forte
- Icone emoji nella prima colonna
- Descrizioni in corsivo per le citazioni
- Nomi brand in bold nella colonna esempi

**Riferimento:** "5 Hybrid Pricing Playbooks"

---

## Layout 15: Cerchi Concentrici / Ecosystem Map

**Quando usarlo:** Ecosistemi, sistemi con core e anelli di espansione, modelli a cipolla.

**Struttura:**
```
              ╭──── Anello Esterno ────╮
          ╭──── Anello Medio ────╮
      ╭──── Anello Interno ────╮
   ┌─── CORE ───┐
   │   [Nome]   │
   │   [desc]   │
   └────────────┘
      ╰────────────────────────╯
          ╰────────────────────────────╯
              ╰────────────────────────────────╯
              
[Elementi satellite intorno con frecce]
```

**Elementi ideali:** 3-4 anelli + 8-12 elementi satellite
**Colori:** Core in colore accento forte, anelli progressivamente più chiari, satellite in grigio/outline
**Note implementazione React:**
- ATTENZIONE: layout complesso, usa div con border-radius-full e padding crescente
- Anelli come div annidati con bordo e sfondo semi-trasparente
- Elementi satellite come card posizionate intorno
- Frecce come emoji o div rotati

**Riferimento:** "Clay GTM Ecosystem Map"

---

## Layout 16: Zigzag / Snake Flow

**Quando usarlo:** Processi con molti step (6+) che devono mostrare progressione ma non starebbero in una lista verticale.

**Struttura:**
```
┌──1──┐          ┌──2──┐
│     │ ───────→ │     │
└─────┘          └─────┘
                    │
         ┌──────────┘
         ↓
┌──4──┐          ┌──3──┐
│     │ ←─────── │     │
└─────┘          └─────┘
   │
   └──────────┐
              ↓
┌──5──┐          ┌──6──┐
│     │ ───────→ │     │
└─────┘          └─────┘
```

**Elementi ideali:** 6-10 step
**Colori:** Badge numerici in colore accento, card con sfondo alternato chiaro, frecce in grigio
**Note implementazione React:**
- Grid 2 colonne
- Righe pari: sx→dx, righe dispari: dx→sx
- Connettori come frecce tra le righe
- Icone emoji opzionali per ogni step

**Riferimento:** "8 Steps to Get Your Outbound Up & Running"

---

## Layout 17: Lista Icona + Descrizione a 2 Colonne

**Quando usarlo:** Lista di tattiche, strategie o concetti con esempi o brand associati.

**Struttura:**
```
│ 🔧 Tattica 1 → Descrizione   │ Esempio A, Esempio B │
│ 🎯 Tattica 2 → Descrizione   │ Esempio C, Esempio D │
│ 💡 Tattica 3 → Descrizione   │ Esempio E, Esempio F │
```

**Elementi ideali:** 5-10 righe
**Colori:** Titolo con sfondo giallo highlight, righe con sfondo bianco, icone colorate
**Note implementazione React:**
- 2 colonne: tattica+descrizione | esempi
- Icone emoji a sinistra di ogni tattica
- Separatori leggeri tra le righe
- Header colonne in maiuscolo small

**Riferimento:** "9 Advanced Distribution Tactics"

---

## Layout 18: Breakdown a Componenti

**Quando usarlo:** Sistemi complessi con componenti indipendenti, ciascuno con sotto-dettagli ricchi.

**Struttura:**
```
[Titolo + Problema/Contesto in alto]

┌─── Componente 1 ───┐  ┌─── Componente 2 ───┐
│ Descrizione         │  │ Descrizione         │
│ • punto 1           │  │ • punto 1           │
│ • punto 2           │  │ • punto 2           │
│ [sotto-elementi]    │  │ [sotto-elementi]    │
└────────────────────┘  └────────────────────┘

┌─── Componente 3 ───┐  ┌─── Componente 4 ───┐
│ Descrizione         │  │ [Sotto-sezioni      │
│ [Tabella interna]   │  │  con loghi/tool]    │
└────────────────────┘  └────────────────────┘

┌─────────── Componente 5 (full-width) ──────────┐
│ Contenuto più dettagliato con sottosezioni      │
└─────────────────────────────────────────────────┘
```

**Elementi ideali:** 3-6 componenti, contenuto variabile per ciascuno
**Colori:** Header componenti in colori pastello diversi, sfondo pagina chiaro, card bianche
**Note implementazione React:**
- Grid 2 colonne per i componenti, full-width per componenti grandi
- Ogni componente come card con header colorato
- Contenuto interno flessibile (liste, tabelle, sotto-grid)
- Sfondo pagina in gradiente leggero

**Riferimento:** "The 5 Key Components of Allbound Pipeline Generation"

---

## Regole di Selezione Layout

### Regola 1: Conta gli Elementi
- 3-5 elementi → Layout semplice (Equazione, Side-by-side, Funnel)
- 6-12 elementi → Layout medio (Cascade, Zigzag, Card numerate)
- 12-20 elementi → Layout complesso (Fasi a bande, Checklist, Breakdown)
- 20+ elementi → Dividi in 2+ infografiche

### Regola 2: Tipo di Relazione
- Sequenziale → Cascade, Timeline, Zigzag, Fasi a bande
- Gerarchica → Piramide, Funnel
- Parallela → Griglia, Side-by-side, Tabella
- Concentrica → Cerchi concentrici
- Composita → Card numerate, Breakdown

### Regola 3: Densità di Testo
- Poco testo (label only) → Piramide, Equazione, Funnel
- Testo medio (1-2 frasi) → Card numerate, Zigzag, Tabella
- Molto testo → Breakdown, Fasi a bande, Checklist

### Regola 4: Se in Dubbio
Usa il **Layout 6 (Card Numerate a Sezioni)** — è il più versatile e si adatta alla maggior parte dei contenuti marketing/strategy.
