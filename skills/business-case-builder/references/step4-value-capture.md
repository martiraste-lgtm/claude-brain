# Step 4 — Connect to Value Capture

Qui le assunzioni diventano numeri di revenue. L'obiettivo non è la precisione, è una **stima
difendibile espressa con la giusta incertezza**, più un piano per ridurre il rischio prima di committare.

---

## 4.1 — Traduci ogni canale in numeri lungo la catena

Per ogni canale, costruisci la catena di calcolo da sinistra a destra, partendo dalle metriche di
business. Usa i numeri **verbatim dell'esempio Tharin** come modello di ragionamento (vedi anche
`worked-example.md`):

**Conversion**
```
10mio utenti/mese affetti (9mio existing + 1mio SEO)
  → 1% free-to-trial = 100k trial/mese
  → +25% miglioramento relativo della conversione
  → 20'000 nuovi trial/mese
  → 45% trial-to-pro
  → 9'000 nuovi clienti paganti/mese
  → LTV 75$ (era 50$, +50%)  ×  12
  ≈ +8mio ARR
```

**Network effects**
```
9'000 nuovi clienti/mese  ×  4 inviti a testa
  → 36'000 utenti invitati/mese
  → 5% conversion
  → 1'800 nuovi clienti/mese  ×  75$  ×  12
  ≈ +1.6mio ARR
```

**Retention**
```
1mio clienti esistenti  ×  25% con questo bisogno = 250k
  +5% retention annua assoluta  →  1.25% dei churned sopravvive
  100k churn/mese  ×  1.25% = 1'250 clienti salvati/mese  ×  75$  ×  12
  ≈ +1.1mio ARR
```

> Nota di fedeltà: nella catena Conversion, Tharin scrive "20'000 nuovi trial (25% di 100k)" e ci
> costruisce sopra i 9'000 clienti (45% di 20'000). Riproduci i suoi numeri così come sono — sono il
> modello di ragionamento, non un calcolo da "correggere".

## 4.2 — Somma e ottieni il totale

```
Conversion   +8.0mio ARR
Network        +1.6mio ARR
Retention      +1.1mio ARR
─────────────────────────
TOTALE        ≈ +10.7mio ARR
```

(L'ipotesi grezza iniziale era +6mio. Il modello la supera e supera la soglia >5mio → l'opportunità
regge.)

## 4.3 — Esprimi in range (non numero secco)

Il totale **non è un numero, è un range**. L'ampiezza riflette la confidence: i driver 🔴 allargano il
range, i 🟢 lo stringono.

Come costruirlo: prendi le assunzioni 🔴 (quelle che reggono di più il numero) e **flettile**.
Esempio: l'intero canale Conversion dipende dal "**+25% di miglioramento conversione**" (🔴, nessun
dato — solo product sense). Se invece fosse +15%, la Conversion scenderebbe di ~40% (da 8 a ~4.8mio).

```
Scenario basso (assunzioni 🔴 caute):   ~6–7mio ARR
Scenario alto  (assunzioni 🔴 ottimiste): ~11–12mio ARR
→ comunica: "+6mio – +12mio ARR"
```

Un range stretto (5–6M) = alta convinzione. Un range largo (1–10M) = molta incertezza. Il range **è**
l'informazione.

## 4.4 — Vista risk-adjusted (sanity check)

Oltre al range, una singola cifra "scontata" aiuta a confrontare opportunità tra loro. Euristica:

```
Valore atteso ≈ Upside totale  ×  confidence media del caso
```

Se la confidence media del caso è ~60–70%, allora 10.7mio × ~0.65 ≈ **~7mio ARR risk-adjusted**.

> Non è una formula sacra di Tharin — è un modo per "tagliare" l'ottimismo del totale e rendere
> comparabili opportunità con confidence diversa. Usala come sanity check, non come verità.

## 4.5 — Contestualizza ("revenue non esiste nel vuoto")

Quattro check prima di chiudere:

1. **% dell'ARR**: +10.7mio su 50mio ARR ≈ **21%**. È materiale (supera la soglia del 10%).
2. **Strategic fit**: l'opportunità è allineata con la strategia complessiva? (Nel caso: sì — risolve
   il "cattivo LTV" identificato come problema strategico.)
3. **Analisi comparativa**: come si confronta con le altre opportunità sul tavolo? (Opportunity × cost,
   vedi `strategic-framing.md`.)
4. **Vista risk-adjusted**: la confidence bassa riduce il valore atteso → tienine conto nel confronto.

## 4.6 — De-risking (il pezzo che rende il caso azionabile)

Identifica il **rischio a monte** che regge tutto, poi progetta come ridurlo *prima* di committare
l'intero investimento.

1. **Rischio critico**: nel caso, l'assunzione "+25% di conversione" guida gli ~8mio di Conversion —
   e siccome il Network effect dipende dai 9'000 clienti generati da quella conversione, **se salta la
   conversione, salta anche il network effect**. È il rischio upstream a massimo impatto.
2. **Painted door test**: valida l'interesse (es. mostra la feature, misura i click) *prima* di
   costruirla davvero.
3. **MVP in 1 quarter** sulla metrica critica: invece dei 4 quarter pieni, un MVP focalizzato sul tasso
   di adozione free→trial per testare l'assunzione chiave.
4. **Kill threshold esplicito**: *"Se l'MVP non raggiunge almeno +15% di miglioramento della
   conversione, rivalutiamo o uccidiamo il progetto."* La soglia va scritta **prima**, non dopo.

Questo collega lo Step 4 alle **milestone** dello Step 3: ogni milestone è un checkpoint
abort/continue, e il kill threshold è il criterio.

---

## Cosa porti fuori dallo Step 4

- Upside **per canale** + **totale**, in **range**.
- Vista **risk-adjusted** (1 cifra comparabile).
- **% dell'ARR** + strategic fit.
- **Piano di de-risking** con rischio critico, test, MVP e **kill threshold**.

→ Passa a `output-templates.md` per confezionare il deliverable.
