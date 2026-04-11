# Framework: Reverse-Engineering della Strategia

**Concetto chiave:** Osserva ciò che fanno, non ciò che dicono.

---

## Il Gap: Strategia Dichiarata vs Strategia Rivelata

### Strategia Dichiarata (Stated Strategy)
- Ciò che viene presentato nelle slide PowerPoint
- Ciò che i dirigenti dicono nei discorsi ufficiali
- Ciò che è scritto nella mission statement

### Strategia Rivelata (Revealed Strategy)
- Dove viene effettivamente speso il budget
- Ciò che viene realmente costruito dal team tecnico
- Come gli utenti si comportano effettivamente con il prodotto

**La domanda giusta:** Cosa rivelano le nostre azioni e il tempo che dedichiamo sulle nostre reali priorità? Le vere priorità non sono quelle che dichiariamo, ma quelle che si vedono da come agiamo e usiamo il nostro tempo.

---

## Processo in 4 Step

### Step 1: Documentare le Decisioni Reali

Elencare ogni decisione significativa degli ultimi 12-18 mesi:
- Funzionalità aggiunte o rimosse
- Allocazione risorse
- Cambiamenti di prezzo
- Espansioni o contrazioni di mercato
- Investimenti tecnologici

### Step 2: Seguire i Soldi e il Tempo

Capire dove l'azienda investe realmente:
- Numero di ingegneri per area di prodotto
- Spesa marketing per segmento
- Attenzione dei dirigenti (meeting, email, presentazioni)
- Pattern ricorrenti di allocazione risorse

### Step 3: Analizzare il Comportamento degli Utenti

Confrontare ipotesi con realtà:
- Funzionalità più utilizzate vs più richieste
- Workflow reali vs workflow ipotizzati
- Fattori di ritenzione (perché restano) vs motivi d'acquisto (perché comprano)
- Pattern e tendenze di utilizzo

### Step 4: Condividere e Allineare

Usare i dati per correggere la rotta:
- Presentare i risultati al team di prodotto
- Coinvolgere stakeholder
- Identificare lacune e disallineamenti
- Proporre riallineamento basato sulle evidenze

---

## Casi Studio di Pivot basati su Strategia Rivelata

### Discord
- **Dichiarata:** Piattaforma per il gaming
- **Rivelata:** 78% dell'uso era per scopi non legati al gaming
- **Risultato:** Piattaforma di comunicazione per community generiche, IPO 2025, fatturato >$600M

### Loom
- **Dichiarata:** Strumento per la produttività degli sviluppatori
- **Rivelata:** 80% degli utenti esperti comunicava con persone fuori dall'ufficio. Creavano librerie video per onboarding e sostituivano la comunicazione scritta
- **Risultato:** "Messaggistica video asincrona per lavoro" → Acquisizione Atlassian per $975M
- **Scelte di prodotto derivate:** Librerie video centralizzate, collaborazione di gruppo, controlli sicurezza enterprise

### dbt Labs (ex Fishtown Analytics)
- **Dichiarata:** Società di consulenza
- **Rivelata:** Lo strumento interno (dbt) aveva 1.000+ utenti con crescita 3x YoY, mentre la consulenza era in stagnazione
- **Risultato:** Trasformazione in piattaforma SaaS, valutazione $4.2B, ARR >$100M nel 2024

---

## Consigli Pratici per il Reverse Engineering

### Come Prepararsi
- **Pratica prima su un'altra azienda:** Come guardare il filmato di una partita. Permette di individuare schemi e scelte che distinguono i vincitori
- **Gruppo cross-funzionale:** Includi persone da ogni livello — executive, middle manager, front-line
- **Tempistiche:** 3-4 ore per la prima sessione (60-90 min raccolta prove, 60-90 min framework, 60 min discussione)

### Come Facilitare
- **Cerca prospettive diverse** che vadano oltre la leadership
- **Rispondi nel modo in cui le cose vengono fatte**, non come vorresti che fossero
- Se qualcuno dice "Questa non è la nostra strategia", rispondi: **"Aiutaci a capire quali prove lo supportano"**
- La conversazione deve restare ancorata a **comportamenti osservabili**, non opinioni

### Come Gestire i Disaccordi
- Chiedi a ciascuno di citare **prove specifiche** (decisioni prodotto, allocazione risorse, comportamento utenti)
- L'obiettivo non è il consenso sull'interpretazione, ma l'**accordo sui fatti**

---

## Le Tre Opzioni Dopo il Reverse Engineering

### Opzione 1: Allineare le Azioni alla Strategia Dichiarata
**Quando:** La strategia dichiarata ha ancora senso, ma l'esecuzione è disconnessa.
- Riallocare risorse in base alle scelte strategiche
- Stabilire allineamento più chiaro tra criteri decisionali e scelte
- Creare strutture, parametri e meccanismi di accountability

### Opzione 2: Riprogettare la Strategia in Base alle Prove
**Quando:** Il comportamento utenti e la realtà del mercato indicano una direzione diversa.
- Progettare nuove scelte attraverso la Strategy Cascade
- Raddoppiare le opportunità emergenti rivelate dagli utenti
- Prendere la decisione difficile di smettere di giocare dove non vincerai mai

### Opzione 3: Approccio Ibrido
**Quando:** Serve una combinazione.
- Mantenere gli elementi delle scelte attuali che funzionano (di solito nel "Where to Play")
- Incorporare nuove intuizioni dal comportamento utenti e feedback mercato
- Stabilire connettività più chiara tra le scelte strategiche
