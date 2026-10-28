---
title: Analizzare le prestazioni aziendali e i KPI con Chat con i collaboratori
description: Utilizza Chat con collaboratori per spiegare perché le metriche sono state spostate, prevedere dove si stanno dirigendo, preparare valutazioni delle prestazioni e trasformare le analisi ripetute in abilità riutilizzabili.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 2%
---

# Panoramica sulle prestazioni aziendali

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Utilizza Adobe CX Enterprise Coworker Chat per capire come sta andando il business, perché una metrica è stata spostata, dove si sta dirigendo e cosa fare dopo. Analizza le modifiche nelle metriche chiave, proiettale in avanti e trasforma i risultati in riepiloghi pronti per le parti interessate e competenze riutilizzabili.

Le prestazioni aziendali sono uno dei numerosi domini di analisi disponibili in Chat con collaboratori. Per visualizzare tutti i domini, vedere [Avviare l&#39;analisi in Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) in Analizzare i dati con Chat di Coworker.

**Ideale per:** analista, utente aziendale

## Prerequisiti

Per utilizzare i casi d’uso in questa pagina, è necessario:

* Chat con collaboratori connessa alle visualizzazioni dati di Customer Journey Analytics o alle suite di rapporti di Adobe Analytics. Vedi [Introduzione all&#39;analisi dei dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accesso alle visualizzazioni dati o alle suite di rapporti che desideri analizzare. La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics.

## Casi d’uso

| Caso d’uso | Funzione |
| --- | --- |
| [Esplora tendenze e cause principali](/help/chat/use-cases/data-insights/root-cause-analysis.md)<p>![Esplora tendenze e cause principali](../../assets/data-validation-aa-cja/trend-line-card.png)</p> | Identifica le tendenze nei dati di Customer Journey Analytics e Adobe Analytics e i fattori che determinano cambiamenti nelle prestazioni, senza query manuali.<p>**Prompt di esempio:** &quot;Perché le conversioni sono diminuite la settimana scorsa?&quot;</p><p>Per ulteriori informazioni, vedere [Customer Journey Analytics &amp; Coworker](/help/chat/use-cases/data-insights/root-cause-analysis.md).</p> |
| [Spiegare perché una metrica è stata spostata](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Esegue un&#39;analisi della causa principale che fa emergere le dimensioni e i segmenti dietro una modifica ed esclude il resto.<p>**Richieste di esempio:**</p><ul><li>&quot;Perché l&#39;aumento delle entrate martedì?&quot;</li><li>&quot;Cosa ha portato il cambiamento nelle sessioni di questo mese?&quot;</li></ul><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Preparare le valutazioni delle prestazioni aziendali](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Trasforma le metriche affidabili in una storia delle prestazioni spiegata, con risultati e passaggi successivi consigliati.<p>**Richieste di esempio:**</p><ul><li>&quot;Dammi una sintesi del mese scorso&quot;</li><li>&quot;Riepilogare le prestazioni per il team di leadership&quot;</li></ul><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Previsione con intestazione di metrica](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Progetta una metrica dai dati storici in modo da poter vedere un messaggio mancante in arrivo.<p>**Richieste di esempio:**</p><ul><li>&quot;Sessioni di previsione per i prossimi 30 giorni&quot;</li><li>&quot;Siamo sulla buona strada per raggiungere il nostro obiettivo di fatturato?&quot;</li></ul><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Creare abilità Customer Journey Analytics personalizzate](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Trasforma un’analisi ripetuta in un’abilità riutilizzabile che persiste nelle sessioni.<p>**Prompt di esempio:** &quot;Trasforma questa analisi settimanale dei ricavi in un&#39;abilità riutilizzabile&quot;</p><p>**Prerequisiti aggiuntivi:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche l&#39;autorizzazione Gestione abilità.</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Ripetizione dell&#39;analisi eseguita correttamente nei diversi mercati](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Applica un approccio analitico collaudato tra marchi, aree geografiche o business unit.<p>**Ideale per:** analista</p><p>**Prompt di esempio:** &quot;Esegui l&#39;abilità funnel settimanale per la visualizzazione dati EMEA&quot;</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |

## Abilità utilizzate

<!-- FLAG: Confidence: High for the root cause analysis skills, `cja-executive-summary`, forecasting with `cja` and `aa`, and `cja-skill-creator` for creating skills. All are listed in the Skills and limitations table and in workflows.md. Medium for mapping Repeat successful analysis across markets to `cja-skill-creator`: the row describes running a saved skill, which is inferred. workflows.md also lists `cja-bacom-anomaly-tracker-v2`, `cja-cno-weekly-pulse`, and `cja-reporting` for executive summaries. They're left out because they look org-specific. Confirm with the PM. -->

Per i casi d’uso descritti in questo articolo, il collaboratore utilizza le seguenti competenze. Per un elenco di tutte le abilità di analisi, incluse le autorizzazioni necessarie e quelle che non coprono, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analizzare i dati con Chat con collaboratori.

| Competenza | Utilizzato per |
| --- | --- |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Esplora tendenze e cause principali<br>Spiega perché una metrica è stata spostata |
| `cja-executive-summary` | Preparare le valutazioni delle prestazioni aziendali |
| `cja`, `aa` | Previsione con intestazione di una metrica |
| `cja-skill-creator` | Creazione di competenze Customer Journey Analytics personalizzate<br>Ripetizione dell&#39;analisi di successo nei diversi mercati |

## Suggerimenti per ottenere risultati migliori

* Denomina la metrica e il periodo della modifica che desideri esaminare. L’analisi della causa principale funziona su una metrica nota in un periodo noto.
* Se desideri una suddivisione di una modifica metrica, chiedi le dimensioni che contribuiscono.
* Richiedi un orizzonte di previsione, ad esempio &quot;prossimi 30 giorni&quot; durante la proiezione delle metriche.
* Specifica il pubblico per un riepilogo, ad esempio la leadership o il team marketing, e se prevedi di presentare i risultati, richiedi una presentazione diapositive.
* Completa prima un’analisi, quindi chiedi a Chat collaboratore di salvarla come abilità. Assegna all’abilità un nome chiaro e descrittivo e tieni presente quanto spesso intendi riutilizzarla.

## Passaggi successivi

* Per una panoramica dell&#39;analisi dei dati con Chat di Coworker, inclusi gli altri domini di analisi e le best practice, consulta [Analizzare i dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md).
* Per visualizzare l&#39;analisi della causa principale in azione, vedere [Customer Journey Analytics &amp; Coworker](/help/chat/use-cases/data-insights/root-cause-analysis.md).
