# Step 3 — Impact / Confidence / Effort

Per ogni driver rilevante ragioni su tre dimensioni. Le prime due (Impact, Confidence) sono quelle che
prima avevi mischiato nel colore; ora le separi. La terza (Effort) entra quando devi capire quanto
costa realizzarlo.

> Promemoria: i business case non sono scienza. Lo scopo qui è **sfidare le idee meglio di "ci credo"**,
> non validare tutto. Troppa validazione è controproducente.

---

## 1. Impact

**Definizione**: l'Impact è il **delta** tra l'alternativa più probabile (cosa farebbe l'utente
altrimenti) e ciò che gli dai. Più grande il delta, più alto l'impatto.

> Analogia Tharin: hai già un giocattolo che ti piace. Se ti do un gioco che ti piace molto di più →
> impatto grande. Se ti do qualcosa di simile a ciò che hai → impatto piccolo.

### Spettro Optimization → Innovation

```
Innovation   ↑   alto impatto (delta grande, ma più rischioso)
             │
Optimization ↓   basso impatto (delta piccolo, ma più sicuro/prevedibile)
```

Perché fare ottimizzazioni se l'impatto è basso? Perché **sono molto più prevedibili** delle
innovazioni. Più un'azienda è matura, più tende all'ottimizzazione (cambiare qualcosa rischia di
danneggiare una base esistente in crescita). Le aziende dovrebbero fare entrambe, ma **le grandi
rischiano di più innovando** rispetto alle startup nuove.

### Matrice "Assessing Impact" (l'altra lente: no-workaround → quality of life)

| Livello | Significato | Segnali |
|---|---|---|
| 🟢 **High Impact** | New value, Innovation | **No workaround** (oggi gli utenti non possono farlo affatto) · **High opportunity score** qualitativo (quanto è importante ⟷ quanto bene riescono a farlo oggi) · **Risolve la maggioranza del motivo di churn** (guida LTV/Retention) |
| 🟡 **Medium Impact** | Improved value | **Substantial improvement** (gli utenti possono già farlo, ma in modo macchinoso) · **Medium opportunity score** qualitativo |
| 🔴 **Low Impact** | Optimization | **Quality of life** (miglioramenti di interfaccia) |

Esempio del "batch export": esportare 1 PDF c'è già; esportarne in blocco 100 →
- "Devo convertire 4 documenti": fastidioso ma fattibile → impatto basso.
- "Devo convertire 100 documenti": teoricamente possibile, ma non fattibile → impatto alto.

A questo punto del caso dovresti avere **solo** driver con impatto sufficiente. Se ne trovi uno
chiaramente low-impact, cancellalo.

---

## 2. Confidence

**Definizione**: quanto sei sicuro che la tua assunzione sull'Impact sia corretta. Meno sei sicuro,
più ampio è il range dei possibili esiti (→ Step 4: la confidence si traduce in ampiezza del range).

Regola generale: **alta confidence ↔ misurazioni quantitative**; la confidence cala man mano che ti
affidi a qualitativo, sensazioni e product sense.

### Matrice "Assessing Confidence"

| Livello | Tipo di evidenza | Fonti |
|---|---|---|
| 🟢 **High** | Datapoint esistenti | **Similar feature metrics** (abbiamo già qualcosa di simile?) · **Experimentation** (abbiamo sperimentato qualcosa di simile?) · **Domain closeness** (vicino all'attuale main use case) |
| 🟡 **Medium** | Indicatori qualitativi | **Customer interviews** (cosa ci dicono i *nostri clienti*?) · **User surveys** (cosa pensano i *nostri utenti*?) |
| 🔴 **Low** | Indicatori qualitativi deboli | **External user interviews** (cosa dice il *mercato*?) · **Product sense** (mi affido all'esperienza, "suona bene") |

### Due leve che alzano la confidence

1. **Domain closeness**: se Tesla aggiunge un *truck*, è vicino al suo dominio (alta confidence). Una
   *bici* è più lontana — sempre trasporto, ma più distante da un'auto. Più sei vicino al core, più
   sei sicuro di ciò che assumi.
2. **Similar feature proof**: se hai già costruito e venduto auto a un certo conversion rate e prezzo,
   hai **dimostrato** di saper vendere "qualcosa" a quelle condizioni. Segnale fortissimo per qualsiasi
   assunzione.

### Warning: interviste interne ≠ mercato

È **pericoloso** dedurre l'adozione di mercato dalle interviste interne, per due effetti:

1. **Gli utenti esistenti non sono un campione rappresentativo del mercato.** Chi oggi non è
   interessato al prodotto ma lo sarebbe con la nuova feature **non è nel gruppo che intervisti**.
   Critico se la feature deve conquistare *nuove* quote di mercato.
2. **Le persone sono pessime nel dirti cosa vogliono.** Anche se quantifichi (% del gruppo che dice X),
   non sai se *fanno* ciò che *dicono* (say ≠ do).

→ **L'esame del comportamento passato è di gran lunga superiore alle ipotesi.** (È anche il motivo per
cui il prototyping è così popolare.)

---

## 3. Effort — Difficult vs Complex

Quando valuti il costo di realizzazione, **il driver principale NON è la durata**. È:

> *"Abbiamo già fatto qualcosa di simile prima?"*

Tre fattori, oltre alla durata pura:

1. **Novità per il team** → se è nuovo, la **complessità** (e l'incertezza della stima) aumenta.
2. **Dipendenze cross-team** → ogni dipendenza aumenta complessità e rischio di slittamento.
3. **Esperienza precedente** → se l'avete già fatto, potete stimare con sicurezza.

**Difficult** = lungo/faticoso ma noto (lo sai stimare). **Complex** = incerto, nuovo, interdipendente
(le stime esplodono). Il rischio vero sta nel *complex*, non nel *difficult*.

> Esempio Tharin: il team non ha mai costruito una feature di collaborazione e impatta marketing,
> growth e sales → stima iniziale **2 quarter**, stima rivista **4 quarter** (un team intero).

### Ridurre il costo: milestone

Se hai un high-cost / high-impact con forte convinzione, **non partire in un colpo solo**. Spezzalo in
**milestone misurabili** che fungono da checkpoint: a ogni milestone decidi se **continuare o abortire**.
("Tanti lanci piccoli che insieme fanno quello grande.") Questo è anche il ponte verso il de-risking
dello Step 4.
