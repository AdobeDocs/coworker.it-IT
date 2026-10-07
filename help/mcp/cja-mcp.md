---
title: Strumenti Customer Journey Analytics in CX Coworker Gateway
description: Scopri quali strumenti Adobe Customer Journey Analytics sono disponibili tramite Adobe CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 3%
---

# Strumenti Customer Journey Analytics in Adobe CX Coworker Gateway {#cja-mcp}

Utilizza gli strumenti del prodotto Customer Journey Analytics per esplorare le visualizzazioni dati, individuare dimensioni e metriche, eseguire rapporti e gestire componenti di analisi selezionati da un client compatibile con MCP. Questi strumenti sono disponibili tramite [CX Coworker Gateway](overview.md) quando il tuo account dispone della licenza e delle autorizzazioni Customer Journey Analytics richieste.

>[!AVAILABILITY]
>
>Gli strumenti Customer Journey Analytics sono disponibili per i clienti con una licenza Customer Journey Analytics. L&#39;accesso è controllato dall&#39;autorizzazione di accesso **MCP** in Adobe Admin Console. Consulta [Accedere agli strumenti di CX Coworker Gateway](access.md).

## Funzionalità principali {#mcp-capabilities}

Gli strumenti Customer Journey Analytics supportano flussi di lavoro di analisi gestiti dal client MCP. Puoi eseguire le seguenti azioni:

* Scopri le visualizzazioni dati e come sono configurate.
* Trova dimensioni, metriche, metriche calcolate, segmenti, intervalli di date, pubblico e progetti.
* Esegui rapporti con classifica e tendenze con dimensioni, metriche, intervalli di date e filtri di segmenti.
* Controlla le definizioni dei componenti e l’utilizzo dei componenti.
* Crea o aggiorna i componenti di Analytics e i progetti Workspace selezionati.

>[!IMPORTANT]
>
>A differenza degli strumenti di sola lettura [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) e [Journey Optimizer](ajo-mcp.md), gli strumenti di Customer Journey Analytics includono operazioni di scrittura. Possono creare e aggiornare segmenti, metriche calcolate, intervalli di date, progetti e tipi di pubblico. Rivedi e convalida tutte le modifiche avviate da MCP prima di fare affidamento su di esse.

## Strumenti disponibili {#mcp-tools}

| Area | Strumento | Descrizione |
| --- | --- | --- |
| Configurazione e guide | `describeCja` | Restituisce guide di riferimento per strumenti, dimensioni, metriche, segmenti, metriche calcolate e strutture di progetto. |
| Configurazione e guide | `setDefaultSessionDataViewId` | Configura la visualizzazione dati predefinita a livello di sessione per le successive chiamate dello strumento. |
| Individuazione | `findDimensions` | Individua le dimensioni disponibili, con supporto per la ricerca semantica. |
| Individuazione | `findMetrics` | Rileva le metriche standard e personalizzate, escluse quelle calcolate. |
| Individuazione | `findCalculatedMetrics` | Esplora le metriche calcolate condivise e create dall&#39;utente. |
| Individuazione | `findSegments` | Elenca i segmenti accessibili all’utente corrente. |
| Individuazione | `findDateRanges` | Recupera i componenti dell’intervallo di date salvati. |
| Individuazione | `findDataViews` | Rileva le visualizzazioni dati disponibili. |
| Individuazione | `findProjects` | Individua i progetti Workspace. |
| Individuazione | `findAudiences` | Elenca i componenti di pubblico disponibili. |
| Reporting e analisi | `runReport` | Esegue rapporti classificati con dimensioni, metriche, intervalli di date e filtri di segmenti facoltativi. |
| Reporting e analisi | `searchDimensionItems` | Recupera i valori di dimensione necessari per i rapporti di raggruppamento. |
| Dettagli componente | `describeDimension` | Mostra metadati dettagliati per una dimensione specifica. |
| Dettagli componente | `describeMetric` | Restituisce i metadati delle metriche e i dettagli delle misurazioni. |
| Dettagli componente | `describeSegment` | Visualizza la definizione e le informazioni sulla compatibilità di un segmento. |
| Dettagli componente | `describeCalculatedMetric` | Mostra la formula e le metriche di base utilizzate. |
| Dettagli componente | `describeProject` | Fornisce dettagli sulla configurazione di un progetto Workspace. |
| Dettagli componente | `describeAudience` | Restituisce i metadati del pubblico e lo stato di pubblicazione. |
| Utilizzo dei componenti | `listComponentUsage` | Classifica i componenti in base alla frequenza di utilizzo. |
| Utilizzo dei componenti | `listFrequentlyUsedWith` | Identifica i componenti comunemente associati tra loro. |
| Utilizzo dei componenti | `listSimilarTo` | Trova componenti alternativi che servono a scopi simili. |
| Crea e aggiorna | `upsertSegment` | Crea un nuovo segmento o ne modifica uno esistente. |
| Crea e aggiorna | `upsertCalculatedMetric` | Crea una nuova metrica calcolata o ne modifica una esistente. |
| Crea e aggiorna | `createDateRange` | Crea un componente intervallo date riutilizzabile. |
| Crea e aggiorna | `upsertProject` | Crea un nuovo progetto Workspace o ne modifica uno esistente. |
| Crea e aggiorna | `upsertAudience` | Crea una nuova definizione di pubblico o ne modifica una esistente. |

## Esempi di prompt {#mcp-use-cases}

| Obiettivo | Esempio di prompt |
| --- | --- |
| Visualizzazioni dati elenco | &quot;Elencare le visualizzazioni dati disponibili in Customer Journey Analytics.&quot; |
| Individuare i componenti | &quot;Trovare le metriche relative alle entrate nella visualizzazione dati `[data view name]`.&quot; |
| Eseguire un rapporto | &quot;Eseguire un report con tendenze degli ordini per mese per l&#39;ultimo trimestre.&quot; |
| Suddividere una metrica | &quot;Visualizza i primi 10 canali di marketing per visite, suddivisi per tipo di dispositivo.&quot; |
| Ispezionare un componente | &quot;Descrivi il segmento `[segment name]` e mostrami la relativa definizione.&quot; |
| Utilizzo controllo | &quot;Quali dimensioni vengono utilizzate più frequentemente nei miei progetti?&quot; |
| Crea un segmento | &quot;Crea un segmento per gli utenti che hanno visualizzato la pagina dei prezzi negli ultimi 30 giorni.&quot; |

## Contesto del prodotto e autorizzazioni {#mcp-context}

Il tuo account deve appartenere a un profilo di prodotto Customer Journey Analytics che include l&#39;elemento di autorizzazione **Accesso MCP**, concesso da un amministratore di sistema o di prodotto in Adobe Admin Console.

Le autorizzazioni per i prodotti sono ancora valide. L’account deve essere in grado di visualizzare le visualizzazioni dati, i componenti, i progetti e i tipi di pubblico richiesti e deve disporre delle autorizzazioni di prodotto appropriate per le operazioni di scrittura, ad esempio la creazione o l’aggiornamento di segmenti, metriche calcolate, intervalli di date, progetti o tipi di pubblico.

## Guarda in azione {#mcp-videos}

**Panoramica**

>[!VIDEO](https://video.tv.adobe.com/v/3486322/?captions=ita&learn=on&enablevpops)

**In azione**

>[!VIDEO](https://video.tv.adobe.com/v/3486333/?captions=ita&learn=on&enablevpops)

## Ulteriori informazioni {#mcp-more}

Per il riferimento completo allo strumento e la guida introduttiva, consulta la [documentazione di Customer Journey Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/cja/){target="_blank"}.