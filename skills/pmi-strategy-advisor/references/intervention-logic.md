# Logica di Intervento sulle Forze

Come pianificare interventi per ribilanciare le forze, stimare i costi politici, e sequenziare le azioni.

---

## Premessa

Rendere esplicito il peso di una forza è il primo passo. Il secondo è chiedersi se quel peso è il risultato di una scelta consapevole o di una deriva non presidiata.

- **Deriva:** spesso esiste una leva anche piccola che può cominciare a correggere la traiettoria
- **Scelta obbligata dal contesto:** saperlo esplicitamente permette almeno di smettere di sprecare energie a combatterla e di concentrarsi su dove si ha effettiva capacità di incidere

**Non tutte le forze sono ugualmente manovrabili.** Alcune sono strutturalmente difficili da toccare (strategia di business calata dall'alto dall'imprenditore, vincoli tecnici storici), altre sono più accessibili (stakeholder interni con leve procedurali, trend con framework di valutazione).

---

## Schema di Valutazione per Ogni Leva

Prima di proporre qualsiasi intervento, rispondere in sequenza a tre domande:

1. **Qual è la leva che posso usare per modificare il peso?**
2. **Qual è il costo di quella leva?** (capitale politico, tempo, rischio organizzativo)
3. **Qual è l'ostacolo principale che potrebbe impedirne l'efficacia?**

Mai proporre una leva senza rispondere a tutti e tre i punti.

---

## Tipologie di Leve per Forza

### Strategia di Business (troppo bassa o implicita)

**Obiettivo:** rendere la strategia esplicita e condivisa, ridurre l'ambiguità operativa.

| Leva | Costo | Ostacolo tipico |
|------|-------|-----------------|
| Facilitare una sessione strategica esplicita (1-2 ore) con imprenditore e team chiave | Medio — richiede apertura dell'imprenditore e tempo protetto | "Non abbiamo tempo adesso" / paura che la strategia esplicitata vincoli troppo |
| Produrre un one-pager strategico bozza e proporre all'imprenditore di validarlo | Basso — è un output scritto, non richiede confronto | Potrebbe essere rifiutato o ignorato se l'imprenditore non vuole formalizzare |
| Fare reverse engineering della strategia rivelata e condividerla come ipotesi | Basso — partire dai fatti (budget, decisioni, tempo) è meno threatening | Resistenza se la strategia rivelata è diversa da quella dichiarata — può creare imbarazzo |

---

### Trend Ineludibili (troppo alti)

**Obiettivo:** introdurre un filtro di valutazione prima che un trend entri nel backlog.

| Leva | Costo | Ostacolo tipico |
|------|-------|-----------------|
| Introdurre un criterio esplicito di valutazione: "quale cliente, quale job, quale metrica" per ogni trend prima di metterlo in roadmap | Basso — è un framework decisionale | Resistenza di chi porta il trend ("ma tutti lo stanno facendo!") |
| Richiedere un piccolo esperimento misurabile prima di investire su un trend | Medio — richiede capacità e tempo per il test | Il team non sa come misurare, o i tempi dell'esperimento sembrano troppo lunghi |
| Fare un audit delle feature trend-driven degli ultimi 12 mesi: quante sono usate? | Basso — è un'analisi retrospettiva | Può essere percepito come un atto di accusa verso chi ha spinto quelle feature |

---

### Stakeholder Interni (troppo alti)

**Obiettivo:** ridurre il volume di richieste non filtrate e aggiungere frizione produttiva al processo.

| Leva | Costo | Ostacolo tipico |
|------|-------|-----------------|
| Introdurre un processo formale di request (es. request for enhancement con template: problema, impatto atteso, priorità proposta) | Medio — richiede accordo degli stakeholder sul processo | La funzione che perde il canale informale si sente penalizzata, cerca di bypassare |
| Stabilire un forum periodico (bi-settimanale o mensile) per raccogliere le richieste degli stakeholder in modo aggregato invece di asincronico | Medio — richiede disponibilità di tutti i partecipanti | Stakeholder con urgenze continue vedono il forum come un rallentamento |
| Esplicitare la capacity del team come vincolo condiviso, non come opinione del PM | Basso se il team ha dati storici di velocity | "Siete troppo lenti" / resistenza ad accettare il vincolo come reale |
| Trasparenza sulla roadmap: pubblicare le priorità correnti e il processo di revisione | Basso | Chi perde priorità può fare pressione per cambiarle — richiede tenuta |

**Nota dall'esperienza:** il costo principale delle leve su questa forza è **relazionale**. Chi perde il canale informale diretto perde potere, e lo sente. Il lavoro di moral suasion per dimostrare che il nuovo processo è nell'interesse di entrambi richiede tempo e credibilità accumulata. Non aspettarsi risultati immediati.

---

### Vincoli Interni (non riconosciuti o sottovalutati)

**Obiettivo:** rendere i vincoli visibili e incorporarli nel processo di pianificazione prima che emergano come sorpresa.

| Leva | Costo | Ostacolo tipico |
|------|-------|-----------------|
| Introdurre velocity tracking di base (anche solo un foglio) per avere dati storici su stima vs reale | Basso — richiede poca infrastruttura | "Non abbiamo tempo per tracciare" / resistenza a misurare la propria velocità |
| Calendarizzare esplicitamente tempo per debito tecnico (es. 20% della capacity) | Medio — toglie capacity al backlog percepito | Business e stakeholder vedono il tempo sul debito come "non produttivo" |
| Fare un audit delle dipendenze tra persone: chi blocca chi quando non è disponibile? | Basso — è un'analisi strutturale | Può rivelare colli di bottiglia individuali che qualcuno non vuole vedere |
| Documentare la regola: nessuna stima senza breakdown in task da max 2 giorni | Basso se il team è d'accordo | Aumenta il tempo di planning percepito — resistenza di chi vuole muoversi "veloce e informale" |

---

### Comportamento dei Clienti (troppo basso o distorto)

**Obiettivo:** aumentare la qualità e la rappresentatività del segnale dal cliente, ridurre la distorsione del cliente singolo.

| Leva | Costo | Ostacolo tipico |
|------|-------|-----------------|
| Introdurre una routine di customer interview mensile (anche 2-3 conversazioni) | Basso — richiede principalmente tempo e volontà | "Non sappiamo come farlo bene" / "i clienti non rispondono" |
| Separare nel backlog le richieste di un singolo cliente dalle richieste multi-cliente | Basso — è una label o colonna | Politicamente sensibile se il singolo cliente è grande — il PM sembra ignorarlo |
| Usare metriche di utilizzo aggregate invece di feedback puntuale per validare priorità | Medio — richiede analytics di prodotto funzionante | "Non abbiamo i dati" (e quindi bisogna prima investire in analytics) |
| Fare una sessione di review della concentrazione del fatturato e delle implicazioni per la roadmap | Medio — richiede coinvolgimento del management | Rivela la dipendenza da pochi clienti, che può essere un tema sensibile |

---

## Principi di Sequenza degli Interventi

### 1. Non attivare due leve contemporaneamente se puoi evitarlo

Ogni leva crea attrito. Due leve contemporanee raddoppiano l'attrito e rendono più difficile capire quale intervento ha funzionato.

Eccezione: se una forza è critica e il contesto è favorevole (es. imprenditore aperto al cambiamento, momento di transizione dell'azienda), può valere la pena accelerare.

### 2. Inizia dalla leva con il rapporto costo/impatto più favorevole

Non sempre la leva più impattante è quella giusta per iniziare. Una leva a basso costo che crea una piccola vittoria visibile costruisce credibilità per le leve successive.

### 3. Misura prima di intervenire

Per ogni intervento, definisci prima come capirai se ha funzionato. Senza baseline, non sai se la situazione è migliorata o peggiorata.

### 4. Stima il capitale politico disponibile

Prima di attivare qualsiasi leva sugli stakeholder interni: quanta credibilità hai accumulato? Hai già dimostrato di capire il business (non solo il prodotto)? Hai già vinto una piccola battaglia?

Se hai appena iniziato un engagement, le leve a basso costo (analisi, trasparenza, documenti) sono più sicure delle leve procedurali (processi formali, criteri di filtraggio).

### 5. Il paradosso dell'imprenditore-stakeholder

In PMI, l'imprenditore è spesso contemporaneamente:
- La fonte della strategia di business (forza 1)
- Lo stakeholder interno più potente (forza 3)
- La persona che spinge i trend che ha letto sull'aereo (forza 2)

Intervenire su una forza spesso richiede il consenso dell'imprenditore. Questo significa che la sequenza giusta è quasi sempre: prima costruire il rapporto e la credibilità con l'imprenditore, poi proporre l'intervento.

---

## Segnali di Avanzamento

Come capire se un intervento sta funzionando:

| Forza | Segnale positivo | Segnale negativo |
|-------|-----------------|-----------------|
| Strategia di business | Il team risponde in modo coerente quando chiedi le priorità | La strategia continua a cambiare senza comunicazione |
| Trend | Le feature proposte hanno una metrica di successo definita | Si parla ancora di trend senza chiedersi "per quale cliente" |
| Stakeholder | Le richieste arrivano con contesto e impatto, non solo urgenza | Il canale informale è ancora il più usato |
| Vincoli | Le stime migliorano, i ritardi si riducono | "Siamo in ritardo anche questa volta" senza analisi della causa |
| Clienti | Si cita più spesso un pattern cross-cliente che una richiesta singola | Il backlog è ancora guidato dall'ultimo cliente che ha chiamato |
