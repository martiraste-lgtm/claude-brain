# Checklist di Validazione Skills

## Checklist Rapida (Pre-Upload)

```
□ Nome cartella in kebab-case
□ File SKILL.md esiste (case-sensitive)
□ Nessun README.md dentro la skill
□ Frontmatter ha delimitatori ---
□ Campo 'name' corrisponde al nome cartella
□ Campo 'description' ha COSA + QUANDO + trigger
□ Almeno 1 esempio concreto
□ Sezione Troubleshooting presente
```

## Validazione Description

La description DEVE contenere:

```
✅ BUONA DESCRIPTION
"Genera sales deck professionali in formato PPTX. Usa quando
l'utente dice 'crea una presentazione di vendita', 'prepara
un pitch deck', 'sales deck per [cliente]'."

Contiene:
[✓] COSA fa: "Genera sales deck professionali"
[✓] QUANDO usarla: "Usa quando l'utente dice..."
[✓] Trigger phrases: "crea una presentazione", "pitch deck"
```

```
❌ CATTIVA DESCRIPTION
"Aiuta con le presentazioni."

Manca:
[✗] Specificità
[✗] Trigger phrases
[✗] Contesto d'uso
```

## Test di Triggering

Dopo la validazione strutturale:

**Test Positivi** - prova frasi che DEVONO attivare la skill
**Test Negativi** - prova frasi che NON devono attivarla

| Segnale | Problema | Soluzione |
|---------|----------|-----------|
| Mai si attiva | Description troppo specifica | Aggiungi trigger phrases |
| Si attiva sempre | Description troppo generica | Aggiungi "Do NOT use for..." |
