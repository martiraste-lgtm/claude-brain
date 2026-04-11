# claude-brain

Configurazione persistente e portatile per Claude Code.

Un repo GitHub che fa da layer di sync tra macchine diverse e superfici diverse — CLI, desktop, sessioni web — senza mai ricominciare da zero.

---

## Il problema

Claude Code è potente, ma ogni installazione su una nuova macchina o ogni sessione web parte da zero: niente istruzioni di comportamento, niente skill personalizzate, niente memoria. Il modello non sa chi sei, come lavori, cosa hai già costruito.

Questo repo risolve quel problema. Clonalo, e Claude sa già tutto.

---

## Architettura

```
~/.claude/  ←  questo repo
│
├── CLAUDE.md          # Istruzioni operative globali
│                      # Chi sono, come ragionare, tono, workflow, framework di riferimento
│                      # Letto automaticamente da Claude Code all'avvio di ogni sessione
│
├── settings.json      # Config minimale (channel aggiornamenti, effort level)
│
├── commands/          # 36 slash-command personalizzati
│                      # Invocabili con /nome-comando da qualsiasi sessione
│                      # Coprono: analisi, strategia, marketing, GTM, research, toolkit
│
├── memory/            # Memoria persistente cross-sessione
│                      # Claude scrive qui le informazioni rilevanti da ricordare nel tempo
│                      # Letta automaticamente nelle sessioni future
│
└── skills/            # 88+ skill personalizzate (Agent Skills)
                       # Ogni skill ha SKILL.md con istruzioni specifiche e references/
                       # Invocabili esplicitamente o tramite trigger di parole chiave
```

---

## Separazione dei ruoli

Il principio architetturale centrale è la separazione tra **istruzioni** e **dati**:

| Layer | File | Caratteristica |
|-------|------|----------------|
| Istruzioni operative | `CLAUDE.md` | Stabile — cambia raramente, solo quando cambia il modo di lavorare |
| Comandi rapidi | `commands/` | Semi-stabile — cresce lentamente con nuovi workflow |
| Skill specializzate | `skills/` | Cresce sistematicamente — ogni nuovo dominio ha la sua skill |
| Memoria accumulata | `memory/` | Vivo — si aggiorna a ogni sessione con nuovi pattern e feedback |

Questa separazione permette di caricare solo il contesto necessario per il task corrente, senza saturare la context window.

---

## Skill disponibili (campione)

| Categoria | Skill | Cosa fa |
|-----------|-------|---------|
| Positioning | `b2b-positioning-diagnostic` | Audit positioning B2B con framework April Dunford — 5 step |
| Homepage | `saas-homepage-analyzer` | Crea o analizza homepage B2B SaaS, VP Canvas, copy draft |
| Content | `linkedin-viral-post-writer` | Post LinkedIn nel proprio stile, basato su pattern analizzati |
| Content | `linkedin-carousel-creator` | Caroselli 15-24 slide con output Canva, Gamma, o Gemini |
| Content | `newsletter-writer` | Articoli Substack long-form |
| GTM | `demand-gen-campaign-brief` | Campaign brief completo con SCOPE framework e KPI benchmark |
| Strategia | `strategic-advisor` | Sparring partner su strategia aziendale, reverse engineering |
| Brand B2C | `brand-culture-b2c-analyst` | Analisi brand/campagne con framework Andjelic e Bina |
| Growth | `how-small-brands-growth` | Diagnosi vettore di disruption per challenger brand (framework Kinner) |
| OKR | `okr-hybrid` | Framework ibrido OKR+NCT con Commitments leading/lagging |
| Preventivi | `preventivo-pmm-fractional` | Preventivi Product Marketing Fractional per startup |
| n8n | `n8n-workflow-patterns` + 5 skill coordinate | Progettazione e debug workflow n8n |

---

## Come usarlo

### Setup su nuova macchina

```bash
# Prerequisiti: git, gh (GitHub CLI), Claude Code installato
git clone https://github.com/martiraste-lgtm/claude-brain.git ~/.claude
```

Claude Code legge `CLAUDE.md` automaticamente all'avvio.

### Setup per sessioni web (Claude.ai Projects)

1. Clona il repo in una directory temporanea
2. Vai su [claude.ai/projects](https://claude.ai/projects) → crea un nuovo progetto
3. Carica `CLAUDE.md` come istruzione del progetto
4. Per lavorare su un progetto specifico, clona anche quel repo (es. `System-content-flywheel`) e carica i file rilevanti

### Aggiornare dopo modifiche locali

```bash
cd ~/.claude && git add -A && git commit -m "chore: update config" && git push
```

### Sincronizzare da remoto (nuova macchina o dopo pull)

```bash
cd ~/.claude && git pull
```

---

## Sistema completo (cross-repo)

`claude-brain` è il layer globale. Si integra con repo di progetto separati:

| Repo | Contenuto | Relazione |
|------|-----------|-----------|
| `claude-brain` | Configurazione globale, skill, comandi, memoria | Questo repo — base di tutto |
| `System-content-flywheel` | Knowledge base editoriale (LinkedIn + Substack) | Progetto specifico — usa le skill di claude-brain |

Ogni progetto ha il suo `CLAUDE.md` locale che estende (non sostituisce) il globale.

---

## Cosa non è nel repo

Il `.gitignore` esclude in modo difensivo tutto ciò che non deve mai andare su un server remoto:

- `.credentials.json` — token OAuth attivi (generati automaticamente da Claude Code)
- `history.jsonl` — cronologia completa delle sessioni
- `projects/` — sessioni archiviate (centinaia di MB)
- `backups/`, `cache/`, `debug/`, `sessions/`, tutto ciò che è effimero o sensibile

**Regola pratica**: se cloni questo repo su una macchina nuova, Claude Code crea da solo i file di sistema che mancano. Non serve nulla di ciò che è escluso.

---

## Note architetturali

Tre scelte non ovvie che vale la pena documentare:

**1. Repo flat invece di nested.** `skills/` aveva il suo `.git` separato (`claude-skills`). Ho rimosso quel repo nested e unificato tutto in `claude-brain`. Un singolo remote di sync è più semplice da mantenere e da clonare su nuove superfici. La storia di `claude-skills` (3 commit) non aveva valore archivistico sufficiente da giustificare la complessità.

**2. `memory/` versionata.** La memoria accumulata da Claude (feedback, pattern osservati, preferenze) è un asset — non un file temporaneo. Versionarla garantisce che nuove macchine e sessioni web partano dallo stesso stato, non da zero.

**3. `.gitignore` costruito per default deny.** Il file non esclude eccezioni — esclude tutto tranne quello che deve esserci. Se un nuovo file di sistema appare in `~/.claude/`, non viene accidentalmente committato. Questo è particolarmente critico per `.credentials.json`, che Claude Code ricrea ad ogni autenticazione con token freschi.

---

## Stato

- **Avviato**: aprile 2026
- **Skill attive**: 88+
- **Comandi slash**: 36
- **Superfici supportate**: CLI, desktop, web, IDE (VS Code, JetBrains)

---

## Autore

**Stefano Martiradonna** — Product Marketing Fractional
Newsletter: [da 0 al PMF](https://substack.com/@daozeroalpmf)
LinkedIn: [linkedin.com/in/stefanomartiradonna](https://www.linkedin.com/in/stefanomartiradonna/)
