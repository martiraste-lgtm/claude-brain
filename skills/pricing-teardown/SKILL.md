---
name: pricing-teardown
description: Sistema esperto per l'audit di conversione di una pricing page SaaS. Usa quando l'utente vuole analizzare, valutare, criticare o ricevere feedback su una pricing page — che condivida un URL, incolli il copy, carichi uno screenshot o descriva cosa c'è sulla pagina. Applica un framework a 10 dimensioni (7 sulla UX del buyer umano + 3 sulla AI-agent readiness) e produce un report con voti, pagella A-F e raccomandazioni prioritizzate. Trigger: "analizza questa pricing page", "teardown del pricing", "valuta la pricing page di", "cosa non va nel mio pricing", "pricing page audit", "grade my pricing page", "migliora la mia pagina prezzi". Skill sorella di saas-homepage-analyzer (stesso metodo, pagina diversa). NON usare per strategia di prezzo / quanto far pagare (usa pm-product-strategy-pricing-strategy), né per audit della homepage (usa saas-homepage-analyzer).
metadata:
  author: Custom (adattato da Growth Unhinged — Kyle Poyar)
  version: 1.0.0
  category: marketing
---

# Pricing Page Teardown

Sistema esperto per valutare pricing page SaaS e consegnare un report con voti e raccomandazioni azionabili. Il framework a 10 dimensioni si fonda su ciò che muove davvero la conversione: esperienza del buyer umano (chiarezza, trust, psicologia) + AI-agent readiness (trasparenza, struttura, discoverability).

Output sempre in **italiano**. Niente fuffa, niente "valuta di migliorare X": ogni finding ha una raccomandazione specifica.

---

## Confine — quando NON usarla

| Hai bisogno di… | Usa |
|---|---|
| Audit della **homepage** (anchor, hero, struttura, copy) | `saas-homepage-analyzer` (skill sorella) |
| Strategia di prezzo — **quanto** e **come** far pagare, packaging, modello | `pm-product-strategy-pricing-strategy` / `pm-product-strategy-monetization-strategy` |
| Valutare l'**H1** della pagina | `b2b-h1-writer` |

Questa skill fa una cosa sola: **teardown di conversione di una pricing page esistente**.

---

## Prima di iniziare

Leggi `references/frameworks.md`. Contiene la rubrica di scoring completa e i dati di benchmark che servono per applicare le 10 dimensioni in modo coerente.

## Intake

Accetta la pricing page in qualsiasi forma:
- **URL** → fai fetch e leggi la pagina (non chiedere permesso, vai e leggila)
- **Screenshot/immagine** → esaminala visivamente
- **Copy incollato** → lavora su ciò che è fornito
- **Descrizione** → fai domande di chiarimento per colmare i gap

Se l'input è scarno (es. "guarda acme.com/pricing"), fai fetch e procedi. Fai domande solo se l'input è così povero da non poter letteralmente valutare.

**Una domanda di chiarimento utile se non è ovvia:** qual è l'ACV / deal size medio approssimativo? Influenza il benchmark di trasparenza del prezzo (dimensione 7, vedi frameworks.md). Se non ottieni risposta, inferisci ragionevolmente da prodotto e piani visibili.

## Nota critica sul fetching

Il web fetch restituisce testo/HTML → **non** cattura in modo affidabile elementi visivi come loghi cliente in immagine, griglie di icone SVG, caroselli di testimonial, contenuto renderizzato in CSS. Sono comunissimi sulle pricing page e facili da perdere in uno scrape testuale.

Prima di scorare qualsiasi dimensione che coinvolge elementi visivi (specie la 5: Trust & Fear Removal), controlla l'HTML grezzo:
- Alt text di `<img>` che riferiscono nomi azienda o "logo"
- Class CSS tipo `logo-grid`, `customer-logos`, `testimonials`, `social-proof`, `wall-of-love`
- Attributi `aria-label` sulle sezioni
- Testo vicino tipo "Trusted by", "Used by", "Join X companies", o nomi cliente nei heading

Se trovi evidenza che loghi/testimonial ci sono ma sono renderizzati visivamente, **riconoscine la presenza nel finding** e scora di conseguenza. Non penalizzare per qualcosa che c'è ma non è stato catturato dal fetch testuale. Nel dubbio, accredita ciò che è probabilmente presente. Il tuo lavoro è identificare gap genuini, non penalizzare i limiti di rendering.

## Framework di valutazione

Valuta su 10 dimensioni in due categorie. Leggi `references/frameworks.md` per la rubrica completa prima di scorare.

### Categoria 1: Esperienza del buyer umano (7 dimensioni)

| # | Dimensione | Cosa verifichi |
|---|-----------|---------------------|
| 1 | Value prop reinforcement | La pagina ricorda perché dovrebbero importargliene, oltre a elencare i piani? |
| 2 | Chiarezza e scopo dei piani | È ovvio il buyer ideale di ogni piano? Un prospect si auto-seleziona correttamente? |
| 3 | Carico cognitivo | Si scansiona in <60 secondi e si capiscono le opzioni? |
| 4 | Benefit vs feature | Il copy descrive outcome, o solo capability? |
| 5 | Trust & fear removal | Ci sono social proof, garanzie, FAQ, loghi che rimuovono l'esitazione? |
| 6 | Psicologia comportamentale | Anchoring, evidenziazione di un piano, simplicity, deal-effect? |
| 7 | Trasparenza del prezzo | Il prezzo è pubblicato in modo chiaro e appropriato per l'ACV del prodotto? |

### Categoria 2: AI-agent readiness (3 dimensioni)

| # | Dimensione | Cosa verifichi |
|---|-----------|---------------------|
| 8 | Pricing machine-readable | Un LLM trova costi e limiti esatti senza tirare a indovinare o contattare sales? |
| 9 | Copertura FAQ e documentazione | Le domande di valutazione tipiche di un agente trovano risposta sulla/vicino alla pagina? |
| 10 | Profondità per-tier | Esistono pagine/doc dedicati per piano con specifiche precise? |

## Scoring

Scora ogni dimensione su scala 1-4:
- **4 — Forte**: fatto bene, un vero asset
- **3 — Adeguato**: presente ma migliorabile
- **2 — Debole**: c'è ma non funziona abbastanza
- **1 — Mancante/rotto**: assente o danneggia attivamente la conversione

Voto complessivo = media dei 10 punteggi, mappata su lettera:
- 3.5-4.0 → **A** · 2.75-3.49 → **B** · 2.0-2.74 → **C** · 1.25-1.99 → **D** · <1.25 → **F**

Non assegnare voti a vuoto: motiva ogni punteggio con 1-2 osservazioni specifiche dalla pagina reale. Voti vaghi ("è un 2/4 perché si può migliorare") sono inutili.

## Output

Di default, consegna il report **inline** in italiano. Se stai lavorando dentro un repo cliente (esiste `clients/[nome]/` o `outputs/`), offri di salvarlo come `[azienda]_pricing-teardown_v1.md` in `clients/[nome]/outputs/` o `outputs/`. Non usare path di sistema esterni.

Usa esattamente questa struttura:

```
# Pricing Teardown: [Azienda]
[URL o descrizione input] · [Data]

## Verdetto
[Una frase secca: la cosa più grossa che funziona e quella più grossa rotta.]

## Voto complessivo: [A/B/C/D/F]
Score: [X.X / 4.0]

---

## Esperienza del buyer umano

### 1. Value Prop Reinforcement — [Score]/4
**Finding:** [Cosa c'è e cosa manca. Specifico.]
**Raccomandazione:** [Esattamente cosa cambiare. Abbastanza specifico da passarlo a un copywriter.]

### 2. Chiarezza e scopo dei piani — [Score]/4
...
### 3. Carico cognitivo — [Score]/4
...
### 4. Benefit vs feature — [Score]/4
...
### 5. Trust & fear removal — [Score]/4
...
### 6. Psicologia comportamentale — [Score]/4
...
### 7. Trasparenza del prezzo — [Score]/4
...

---

## AI-agent readiness

### 8. Pricing machine-readable — [Score]/4
...
### 9. Copertura FAQ e documentazione — [Score]/4
...
### 10. Profondità per-tier — [Score]/4
...

---

## Raccomandazioni prioritarie

### Quick win (questa settimana)
[3-5 cambi a basso sforzo e alto impatto. Lista numerata, ognuno con una riga di razionale.]

### Miglioramenti strategici (questo trimestre)
[2-3 cambi strutturali più grossi. Lista numerata, ognuno con una riga di razionale.]

---

## Scorecard

| Dimensione | Score |
|-----------|-------|
| 1. Value prop reinforcement | /4 |
| 2. Chiarezza e scopo dei piani | /4 |
| 3. Carico cognitivo | /4 |
| 4. Benefit vs feature | /4 |
| 5. Trust & fear removal | /4 |
| 6. Psicologia comportamentale | /4 |
| 7. Trasparenza del prezzo | /4 |
| 8. Pricing machine-readable | /4 |
| 9. FAQ e documentazione | /4 |
| 10. Profondità per-tier | /4 |
| **Complessivo** | **/4 ([Voto])** |
```

---

## Principi da tenere a mente

**Specifico, non generico.** "Aggiungi social proof" è inutile. "Aggiungi 3-5 loghi cliente direttamente sotto le card dei piani, con una pull quote di un cliente riconoscibile" è azionabile. Riferisci copy reale, nomi dei piani, elementi specifici della pagina.

**Raccomandazioni ordinate per impatto.** I quick win devono essere i cambi a leva più alta che un growth marketer può spedire senza redesign. Gli strategici affrontano problemi strutturali (modello di prezzo, architettura dei piani, layer di trasparenza mancante).

**La sezione AI-agent readiness è forward-looking ma urgente.** Le aziende con pricing opaco ("Contact sales", limiti nascosti, nessuna FAQ sul billing) vengono **già** deprioritizzate dagli LLM quando raccomandano tool ai buyer. Inquadrala così: non come problema futuro, ma come svantaggio *presente*.

**Fidati dei dati di benchmark.** Il benchmark di trasparenza per ACV (in frameworks.md) è contesto utile per la dimensione 7. Se il pricing di un'azienda è opaco ma è normale per il suo tier di ACV, dillo — e raccomanda comunque un percorso verso più trasparenza.

**Check rapido di visibilità AI.** Chiedi a ChatGPT o Claude "Quanto costa [prodotto]?" e guarda che risposta torna: rivela se il pricing è surfacizzato correttamente e quali fonti terze (G2, Capterra, Reddit) plasmano la narrativa (~85% delle menzioni brand nell'AI search viene da fonti terze).
