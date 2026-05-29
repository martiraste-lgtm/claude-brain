# Framework — Il business casing di Leah Tharin

Leggi questo file **all'inizio** di ogni sessione. È la mappa del metodo.

## Cos'è un business case (e cosa NON è)

Un business case è uno **strumento veloce per valutare se un'opportunità vale l'investimento, *prima*
di impegnare risorse sostanziali**. È risk management, non un esercizio contabile.

> "Business cases are not science, and therefore too much validation is counterproductive."

Non serve a essere certi. Serve a **pensare ogni punto** in modo strutturato e a sfidare le proprie
idee meglio di "sono sicuro che funzioni, ci credo". Il valore è nel ragionamento, non nella terza
cifra decimale.

## I 4 step

```
1. Draft            →  2. Breaking it up   →  3. Evaluate            →  4. Connect to
   (assunzione +        (scomponi i             (Confidence /            Value Capture
    canali +            driver nei              Impact /                 (revenue, range,
    upside grezzo)      sotto-driver)           Effort)                  risk-adjusted)
```

1. **Draft** — Costruisci l'assunzione centrale e i principali **value driver** (i canali che
   l'iniziativa tocca). Metti una stima grezza di upside per verificare che superi la soglia minima
   che ti sei dato.
2. **Breaking it up** — Scomponi ogni canale nei sotto-driver che contano. Semplifica (togli i
   non-provati). Applica il **color system** 🔴🟡🟢.
3. **Evaluate** — Per ogni driver valuta **Confidence** (quanto sei sicuro), **Impact** (quanto pesa
   il delta per l'utente) e **Effort** (Difficult vs Complex).
4. **Connect to Value Capture** — Traduci le assunzioni in numeri lungo la catena, somma l'upside,
   esprimilo in **range**, fai la vista **risk-adjusted**, contestualizza sull'ARR e costruisci il
   **de-risking**.

## Il modello mentale visivo

Tharin disegna sempre lo stesso albero, da sinistra a destra:

```
[Assunzione core] → [Canali] → [Sotto-driver, con color code] → [Numeri lungo la catena] → [Upside]
```

Esempio (feature "Collaboration" su un prodotto tipo Smallpdf):

```
Add "Collaboration"  ┌─ Conversion ──→ SEO / Free→Trial / Trial→Pro / LTV ──→ +8M ARR
to a B2B product ────┼─ Network effects ──→ External invited users ──────────→ +1.6M ARR
                     └─ Retention ──→ Existing base / Reduced churn ──────────→ +1.1M ARR
```

Il valore di questo formato: chiunque lo guardi da fuori **vede subito dove non sei sicuro** (i nodi
🔴) e su cosa regge il numero finale.

## I principi (da applicare sempre)

1. **Reliability batte Optimism.** Un caso onesto sui rischi costruisce fiducia; uno ottimista la
   brucia alla prima promessa mancata.
2. **Behavior batte statements.** Dati ed esperimenti > interviste e ipotesi. "People are bad at
   telling you what they want" e, soprattutto, *say ≠ do*.
3. **Simplicity crea alignment.** La complessità genera disallineamento. Limitati ai driver che
   contano. Deve stare su una pagina.
4. **Comunica in range.** 1–10M = molto incerto; 5–6M = abbastanza solido. Il range trasmette la tua
   convinzione.
5. **Confirmation bias è il nemico.** Premia gli "honest assessments, not fairy tales".
6. **I rischi a monte hanno il massimo impatto.** Se l'assunzione iniziale della catena salta, salta
   tutto a valle. Valida lì per primo.
7. **Mai double-counting.** Un driver condiviso (es. LTV tra Conversion e Network) si **visualizza
   come collegamento**, non si somma due volte.

## Scegliere la profondità: leggero vs completo

Non ogni decisione merita il caso completo a 4 step con tutti i numeri.

- **Caso leggero** (1 paragrafo, vedi `strategic-framing.md`): per un singolo differentiator o una
  decisione rapida. Es: *"Se 100 account provano il prodotto in 30 giorni, crediamo che 30 abbiano il
  problema X; pensiamo di convincerne 10 (30%) a comprare se lo risolviamo."* Ogni assunzione ha un
  dato dietro, ma resta una stima rapida.
- **Caso completo** (i 4 step end-to-end): per un investimento grande, multi-canale, che impatta
  diverse funzioni (marketing, growth, sales) e merita una valutazione difendibile prima di committare.

Regola pratica: parti leggero. Vai sul completo solo se l'upside potenziale è alto e l'effort è
sostanziale.

## Prerequisiti

- **Soglia minima**: l'utente dovrebbe avere una soglia ("guardo solo iniziative che muovono almeno
  il 10% dell'ARR"). Serve allo Step 1 per scartare subito le opportunità troppo piccole.
- **Metriche di business**: ARR/MRR, utenti, conversion, LTV, churn (o CAC/funnel in contesto GTM). Se
  non ci sono, **si assumono e si dichiarano** — è esattamente quello che fa Tharin nell'esempio.
- **ICP chiaro**: se il caso si fonda sull'ICP e non è definito → prima `gtm-icp-definition`.
