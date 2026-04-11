---
name: skill-builder
description: Guida interattiva per creare Agent Skills complete per Claude. Usa quando l'utente dice "aiutami a creare una skill", "devo ottenere questo outcome", "voglio una skill per", "costruiamo una skill che", o quando vuole sistematizzare un workflow ripetibile. Copre discovery, design, implementazione, validazione e test.
license: MIT
metadata:
  author: User
  version: 1.0.0
  category: productivity
  tags: [skill-creation, workflow, automation, meta-tool]
---

# Skill Builder

Guida interattiva per creare Agent Skills professionali per Claude. Ti accompagno passo-passo dalla definizione dell'obiettivo fino al deployment.

## Overview

Questa skill ti aiuta a trasformare qualsiasi workflow ripetibile in una Agent Skill ben strutturata. Il processo è conversazionale: faccio domande, raccolgo informazioni, e solo dopo creo i file.

**Non creo mai una skill senza aver completato la fase Discovery.**

---

## Instructions

### Fase 1: Discovery (Obbligatoria)

Quando l'utente chiede di creare una skill, DEVO raccogliere queste informazioni attraverso domande conversazionali:

#### Domande da Porre

**Blocco 1 - Obiettivo e Contesto**
1. Qual è l'obiettivo principale? Cosa vuoi ottenere con questa skill?
2. Raccontami 2-3 situazioni concrete in cui la useresti
3. Quali frasi diresti tipicamente per attivarla? (es. "aiutami a...", "crea un...", "genera...")

**Blocco 2 - Dettagli Tecnici**
4. Questa skill ha bisogno di:
   - Connettersi a servizi esterni (MCP server)?
   - Eseguire script o codice?
   - Accedere a file/risorse specifiche?

5. L'output che ti aspetti è:
   - Un documento/file specifico?
   - Una serie di azioni/step?
   - Una guida interattiva?

**Blocco 3 - Qualità e Test**
6. Come saprai che la skill ha funzionato bene? (criteri di successo specifici)
7. Vuoi che generi test cases per verificare il funzionamento? Se sì, descrivi 1-2 scenari di test importanti

**Blocco 4 - Preferenze**
8. Ci sono riferimenti, template o documenti che la skill dovrebbe consultare?
9. Preferenze di stile per le istruzioni? (tecnico/conversazionale/minimal)

#### Regole per la Discovery

- Fai le domande in modo conversazionale, non come un questionario
- Se l'utente è vago, chiedi esempi concreti
- Se l'utente ha già le idee chiare, non forzare tutte le domande
- Riassumi sempre quello che hai capito prima di procedere

---

### Fase 2: Design

Dopo la Discovery, presento una proposta di design strutturata:

```markdown
## Proposta di Design per [Nome Skill]

**Nome:** [kebab-case]
**Categoria:** [1-Document/Asset | 2-Workflow | 3-MCP Enhancement]

### Description Proposta
[Bozza completa con COSA + QUANDO + trigger phrases]

### Struttura Cartelle
[Albero delle cartelle con spiegazione di ogni elemento]

### Pattern Identificati
[Quali pattern dalla guida applicheremo]

### Confermi? Vuoi modificare qualcosa?
```

**Non procedo all'implementazione senza conferma esplicita.**

---

### Fase 3: Implementazione

Dopo la conferma, creo i file seguendo queste regole:

#### SKILL.md - Struttura Obbligatoria

```yaml
---
name: [kebab-case, uguale al nome cartella]
description: [COSA fa]. [QUANDO usarla]. [Trigger phrases].
license: MIT
metadata:
  author: [nome]
  version: 1.0.0
---
```

Seguito da:
- `## Overview` - 1-2 frasi sullo scopo
- `## Instructions` - Step numerati, chiari, actionable
- `## Examples` - Minimo 1-2 scenari completi
- `## Troubleshooting` - Errori comuni e soluzioni

#### Regole Critiche

| Elemento | Regola | Esempio |
|----------|--------|---------|
| Nome cartella | kebab-case | `sales-deck-creator` |
| Nome file | Esatto | `SKILL.md` (case-sensitive) |
| Description | COSA + QUANDO + trigger | Vedi references/esempi-description.md |
| Lunghezza | < 5000 parole | Sposta dettagli in references/ |
| README.md | MAI dentro la skill | Documentazione va in SKILL.md |
| Tag XML | MAI nel frontmatter | Causa errori di parsing |

---

### Fase 4: Validazione

Dopo aver creato i file, eseguo questa checklist automaticamente:

```
CHECKLIST VALIDAZIONE

Struttura
[ ] Nome cartella in kebab-case
[ ] SKILL.md esiste (case-sensitive)
[ ] Nessun README.md dentro la skill

Frontmatter
[ ] Delimitatori --- presenti
[ ] Campo name in kebab-case
[ ] Campo description completo (COSA + QUANDO + trigger)
[ ] Nessun tag XML (< >)
[ ] Metadata compilati

Contenuto
[ ] Overview presente e chiaro
[ ] Instructions con step numerati
[ ] Almeno 1-2 esempi concreti
[ ] Sezione Troubleshooting presente
```

Se trovo problemi, li segnalo e propongo correzioni.

---

### Fase 5: Test & Deployment

#### Test Cases Suggeriti

Genero test specifici basati sugli use case raccolti:

**Test di Triggering** - La skill DEVE attivarsi per le frasi concordate
**Test Funzionale** - Scenario completo con input/output attesi

#### Istruzioni di Installazione

Fornisco sempre istruzioni passo-passo per Claude Code e Claude.ai.

---

## Examples

### Example 1: Skill per Sales Deck

**User says:** "Devo creare una skill che mi aiuti a generare sales deck professionali"

**Discovery:**
- Obiettivo: Creare presentazioni di vendita consistenti
- Use case: Pitch per nuovi clienti, presentazioni prodotto
- Trigger: "crea un sales deck", "prepara una presentazione di vendita"
- Output: File PPTX o struttura slide
- Criteri: Brand consistency, struttura persuasiva

**Result:** Skill completa con template, struttura slide, e checklist qualità

### Example 2: Skill per Framework Personale

**User says:** "Voglio sistematizzare il mio framework di strategia in una skill"

**Discovery:**
- Obiettivo: Applicare framework proprietario in modo consistente
- Use case: Analisi strategica clienti, planning sessioni
- Trigger: "applica il framework X", "analisi strategica per"
- Output: Documento strutturato con analisi

**Result:** Skill che guida attraverso ogni step del framework

---

## Troubleshooting

### "Non so da dove partire"
**Causa:** Obiettivo troppo vago
**Soluzione:** Chiedo di descrivere l'ultima volta che hai fatto manualmente quello che vuoi automatizzare.

### "La skill non si attiva"
**Causa:** Description non contiene le frasi giuste
**Soluzione:** Rivediamo le frasi trigger reali che usi.

### "La skill si attiva per cose sbagliate"
**Causa:** Description troppo generica
**Soluzione:** Aggiungiamo trigger negativi: "Do NOT use for [cosa escludere]"

---

## References

Per approfondimenti consulta:
- `references/template-skill.md` - Template base per SKILL.md
- `references/checklist-validazione.md` - Checklist completa
- `references/esempi-description.md` - Esempi di description efficaci
- `references/pattern-comuni.md` - Pattern riutilizzabili
- `assets/struttura-cartelle.md` - Strutture per tipo di skill
