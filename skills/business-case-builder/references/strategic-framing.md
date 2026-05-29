# Strategic Framing — quando e quanto fare un business case

Fonte: Leah Tharin, "The roadmap of a commercial PM". Questo è il **gate strategico** che viene prima
dei numeri. Risponde a due domande: *questa opportunità merita un business case in numeri duri?* e
*quanto pesante deve essere?*

## Il gate: Table stake / Differentiator / Debt

Ogni iniziativa ricade in una di tre categorie. Determinano se e come si fa il business case.

### 1. Table stake — *il minimo per partecipare al mercato*

Ciò che il mercato si aspetta come **base** per considerarti un prodotto della categoria. **Non ti
fanno comprare**: definiscono solo l'appartenenza alla categoria (un'auto ha 4 ruote, guida, è a
norma — nessuno la compra *per questo*).

- **Pensa al futuro, non a oggi.** Ciò che oggi entusiasma diventa table stake domani (vedi l'AI: 2
  anni fa differentiator, oggi attesa).
- **Metriche tipiche mosse**: retention 30day+, LTV, support tickets, sentiment, churn.
- **Trappola del data-driven**: mettere un table stake in **numeri duri è quasi impossibile**
  ("l'interfaccia fa schifo e i clienti si aspettano di più" non si quantifica). Il buy-in viene da
  **conviction condivisa su trend + sentiment**, non da un ARR.
- **Eccezione critica**: se il core del prodotto è messo male e i table stake non sono soddisfatti,
  *influenzi* l'acquisizione → è un problema di product-market fit (early stage o Red Queen effect).
  In quel caso la roadmap contiene **solo** table stake finché non sono a posto.

→ **Implicazione per il business case**: se l'opportunità è un table stake, **non forzare i numeri**.
Fai un caso leggero/qualitativo basato su conviction e sentiment. Dillo apertamente all'utente.

### 2. Differentiator — *ciò che ti fa scegliere e ti fa salire di prezzo*

Una **specializzazione opinionata** che fai meglio di chiunque altro. Permette di salire upmarket e
chiedere di più. In termini di Jobs theory: un **underserved need** (il bisogno "arrivare da A a B"
è table stake; "la mia auto è troppo costosa / rumorosa / piccola" è l'underserved need).

- **Non li costruisci tutti**: meglio padroneggiarne **uno** alla volta (più facile da comunicare e
  da onboardare). I table stake invece sono tutti obbligatori.
- **Metriche tipiche mosse**: conversion (free→trial, trial→paid), CAC, MQL di qualità, NRR,
  engagement, word of mouth / brand.
- **Si business-casano facilmente**, proprio perché sono specifici.

→ **Implicazione per il business case**: è il **terreno ideale**. Procedi col caso completo a 4 step.

### 3. Debt / Focus — *cosa ci rallenta / cosa togliere*

Bilanciare risorse tra costruire nuovo e mantenere l'esistente. Logica diversa dal business case di
upside:

- **Accountability**: cosa abbiamo promesso vs cosa abbiamo consegnato (sui deadline, non solo sui
  risultati commerciali).
- **Accept vs pay-back del debito**: lo accetti (lo metti a budget nei tempi) o lo ripaghi (rallenti
  ora per accelerare dopo). Il debito è un *investimento*, non solo un peso.
- **Unship**: quali feature fuori da table stake/differentiator costano più di quanto rendono. Prima
  di toglierle, **quantifica il downside** (chi le usa, quanto le rimpiangerebbe). Senza downside
  dimostrato, nessun CEO ti lascia togliere niente.

→ **Implicazione per il business case**: il "caso" qui è sul **downside** e sul costo-opportunità, non
sull'upside di revenue.

## Le 3 domande per categoria (dal framework roadmap di Tharin)

| | Table stakes (rivedi 1×/anno) | Differentiators (rivedi 1×/trimestre) | Focus (continuo) |
|---|---|---|---|
| Q1 | Cosa si aspetta il mercato come minimo nei prossimi ~5 anni? | Quali problemi ricorrenti dei nostri ICP crescono (o diventano risolvibili) nei prossimi 5 anni? | Quale debito tecnico/di prodotto ci ha rallentato negli ultimi trimestri? |
| Q2 | Dove siamo ora rispetto a quell'aspettativa? Cosa manca di critico? | Dove siamo ora rispetto a questi differentiator? | Quali feature lanciate, fuori da table stakes/differentiator, andrebbero dismesse? |
| Q3 | In che ordine affrontiamo i gap? | **Qual è il business case per ciascun differentiator?** | Qual è il downside finanziario di dismettere ciascuna? |

## La versione leggera del business case (per i differentiator)

Per un singolo differentiator non serve sempre il caso completo. Tharin usa una formula a una frase:

> *"Se 100 account provano il prodotto in 30 giorni, crediamo che 30 abbiano il problema di gestire
> file in bulk con la soluzione attuale. Pensiamo di convincerne 10 (30%) a comprare se risolviamo
> questo differentiator."*

Regole della versione leggera:
- Dietro ogni assunzione, **un dato** (anche piccolo).
- Più sei **specifico sul problema**, più è facile costruire il caso.
- **Parti dall'inizio della catena**: prima di analizzare cohort e milioni di dati, trova *qualche*
  ICP che ti dice in parole sue, senza imboccarlo, che ha quel problema. "Dietro ogni grande
  opportunità c'è un dolore reale."
- Rivisitalo spesso (anche trimestralmente) man mano che impari sui clienti.

## La matrice opportunity × cost (2×2)

Prioritizza i driver/iniziative su due assi: **Opportunity** (impatto) e **Cost** (tempo + soldi).

```
         Alto impatto
              │
   Fai DOPO   │   FAI SUBITO
 (high cost)  │   (low cost, high impact)
──────────────┼────────────── Costo →
  Ignora      │   Quick win
 (high cost,  │   (low cost,
  low impact) │    low impact)
              │
         Basso impatto
```

- **Prima i low-cost/high-impact.** Ovvio ma spesso ignorato (sono meno "sexy" da comunicare).
- **High-cost/high-impact**: di solito *dopo* le ottimizzazioni low-cost. Tendiamo a sottostimare i
  costi degli item grossi → si gonfiano e mangiano interi trimestri. Se ne hai uno con forte
  convinzione, **riduci il costo spezzandolo in milestone** misurabili (checkpoint per abortire/continuare).
- Affronti un high-cost/high-impact solo se: (a) hai esaurito le opportunità low-cost, oppure (b) il
  mercato ti costringe (Red Queen).

## I 5 principi di comunicazione del business case

1. **Comunica in range, non numero secco.** $1M–$10M comunica più incertezza di $5M–$6M.
2. **Semplice e centrato sul problema dell'ICP, non sulla feature.** La feature si menziona, ma sempre
   accanto al problema che risolve (così puoi pivotare se impari qualcosa). *Hint: "rendiamo i clienti
   più di successo" NON è un problema.*
3. **Si basa sulla tua conoscenza o su quella di altri?** Per i differentiator servono interviste ICP
   regolari. Mostra il problema (l'emozione grezza di un'intervista, un flusso rotto) + il dato. Se
   te lo porta qualcun altro (il CEO da un tradeshow), fidati ma **verifica** prima di committare.
4. **Onesto e realistico ≠ pessimista o ottimista.** Dichiara dove sei certo e dove no. L'incertezza è
   accettabile se l'upside è grande e l'allineamento con leadership è stato creato *prima*.
5. **Una pagina.** Ci si arriva in secondi, non minuti. Dati e ragionamento stanno nei dettagli sotto;
   l'overview contiene solo impact (se applicabile) e timeline.

> **Allineamento pre-presentazione**: una roadmap/un business case allineato si costruisce in tanti
> 1:1 con i vari silo *prima* della presentazione generale. Non mettere mai qualcuno in difficoltà
> presentando in pubblico qualcosa con cui non è allineato.
