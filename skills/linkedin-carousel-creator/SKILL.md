---
name: linkedin-carousel-creator
description: Trasforma articoli, post, appunti, framework e liste in caroselli LinkedIn professionali (15-24 slide) nello stile Herubel/Wester. Singolo output a scelta tra Canva MCP, prompt Gemini, o Gamma MCP. Usa quando l'utente dice "crea un carosello", "trasforma in carosello LinkedIn", "carousel da questo articolo", "carosello su", "slide LinkedIn per", "carousel per la newsletter". Do NOT use for infografiche singole (usa infographic-creator), sales deck (usa sales-deck-creator), o post LinkedIn testuali (usa linkedin-viral-post-writer).
license: MIT
metadata:
  author: User
  version: 1.0.0
  category: document-creation
  tags: [linkedin, carousel, visual-content, personal-brand, newsletter]
---

# LinkedIn Carousel Creator

Trasforma contenuti testuali in caroselli LinkedIn professionali (15-24 slide) con design system Herubel/Wester. Output singolo a scelta: Canva MCP, prompt Gemini, o Gamma MCP.

## Overview

Questa skill prende un contenuto sorgente (articolo, post, appunti, framework, lista) e lo trasforma in un carosello LinkedIn con arco narrativo strutturato, design system coerente, e output pronto per la pubblicazione. Uso personale per il brand "da 0 al PMF".

---

## Instructions

### Step 1: Leggi i file di reference

Prima di iniziare, leggi TUTTI questi file:

1. `references/brand-system.md` — colori, font, elementi visivi, anti-pattern
2. `references/slide-types-library.md` — 10 tipi di slide con layout e regole
3. `references/narrative-structures.md` — 2 modelli narrativi (educativo, storytelling)
4. `references/content-extraction-rules.md` — come estrarre e sintetizzare dal testo sorgente
5. `references/copy-rules.md` — densita testo, formattazione, highlight per tipo slide
6. `references/visual-examples-analysis.md` — breakdown caroselli di riferimento
7. `references/gemini-prompt-template.md` — template prompt per Gemini
8. `references/canva-workflow.md` — workflow Canva MCP e Gamma MCP

Consulta anche per coerenza di tono:
- `~/.claude/skills/linkedin-viral-post-writer/references/mio-stile.md`
- `~/.claude/skills/linkedin-viral-post-writer/references/mio-pubblico.md`

---

### Step 2: Raccogli e analizza il contenuto sorgente

Accetta l'input dell'utente in qualsiasi formato:
- Articolo lungo
- Post LinkedIn
- Appunti / bullet point
- Framework / modello
- URL (leggi il contenuto)

**Analisi:**

1. Classifica il tipo di input (articolo, post, appunti, framework)
2. Identifica la **tesi centrale** (1 frase, max 15 parole)
3. Estrai **8-15 concetti chiave** con tipo (dato, principio, esempio, confronto, step)
4. Identifica la **tensione narrativa** (problema → trasformazione)

Segui le regole in `content-extraction-rules.md`.

**Se il contenuto e insufficiente** (meno di 6 concetti estraibili), chiedi:
- "Qual e la tesi centrale?"
- "Hai dati o numeri?"
- "C'e un errore comune su questo tema?"
- "Qual e il tuo contrarian take?"

---

### Step 3: Scegli la struttura narrativa

Usa la matrice decisionale da `narrative-structures.md`:

- **Model A — Educativo/Framework**: per framework, metodologie, guide step-by-step, liste di principi (15-20 slide)
- **Model B — Narrativo/Storytelling**: per problemi/soluzioni, case study, errori comuni, opinioni contrarian (18-24 slide)

Presenta la scelta all'utente:

> **Struttura consigliata**: Model [A/B] — [motivazione in 1 riga]
> **Slide previste**: [numero]
> **Confermi o preferisci l'altro modello?**

Non procedere senza conferma.

---

### Step 4: Costruisci lo storyboard slide-by-slide

Per ogni slide, definisci:

| Campo | Descrizione |
|-------|-------------|
| Numero | Posizione nel carosello |
| Tipo | Uno dei 10 tipi da `slide-types-library.md` |
| Titolo/Headline | Max 8 parole |
| Body | Contenuto testuale (rispetta limiti da `copy-rules.md`) |
| Highlight | Keyword evidenziate + colore (da mapping semantico) |
| Elementi visivi | Stick figure, frecce, bordi, diagrammi |

**Regole da applicare:**
- Max 3-4 righe per slide testuale
- Max 2-3 highlight per slide
- Zero emoji, sentence case
- 1 concetto = 1 slide
- Ponte/Bridge ogni 4-5 slide dense
- Coerenza cromatica: stesso concetto = stesso colore per tutto il carosello

**Checklist pre-output:**

```
[ ] L'arco narrativo ha un filo logico chiaro
[ ] Ogni slide ha UN solo concetto
[ ] I titoli letti in sequenza raccontano la storia
[ ] Max 3-4 righe per slide testuale
[ ] Max 2-3 highlight per slide
[ ] Zero emoji, sentence case
[ ] Bridge ogni 4-5 slide dense
[ ] Totale slide: 15-24
[ ] CTA specifica nell'ultima slide
[ ] Cover funziona come thumbnail nel feed
```

Presenta lo storyboard completo all'utente per review. Non generare l'output senza approvazione.

---

### Step 5: Chiedi CTA e scelta output

**CTA**: chiedi quale call to action per l'ultima slide. Esempi:
- "Iscriviti alla newsletter 'da 0 al PMF'"
- "Seguimi per altri framework"
- "Salva questo carosello"
- "Commenta con il tuo caso"
- Altra CTA specifica

**Output**: chiedi quale SINGOLO output generare:

> Quale output vuoi generare?
> 1. **Canva MCP** — creo il carosello direttamente su Canva
> 2. **Prompt Gemini** — genero un prompt strutturato da incollare in Gemini
> 3. **Gamma MCP** — creo il carosello su Gamma (formato social 4:5)

Genera UN SOLO output, non tutti e tre.

---

### Step 6: Genera l'output scelto

#### Se Canva MCP

Segui il workflow in `canva-workflow.md`, Sezione B:

1. Verifica brand kit (`list-brand-kits`)
2. `generate-design` con query dettagliata (tutto il contenuto slide-by-slide)
3. L'utente sceglie il candidato → `create-design-from-candidate`
4. `resize-design` a 1080x1350
5. `start-editing-transaction`
6. `perform-editing-operations` (testo, formattazione, colori per ogni pagina)
7. Preview → `commit-editing-transaction` dopo approvazione
8. `export-design` nel formato scelto (PDF per carousel nativo, PNG per immagini)

**Nota**: gli highlight colorati e le stick figure potrebbero richiedere editing manuale in Canva dopo la generazione.

#### Se Prompt Gemini

Segui il template in `gemini-prompt-template.md`:

1. Carica il template master
2. Compila il brand system block (statico)
3. Per ogni slide dello storyboard: numero, tipo, testo esatto, highlight con colori, elementi visivi, layout
4. Aggiungi regole anti-pattern
5. Presenta il prompt come code block copiabile

Consiglia di generare 1-3 slide per prompt, non tutto il carosello insieme.

#### Se Gamma MCP

Segui il workflow in `canva-workflow.md`, Sezione C:

1. `get_themes` → trova tema minimal/bianco
2. Prepara inputText come markdown slide-by-slide
3. `generate` con format "social", dimensions "4x5", language "it", textMode "preserve", noImages
4. Condividi gammaUrl con l'utente
5. Se serve export: rigenera con exportAs "pptx" o "pdf"

---

### Step 7: Verifica qualita

Dopo la generazione, verifica:

```
CHECKLIST POST-GENERAZIONE
[ ] Tutte le slide rispettano il brand system
[ ] Testo leggibile e non troncato
[ ] Colori highlight corretti (mapping semantico)
[ ] Ritmo narrativo mantenuto (Bridge ogni 4-5 dense)
[ ] CTA presente e specifica nell'ultima slide
[ ] Formato corretto (1080x1350 per Canva, 4:5 per Gamma)
```

Segnala eventuali problemi e suggerisci correzioni.

---

### Step 8: Chiedi feedback e itera

Chiedi all'utente:

> "Il carosello ti convince? Vuoi modificare qualche slide, cambiare l'ordine, o rigenerare?"

Se l'utente vuole modifiche:
- Aggiorna lo storyboard
- Rigenera solo le slide modificate (per Gemini: nuovo prompt parziale; per Canva: nuove editing operations; per Gamma: rigenerazione completa)

---

## Examples

### Example 1: Articolo su framework di positioning

**Input**: Articolo di 1500 parole sul SPICED framework per il messaging B2B.

**Analisi**: tesi = "il messaging B2B fallisce perche manca un framework strutturato", 12 concetti, tensione = "random copy vs framework-driven messaging"

**Struttura**: Model A (Educativo/Framework), 18 slide

**Storyboard** (estratto):
1. Cover: "Il framework che cambia il tuo messaging B2B" [highlight: "framework" arancione, "messaging" crema]
2. Contesto: "Il 90% dei siti B2B dice la stessa cosa" [highlight: "90%" coral]
3. Ponte: "Il problema non e il copy. E il framework."
4. Diagramma: matrice SPICED con 5 componenti
5-10. Deep dive su ogni componente (Dettaglio + Punto + Dato)
11. Confronto: prima vs dopo SPICED
12-14. Come applicarlo (3 step)
15. Sommario: checklist SPICED
16. CTA: "Iscriviti alla newsletter 'da 0 al PMF'"

**Output scelto**: Prompt Gemini → code block copiabile con brand system + contenuto slide-by-slide

### Example 2: Post newsletter su GTM

**Input**: Post di 800 parole su "perche il tuo GTM non scala"

**Analisi**: tesi = "servono sistemi, non tattiche random", 8 concetti, tensione = "founder che cambia tattica ogni quarter vs GTM system"

**Struttura**: Model B (Narrativo/Storytelling), 16 slide

**Output scelto**: Gamma MCP → carosello su Gamma in formato social 4:5

---

## Troubleshooting

### "Il carosello ha troppe slide"
**Causa**: contenuto sorgente troppo ricco, tentativo di includere tutto.
**Soluzione**: torna allo Step 2. Seleziona 1 sotto-topic, non comprimere tutto. Max 24 slide.

### "Il testo non sta nelle slide"
**Causa**: copy troppo lungo per il formato visivo.
**Soluzione**: applica le regole di `copy-rules.md`. Max 3-4 righe per slide, max 25 parole per riga. Taglia, non comprimi.

### "Lo stile non sembra Herubel"
**Causa**: troppi colori, bordi solidi, font sbagliato, emoji, o sfondo colorato.
**Soluzione**: rivedi `brand-system.md`. Sfondo bianco, testo nero, highlight SOLO su keyword, bordi tratteggiati, zero emoji.

### "Canva non genera il design corretto"
**Causa**: la query di `generate-design` era troppo vaga.
**Soluzione**: riscrivi la query con contenuto slide-by-slide esplicito. Includi "white background, black text, minimal, no photos, no emoji" nella query.

### "Gamma non rispetta il formato"
**Causa**: il tema scelto non e minimal o il formato non e "social".
**Soluzione**: usa `get_themes` per trovare il tema piu pulito. Assicurati di usare `format: "social"` e `dimensions: "4x5"`.
