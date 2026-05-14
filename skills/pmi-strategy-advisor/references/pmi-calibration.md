# Calibrazione per PMI

Come il peso e la dinamica delle Cinque Forze cambiano in una PMI rispetto a una grande organizzazione complessa (corporate, enterprise, scale-up con struttura consolidata).

---

## Premessa

Il framework delle Cinque Forze è stato sviluppato nel contesto di product manager in grandi aziende. In una PMI le stesse forze esistono, ma i meccanismi sono diversi. Ignorare queste differenze porta a diagnosi sbagliate e interventi inutili.

La differenza principale non è di scala, è **strutturale**: nelle PMI la concentrazione del potere è molto più alta, la strategia è spesso implicita, e i confini tra le forze sono più porosi.

---

## Come cambiano le Cinque Forze in una PMI

### 1. Strategia di Business → Spesso nella testa dell'imprenditore

**In una grande organizzazione:** la strategia è (almeno formalmente) scritta, condivisa, declinata in obiettivi di business unit, poi di team.

**In una PMI:** la strategia esiste raramente come documento. Vive nella testa dell'imprenditore o del fondatore. Le persone del team la inferiscono dalle decisioni, dalle conversazioni, da cosa viene approvato e cosa no.

**Implicazioni per la diagnosi:**
- Non chiedere "qual è la vostra strategia" aspettandosi un documento — non esiste quasi mai
- La strategia rivelata (dove va il tempo, il budget, le energie dell'imprenditore) è molto più informativa di quella dichiarata
- Cambia rapidamente in risposta a stimoli esterni (un cliente importante, un competitor che si muove, un'opportunità di mercato) senza che il cambiamento venga comunicato formalmente

**Segnali di disfunzione tipica PMI:**
- La strategia cambia ogni 3-6 mesi senza che nessuno sappia perché
- Decisioni "strategiche" vengono prese in risposta a una singola conversazione con un cliente
- Il team di prodotto non sa con certezza quali sono le priorità dell'anno

---

### 2. Trend Ineludibili → Amplificati dalla minor capacità di assorbimento

**In una grande organizzazione:** c'è capacità di creare team dedicati, fare esperimenti isolati, assorbire il costo del fallimento su un trend.

**In una PMI:** il team è piccolo, ogni iniziativa compete direttamente con tutte le altre, e il costo di un trend sbagliato è alto in proporzione. Il rischio principale non è non seguire un trend, ma seguirne troppi senza prioritizzare.

**Implicazioni per la diagnosi:**
- Chiedi quanti trend stanno inseguendo contemporaneamente
- Un'AI feature aggiunta senza ripensare l'architettura e i costi è un segnale classico di pressione esterna non metabolizzata
- La pressione verso i trend arriva spesso attraverso l'imprenditore (che legge newsletter, frequenta eventi, parla con altri imprenditori) più che dal team

**Segnali di disfunzione tipica PMI:**
- "Dobbiamo fare l'AI perché tutti la stanno facendo" senza chiedersi per quale cliente e per quale job
- Feature aggiunte che nessuno usa perché erano "nel trend" di un anno fa
- Budget allocato su trend senza metriche di successo definite

---

### 3. Stakeholder Interni → Sostituiti dall'imprenditore con potere totale

**In una grande organizzazione:** gli stakeholder sono multipli (sales, ops, leadership, business unit), con poteri frammentati e interessi diversi che si compensano almeno parzialmente.

**In una PMI:** spesso c'è un singolo decisore — l'imprenditore o il fondatore — con potere totale e accesso diretto al team di prodotto. Questo è sia un vantaggio (meno burocrazia, decisioni rapide) che un rischio (nessun contrappeso, nessuna negoziazione).

**Variante frequente:** in PMI che hanno una funzione commerciale strutturata, il responsabile vendite diventa il secondo stakeholder più potente. Quando la funzione vendita ha accesso diretto al backlog, si crea una feature factory guidata dai deal.

**Implicazioni per la diagnosi:**
- Chi ha l'ultima parola su cosa si costruisce? Sempre la stessa persona?
- La funzione commerciale ha un canale diretto verso il team di sviluppo?
- Esiste un processo per valutare le richieste o tutto passa verbalmente?

**Segnali di disfunzione tipica PMI:**
- Imprenditore che parla direttamente con gli sviluppatori bypassando il processo
- Ogni nuovo deal porta con sé feature "obbligatorie" per chiudere il contratto
- Il responsabile commerciale ha di fatto una shadow roadmap che il team segue
- Il caso estremo (citato nel testo): l'imprenditore decide di far gestire il prodotto da un venditore, trasformando il team in un'integrazione sistemica a richiesta dei deal

---

### 4. Vincoli Interni → Più pesanti, meno visibili

**In una grande organizzazione:** i vincoli sono strutturali e visibili — team size ufficialmente definiti, roadmap formali, processi di capacity planning. La sfida è la burocrazia, non la mancanza di struttura.

**In una PMI:** i vincoli sono spesso invisibili perché non c'è capacity planning formale. Si promette senza sapere cosa costa. Si accumula debito tecnico perché non c'è mai il "momento giusto" per pagarlo. Le dipendenze tra le poche persone del team creano colli di bottiglia che nessuno mappa formalmente.

**Implicazioni per la diagnosi:**
- Chiedi: quando è l'ultima volta che una feature ha richiesto il doppio del tempo stimato?
- Esiste una stima della percentuale di lavoro che va su manutenzione/bug vs nuove feature?
- Ci sono persone che sono collo di bottiglia su tutto (il "10x dev" che però blocca tutto ciò che non fa da sola)?

**Segnali di disfunzione tipica PMI:**
- Nessun sprint o processo iterativo formale → tutto è urgente, tutto è in ritardo
- Debito tecnico mai affrontato direttamente → "lo faremo dopo il prossimo rilascio" da 3 anni
- Team piccolo con troppe dipendenze cross-skill → ogni assenza blocca

---

### 5. Comportamento dei Clienti → Direttamente accessibile, ma rischio "cliente singolo"

**In una grande organizzazione:** l'accesso al cliente è mediato da CS, sales, analytics. La voce del cliente è filtrata e aggregata prima di arrivare al team di prodotto.

**In una PMI:** il fondatore spesso conosce personalmente i clienti. L'accesso è diretto. Ma questo crea un rischio opposto: **over-indexing sul cliente singolo**.

**Due regimi estremi in PMI:**

**PMI con pochi clienti grandi (es. 3-5 clienti che fanno il 70%+ del fatturato):**
- Di fatto si fa custom development mascherato da prodotto
- La roadmap è la somma delle richieste dei clienti top
- Non c'è strategia di prodotto, c'è servizio personalizzato con pricing da prodotto

**PMI con molti clienti piccoli:**
- La voce del cliente è accessibile ma richiede aggregazione
- Il rischio è che senza analytics, si senta solo chi si lamenta (survivorship bias del feedback)
- I clienti soddisfatti sono silenziosi; quelli che chiedono feature sono rumorosi

**Implicazioni per la diagnosi:**
- Qual è la concentrazione del fatturato sui top 5 clienti?
- Come arrivano le richieste dei clienti al team? Passano da sales/CS o arrivano direttamente?
- Esiste un processo per distinguere "richiesta di un singolo cliente" da "pattern trasversale"?

---

## Profilo Tipico di Disfunzione PMI

Il pattern più comune nelle PMI con 5-50M di fatturato e un team di prodotto piccolo (1-5 persone):

| Forza | Peso tipico | Giudizio tipico |
|-------|-------------|-----------------|
| Strategia di business | 4-6 | Troppo basso (implicita, cambia spesso) |
| Trend ineludibili | 5-7 | Troppo alto (inseguiti senza filtro) |
| Stakeholder interni | 8-9 | Troppo alto (imprenditore o sales dominano) |
| Vincoli interni | 7-8 | Troppo alto (ma sottovalutati in planning) |
| Comportamento clienti | 3-5 | Troppo basso (o distorto sul cliente singolo) |

Questo non è un dato statistico, è un pattern qualitativo ricorrente. Serve come ipotesi di partenza in assenza di dati specifici, da validare o falsificare con le domande diagnostiche.

---

## Domande Diagnostiche Specifiche per PMI

Queste domande completano quelle generali in `five-forces-radar.md`:

1. **Strategia:** "Se chiedo al tuo team operativo quali sono le priorità di prodotto per il prossimo anno, quanto si avvicineranno alla tua risposta?"
2. **Trend:** "Negli ultimi 12 mesi, quante feature avete costruito principalmente perché 'lo facevano tutti'? Quante le usano davvero i clienti?"
3. **Stakeholder:** "Riesci a dire no a una richiesta diretta del titolare (o del responsabile commerciale)? Cosa succede in quel caso?"
4. **Vincoli:** "L'ultima volta che avete stimato una feature e poi impiegato il doppio del tempo: cosa è successo? Qual era la causa?"
5. **Clienti:** "Il tuo top cliente per fatturato: quanto della roadmap degli ultimi 12 mesi dipende da sue richieste specifiche?"
