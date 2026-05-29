# Step 1 (Draft) + Step 2 (Breaking it up)

Questi due step costruiscono lo stesso albero: prima lo abbozzi (Draft), poi lo scomponi e lo colori
(Breaking it up). Lavora **un canale/driver per turno**.

---

## Step 1 — Draft

Obiettivo: mettere su carta l'assunzione centrale, i canali che tocca, e una stima grezza di upside.

### 1.1 — Assunzione centrale (una frase)

Cosa vuoi aggiungere/cambiare/investire e perché pensi porti valore.

> Esempio Tharin: *"Aggiungere la Collaboration a un prodotto B2B di gestione documenti (tipo
> Smallpdf), per far collaborare gli utenti sui documenti — feature oggi del tutto assente."*

### 1.2 — Canali principali (i value driver)

Quali aree del business l'iniziativa tocca. Per una **feature di prodotto**, i tre canali tipici di
Tharin:

1. **Conversion** — aggiungere valore influenza la conversione (free→trial, trial→pro).
2. **Network effects** — feature che si basano sulla collaborazione spingono gli inviti tra utenti.
3. **Retention** — la feature impatta la base esistente, idealmente riduce churn e aumenta stickiness.

> **Adatta al contesto** (vedi nota multi-contesto in SKILL.md):
> - **GTM/marketing**: i canali sono di acquisizione (SEO, paid, outbound, partnership, referral…) e
>   le metriche sono CAC, conversion di funnel, pipeline, payback.
> - **Consulting**: i canali e le metriche sono quelli del cliente; il framing è da deliverable.

### 1.3 — Stima grezza di upside + check soglia

Metti un numero iniziale, anche con i punti interrogativi: *"+6mio ARR ???"*. Serve solo a una cosa:
**verificare che superi la soglia minima** che l'utente si è dato (es. ">10% dell'ARR", cioè >5mio su
50mio). Se non la supera, **fermati**: non vale il business case. Se la supera, sai che regge su gambe
fragili e i prossimi step servono a valutarlo.

---

## Step 2 — Breaking it up

Obiettivo: scomporre ogni canale nei sotto-driver che contano, semplificare, e colorare.

### 2.1 — Scomponi ogni canale nei sotto-driver

Per ogni canale identifica i sotto-driver rilevanti. Esempio Tharin per **Conversion**:

- **SEO** — il canale principale di acquisizione dell'azienda; per la sua dimensione sarà toccato.
- **Free→Trial / Trial→Pro** — il funnel free→paid, soprattutto trial→pro quando gli utenti vedono
  l'utilità della collaborazione.
- **LTV** — se gli utenti adottano la collaborazione e invitano altri, sono più vincolati al prodotto
  → LTV più alto.

Per **Network effects**:
- **External users** — persone invitate che non sarebbero entrate altrimenti. Vanno visualizzate con
  il loro tasso di movimento nel prodotto.
- **LTV** — già identificato in Conversion → **visualizza solo il collegamento, non ricontarlo**
  (no double-counting).

Per **Retention**:
- **Clienti esistenti** (base di 1mio) — alcuni hanno questo bisogno; effetto diretto sul **churn**,
  che a sua volta tocca l'LTV (di nuovo: attento al double-counting).

> **Regola di semplicità**: limitati ai sotto-driver più importanti. Se l'albero diventa illeggibile,
> stai complicando troppo il caso.

### 2.2 — Semplifica e fai sense-check

Guarda l'albero e togli ciò che non regge. Esempio Tharin: elimina **"Paid"** dal grafo perché (a) ha
poco senso rispetto agli altri canali e (b) **l'azienda non ha mai dimostrato di saper gestire un
canale paid** (tutto viene da SEO). *Delete.*

Principio: tieni nel caso solo driver che possono muovere abbastanza upside. Se qualcosa è chiaramente
low-impact, cancellalo.

### 2.3 — Applica il color system

Colora ogni driver. Il colore riflette **quanto sei sicuro** che venga impattato **e di quanto** (al
momento è un mix di impatto + confidence; lo separi nello Step 3):

- 🔴 **Rosso** — wild guess, impatto/confidence poco chiari.
- 🟡 **Giallo** — stima parzialmente fondata, impatto medio-alto.
- 🟢 **Verde** — stima ben informata, impatto alto.

Esempio Tharin (esito del ragionamento driver per driver):

| Driver | Colore | Perché |
|---|---|---|
| SEO | 🟡 | Gran parte del business è SEO, anche un piccolo cambiamento conta — ma la SEO è difficile da muovere e la collaborazione non è un core use case |
| Free→Trial | 🟡 | La gente non si iscrive per la collaborazione, ma per gestire documenti |
| Trial→Pro | 🟢 | Una volta dentro, apprezzeranno l'aspetto collaborativo → grande impatto |
| LTV | 🟢 | Sappiamo da altri prodotti che l'LTV è guidato molto dai team collaborativi |
| Externals (network) | 🟢 | La collaborazione è un enorme driver di network effect — è il motivo per cui guardiamo l'opportunità |
| Clienti esistenti | 🟡 | Le funzioni collaborative impattano LTV/retention, ma non sappiamo quanti dei clienti attuali ne abbiano davvero bisogno |
| Reduced churn | 🟢 | Per i clienti impattati il miglioramento del churn può essere sostanziale (fino a ~+200% LTV nei casi noti) |

Il senso dell'esercizio **non è essere sicuri**, è **pensare ogni punto** e rendere visibile a
chiunque dove sei incerto.
