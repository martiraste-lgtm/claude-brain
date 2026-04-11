# Workflow Canva MCP e Gamma MCP

Istruzioni operative per generare caroselli LinkedIn usando Canva MCP e Gamma MCP.

---

## Sezione A — Setup Brand Kit Canva (una tantum)

### Verifica brand kit esistente

```
1. Chiama mcp__claude_ai_Canva__list-brand-kits
2. Cerca un brand kit con nome che contiene "carosello", "carousel", "da 0 al PMF", o "LinkedIn"
3. Se esiste: salva il brand_kit_id e procedi alla Sezione B
4. Se non esiste: guida l'utente alla creazione manuale (sotto)
```

### Creazione brand kit manuale

Il brand kit Canva non puo essere creato via MCP — l'utente deve crearlo manualmente su canva.com.

**Istruzioni da dare all'utente:**

> Vai su canva.com > Brand Kit > Crea nuovo brand kit
>
> **Nome**: "da 0 al PMF — Caroselli LinkedIn"
>
> **Colori da aggiungere:**
> - Sfondo: #FFFFFF (bianco)
> - Testo: #000000 (nero)
> - Accento 1: #E8D5E8 (rosa/lavanda)
> - Accento 2: #FFF3CD (crema/giallo)
> - Accento 3: #FFB74D (arancione)
> - Accento 4: #FFB3B3 (coral/rosso)
> - Accento 5: #D4EDDA (verde)
> - Grigio: #4A4A4A (testo secondario)
>
> **Font:**
> - Titoli: Poppins Bold (o Inter Bold, o Montserrat Bold)
> - Body: Poppins Regular (o Inter Regular, o Montserrat Regular)
>
> Dopo la creazione, torna qui e conferma. Recupero automaticamente il brand_kit_id.

Dopo la conferma, ri-esegui `list-brand-kits` per ottenere l'ID.

---

## Sezione B — Generazione Carosello su Canva

### Workflow completo (7 step)

#### Step 1: Genera il design

```
mcp__claude_ai_Canva__generate-design(
  query: "[Descrizione dettagliata del carosello con contenuto slide-by-slide]",
  design_type: "presentation",
  brand_kit_id: "[brand_kit_id dal Setup]"
)
```

**Come scrivere la query:**

La query deve essere il piu dettagliata possibile. Include:
- Il topic del carosello
- Il numero di slide (pagine)
- Per ogni slide: tipo, titolo, contenuto testuale
- Lo stile visivo: "minimal, white background, black text, colored highlights on keywords, sans-serif geometric font, no photos, no emoji"

Esempio di query:
> "Create a 16-page LinkedIn carousel presentation about B2B positioning mistakes. Minimal style: white background, black text, sans-serif geometric font (Poppins), no photos, no emoji. Page 1: Cover slide with title '3 errori di positioning che fanno tutte le startup' with highlighted keywords. Page 2: Context slide with statement 'Il 90% delle startup B2B ha lo stesso problema'. Page 3: ..."

**Risultato**: restituisce un job_id con candidate designs.

#### Step 2: Seleziona il candidato

Mostra all'utente i candidati disponibili. L'utente sceglie quello piu vicino allo stile desiderato.

```
mcp__claude_ai_Canva__create-design-from-candidate(
  job_id: "[job_id dal Step 1]",
  candidate_id: "[candidate scelto dall'utente]"
)
```

**Risultato**: restituisce il design_id del nuovo design.

#### Step 3: Ridimensiona a formato LinkedIn

```
mcp__claude_ai_Canva__resize-design(
  design_id: "[design_id dal Step 2]",
  design_type: {
    type: "custom",
    width: 1080,
    height: 1350
  }
)
```

**Risultato**: restituisce un nuovo design_id per la versione ridimensionata.

#### Step 4: Inizia editing

```
mcp__claude_ai_Canva__start-editing-transaction(
  design_id: "[design_id dal Step 3]"
)
```

**Risultato**: restituisce transaction_id + lista degli elementi editabili per pagina.

#### Step 5: Applica modifiche

```
mcp__claude_ai_Canva__perform-editing-operations(
  transaction_id: "[transaction_id dal Step 4]",
  operations: [
    {
      type: "replace_text",
      element_id: "[id elemento testo]",
      text: "[testo corretto dalla storyboard]"
    },
    {
      type: "format_text",
      element_id: "[id elemento testo]",
      formatting: {
        color: "#000000",
        font_size: 48,
        font_weight: "bold",
        text_align: "center"
      }
    }
  ]
)
```

**Operazioni tipiche per carosello:**
- `replace_text`: sostituisci tutto il testo con il contenuto esatto dallo storyboard
- `format_text`: applica font size, weight, colore, allineamento
- `find_and_replace_text`: per correzioni rapide su piu pagine

**Nota**: ripetere per ogni pagina/slide del carosello.

#### Step 6: Conferma e salva

Mostra preview all'utente usando:
```
mcp__claude_ai_Canva__get-design-thumbnail(
  transaction_id: "[transaction_id]",
  page_index: [numero pagina]
)
```

Se l'utente approva:
```
mcp__claude_ai_Canva__commit-editing-transaction(
  transaction_id: "[transaction_id]"
)
```

Se l'utente vuole modifiche: torna allo Step 5 con nuove operazioni.

Se l'utente vuole annullare:
```
mcp__claude_ai_Canva__cancel-editing-transaction(
  transaction_id: "[transaction_id]"
)
```

#### Step 7: Esporta

```
mcp__claude_ai_Canva__export-design(
  design_id: "[design_id]",
  format: {
    type: "pdf",
    size: "a4"
  }
)
```

Formati disponibili:
- **PDF**: `{type: "pdf", size: "a4"}` — per preview e condivisione
- **PNG**: `{type: "png", width: 1080, height: 1350}` — per upload LinkedIn (1 immagine per pagina)
- **PPTX**: `{type: "pptx"}` — per editing in PowerPoint

Per LinkedIn: consigliare PDF (carosello nativo) o PNG (immagini multiple).

---

### Limitazioni Canva MCP

| Limitazione | Impatto | Workaround |
|-------------|---------|------------|
| Non crea elementi da zero | Non puoi aggiungere shape/box/frecce che non esistono nel design generato | Usa `generate-design` con query molto dettagliata |
| Non imposta sfondo pagina | Il background potrebbe non essere bianco puro | Verifica visivamente, chiedi all'utente di correggere manualmente se necessario |
| Non aggiunge immagini inline | Non puoi inserire stick figure o icone via MCP | L'utente aggiunge manualmente in Canva dopo l'export |
| Editing limitato a elementi esistenti | Puoi solo modificare cio che `generate-design` ha creato | La query iniziale deve essere il piu completa possibile |
| Non gestisce highlight colorati | Non puoi creare rettangoli colorati dietro il testo | L'utente aggiunge highlights manualmente in Canva |

**Strategia consigliata**: usa Canva MCP per la struttura e il testo, poi l'utente fa il fine-tuning visivo (highlight, icone, bordi) direttamente in Canva.

---

## Sezione C — Generazione Carosello su Gamma

### Workflow MCP diretto (2 step)

#### Step 1: Trova il tema

```
mcp__claude_ai_Gamma__get_themes()
```

Cerca un tema minimal/bianco. Criteri:
- Sfondo bianco o chiaro
- Font sans-serif
- Stile pulito, senza decorazioni

Salva il `themeId`.

#### Step 2: Genera il carosello

```
mcp__claude_ai_Gamma__generate(
  inputText: "[contenuto slide-by-slide in markdown]",
  format: "social",
  cardOptions: {
    dimensions: "4x5"
  },
  textOptions: {
    language: "it",
    amount: "brief"
  },
  textMode: "preserve",
  themeId: "[themeId dal Step 1]",
  imageOptions: {
    source: "noImages"
  }
)
```

**Come formattare inputText:**

Il contenuto deve essere in markdown con header per ogni slide:

```markdown
## Slide 1: 3 errori di positioning che fanno tutte le startup

## Slide 2
Il 90% delle startup B2B ha lo stesso problema: il positioning e un ripensamento, non una decisione strategica.

## Slide 3
**Errore 1: copiare i competitor**
- Guardi cosa fanno gli altri
- Copi il loro messaging
- Finisci per sembrare uguale a tutti

## Slide 4
...
```

**Parametri chiave:**
- `format: "social"` — genera nel formato social, non presentazione
- `dimensions: "4x5"` — ratio LinkedIn corretto
- `textMode: "preserve"` — usa il testo esatto che fornisci, non lo riscrive
- `source: "noImages"` — niente immagini stock, solo testo e grafici

**Risultato**: restituisce `gammaUrl` — condividilo con l'utente.

#### Esportazione (opzionale)

Se l'utente vuole esportare:
```
mcp__claude_ai_Gamma__generate(
  ...stessi parametri...
  exportAs: "pptx"  // oppure "pdf"
)
```

### Workflow alternativo — Webhook n8n

Se il workflow MCP diretto non produce risultati soddisfacenti, usa il webhook:

```python
import requests

url = "https://stefano1479.app.n8n.cloud/webhook/sales-deck-to-gamma"

payload = {
    "title": "{{titolo_carosello}}",
    "content": "{{contenuto_markdown_slide_by_slide}}",
    "format": "social",
    "dimensions": "4x5"
}

response = requests.post(url, json=payload)
print(response.json())
```

**Nota**: questo webhook e stato creato per sales deck. Potrebbe necessitare adattamenti per il formato carosello (4:5 vs 16:9). Verifica con l'utente se il risultato e soddisfacente.

---

### Limitazioni Gamma MCP

| Limitazione | Impatto | Workaround |
|-------------|---------|------------|
| Non edita dopo la creazione | Se il risultato non va bene, devi rigenerare da zero | Usa `textMode: "preserve"` per controllare il testo |
| Temi limitati | Potrebbe non avere un tema che matcha lo stile Herubel | Scegli il tema piu minimal disponibile |
| No highlight colorati | Non puoi applicare evidenziatori specifici | L'utente li aggiunge nell'editor Gamma |
| No stick figure/icone custom | Solo gli elementi del tema | Gamma e piu adatto per testo-heavy carousel |
| Dimensioni social limitate | 4x5 e supportato ma il layout potrebbe non essere ottimale | Verifica la resa, usa Canva come alternativa |

**Quando preferire Gamma vs Canva:**
- **Gamma**: quando serve un draft veloce da rifinire, o quando il carosello e principalmente testuale
- **Canva**: quando serve piu controllo visivo, elementi grafici complessi, o brand kit application
