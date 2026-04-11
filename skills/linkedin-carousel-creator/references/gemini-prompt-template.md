# Template Prompt per Gemini

Prompt strutturato per generare slide di caroselli LinkedIn con Gemini (image generation). Il prompt viene compilato slide per slide a partire dallo storyboard.

---

## Istruzioni per l'Uso

1. Lo storyboard (Step 4 della skill) produce il contenuto slide per slide
2. Compila il template sotto sostituendo i placeholder `{{...}}`
3. Genera 1-3 slide per prompt (non tutto il carosello in un singolo prompt)
4. Presenta il prompt completo all'utente come code block copiabile
5. L'utente lo incolla in Gemini e genera le immagini

---

## Template Master

```
Crea un'immagine per una slide di carosello LinkedIn.

FORMATO E DIMENSIONI:
- Dimensioni: 1080 x 1350 pixel (ratio 4:5, verticale)
- La slide deve essere una singola immagine statica, pronta per LinkedIn
- Non aggiungere mockup di telefono o cornici — solo il contenuto della slide

STILE VISIVO — REGOLE ASSOLUTE:
- Sfondo: bianco puro (#FFFFFF), sempre, senza eccezioni
- Testo: nero pieno (#000000) per massimo contrasto
- Font: sans-serif geometrico (tipo Inter, Poppins, o Montserrat), pulito e moderno
- Stile minimalista, professionale, con molto spazio bianco
- Zero emoji
- Zero stock photo o immagini fotografiche
- Zero gradienti o effetti
- Zero ombre (drop shadow)

TIPOGRAFIA:
- Titoli/statement: BOLD, molto grande (equivalente 60-80pt)
- Body text: regular weight, medio (equivalente 28-36pt)
- Label/caption: regular weight, piccolo (equivalente 20-24pt)
- Tutto in sentence case (solo prima parola maiuscola)
- Lingua: italiano

EVIDENZIATORI (HIGHLIGHT):
Le keyword importanti hanno un rettangolo colorato posizionato DIETRO il testo (come un evidenziatore).
I colori disponibili per gli highlight sono SOLO questi (pastello, morbidi):
- Rosa/lavanda: #E8D5E8
- Crema/giallo: #FFF3CD
- Arancione: #FFB74D
- Coral/rosso: #FFB3B3
- Verde: #D4EDDA

IMPORTANTE: i colori sono usati SOLO come evidenziatori dietro le keyword. Mai come sfondo, mai come decorazione, mai come bordo colorato.

ELEMENTI GRAFICI AMMESSI:
- Stick figure / icone persona stilizzate (linee nere, minimal)
- Bordi tratteggiati o puntinati su card/box (colore #CCCCCC, sottili)
- Frecce (nere, pulite, 2-3px)
- Cerchi numerati con sfondo colorato (per liste ordinate)
- Griglie e layout a colonne per confronti

NON INCLUDERE MAI:
- Foto reali o stock photo
- Emoji o emoticon
- Sfondi colorati o con pattern
- Gradienti
- Ombre portate
- Bordi spessi o solidi
- Font serif, script, o decorativi
- Piu di 4 righe di testo per slide
- Piu di 3 keyword evidenziate per slide

---

SLIDE DA GENERARE:

Tipo di slide: {{tipo_slide}}
Numero slide: {{numero}} di {{totale}}

Contenuto testuale esatto (usa ESATTAMENTE queste parole):
{{contenuto_testuale}}

Keyword da evidenziare (con rettangolo colorato dietro):
{{lista_keyword_con_colore}}

Elementi visivi richiesti:
{{descrizione_elementi_visivi}}

Layout:
{{descrizione_layout}}

Note aggiuntive:
{{note}}
```

---

## Compilazione per Tipo di Slide

### Cover (Slide 1)

```
Tipo di slide: Cover — prima slide del carosello
Numero slide: 1 di {{totale}}

Contenuto testuale esatto:
- Titolo: "{{titolo_carosello}}"

Keyword da evidenziare:
- "{{keyword_1}}": evidenziata con sfondo {{colore_1}} (#{{hex_1}})
- "{{keyword_2}}": evidenziata con sfondo {{colore_2}} (#{{hex_2}})

Elementi visivi richiesti:
- Il titolo deve essere MOLTO grande, bold, centrato nella parte alta della slide
- Sotto il titolo, eventuale sottotitolo in regular weight
- In basso: @{{handle}} in piccolo

Layout:
- Titolo centrato nella meta superiore
- Sottotitolo (se presente) subito sotto
- Handle/nome in basso, piccolo, centrato
- Molto spazio bianco attorno al titolo
```

### Confronto

```
Tipo di slide: Confronto — due colonne che mostrano A vs B
Numero slide: {{numero}} di {{totale}}

Contenuto testuale esatto:
- Titolo sezione: "{{titolo}}"
- Colonna sinistra ({{label_A}}):
  - {{punto_A1}}
  - {{punto_A2}}
  - {{punto_A3}}
- Colonna destra ({{label_B}}):
  - {{punto_B1}}
  - {{punto_B2}}
  - {{punto_B3}}

Keyword da evidenziare:
- Header colonna sinistra "{{label_A}}": sfondo {{colore_A}} (#{{hex_A}})
- Header colonna destra "{{label_B}}": sfondo {{colore_B}} (#{{hex_B}})

Elementi visivi richiesti:
- 2 card affiancate con bordo tratteggiato
- Header di ogni card con sfondo pastello
- Punti allineati in lista con bullet semplici

Layout:
- Titolo in alto, centrato, bold
- 2 colonne uguali sotto, con gap di 20-30px
- Ogni colonna e una card con bordo tratteggiato, angoli arrotondati
```

### Dettaglio (3 Card)

```
Tipo di slide: Dettaglio — titolo + 3 card numerate
Numero slide: {{numero}} di {{totale}}

Contenuto testuale esatto:
- Titolo sezione: "{{titolo}}"
- Card 1: "{{label_1}}" — {{descrizione_1}}
- Card 2: "{{label_2}}" — {{descrizione_2}}
- Card 3: "{{label_3}}" — {{descrizione_3}}

Keyword da evidenziare:
- Label delle card ({{label_1}}, {{label_2}}, {{label_3}}): sfondo {{colore}} (#{{hex}})

Elementi visivi richiesti:
- 3 card impilate verticalmente
- Ogni card ha: numero in cerchio colorato a sinistra + label bold + descrizione regular
- Bordo tratteggiato su ogni card

Layout:
- Titolo in alto, bold, centrato
- 3 card sotto, impilate con gap di 15-20px
- Ogni card occupa circa il 25% dell'altezza disponibile
```

---

## Esempio Compilato (6 slide)

Esempio per un carosello "3 errori di positioning che fanno tutte le startup":

### Slide 1 — Cover

```
SLIDE DA GENERARE:

Tipo di slide: Cover — prima slide del carosello
Numero slide: 1 di 16

Contenuto testuale esatto:
- Titolo: "3 errori di positioning che fanno tutte le startup"

Keyword da evidenziare:
- "3 errori": evidenziata con sfondo coral (#FFB3B3)
- "positioning": evidenziata con sfondo arancione (#FFB74D)

Elementi visivi richiesti:
- Titolo MOLTO grande, bold, centrato
- In basso: @stefanomartiradonna in piccolo

Layout:
- Titolo centrato nella meta superiore
- Handle in basso, piccolo, centrato
- Molto spazio bianco
```

### Slide 2 — Contesto

```
SLIDE DA GENERARE:

Tipo di slide: Contesto — statement che stabilisce il problema
Numero slide: 2 di 16

Contenuto testuale esatto:
"Il 90% delle startup B2B ha lo stesso problema: il positioning e un ripensamento, non una decisione strategica."

Keyword da evidenziare:
- "90%": evidenziata con sfondo coral (#FFB3B3)
- "ripensamento": evidenziata con sfondo coral (#FFB3B3)

Elementi visivi richiesti:
- Testo grande centrato, 3 righe
- Nessun altro elemento — solo testo su bianco

Layout:
- Statement centrato verticalmente e orizzontalmente
- Font semi-bold, 40-48pt equivalente
```

### Slide 5 — Confronto

```
SLIDE DA GENERARE:

Tipo di slide: Confronto — positioning sbagliato vs giusto
Numero slide: 5 di 16

Contenuto testuale esatto:
- Titolo sezione: "Positioning"
- Colonna sinistra (Come lo fanno):
  - Copiano i competitor
  - Parlano di feature
  - Cambiano ogni quarter
- Colonna destra (Come dovrebbe essere):
  - Partono dal cliente
  - Parlano di valore
  - Testano e iterano

Keyword da evidenziare:
- "Come lo fanno": sfondo coral (#FFB3B3)
- "Come dovrebbe essere": sfondo verde (#D4EDDA)

Elementi visivi richiesti:
- 2 card affiancate con bordo tratteggiato
- Header colorati (coral sinistra, verde destra)

Layout:
- Titolo piccolo in alto
- 2 colonne uguali sotto
```

---

## Note sull'Uso con Gemini

1. **Genera 1-3 slide per prompt** — Gemini gestisce meglio batch piccoli
2. **Sii specifico sul testo** — scrivi il testo ESATTO, non "un testo che parla di..."
3. **Includi sempre le regole di stile** — Gemini tende a decorare; le regole "NON INCLUDERE MAI" sono essenziali
4. **Itera** — la prima generazione raramente e perfetta. Chiedi aggiustamenti specifici ("riduci il testo", "sposta il titolo piu in alto", "il colore highlight deve essere piu chiaro")
5. **Verifica dimensioni** — assicurati che l'output sia 1080x1350 e non venga ritagliato o ridimensionato
