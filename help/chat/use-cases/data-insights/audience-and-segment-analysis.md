---
title: Confrontare tipi di pubblico e segmenti di clienti con Chat con i collaboratori
description: Utilizza Chat con collaboratori per confrontare i gruppi di clienti, trovare opportunità di crescita trascurate, tracciare le tendenze del pubblico e trasformare le informazioni in tipi di pubblico da creare.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f914f4a123216985ae9b562413f26e7b8c29eb0f
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 2%
---

# Panoramica dell’analisi del pubblico e dei segmenti

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions. -->

Utilizza Adobe CX Enterprise Coworker Chat per capire quali gruppi di clienti si comportano in modo diverso e come, in modo da poter concentrarti su quelli più importanti. Confronta canali, periodi di tempo e segmenti uno accanto all’altro, tieni traccia di come cambiano i tipi di pubblico nel tempo e trasforma ciò che scopri in un pubblico da creare.

L’analisi del pubblico e dei segmenti è uno dei numerosi domini di analisi disponibili in Chat con collaboratori. Per visualizzare tutti i domini, vedere [Avviare l&#39;analisi in Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) in Analizzare i dati con Chat di Coworker.

**Ideale per:** analista, utente aziendale

## Prerequisiti

<!-- FLAG: Confidence: High for the shared bullets (sourced from the Skills and limitations table and analytics-chat.md). Medium for the "Additional prerequisite" notes on the operational trends rows in the Use cases table: workflows.md lists the operational time-series skill as available for "All Eligible Applications" but doesn't state required permissions. Mapping Track audience size trends to the same requirement is inferred. Low for the "Additional prerequisite" note on the Take an insight into an audience row: inferred from the Audiences section of workflows.md, which lists Real-Time CDP as the application for audience creation. Confirm with the PM. -->

Per utilizzare i casi d’uso in questa pagina, è necessario:

* Chat con collaboratori connessa alle visualizzazioni dati di Customer Journey Analytics o alle suite di rapporti di Adobe Analytics. Vedi [Introduzione all&#39;analisi dei dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accesso alle visualizzazioni dati o alle suite di rapporti che desideri analizzare. La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics.

## Casi d’uso

| Caso d’uso | Funzione |
| --- | --- |
| [Confronta prestazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Confronta le metriche per canali, periodi di tempo o segmenti affiancati.<p>**Prompt di esempio:** &quot;Confronta i ricavi per canale, mese e mese&quot;</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| [Confronta gruppi di clienti](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) | Mostra quali gruppi si comportano in modo diverso, senza richiedere la scrittura della logica dei segmenti.<p>**Ideale per:** utente aziendale</p><p>**Richieste di esempio:**</p><ul><li>&quot;I visitatori social a pagamento si convertono in modo diverso rispetto all’e-mail?&quot;</li><li>&quot;Confrontare i visitatori nuovi e quelli di ritorno in base ai ricavi&quot;</li></ul><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations).</p> |
| Trovare opportunità di crescita trascurate | Esplora tipi di pubblico, percorsi e canali per identificare le opportunità che i dati sulle prestazioni complessive possono nascondere.<p>**Richieste di esempio:**</p><ul><li>&quot;Quale pubblico converte al di sopra della media ma ottiene poco traffico?&quot;</li><li>&quot;Quali canali sono sottoutilizzati per il loro tasso di conversione?&quot;</li></ul> |
| [Analizzare le tendenze e le cause operative](/help/chat/use-cases/workflows.md#data-insights) | Esegui query sui dati storici delle serie temporali per tipi di pubblico, set di dati e percorsi e identifica la causa di un cambiamento.<p>**Ideale per:** Amministratore, Analista</p><p>**Prompt di esempio:** &quot;Mostra le tendenze delle dimensioni del pubblico negli ultimi 90 giorni&quot;</p><p>**Prerequisiti aggiuntivi:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche l&#39;accesso ai tipi di pubblico, ai set di dati o ai percorsi che si desidera analizzare.</p><p>Per ulteriori informazioni, consulta [Informazioni sui dati](/help/chat/use-cases/workflows.md#data-insights) nei casi di utilizzo di Chat con coorker.</p> |
| Tracciare le tendenze delle dimensioni del pubblico | Individua i tipi di pubblico che crescono o si riducono e analizza la causa.<p>**Ideale per:** Amministratore, Analista</p><p>**Prompt di esempio:** &quot;Quali tipi di pubblico sono cresciuti più velocemente in questo trimestre?&quot;</p><p>**Prerequisiti aggiuntivi:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche l&#39;accesso ai tipi di pubblico che si desidera monitorare.</p> |
| Trasformare un’insight in un pubblico | Passa da un’insight a un pubblico che puoi creare senza dover ricominciare da capo.<p>**Richieste di esempio:**</p><ul><li>&quot;Apri questo confronto in Analysis Workspace&quot;</li><li>&quot;Aiutami a creare un pubblico da questo gruppo&quot;</li></ul><p>**Prerequisiti aggiuntivi:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche l&#39;accesso a Real-Time Customer Data Platform e l&#39;autorizzazione per la creazione di tipi di pubblico.</p> |

## Abilità utilizzate

<!-- FLAG: Confidence: High for Compare performance and Analyze operational trends and causes (skills listed for "Comparative analysis" and "Operational time-series & causal analysis" in workflows.md). Medium for Compare customer groups and Track audience size trends, which are mapped to the same skills based on their descriptions. Low for `audience-creation-flow`: inferred from the Audiences section of workflows.md. No skill is listed for Find overlooked growth opportunities because no source names one. Only `cja`, `aa`, and the root cause analysis skills currently appear in the Skills and limitations table on analytics-overview.md. -->

Per i casi d’uso descritti in questo articolo, il collaboratore utilizza le seguenti competenze. Per un elenco di tutte le abilità di analisi, incluse le autorizzazioni necessarie e quelle che non coprono, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analizzare i dati con Chat con collaboratori.

| Competenza | Utilizzato per |
| --- | --- |
| `cja`, `aa` | Confronta prestazioni<br>Confronta gruppi di clienti |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Confronta prestazioni |
| `operational-stats-causal-analysis` | Analizza le tendenze operative e le cause<br>Tieni traccia delle tendenze della dimensione del pubblico |
| `audience-creation-flow` | Trasformare un’insight in un pubblico |

## Suggerimenti per ottenere risultati migliori

* Specifica i segmenti, i tipi di pubblico, i canali o i dispositivi da includere, escludere o confrontare.
* Fai riferimento a segmenti e altri componenti per il loro nome esatto.
* Denomina la metrica e l’intervallo di date su cui desideri confrontare il dato, ad esempio il mese dei ricavi rispetto al mese.
* Chiedi le dimensioni che contribuiscono se vuoi sapere perché un gruppo si comporta in modo diverso da un altro.

## Passaggi successivi

* Per una panoramica dell&#39;analisi dei dati con Chat di Coworker, inclusi gli altri domini di analisi e le best practice, consulta [Analizzare i dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md).
* Per creare tipi di pubblico direttamente in Chat con Coworker, consulta [Valutare lo stato di Experience Platform e creare tipi di pubblico dal linguaggio naturale con Coworker](/help/chat/use-cases/audiences/create-audience-from-natural-language.md).
