---
name: infographic-creator
description: Trasforma testi, appunti e idee grezze in infografiche professionali per marketing e business strategy. Genera sia l'infografica diretta (React/SVG/HTML) sia un prompt dettagliato per ricrearla su tool AI esterni (Gemini, Banana, NotebookLM, Midjourney). Usa quando l'utente dice "crea un'infografica", "trasforma in infografica", "visualizza questo concetto", "fammi uno schema visivo", "crea un visual", "infografica da questo testo", "rendi visivo", o carica testi lunghi da trasformare in formato visivo. Ambiti: marketing, growth, GTM, business strategy, framework, positioning, content strategy. Do NOT use for charts/grafici numerici (usa data-viz), mappe geografiche, o diagrammi UML tecnici.
license: MIT
metadata:
  author: User
  version: 1.0.0
  category: document-creation
  tags: [infographic, visual-design, marketing, content-creation, business-strategy]
---

# Infographic Creator

Skill per trasformare contenuti testuali in infografiche professionali, con doppio output: artifact visivo diretto + prompt per tool AI esterni.

## Instructions

### Step 1: Analizza il Contenuto

Leggi attentamente il testo/idea fornita dall'utente e identifica:

1. **Tipo di informazione principale** - Classifica il contenuto:
   - GERARCHIA: priorità, livelli di importanza, piramidi
   - PROCESSO: step sequenziali, workflow, fasi
   - CONFRONTO: due o più approcci a paragone
   - CATALOGO: lista di elementi con attributi
   - ECOSISTEMA: sistema con elementi interconnessi
   - FRAMEWORK: modello concettuale strutturato
   - CHECKLIST: lista di controllo con categorie
   - ERRORI/PROBLEMI: lista di cosa evitare con sintomi

2. **Quantità di concetti** - Conta gli elementi distinti (ideale: 5-15)
3. **Relazioni tra elementi** - Sequenziali, gerarchiche, parallele, circolari
4. **Livello di dettaglio** - Quanto testo serve per ogni elemento

Consulta `references/content-extraction-rules.md` per le regole complete di estrazione e sintesi.

### Step 2: Seleziona il Layout

In base al tipo di informazione, seleziona il layout più adatto dalla libreria di 18 layout.

Consulta `references/layout-library.md` per la libreria completa con regole di selezione.

**Matrice di decisione rapida:**

| Tipo informazione | Layout consigliati |
|---|---|
| Gerarchia/priorità | Piramide a zone, Funnel |
| Processo 3-6 step | Cascade verticale, Zigzag snake flow |
| Processo 7+ step | Fasi a bande con progress, Card numerate a sezioni |
| Confronto 2 opzioni | Side-by-side |
| Confronto N opzioni | Griglia categorizzata, Tabella con icone |
| Framework concettuale | Card numerate a sezioni, Diagramma formula |
| Ecosistema/sistema | Cerchi concentrici |
| Checklist multi-area | Checklist multi-colonna |
| Lista errori/problemi | Lista errori a righe |
| Equazione concettuale | Equazione visiva |
| Tattica + esempi | Lista icona + descrizione 2 colonne |
| Breakdown dettagliato | Breakdown a componenti |
| Timeline giorno/fase | Timeline numerata |

Se il contenuto è ambiguo, proponi 2-3 layout all'utente e chiedi quale preferisce.

### Step 3: Estrai e Sintetizza

Trasforma il contenuto grezzo in elementi strutturati per l'infografica:

1. **Titolo principale** - Max 8-10 parole, d'impatto, che catturi il concetto core
2. **Sottotitolo** (opzionale) - 1 riga di contesto aggiuntivo
3. **Elementi principali** - Da 5 a 15 blocchi, ciascuno con:
   - Label/titolo breve (2-5 parole)
   - Descrizione sintetica (1-2 frasi max, 15-30 parole)
   - Eventuale sotto-elementi o bullet
4. **Raggruppamenti** - Come gli elementi si organizzano in sezioni/zone
5. **Relazioni visive** - Frecce, connessioni, flusso

CRITICO: Ogni elemento di testo nell'infografica deve essere brevissimo. Se una frase supera le 20 parole, riscrivila più corta. Le infografiche comunicano per sintesi, non per prosa.

Consulta `references/content-extraction-rules.md` per tecniche avanzate.

### Step 4: Genera l'Infografica

Produci l'infografica come artifact React (.jsx) seguendo il brand system.

Consulta `references/brand-system.md` per palette colori, tipografia e stile.

**Regole di implementazione React/JSX:**

1. Usa solo Tailwind CSS core utility classes
2. Dimensioni: progetta per 800x1200px (formato portrait social-friendly)
3. Struttura il componente con sezioni ben separate
4. Usa `div` con border-radius per le card, non SVG complesso
5. Per icone semplici usa emoji o caratteri Unicode, non librerie esterne
6. Assicurati che il testo sia leggibile (min 12px equivalente)
7. Testa mentalmente: se stampassi questo, sarebbe leggibile?

**Gerarchia tipografica:**
- Titolo principale: text-2xl o text-3xl, font-bold
- Titolo sezione: text-lg o text-xl, font-semibold
- Label card: text-base, font-semibold
- Testo corpo card: text-sm, text-gray-600
- Note/footer: text-xs

**Prima di finalizzare, verifica:**
- Tutti i testi sono visibili e non troncati
- I colori seguono il brand system
- La gerarchia visiva è chiara (si capisce cosa leggere prima)
- Lo spazio bianco è sufficiente (non affollato)
- Il layout funziona nel formato scelto

### Step 5: Genera il Prompt per Tool Esterni

Dopo l'infografica, genera un prompt strutturato per ricrearla su Gemini/Banana/altro.

Consulta `references/prompt-templates.md` per i template completi.

**Struttura del prompt esterno:**

```
TITOLO: [titolo esatto dell'infografica]
FORMATO: [dimensioni, orientamento]
STILE: [descrizione dello stile visivo]

LAYOUT: [tipo di layout scelto]
[Descrizione dettagliata della disposizione spaziale]

PALETTE COLORI:
- Sfondo: [HEX]
- Sezione 1: [HEX] - [dove si usa]
- Sezione 2: [HEX] - [dove si usa]
- Accento: [HEX] - [dove si usa]

TIPOGRAFIA:
- Titolo: [stile]
- Sottotitoli: [stile]
- Corpo: [stile]

CONTENUTO ESATTO:
[Tutti i testi esatti che devono apparire, posizione per posizione]

ELEMENTI GRAFICI:
[Descrizione di icone, frecce, connettori, forme]
```

Il prompt deve essere così dettagliato che il tool AI possa ricreare l'infografica senza ambiguità.

### Step 6: Chiedi Feedback e Itera

Dopo aver presentato l'output:

1. Chiedi se il layout scelto è quello giusto
2. Chiedi se i testi sintetizzati catturano il messaggio
3. Proponi varianti se il risultato non convince
4. Offri di aggiustare colori, dimensioni, raggruppamenti

## Firma/Brand Footer

La firma in fondo all'infografica è OPZIONALE. Chiedi sempre all'utente:
- "Vuoi aggiungere il tuo nome/brand in fondo all'infografica?"
- Se sì, chiedi nome e eventuale URL/handle

## Performance Notes

- Prenditi il tempo necessario per analizzare bene il contenuto prima di scegliere il layout
- La qualità della sintesi è più importante della velocità
- Non saltare la fase di estrazione: un'infografica con troppo testo è peggio di nessuna infografica
- Se il contenuto è troppo complesso per una singola infografica, proponi di dividerlo in 2-3 infografiche separate

## Examples

### Example 1: Testo lungo → Infografica processo

**User says:** "Trasforma questo articolo sulle 5 fasi del go-to-market in un'infografica"

**Actions:**
1. Analizza il testo, identifica: PROCESSO con 5 fasi
2. Seleziona layout: "Fasi a bande colorate con progress bar" (layout 11)
3. Estrae: titolo, 5 fasi con nome + 3-4 bullet ciascuna
4. Genera artifact React con bande colorate progressive
5. Genera prompt per Gemini con tutti i dettagli

**Result:** Infografica a bande + prompt copia-incolla

### Example 2: Idea grezza → Infografica framework

**User says:** "Ho un framework di pricing in 4 modelli, ognuno con pro e contro e esempi di aziende che lo usano. Fammi un'infografica"

**Actions:**
1. Analizza: CATALOGO con 4 elementi e attributi multipli
2. Seleziona layout: "Tabella con icone ed esempi" (layout 14)
3. Chiede all'utente i dettagli mancanti se necessario
4. Genera infografica tabellare con icone e loghi
5. Genera prompt esterno

**Result:** Infografica tabellare professionale + prompt

### Example 3: Concetto astratto → Infografica

**User says:** "Visualizza il concetto che il positioning è composto da target customer + differenziazione"

**Actions:**
1. Analizza: FRAMEWORK tipo equazione
2. Seleziona layout: "Equazione visiva" (layout 4)
3. Struttura: A + B = C con sotto-elementi per ciascuno
4. Genera infografica con formula visiva
5. Genera prompt esterno

**Result:** Infografica equazione visiva + prompt

## Troubleshooting

### Il layout scelto non funziona

**Cause:** Il contenuto ha troppi/pochi elementi per quel layout
**Solution:** Proponi un layout alternativo. Se troppi elementi, suggerisci di dividere in più infografiche. Se troppo pochi, suggerisci di arricchire o usare un layout più semplice.

### Il testo nelle card è troppo lungo

**Cause:** La sintesi non è stata abbastanza aggressiva
**Solution:** Riscrivi ogni elemento card con max 15 parole. Usa verbi d'azione, elimina articoli e congiunzioni non necessarie.

### L'infografica sembra affollata

**Cause:** Troppi elementi o troppo dettaglio
**Solution:** Riduci a max 12 elementi principali. Sposta i dettagli in sotto-livelli o elimina quelli meno critici.

### I colori non sono coerenti

**Cause:** Troppi colori usati o colori non dalla palette brand
**Solution:** Consulta `references/brand-system.md`. Usa max 3-4 colori dalla palette più bianco e grigio.

### Il prompt esterno non produce buoni risultati

**Cause:** Prompt troppo vago o mancano dettagli posizionali
**Solution:** Aggiungi coordinate spaziali più precise (alto/centro/basso, sinistra/destra), specifica dimensioni in px, descrivi ogni elemento come se stessi dando istruzioni a un designer.
