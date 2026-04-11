# Template Prompt per Tool AI Esterni

Template strutturati per ricreare le infografiche su Gemini, Banana, NotebookLM, Midjourney e altri tool AI di generazione immagini.

---

## Template Universale

Usa questo template come base per qualsiasi tool. Adattalo in base al tool specifico.

```
Crea un'infografica professionale con le seguenti specifiche:

TITOLO: "[Titolo esatto dell'infografica]"
SOTTOTITOLO: "[Sottotitolo se presente]"

FORMATO E DIMENSIONI:
- Orientamento: [portrait/landscape/square]
- Proporzioni: [4:3 / 3:4 / 1:1 / 9:16]
- Risoluzione: alta qualità, adatta per social media

STILE VISIVO:
- Stile: professionale, pulito, minimalista moderno
- Sensazione: [caldo/freddo/neutro] e [corporate/creativo/educational]
- Ispirazione: infografiche di marketing B2B stile LinkedIn
- NO: illustrazioni complesse, foto stock, 3D, effetti glass-morphism

LAYOUT: [nome del layout]
[Descrizione della struttura spaziale - vedi sezione specifica sotto]

PALETTE COLORI:
- Sfondo generale: #F8F8F8 (grigio molto chiaro)
- Header/titolo principale: #2D2D2D (grigio antracite scuro)
- Sezione 1 (in alto): #FDE0D8 (rosa salmon chiaro)
- Sezione 2 (centro): #FDE8C8 (arancio pesca chiaro)
- Sezione 3 (in basso): #FDF5D0 (giallo crema chiaro)
- Colore accento (badge, numeri, CTA): #F47B20 (arancione)
- Card interne: #FFFFFF (bianco) con ombra leggera
- Testo titoli: #2D2D2D
- Testo corpo: #555555

TIPOGRAFIA:
- Font: sans-serif pulito (stile Inter/Helvetica/SF Pro)
- Titolo principale: grande, grassetto, [colore]
- Titoli sezione: medio, grassetto, maiuscolo
- Label card: medio-piccolo, semi-grassetto
- Corpo testo: piccolo, peso normale, grigio

CONTENUTO TESTUALE ESATTO:
[Inserisci qui OGNI testo che deve apparire nell'infografica, 
 organizzato per posizione]

ELEMENTI GRAFICI AGGIUNTIVI:
- [Icone, frecce, connettori, badge numerici - descrivi ciascuno]

FOOTER (se presente):
- [Nome autore, handle, URL]

NOTE IMPORTANTI:
- Tutto il testo deve essere leggibile e nitido
- Rispetta la gerarchia visiva: il titolo è l'elemento più grande
- Lo spazio bianco è essenziale: non affollare
- Le card devono avere angoli arrotondati e ombra leggera
```

---

## Template per Layout Specifici

### Template: Piramide a Zone (Layout 1)

```
LAYOUT: Piramide a 3 zone
La struttura è una piramide vista frontalmente, divisa in 3 fasce orizzontali.

ZONA SUPERIORE (vertice, la più stretta):
- Sfondo: #FDE0D8 (rosa)
- Label zona: "[nome zona]" (sul lato sinistro)
- Contenuto: [N] elementi come chip/badge bianchi con bordo arrotondato
- Elementi: "[elem1]", "[elem2]", "[elem3]"

ZONA CENTRALE:
- Sfondo: #FDE8C8 (arancio chiaro)
- Label zona: "[nome zona]" (sul lato sinistro)
- Contenuto: [N] elementi come chip/badge bianchi
- Elementi: "[elem1]", "[elem2]", "[elem3]", "[elem4]"

ZONA INFERIORE (base, la più larga):
- Sfondo: #FDF5D0 (giallo chiaro)
- Label zona: "[nome zona]" (sul lato sinistro)
- Contenuto: [N] elementi come chip/badge bianchi
- Elementi: "[elem1]", "[elem2]", "[elem3]", "[elem4]", "[elem5]"

Ogni zona è separata da una linea orizzontale sottile.
Le etichette delle zone sono sulla sinistra con una freccia curva che indica la zona.
```

### Template: Card Numerate a Sezioni (Layout 6)

```
LAYOUT: Card numerate organizzate in sezioni colorate

HEADER:
- Barra in alto full-width, sfondo #2D2D2D
- Titolo in bianco: "[Titolo]"

SEZIONE 1: "[Nome sezione]"
- Sfondo sezione: #FDE0D8 (rosa chiaro)
- Titolo sezione centrato in grassetto maiuscolo
- Contiene [N] card bianche affiancate in riga (griglia)
- Card 1: badge arancione "1", titolo "[titolo]", testo "[descrizione]"
- Card 2: badge arancione "2", titolo "[titolo]", testo "[descrizione]"
- Card 3: ...
- Card 4: ...
(I badge sono cerchi arancione #F47B20 con numero bianco, posizionati in alto a destra di ogni card)

SEZIONE 2: "[Nome sezione]"
- Sfondo sezione: #FDE8C8 (arancio chiaro)
- Stessa struttura della sezione 1
- Card 5-8 (o quante necessarie)

SEZIONE 3: "[Nome sezione]"
- Sfondo sezione: #FDF5D0 (giallo chiaro)
- Stessa struttura
- Card 9-12 (o quante necessarie)

FOOTER:
- [Opzionale: nome autore con avatar circolare]

Le sezioni sono separate da spazio bianco.
Una linea tratteggiata verticale corre lungo il lato destro collegando le sezioni.
```

### Template: Tabella con Icone (Layout 14)

```
LAYOUT: Tabella verticale con icone e 3 colonne

HEADER TABELLA:
- Sfondo: #FDF5D0 (giallo) o [colore highlight]
- Titolo grande sopra la tabella: "[Titolo]"
- Sottotitolo: "[sottotitolo]"

INTESTAZIONI COLONNE:
- Colonna 1: "[nome]" (es. MODELLO)
- Colonna 2: "[nome]" (es. COME FUNZIONA)
- Colonna 3: "[nome]" (es. ESEMPI)
- Sfondo intestazione: grigio chiaro, testo maiuscolo piccolo

RIGHE:
Riga 1:
- Col 1: icona [emoji] + "[Nome modello]" in grassetto
- Col 2: "[Descrizione breve]" + eventuale citazione in corsivo
- Col 3: "[Esempio A]", "[Esempio B]"

Riga 2:
- [stessa struttura]

[Ripeti per ogni riga]

FOOTER:
- [Logo/firma centrata]

Le righe sono separate da linee grigie sottili.
Ogni riga ha altezza sufficiente per il contenuto senza affollamento.
```

### Template: Zigzag / Snake Flow (Layout 16)

```
LAYOUT: Percorso a zigzag con step numerati che alternano sinistra-destra

Lo schema si sviluppa verticalmente con gli step che si alternano:
- Step dispari (1, 3, 5, 7): posizionati a SINISTRA
- Step pari (2, 4, 6, 8): posizionati a DESTRA
- Frecce/connettori collegano ogni step al successivo creando un percorso a serpentina

STEP 1 (sinistra):
- Badge circolare arancione con "1"
- Icona: [emoji]
- Titolo: "[titolo]" in grassetto
- Descrizione: "[testo breve]"

STEP 2 (destra):
[connettore/freccia dallo step 1]
- Badge circolare arancione con "2"
- Icona: [emoji]
- Titolo: "[titolo]"
- Descrizione: "[testo breve]"

[Continua alternando sinistra-destra]

STEP [ultimo]:
- Può essere più grande (full-width) per il risultato finale

Sfondo: grigio molto chiaro con elementi decorativi leggeri (cerchi, onde)
Connettori: frecce grigie o viola che creano il percorso serpentina
Badge: cerchi #F47B20 con numeri bianchi
Card step: sfondo bianco con ombra leggera e bordo arrotondato
```

### Template: Lista Errori a Righe (Layout 12)

```
LAYOUT: Lista di errori/problemi in formato tabellare a righe

TITOLO: "[N] [Errori/Problemi] che [conseguenza negativa]"
- Font grande, grassetto, centrato
- Colore: #2D2D2D

STRUTTURA RIGHE:
Ogni riga ha 3 colonne:
- Colonna 1 (stretta): numero in badge colorato + nome del problema in grassetto
- Colonna 2: ✕ + [primo sintomo/conseguenza]
- Colonna 3: ✕ + [secondo sintomo/conseguenza]

Riga 1:
- Badge: "1" su sfondo [rosa #FDE0D8]
- Problema: "[descrizione problema]"
- ✕ "[sintomo 1]"
- ✕ "[sintomo 2]"

[Ripeti per ogni errore]

Le ✕ sono in colore rosso.
I badge numerici hanno colori progressivi (rosa → arancio → giallo).
Sfondo righe: alternato bianco / grigio chiaro #F5F5F5.
```

---

## Adattamenti per Tool Specifici

### Per Gemini (Google)

Aggiungi all'inizio del prompt:
```
Genera un'immagine di un'infografica professionale. 
L'infografica deve avere testo leggibile e nitido.
Stile: flat design, minimalista, tipo infografica LinkedIn.
```

### Per Banana/Canvas AI

Aggiungi:
```
Stile: infografica social media professionale.
Il testo deve essere il focus principale.
Evita elementi decorativi eccessivi.
Mantieni lo stile pulito e corporate.
```

### Per Midjourney

Aggiungi come suffisso:
```
--ar 3:4 --style raw --no photorealistic, 3d, glossy
Professional infographic, flat design, clean typography, 
data visualization style, LinkedIn post style
```

### Per NotebookLM / Canva AI

Usa un formato più descrittivo e meno tecnico:
```
Crea un'infografica con queste caratteristiche:
- Sfondo chiaro
- Stile professionale e pulito
- Colori: [descrivi a parole: "palette calda con rosa, arancio e giallo pastello"]
- Formato verticale per social media
- [Descrivi il layout a parole naturali]
```

---

## Note Importanti

1. **Sempre includere TUTTO il testo esatto** — i tool AI non inventano testo coerente
2. **Specificare le posizioni** — "in alto a sinistra", "centrato", "in basso"
3. **Descrivere le relazioni spaziali** — "sotto X", "a destra di Y", "collegato con freccia a Z"
4. **Meno ambiguità = risultato migliore** — se un dettaglio è importante, scrivilo esplicitamente
5. **Iterare** — il primo risultato raramente è perfetto, usa il prompt come base e raffina
