---
title: Creare ed eseguire un’abilità gate di qualità in Collaborator
description: Scopri come utilizzare un’abilità personalizzata in Collaboratore per convalidare automaticamente le attivazioni del pubblico in base a elenchi di soppressione, limiti di frequenza e standard di denominazione prima della distribuzione.
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 101
last-substantial-update: 2026-09-08
jira: KT-22379
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%
---

# Creare ed eseguire un’abilità gate di qualità utilizzando competenze IA personalizzate

I team di marketing si basano su regole e processi di governance per garantire che i tipi di pubblico vengano attivati correttamente. Prima di lanciare un pubblico su una destinazione, i team devono spesso verificare gli elenchi di soppressione, i limiti di frequenza, i requisiti di consenso e le convenzioni di denominazione.
 
La sfida è che questi controlli spesso dipendono dalla conoscenza tribale e dalle revisioni manuali. Quando i processi vivono nella testa delle persone, possono verificarsi degli errori.

Questo video illustra come un’abilità personalizzata del Collaboratore funga da gate di attivazione, convalidando automaticamente i tipi di pubblico in base agli standard di attivazione della tua organizzazione prima che si spostino a valle.

>[!VIDEO](https://video.tv.adobe.com/v/3503162/?learn=on&enablevpops)

## Esempio di abilità gate di qualità dell’attivazione
 
Puoi creare la tua abilità **Activation Quality Gate** riutilizzabile incollando un prompt in Coworker. Le funzionalità di authoring delle competenze del collaboratore convertono il prompt in un&#39;abilità salvata all&#39;interno del **tuo ambiente**. Di seguito è riportato un esempio basato sulla dimostrazione video.
 
La chiave è definire **i tuoi standard di superamento/fallimento** per i tre gate di governance:
 
1. Soppressione/Consenso
2. Limite di frequenza
3. Convenzione di denominazione
 
La struttura rimane la stessa per tutti. Personalizzare le sezioni contrassegnate con **`[...]`** in modo che corrispondano agli standard della propria organizzazione.

## Prompt principale

> **Salva come abilità denominata &quot;Controllo qualità attivazione&quot;**.

```text
It's a governance gate that runs a pre-activation checklist before any audience is sent to a destination.

It is read-only. It never activates, mutates, or copies anything.

Resolve the named audience and destination from our Knowledge Graph, evaluate the three gates below, then render one visual scorecard containing:

- An Alert banner
- One MetricCard per gate
- A DataTable with:
- Gate
- Status
- Finding
- Required Fix

Provide a single verdict:

- CLEARED only if all three gates pass
- BLOCKED if any gate fails

For every failed gate, provide the specific remediation needed.
 
All gates fail closed:

- Missing data = BLOCKED
- Never assume success when information is unavailable
 
Trigger phrases:

- "run the activation gate"
- "is this audience ready to activate"
- "pre-activation checklist"
- "can I activate to ..."

The three gates are:
 
[Paste Gate 1, Gate 2, and Gate 3 definitions here]
```

## Gate 1: soppressione/consenso
 
> Modifica questa sezione per soddisfare i requisiti di eliminazione e consenso della tua organizzazione.
 

```text
Gate 1 – Suppression List

Pass only if a recognized suppression, opt-out, or consent audience is applied alongside the target audience.

Discover eligible lists using name patterns such as:

- suppress
- opt-in
- opt out
- consent
- do not contact
 
Because suppression lists may live in destination dataflows rather than audience metadata, require the marketer to confirm one is attached.
 
If no suppression or consent list exists anywhere in the sandbox, fail hard.
 
Our standard:

[Example: A consent audience is mandatory for all email and SMS destinations. For direct mail destinations it is optional.]
```

## Gate 2: Limite Di Frequenza

> Modifica questa sezione per soddisfare i requisiti di frequenza di consegna della tua organizzazione.

```text
Gate 2 – Frequency Cap
 
Read the delivery frequency on the resolved destination.

Pass if:

- Frequency is present
- Frequency is bounded

Fail if:

- Frequency is blank
- Frequency is unbounded

Our standard:

[Example: Frequency must be DAILY or less frequent. Any hourly cadence or blank value is blocked.]
```

## Gate 3: convenzione di denominazione
 
> Modifica questa sezione per farlo corrispondere alle regole di denominazione del pubblico della tua organizzazione.
 

```text
Gate 3 – Naming Convention

Evaluate the audience name programmatically.

Any rule violation causes failure.

Block names that:

- Contain "test"
- Contain "copy"
- Contain an auto-copy suffix such as _[6-hex]
- Contain timestamps
- Contain 24-character object IDs
- Start with a bare number or cryptic short code
- Are entirely lowercase
- Are excessively short or unclear
- Use generic defaults such as:
- Save audience
- Email
- New Accounts
- Lack a category–qualifier separator

Our standard:

[Example: [Line of Business] – [Criteria] in title case]

Example:

Mortgage – High Propensity Prospects

When blocked on naming, always propose a compliant replacement name.
```

## Linee guida

### &#x200B;1. Personalizza solo le sezioni tra parentesi

Aggiorna solo le sezioni contenute in **`[...]`**.
 
Queste sezioni definiscono gli standard di governance specifici dell’organizzazione.
 
Tutto il resto deve rimanere invariato:

- Risoluzione del pubblico
- Valutazione del gate
- Rendering scorecard
- Logica del verdetto


### &#x200B;2. Verifica prerequisiti
 
Questa abilità dipende da:
 
- Accesso a Knowledge Graph
- Individuazione del pubblico
- Individuazione della destinazione
- Individuazione elenco di soppressione
- Supporto di artefatti visivi
- Banner di avviso
- MetricCard
- Rendering DataTable

Se queste funzionalità non sono disponibili nell’ambiente del cliente, l’abilità non può essere eseguita come previsto.

### &#x200B;3. Mantieni abilità di sola lettura

L’abilità deve rimanere sempre di sola lettura.

Includi questo requisito esplicitamente nel prompt per garantire che l’abilità non venga mai confusa con un flusso di lavoro di attivazione.

Il controllo qualità attivazione valuta solo la fattibilità dell&#39;attivazione. **non** attiva i tipi di pubblico, modifica le configurazioni o copia i dati.
