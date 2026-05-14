# Il Radar delle Cinque Forze

Framework per diagnosticare quali forze determinano realmente le decisioni di prodotto e di priorità in un'organizzazione complessa.

**Fonte originale:** framework sviluppato nel contesto del product management in grandi organizzazioni (autore: Gianluca Diegoli, usato in seminari su product strategy). Adattato qui per uso in consulting engagement.

---

## Premessa

Le decisioni di prodotto in un'organizzazione già esistente non dipendono solo dai clienti, e non sono frutto di un processo lineare. Sono il risultato di una **negoziazione, spesso implicita**, tra forze diverse che agiscono contemporaneamente e hanno pesi diversi a seconda del contesto, del momento e della persona al centro.

Ignorare questo significa prendere decisioni come se si vivesse in un sistema più semplice di quello reale.

La rappresentazione a **radar** sottolinea la dinamicità del sistema: le forze sono sempre in tensione, i pesi cambiano nel tempo, e modificare una forza ha effetti sulle altre.

---

## Le Cinque Forze

### 1. Strategia di Business

**Cosa è:** La direzione aziendale che definisce il perimetro entro cui si opera. Vincola alcune scelte, ne abilita altre.

**Framework teorici correlati:**
- Strategy Choice Cascade (Roger Martin, *Playing to Win*): 5 scelte concatenate — winning aspiration, where to play, how to win, capabilities, management systems — ogni livello vincola il successivo
- Strategic Intents (Melissa Perri): la strategia scende dall'alto e si propaga fino al backlog
- Product Strategy Stack (Ravi Mehta, Reforge): stessa logica, formalizzata per product orgs

**Come si manifesta in pratica:**
- Quando è sana: orienta le priorità, crea senso di direzione, riduce le negoziazioni continue
- Quando è disfunzionale: schiaccia l'autonomia, le scelte vengono calate dall'alto senza margine di interpretazione, il team esegue senza capire perché
- In PMI: spesso è implicita nella testa dell'imprenditore, non scritta, mai allineata formalmente col team

**Domande diagnostiche:**
- Hai visto una strategia scritta? Se sì, quando è stata prodotta?
- Chiedendo a tre persone diverse "dove sta andando questa azienda", le risposte si somigliano?
- Le ultime 5 decisioni importanti sono coerenti con la direzione dichiarata?

---

### 2. Trend Ineludibili

**Cosa sono:** Tendenze di mercato che non si possono ignorare senza perdere rilevanza competitiva. Oggi l'esempio più visibile è l'AI generativa. Ma vale anche per nuove regolamentazioni, disruption tecnologiche, cambi di comportamento d'acquisto.

**Meccanismo di pressione:** Creare pressione a adottare qualcosa non perché sia la cosa giusta per il prodotto e per i clienti, ma perché "non averlo è percepito come un segnale di arretratezza" da analisti, investitori, clienti.

**I tre problemi tipici della risposta ai trend:**
1. **Feature cosmética:** il trend viene aggiunto a un'architettura esistente in modo artificiale, senza ripensare il flusso utente né portare valore misurabile
2. **Skill gap:** introdurre un trend richiede competenze che il team non ha, e il tempo di apprendimento erode il tempo di sviluppo
3. **Struttura dei costi:** alcuni trend (es. AI) cambiano il modello economico del prodotto — costo marginale variabile invece che fisso — e questo rompe il pricing esistente

**Domande diagnostiche:**
- Quali trend senti che devi seguire "altrimenti rimani indietro"?
- Di queste iniziative trend-driven, quante hanno prodotto valore misurabile per i clienti?
- Chi nel team è in grado di valutare se un trend vale davvero la pena?

---

### 3. Stakeholder Interni

**Cosa sono:** Chi ha il potere, formale o informale, di orientare le priorità. Sales, operations, business unit, leadership, imprenditore.

**Framework teorici correlati:**
- Marty Cagan (*Inspired*, *Empowered*): lo stakeholder non è un cliente da accontentare, è un partner da coinvolgere. Ma quando il sistema è disfunzionale, la roadmap diventa la somma delle richieste di chi grida più forte.
- John Cutler: il problema non è sempre individuale (il PM "non abbastanza bravo"). Spesso è strutturale: le pressioni interne hanno un canale diretto verso il backlog, e nessun PM da solo può compensare.

**Come si manifesta in pratica:**
- Feature factory: il backlog è guidato da richieste, non da problemi. Ogni richiesta arriva con priorità massima.
- Shadow roadmap: gli stakeholder più forti hanno già deciso cosa si farà, il processo formale è una formalità
- Escalation loop: ogni "no" viene scavalcato andando più in alto nella gerarchia

**Domande diagnostiche:**
- Da dove vengono la maggior parte delle feature nel backlog?
- Chi può far cambiare una priorità già definita, e come lo fa di solito?
- Esiste un processo formale per ricevere richieste? Viene usato?

---

### 4. Vincoli Interni

**Cosa sono:** Capacity del team, debito tecnico, dipendenze tra team, organizational drag. La forza più pesante e paradossalmente la più sottovalutata in fase di pianificazione.

**Framework teorici correlati:**
- John Cutler (*The Beautiful Mess*): tassonomia di disfunzioni che nascono da capacity, debito tecnico, dipendenze tra team. Tesi: "il prodotto è il sistema, non solo quello che il sistema produce."

**I tre vincoli principali:**
1. **Capacity del team:** il perimetro del team di ingegneria non ha capacità infinita — ogni nuova iniziativa compete con le altre
2. **Debito tecnico:** più o meno rilevante a seconda della storia del prodotto, ma sempre presente. Capace di impedire intere classi di scelte.
3. **Tempo di apprendimento:** ogni nuova esigenza tecnica significativa porta con sé una curva di apprendimento che erode il tempo di sviluppo disponibile

**Come si manifesta in pratica:**
- Roadmap irrealistiche: promesse fatte senza verificare la capacity reale
- Silos: dipendenze tra team rallentano ogni iniziativa cross-funzionale
- Everest tecnico: il debito tecnico è così alto che ogni nuova feature richiede il triplo del tempo stimato

**Domande diagnostiche:**
- Quando l'ultima roadmap è slittata? Di quanto? Per quali ragioni?
- Qual è la percentuale stimata di tempo dedicata al debito tecnico vs nuove feature?
- Ci sono aree del codebase/sistema che nessuno vuole toccare?

---

### 5. Comportamento dei Clienti

**Cosa è:** Bisogni, comportamenti, segnali d'uso, pattern di acquisto e abbandono dei clienti.

**Framework teorici correlati:**
- Jobs to Be Done (Christensen, Bob Moesta): i clienti "assumono" soluzioni per portare a termine un lavoro — con dimensioni funzionali, emotive, sociali
- Continuous discovery (Teresa Torres): l'ascolto del cliente come pratica quotidiana, non episodica
- Design thinking: primato del bisogno utente come punto di partenza

**Il paradosso della voce del cliente:**
Mentre gli strumenti per ascoltarla non sono mai stati così buoni (analytics, NPS, session recording, JTBD interviews), la capacità effettiva dei clienti di orientare la roadmap dipende da quanto le altre quattro forze lasciano spazio.

**Due regimi molto diversi:**
- **Pochi clienti grandi:** un singolo cliente da decine di milioni può far deragliare qualsiasi roadmap. Si fa custom development mascherato da prodotto.
- **Molti clienti piccoli:** le metriche aggregate sono la bussola principale, nessun cliente singolo ha abbastanza peso da imporre la direzione.

**Domande diagnostiche:**
- Come arriva la voce del cliente al team di prodotto? Attraverso quanti livelli di mediazione?
- Qual è la concentrazione del fatturato? I primi 3 clienti quanto pesano sul totale?
- Quando è l'ultima volta che qualcuno nel team ha parlato direttamente con un cliente (non tramite sales o CS)?

---

## Perché i Competitor NON sono una Forza

Inserire "cosa fanno i competitor" tra le forze che orientano le decisioni significa collocarsi strutturalmente in posizione reattiva: si decide cosa costruire in funzione di ciò che costruisce qualcun altro.

L'analisi competitiva è uno strumento informativo essenziale. Sapere come i competitor si posizionano, quali segmenti presidiano, come prezzano, quali funzionalità hanno o non hanno è utile per calibrare le proprie scelte. Ma entra nel processo come **dato di contesto**, non come una forza che determina la direzione.

La distinzione conta: nel primo caso si risponde a qualcun altro. Nel secondo si usa l'informazione per decidere autonomamente dove andare.

---

## Come Valutare il Peso di Ogni Forza

Per ciascuna delle cinque forze, valuta due dimensioni:

### Dimensione 1: Peso percepito (1–10)
Quanto questa forza incide realmente sulle decisioni — non quanto dovrebbe, ma quanto lo fa nella pratica. 1 = quasi nessuna influenza, 10 = determina praticamente tutto.

### Dimensione 2: Giudizio qualitativo
Quel peso è:
- **Troppo basso**: questa forza dovrebbe pesare di più per una strategia sana
- **Giusto**: il peso attuale è equilibrato rispetto al contesto
- **Troppo alto**: questa forza è dominante in modo disfunzionale

### Come leggere la combinazione

La stessa media descrive scenari completamente diversi a seconda del giudizio:

| Peso | Giudizio | Cosa significa |
|------|----------|----------------|
| Alto | Giusto | Forza dominante e legittima — non toccare |
| Alto | Troppo alto | Forza disfunzionale — intervento necessario |
| Basso | Giusto | Forza marginale e correttamente marginale |
| Basso | Troppo basso | Forza trascurata — attenzione, rischio latente |

---

## Domande di Sintesi Post-Diagnosi

Dopo aver mappato tutte e cinque le forze:

1. **Quale forza è dominante?** Il comportamento reale dell'organizzazione è spiegabile principalmente da una forza?
2. **Questa dominanza è coerente con la strategia dichiarata?** O la contraddice?
3. **Quale forza è più sottopesata rispetto a dove dovrebbe essere?**
4. **Se potessi spostare il peso di una sola forza, quale cambierebbe di più il sistema?**
