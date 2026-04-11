# Brand System — Caroselli LinkedIn

Design system per caroselli LinkedIn nello stile Herubel/Wester, adattato al brand "da 0 al PMF".

---

## Dimensioni Canvas

- **Formato**: 1080 x 1350 px (ratio 4:5, standard LinkedIn carousel)
- **Ogni slide** = 1 pagina separata
- **Margini sicuri**: 60px su tutti i lati (area contenuto effettiva: 960 x 1230 px)
- **Padding interno card**: 40px

---

## Palette Colori

### Colori base

| Ruolo | HEX | Uso |
|-------|-----|-----|
| Sfondo | `#FFFFFF` | Bianco puro, sempre. Nessuna eccezione |
| Testo | `#000000` | Nero pieno per massimo contrasto |
| Testo secondario | `#4A4A4A` | Grigio scuro per label, caption, sottotitoli |

### Colori accento (SOLO come evidenziatori dietro keyword)

| Nome | HEX Primario | HEX Alternativo | Mapping Semantico |
|------|-------------|-----------------|-------------------|
| Rosa/Lavanda | `#E8D5E8` | `#F0E0F0` | Categorie, label di classificazione |
| Crema/Giallo | `#FFF3CD` | `#FFF5E0` | Sistemi, framework, metodologie |
| Arancione | `#FFB74D` | `#FF9800` | Strategia, emphasis, punto chiave |
| Coral/Rosso | `#FFB3B3` | `#F8BBD0` | Negativo, problema, errore, core concept |
| Verde | `#D4EDDA` | `#C3E6CB` | Positivo, soluzione, azione, outcome |

### Regole colore ASSOLUTE

1. I colori accento sono **SOLO evidenziatori** — rettangolo colorato dietro il testo della keyword
2. **Mai** usare colori come sfondo slide, bordi decorativi o riempimento di aree vuote
3. **Max 2-3 keyword evidenziate per slide** — mai di piu
4. **1 solo colore dominante per slide** — puoi usare un secondo colore ma in quantita minore
5. Il colore dell'evidenziatore segue il mapping semantico: non scegliere colori a caso

---

## Tipografia

### Gerarchia font

| Livello | Peso | Dimensione | Uso |
|---------|------|-----------|-----|
| Titolo/Statement | Bold (700) | 60-80px | Headline di slide Cover, Bridge, CTA |
| Sottotitolo | Semi-Bold (600) | 40-48px | Titoli di sezione dentro la slide |
| Body | Regular (400) | 28-36px | Testo descrittivo, spiegazioni |
| Label/Caption | Regular (400) | 20-24px | Etichette, numerazione, note |

### Font family

- **Primario**: Sans-serif geometrico (Inter, Poppins, Montserrat, o equivalente disponibile su Canva/Gamma)
- **Mai**: serif, script, decorativo, monospace

### Regole tipografiche

1. **Sentence case** sempre — mai Title Case, mai TUTTO MAIUSCOLO (eccezione: acronimi come GTM, PLG, ICP)
2. **Zero emoji** — mai, in nessuna slide
3. **Max 3-4 righe** per slide di testo puro
4. **Max 25 parole per riga**
5. **Interlinea**: 1.3-1.5x la dimensione del font
6. **Allineamento**: centrato per titoli/statement, a sinistra per body e liste

---

## Elementi Visivi

### Highlight (evidenziatore)

- Rettangolo colorato posizionato **dietro** il testo della keyword
- Bordi arrotondati leggeri (border-radius: 4-6px)
- Padding orizzontale: 8-12px oltre il testo
- Padding verticale: 4-6px oltre il testo
- Opacita: 100% (colori pastello, gia morbidi di natura)

### Sottolineatura

- Linea sotto il testo per concetti critici
- Spessore: 3-4px
- Colore: nero (#000000) o uno dei colori accento
- Max 1 concetto sottolineato per slide

### Stick Figure / Icone persona

- Figure stilizzate semplici per rappresentare ruoli/personaggi (marketer, founder, cliente)
- Stile: lineare, minimal, nero su bianco
- Dimensione: 80-120px di altezza
- Usare quando il contenuto parla di persone, ruoli, o interazioni

### Bordi e Box

- **Bordi tratteggiati/puntinati** su card e box — non bordi solidi
- Colore bordo: `#CCCCCC` o `#E0E0E0`
- Spessore: 2px
- Border-radius: 12-16px
- Background card: bianco (nessun fill colorato)

### Frecce

- **Frecce strutturali**: connettono concetti, mostrano flusso (nere, 2-3px)
- **Frecce decorative**: enfatizzano direzione o movimento (piu grandi, possono essere colorate)
- Stile: pulite, non disegnate a mano

### Elementi numerati

- Cerchi o quadrati con numero dentro
- Background: uno dei colori accento
- Testo numero: nero o bianco (contrasto)
- Dimensione: 40-50px
- Usati per liste ordinate, step, priorita

### Grid Layout

- Per confronti e liste strutturate
- Colonne: max 2-3
- Righe: max 3-4
- Gap tra celle: 20-30px
- Ogni cella puo avere bordo tratteggiato

---

## Foto Autore

**NON inclusa** nel design system attuale. L'utente aggiunge manualmente la propria foto dove necessario (cover, bridge, CTA) dopo la generazione del carosello.

---

## Anti-Pattern — Cosa NON Fare MAI

| Elemento | Regola |
|----------|--------|
| Sfondo colorato | MAI — solo bianco |
| Gradient | MAI — nessun gradiente, mai |
| Stock photo | MAI — nessuna foto generica |
| Emoji | MAI — zero emoji nel testo |
| Title Case | MAI — solo sentence case |
| Piu di 4 righe | MAI per slide di testo puro |
| Piu di 3 highlight | MAI per singola slide |
| Bordi solidi spessi | MAI — solo tratteggiati/sottili |
| Font decorativi | MAI — solo sans-serif geometrico |
| Colori saturi/brillanti | MAI — solo pastello come da palette |
| Ombreggiature pesanti | MAI — nessun drop shadow visibile |
| Animazioni/effetti | MAI — tutto statico |
