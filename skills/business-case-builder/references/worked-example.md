# Worked Example — "Collaboration" (caso nativo Tharin)

Esempio completo end-to-end, **numeri verbatim dalla serie "Business Case 101"**. Usalo per mostrare
all'utente come si presenta un caso finito, o come ancora per ragionare. Sotto, le note di adattamento
per i contesti GTM e consulting (adattamenti dichiarati, non contenuto letterale di Tharin).

---

## Contesto

Gestiamo un prodotto tipo **Smallpdf** (gestione documenti digitali: PDF, doc, xls). Vogliamo valutare
se vale la pena aggiungere la **Collaboration** (far collaborare gli utenti sui documenti) — feature
oggi del tutto assente.

### Metriche di business (assunte e dichiarate)

| Metrica | Valore |
|---|---|
| Utenti attivi free mensili (MAU) | 50mio |
| ARR (tutto self-serve) | 50mio |
| Utenti paganti | 1mio |
| LTV medio per cliente | 50$ |
| Subscription | ~4$/mese |
| Churn medio | ~1 anno (4×12 ≈ 50$) |
| Churn mensile complessivo | 100'000 clienti |
| **Soglia minima** d'investimento | iniziative che muovono ≥10% dell'ARR (>5mio) |

---

## Step 1 — Draft

- **Assunzione**: aggiungere "Collaboration" al prodotto.
- **Canali toccati**: Conversion, Network effects, Retention.
- **Upside grezzo iniziale**: +6mio ARR (??). Supera la soglia (>5mio) → vale la pena continuare. Ma
  regge su gambe fragili → si scompone.

## Step 2 — Breaking it up + color

```
Add "Collaboration"  ┌─ Conversion ──→ SEO 🟡 / Free→Trial 🟡 / Trial→Pro 🟢 / LTV 🟢
to a B2B product ────┼─ Network effects ──→ Externals 🟢   (LTV: solo collegamento, no double-count)
                     └─ Retention ──→ Existing customers 🟡 / Reduced churn 🟢
```

Sense-check: **"Paid" eliminato** — l'azienda non ha mai dimostrato un canale paid (tutto è SEO).

## Step 3 — Impact / Confidence / Effort (sintesi)

- **Trial→Pro, LTV, Externals, Reduced churn**: 🟢 alto impatto + buona confidence (domain closeness +
  evidenza da altri prodotti che l'LTV è guidato dai team collaborativi).
- **SEO, Free→Trial, Existing customers**: 🟡 — impatto reale ma confidence media (SEO difficile da
  muovere; non sappiamo quanti clienti esistenti abbiano davvero il bisogno).
- **Assunzioni 🔴 chiave** (emergono nei numeri): +25% miglioramento conversione, 4 inviti/utente, +5%
  retention.
- **Effort**: il team non ha mai costruito collaborazione, impatta marketing/growth/sales → stima
  iniziale 2 quarter, **rivista a 4 quarter** (un team intero). Complex, non solo difficult.

## Step 4 — Connect to Value Capture

**Conversion** → +8mio ARR
```
10mio utenti/mese (9mio existing + 1mio SEO) → 1% trial = 100k → +25% → 20'000 nuovi trial/mese
→ 45% trial-to-pro → 9'000 nuovi clienti/mese × 75$ (LTV +50%) × 12 ≈ 8mio ARR
```

**Network effects** → +1.6mio ARR
```
9'000 clienti/mese × 4 inviti → 36'000 utenti/mese → 5% → 1'800 nuovi clienti/mese × 75$ × 12 ≈ 1.6mio
```

**Retention** → +1.1mio ARR
```
1mio clienti × 25% bisogno → +5% retention → 1.25% dei churned salvato
100k churn/mese × 1.25% = 1'250 clienti/mese × 75$ × 12 ≈ 1.1mio
```

**Totale ≈ +10.7mio ARR** (≈ 21% dell'ARR). Range comunicabile: **~+6mio / +12mio ARR**
(dipende quasi tutto dal +25% di conversione 🔴). Risk-adjusted (~0.65) ≈ ~7mio.

**De-risking**: il rischio critico è il +25% di conversione (regge sia Conversion sia, a cascata, il
Network effect). → painted door test + MVP in 1 quarter sul free→trial + **kill threshold: se l'MVP
non fa almeno +15% conversione, si rivaluta**.

---

# Note di adattamento (estensioni del metodo, NON Tharin letterale)

Lo **scheletro a 4 step è identico**. Cambiano i canali e le metriche.

## Contesto GTM / marketing

"Vale la pena investire in [canale/campagna/lancio]?"

- **Canali (Step 1-2)** = leve di acquisizione e funnel: SEO/contenuti, paid, outbound, partnership,
  referral, eventi.
- **Metriche (Step 4)** = invece di "conversion → LTV → ARR": spesa → impression/lead → MQL → SQL →
  pipeline → win rate → revenue; oppure CAC, payback, ROAS.
- **Esempio di catena**: budget 30k → CPL 50€ → 600 lead → 15% MQL = 90 MQL → 25% SQL = ~22 SQL →
  20% win = ~4-5 nuovi clienti × ACV → revenue; confronta col CAC/payback target.
- **Color system e de-risking**: identici. Il rischio critico spesso è il tasso di conversione del
  canale nuovo (🔴 se non l'hai mai testato) → test a budget ridotto prima di scalare (l'equivalente
  del painted door).
- **Gate strategico**: una campagna "me too" su un canale saturo è spesso un table stake (poco
  business-casabile in upside); un canale/angle differenziante è il terreno giusto.

## Contesto consulting (deliverable per cliente)

Business case da consegnare a una startup/PMI che segui come fractional.

- **Metriche e baseline** sono quelle del **cliente** (vanno raccolte o assunte e dichiarate
  esplicitamente, come fa Tharin).
- **Framing**: documento da leadership. Apri con la raccomandazione e l'upside in range (una pagina,
  vedi `output-templates.md`), poi il dettaglio.
- **Tono**: meno "sparring interno", più deliverable difendibile — ma stessa onestà sull'incertezza
  (reliability batte optimism vale doppio quando il tuo nome è sul documento).
- **Attenzione al double-counting e all'optimism bias**: in un deliverable cliente sono i due errori
  che ti fanno perdere credibilità. Marca i 🔴 come assunzioni esplicite da validare insieme al cliente.
