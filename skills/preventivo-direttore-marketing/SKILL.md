---
name: preventivo-direttore-marketing
description: Crea preventivi personalizzati per il ruolo di Direttore Marketing Fractional per PMI italiane. Trigger - "preventivo per PMI", "proposta direttore marketing", "preventivo dir marketing", "proposta fractional PMI", "preventivo per azienda". Do NOT use per preventivi PMM startup (usa preventivo-pmm-fractional).
license: MIT
metadata:
  author: Stefano Martiradonna
  version: 1.0.0
---

# Preventivo — Direttore Marketing Fractional per PMI

Skill per creare preventivi personalizzati per ingaggi come Direttore Marketing Fractional con PMI italiane. Il preventivo viene generato attraverso una fase di intake (domande sul cliente) seguita dalla generazione del documento completo.

---

## Istruzioni

### Prima di iniziare

Leggi SEMPRE tutti i file in `references/` prima di generare il preventivo:
- `references/template-preventivo-dir-mktg.md` — Template base con struttura e regole di stile
- `references/framework-strategy-cascade.md` — Framework strategici di riferimento (Martin, Rumelt, Porter, Christensen, Lindstrom, Osterwalder)
- `references/guida-personalizzazione-pmi.md` — Guida per adattare il preventivo al settore e alla dimensione della PMI

---

### Step 1 — Intake

Poni queste domande a Stefano, una alla volta o in blocco:

1. **Azienda** — "Per quale azienda è il preventivo? Settore, dimensione indicativa (fatturato e/o dipendenti)?"
2. **Referente e decisore** — "Chi è il referente? (AD, titolare, DG) Chi prende la decisione?"
3. **Prodotti/servizi** — "Cosa fanno? Quali sono i prodotti o servizi principali?"
4. **Problema** — "Qual è il motivo del contatto? Cosa non sta funzionando o cosa vogliono raggiungere?"
5. **Team marketing** — "Hanno un team marketing interno? Se si, com'è composto? Chi fa cosa oggi?"
6. **Canali attuali** — "Quali canali usano oggi? (fiere, sito, social, rete vendita, agenti, formazione)"
7. **Urgenza e aspettative** — "C'è un evento che rende urgente? Cosa si aspettano dai primi 60 giorni?"

**Se Stefano fornisce contesto libero** (es. appunti dalla call, materiale), estrarre le risposte e chiedere conferma solo su ciò che manca.

---

### Step 2 — Analisi e premessa

Sulla base delle risposte:

1. **Identifica il problema dell'AD** — Non il problema di marketing, ma il problema di business che l'AD sente sulla pelle (fatturato, margini, clienti che se ne vanno, commerciali senza direzione)
2. **Formula il "why now"** — Perché affrontare questo lavoro adesso e non tra 6 mesi? Qual è il costo dell'inazione?
3. **Calibra le sotto-sezioni** — In base al settore e alla dimensione:
   - PMI di prodotto/manifattura: peso su fiere, rete vendita, distribuzione
   - PMI di servizi: peso su referral, contenuti, relazioni commerciali
   - PMI con storia lunga (20+ anni): riconoscere il valore dell'esperienza
4. **Scegli l'esempio di intervento specifico** (sezione 3.3) — Fiere? Formazione? Lancio prodotto? Deve essere rilevante per quel settore.
5. **Proponi la premessa** a Stefano prima di generare il resto. Chiedi conferma.

---

### Step 3 — Generazione del preventivo

Genera il preventivo completo seguendo la struttura in `references/template-preventivo-dir-mktg.md`:

1. **Intestazione formale** — Dati di Stefano + referente e ruolo del cliente
2. **Indice** — Sempre presente, con le 4 sezioni principali
3. **Premessa** — Personalizzata: problema dell'AD, why now, logica 60 giorni, nota operativa
4. **Fase 1 (Giorni 1-30)** — Analisi con sotto-sezioni:
   - 2.1 Segmenti target e percorso vendita
   - 2.2 Prodotti e contesto competitivo
   - 2.3 Osservazione del team
   - 2.4 Materiali e canali
   - 2.5 Prime correzioni immediate
   - Output Fase 1 (tabella con impatto atteso)
5. **Fase 2 (Giorni 31-60)** — Interventi con sotto-sezioni:
   - 3.1 Priorità operative (Impatto/Sforzo)
   - 3.2 Messaggi, materiali e primi asset
   - 3.3 Esempio intervento specifico [OPZIONALE, calibrato sul settore]
   - 3.4 Obiettivi business → marketing (cascading) — SEZIONE CORE
   - Output Fase 2 (tabella con impatto atteso)
6. **Compenso e condizioni** — Placeholder `[COMPENSO]` e `[CONDIZIONI]`

**Regole di generazione:**
- Italiano formale, zero anglicismi non necessari
- Tradurre i termini di marketing: "segmento target" non "target segment"
- Tono autorevole, professionale, mai confidenziale
- Intestazione formale con dati fiscali sempre presente
- Sotto-sezioni numerate gerarchicamente
- Tabelle per gli output con colonna "impatto atteso"
- Non citare MAI i framework per nome (l'AD non conosce Martin o Rumelt) — usa i principi
- La sezione 3.4 (cascading obiettivi) e il pezzo piu forte del preventivo: sviluppala in dettaglio

---

### Step 4 — Review e iterazione

Presenta la bozza a Stefano e chiedi:
- "La premessa aggancia il problema giusto?"
- "L'esempio di intervento specifico e rilevante per questo settore?"
- "Il livello di formalita e calibrato sul decisore?"

Itera fino a conferma.

---

## Esempi

### Esempio di trigger
- "Devo fare un preventivo per una PMI che fa dispositivi medici, 15M di fatturato"
- "Proposta direttore marketing per un'azienda food, 50 dipendenti, fanno B2B e B2C"
- "Preventivo per PMI manifatturiera, il titolare si è stufato di fare marketing a caso"

### Esempio di intake rapido
> Stefano: "Ho parlato con Ennio, è l'AD di MecTech. Fanno componenti meccanici di precisione, 8M di fatturato, 40 dipendenti. Il problema è che il commerciale va a fiere e torna con biglietti da visita che poi non lavora nessuno. Non hanno un CRM, il marketing lo fa la segretaria part-time. Ennio vuole capire come strutturare meglio il commerciale e il marketing."

Estrai:
1. MecTech, componenti meccanici, 8M fatturato, 40 dipendenti
2. Ennio, AD
3. Componenti meccanici di precisione
4. Lead da fiere non lavorati, no CRM, marketing non strutturato
5. Segretaria part-time, no team marketing
6. Fiere (canale principale), probabilmente sito e poco altro
7. Non urgenza specifica, ma frustrazione cronica

Chiedi conferma e procedi con Step 2.

---

## Troubleshooting

**Il preventivo sembra troppo "da agenzia"**
- Rileggere la premessa: deve parlare di fatturato, clienti, margini — non di brand awareness o engagement
- Verificare che non ci siano anglicismi inutili

**L'AD è molto operativo / molto delegante**
- AD operativo: più dettaglio sulle attività concrete, meno strategia alta
- AD delegante: più peso sulla direzione e sul "cosa cambierà", meno sul come

**Il settore è molto specifico (healthcare, regolamentato)**
- Aggiungere una nota sui vincoli normativi nella premessa
- Calibrare gli esempi di leve su ciò che è fattibile nel settore

**Non è chiaro se serve Dir. Marketing o PMM**
- Se è una startup tech (anche italiana): usa `preventivo-pmm-fractional`
- Se è una PMI tradizionale (manifattura, servizi, food, healthcare): usa questa skill
- Se è ambiguo: chiedi a Stefano
