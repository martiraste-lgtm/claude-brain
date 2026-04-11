# Brand System

Guida visiva del brand per tutte le infografiche generate.

---

## Palette Colori Principale

### Colori Base

| Ruolo | Colore | HEX | Uso |
|-------|--------|-----|-----|
| Header/Titolo | Grigio antracite | `#2D2D2D` | Barra titolo principale, testi titolo |
| Sezione 1 | Rosa salmon | `#FDE0D8` | Prima sezione / zona "alta priorità" / warning |
| Sezione 2 | Arancio chiaro | `#FDE8C8` | Sezione intermedia / zone di transizione |
| Sezione 3 | Giallo chiaro | `#FDF5D0` | Terza sezione / zona "fondamenta" / base |
| Accento primario | Arancione | `#F47B20` | Badge numerici, CTA, elementi di focus |
| Card background | Bianco | `#FFFFFF` | Sfondo card, contenitori interni |
| Testo primario | Grigio scuro | `#2D2D2D` | Titoli, header, testo importante |
| Testo secondario | Grigio medio | `#555555` | Corpo testo nelle card |
| Sfondo pagina | Grigio chiaro | `#F8F8F8` | Background generale dell'infografica |

### Colori Estesi (per infografiche con 4+ sezioni)

| Ruolo | HEX | Quando usare |
|-------|-----|-------------|
| Verde chiaro | `#E8F5E9` | Sezione "successo", "validazione", "risultato" |
| Blu chiaro | `#E3F2FD` | Sezione "informazione", "analisi", "dati" |
| Viola chiaro | `#F3E5F5` | Sezione "strategia", "visione", "leadership" |
| Rosso chiaro | `#FFEBEE` | Sezione "errore", "rischio", "attenzione" |

### Progressioni Cromatiche

**Per gerarchie (3 zone):**
```
Top/Superficie: #FDE0D8 (rosa)
Medio/Core:     #FDE8C8 (arancio)
Base/Fondamenta: #FDF5D0 (giallo)
```

**Per processi (5 fasi):**
```
Fase 1: #FFEBEE (rosso chiaro)
Fase 2: #FDE0D8 (rosa)
Fase 3: #FDE8C8 (arancio)
Fase 4: #FDF5D0 (giallo)
Fase 5: #E8F5E9 (verde chiaro)
```

**Per processi (3 fasi):**
```
Fase 1: #FDE0D8 (rosa)
Fase 2: #FDE8C8 (arancio)
Fase 3: #FDF5D0 (giallo)
```

---

## Tipografia

### Font Stack
```css
font-family: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
```

Se Inter non è disponibile, usa il system sans-serif. Non usare mai serif o monospace per le infografiche.

### Scala Tipografica (Tailwind)

| Elemento | Classe Tailwind | Peso | Colore |
|----------|----------------|------|--------|
| Titolo principale | `text-2xl` o `text-3xl` | `font-bold` | `#2D2D2D` o `#FFFFFF` (su sfondo scuro) |
| Sottotitolo | `text-lg` | `font-normal` o `font-light` | `#555555` |
| Titolo sezione | `text-xl` | `font-bold` | `#2D2D2D` |
| Label card/badge | `text-base` | `font-semibold` | `#2D2D2D` |
| Corpo testo card | `text-sm` | `font-normal` | `#555555` |
| Caption/footer | `text-xs` | `font-normal` | `#888888` |

### Regole Tipografiche

1. **Max 3 livelli di dimensione** per infografica (titolo, sottotitolo, corpo)
2. **Bold solo per titoli e label** — mai per corpo testo
3. **MAIUSCOLO** solo per etichette di sezione brevi (es. "BIG PLAN", "EXECUTION")
4. **Corsivo** solo per citazioni o note
5. **Line-height:** relaxed per corpo testo (`leading-relaxed`), tight per titoli (`leading-tight`)

---

## Stile Card

### Card Standard
```
Sfondo: #FFFFFF
Border-radius: 12px (rounded-xl)
Ombra: shadow-sm
Padding: 16px (p-4)
Border: 1px solid #E5E5E5 (border border-gray-200) — opzionale
```

### Card con Badge Numerico
```
Card come sopra +
Badge: cerchio 28x28px, sfondo #F47B20, testo bianco, font-bold
Posizione badge: top-right della card, offset -4px
```

### Card Sezione (contenitore)
```
Sfondo: colore sezione dalla palette
Border-radius: 16px (rounded-2xl)
Padding: 24px (p-6)
Border: nessuno
Contiene: titolo sezione + grid di card interne
```

---

## Elementi Grafici

### Connettori/Frecce
- Frecce verticali: carattere `↓` o div con border-left tratteggiato
- Frecce orizzontali: carattere `→` o div con border-top tratteggiato
- Linee tratteggiate: `border-dashed border-gray-300`
- Colore connettori: `#CCCCCC` o `#2D2D2D` per connessioni principali

### Badge Numerici
```
Forma: cerchio perfetto
Sfondo: #F47B20
Testo: bianco, font-bold
Dimensione: w-7 h-7 (28px) o w-8 h-8 (32px)
Border: 2px solid white (per sovrapposizione)
```

### Icone
- Usa emoji Unicode per semplicità e compatibilità
- Dimensione: text-lg o text-xl
- Non usare librerie esterne di icone nell'artifact
- Esempi comuni: 🎯 📊 💡 🔧 ⚡ 📋 ✅ ❌ 🚀 💰 👥 📈

### Separatori
- Linea sottile: `border-t border-gray-200`
- Linea sezione: `border-t-2 border-gray-300`
- Spazio: `my-4` o `my-6` tra sezioni

---

## Layout e Spaziatura

### Dimensioni Canvas
- **Portrait (social/mobile):** 800×1200px — il formato più comune
- **Landscape (presentation):** 1200×800px — per slide/desktop
- **Square (social post):** 1000×1000px — per Instagram/LinkedIn

### Spaziatura
```
Padding esterno: p-6 o p-8
Gap tra sezioni: gap-6
Gap tra card: gap-4
Gap tra elementi dentro card: gap-2
```

### Regole di Densità
- **Max 70% dello spazio occupato** — il 30% deve essere spazio bianco
- **Se non entra, togli contenuto** — non riduci la dimensione del testo sotto text-xs
- **Respira:** ogni sezione deve avere almeno 16px di padding

---

## Firma/Footer (Opzionale)

Quando l'utente vuole la firma in fondo:

```
┌────────────────────────────────────────┐
│  [Avatar/iniziali]  Nome Cognome       │
│                     @handle / URL      │
└────────────────────────────────────────┘
```

- Sfondo: `#F8F8F8` o trasparente
- Testo: `text-sm`, `text-gray-500`
- Avatar: cerchio 32px con iniziali o emoji
- Posizione: centrato in fondo, con `mt-6` di spazio sopra
- Il footer NON deve mai competere con il contenuto per attenzione

---

## Anti-Pattern (Cosa NON Fare)

1. **Mai più di 5 colori diversi** in una singola infografica
2. **Mai testo sotto 10px** — illeggibile
3. **Mai sfondo scuro per tutto** — solo per header/titolo principale
4. **Mai bordi spessi** — max 1-2px, colori leggeri
5. **Mai ombre forti** — solo shadow-sm, mai shadow-lg
6. **Mai gradients complessi** — solo sfumature leggere se necessarie
7. **Mai mescolare stili di card** — mantieni consistenza dentro la stessa infografica
