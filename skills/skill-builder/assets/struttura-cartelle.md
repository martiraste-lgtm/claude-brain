# Strutture Cartelle per Tipo di Skill

## Struttura Minima
```
skill-name/
└── SKILL.md
```
**Usa per:** Skill semplici, < 1000 parole

## Struttura Standard
```
skill-name/
├── SKILL.md
└── references/
    ├── template.md
    └── guidelines.md
```
**Usa per:** Skill con template o documentazione extra

## Struttura Completa
```
skill-name/
├── SKILL.md
├── references/
│   ├── workflow.md
│   └── troubleshooting.md
├── scripts/
│   └── validate.py
└── assets/
    └── templates/
```
**Usa per:** Skill complesse con script e risorse

## Regole Naming

```
✅ kebab-case: sales-deck-creator
❌ Spazi: Sales Deck Creator
❌ Underscore: sales_deck_creator
❌ CamelCase: SalesDeckCreator
```
