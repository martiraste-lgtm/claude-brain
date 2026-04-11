---
name: preventivo-pmm-fractional
description: Crea preventivi personalizzati per il ruolo di Product Marketing Fractional per startup tech (B2B/B2C, early stage e growth). Trigger - "preventivo per startup", "proposta PMM", "preventivo product marketing", "proposta fractional per startup". Do NOT use per preventivi Direttore Marketing PMI (usa preventivo-direttore-marketing).
license: MIT
metadata:
  author: Stefano Martiradonna
  version: 1.0.0
---

# Preventivo — Product Marketing Fractional per Startup

Skill per creare preventivi personalizzati per ingaggi come Product Marketing Fractional con startup tech in fase early stage o growth. Il preventivo viene generato attraverso una fase di intake (domande sul cliente) seguita dalla generazione del documento completo.

---

## Istruzioni

### Prima di iniziare

Leggi SEMPRE tutti i file in `references/` prima di generare il preventivo:
- `references/template-preventivo-pmm.md` — Template base con struttura e regole di stile
- `references/framework-gtm-proprietario.md` — Framework GTM proprietario di Stefano
- `references/guida-personalizzazione.md` — Guida per adattare il preventivo alla fase e settore

---

### Step 1 — Intake

Poni queste domande al cliente (Stefano), una alla volta o in blocco se il contesto lo permette:

1. **Nome azienda e settore** — "Per quale startup è il preventivo? In che settore opera?"
2. **Fase** — "In che fase è? Pre-PMF, post-PMF, early growth, scaling? Indicativamente che ARR/revenue ha?"
3. **Prodotto** — "Cosa fanno in una frase? Qual è il prodotto/servizio principale?"
4. **Problema** — "Qual è il problema principale che li ha portati a cercarti? Cosa non sta funzionando?"
5. **Materiale esistente** — "Cosa hanno già? (strategy doc, ICP, positioning, asset, CRM, LP) Quanto è solido?"
6. **Team e decisore** — "Com'è il team? Chi decide? Il founder è coinvolto nel sales?"
7. **Urgenza** — "C'è una scadenza o un evento che rende urgente il lavoro? (round, lancio, hiring)"

**Se Stefano fornisce contesto libero** (es. appunti dalla call, materiale del cliente), estrarre le risposte alle 7 domande dal contesto e chiedere conferma solo su ciò che manca.

---

### Step 2 — Analisi e inquadramento

Sulla base delle risposte:

1. **Identifica il gap strategico** — Qual è la tensione tra dove sono e dove vogliono arrivare? Cosa manca concretamente?
2. **Calibra le fasi** — In base alla fase della startup, decidere il peso relativo di ogni fase del framework:
   - Pre-PMF: più discovery, validazione, meno scaling
   - Post-PMF early: equilibrato su tutte le fasi
   - Growth: più sistematizzazione, GTM, meno strategy da zero
3. **Proponi l'inquadramento** a Stefano prima di generare il preventivo completo. Chiedi conferma.

---

### Step 3 — Generazione del preventivo

Genera il preventivo completo seguendo la struttura in `references/template-preventivo-pmm.md`:

1. **Inquadramento** — Personalizzato al 100% per il cliente. Apri con il gap, non con i complimenti.
2. **Approccio** — Framework GTM con personalizzazione per la loro fase
3. **Piano di lavoro** — 4 blocchi (Mese 1 / Mese 2 / Mese 3 / Mesi 4-6) con obiettivo, aree di lavoro, deliverables per ogni fase
4. **Ritmo operativo** — Call, asincrono, workshop
5. **Revisione e continuità** — Verifiche a mese 1, 3, 6
6. **Compenso e condizioni** — Inserisci `[COMPENSO]` e `[CONDIZIONI]` come placeholder

**Regole di generazione:**
- Registro misto IT/EN (ECP, GTM, NSM, outreach, sales deck in inglese)
- Diretto, parla al founder come peer
- Niente formalismi (no "Egregio", no intestazione fiscale)
- Ogni deliverable è concreto e nominato
- Se il cliente ha gia materiale solido, la nota metodologica lo riconosce e accelera
- Non includere sezioni irrilevanti per la fase (es. non parlare di automazione a una startup pre-PMF)

---

### Step 4 — Review e iterazione

Presenta la bozza a Stefano e chiedi:
- "Qualcosa da aggiungere, togliere o riformulare?"
- "Il tono e il livello di dettaglio sono giusti per questo founder?"
- "Vuoi che approfondisca qualche sezione?"

Itera fino a conferma.

---

## Esempi

### Esempio di trigger
- "Devo fare un preventivo per una startup fintech in fase post-PMF che fa 300K ARR"
- "Prepara la proposta PMM per Acme, B2B SaaS healthcare, pre-PMF"
- "Preventivo product marketing per una startup DTC food in early growth"

### Esempio di intake rapido
> Stefano: "Ho fatto una call con Mario di TechCo. Fanno un SaaS per HR, post-PMF, 500K ARR. Il problema è che crescono solo da network. Hanno ICP e positioning ma non li usano. Team di 5, founder fa tutto il sales. Vogliono iniziare outbound entro 2 mesi."

In questo caso, estrai le risposte:
1. TechCo, HR SaaS
2. Post-PMF, 500K ARR
3. SaaS per HR
4. Crescita solo da network, no canali scalabili
5. ICP e positioning esistenti ma inutilizzati
6. Team 5, founder-led sales
7. Outbound entro 2 mesi

Chiedi conferma e procedi con Step 2.

---

## Troubleshooting

**Il preventivo sembra troppo generico**
- Torna all'inquadramento: deve contenere almeno 2 elementi specifici di quel cliente
- Verifica che i deliverables siano calibrati sulla fase (non un elenco standard)

**Il founder è molto tecnico / molto business**
- Adatta il linguaggio: founder tecnici vogliono vedere il "come", founder business vogliono vedere il "risultato"

**Lo scope sembra troppo ampio per il budget**
- Suggerisci a Stefano di ridurre le fasi o concentrarsi su un sotto-insieme del framework
