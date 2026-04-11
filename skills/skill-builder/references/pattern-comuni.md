# Pattern Comuni per Skills

## Pattern 1: Sequential Workflow

**Usa quando:** Processi con step in ordine specifico.

```markdown
## Workflow: [Nome]

### Step 1: [Nome]
**Input:** [cosa serve]
**Azioni:** [lista azioni]
**Output:** [cosa produce]

### Step 2: [Nome]
**Dipende da:** Step 1
...
```

---

## Pattern 2: Decision Tree

**Usa quando:** Stesso obiettivo, approcci diversi in base al contesto.

```markdown
## Decision Logic

IF [condizione A]:
  → Approccio X (motivo: ...)
ELIF [condizione B]:
  → Approccio Y
ELSE:
  → Approccio Z (default)
```

---

## Pattern 3: Iterative Refinement

**Usa quando:** La qualità migliora con iterazioni.

```markdown
## Quality Loop

1. Genera bozza
2. Valuta contro criteri
3. Se non passa: correggi e ri-valuta
4. Finalizza quando tutti i criteri OK
```

---

## Pattern 4: Template + Customization

**Usa quando:** Output standardizzato con parti variabili.

```markdown
## Template

[PARTE FISSA]
{{VARIABILE_1}}
{{VARIABILE_2}}
[PARTE FISSA]
```

---

## Quando Usare Quale

| Situazione | Pattern |
|------------|---------|
| Fasi definite | Sequential Workflow |
| Risposte diverse per contesto | Decision Tree |
| Qualità critica | Iterative Refinement |
| Output standard | Template + Customization |
