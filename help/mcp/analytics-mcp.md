---
title: Strumenti Adobe Analytics in CX Coworker Gateway
description: Scopri quali strumenti Adobe Analytics sono disponibili tramite Adobe CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 4%
---
# Strumenti di Adobe Analytics in Adobe CX Coworker Gateway {#aa-mcp}

Puoi utilizzare gli strumenti di Adobe Analytics per esplorare le suite di rapporti, scoprire dimensioni e metriche, eseguire rapporti e gestire componenti di analisi selezionati da un client compatibile con MCP. Questi strumenti sono disponibili tramite il [Adobe CX Coworker Gateway](overview.md) unificato quando l&#39;account dispone della licenza e delle autorizzazioni Adobe Analytics richieste.

>[!AVAILABILITY]
>
>Gli strumenti di analisi sono disponibili per i clienti con una licenza Adobe Analytics. L&#39;accesso è controllato dall&#39;autorizzazione di accesso **MCP** in Adobe Admin Console. Per ulteriori informazioni, leggere [Strumenti di Access Gateway](access.md).

## Funzionalità principali {#mcp-capabilities}

Gli strumenti Adobe Analytics supportano i flussi di lavoro di rilevamento e reporting di Analytics dal client MCP. Puoi eseguire le seguenti azioni:

- Scopri le suite di rapporti e come sono configurate.
- Trova dimensioni, metriche, metriche calcolate, segmenti, intervalli di date e progetti Workspace.
- Esegui rapporti con classifica e tendenze con dimensioni, metriche, intervalli di date e filtri di segmenti.
- Crea e aggiorna i componenti riutilizzabili selezionati, ad esempio segmenti e intervalli di date.
- Genera informazioni dai dati di Adobe Analytics utilizzando il linguaggio naturale.

>[!IMPORTANT]
>
>Alcuni strumenti di Adobe Analytics possono creare o aggiornare i componenti di analisi. Rivedi e convalida tutte le modifiche avviate da MCP prima di fare affidamento su di esse.

## Copertura dello strumento {#mcp-tools}

| Area | Che cosa puoi fare |
| --- | --- |
| Suite di rapporti | Scopri le suite di rapporti disponibili per il tuo account e controlla i dettagli di configurazione. |
| Componenti | Trova e descrivi dimensioni, metriche, metriche calcolate, segmenti e intervalli di date. |
| Generazione di rapporti | Esegui rapporti con classifica e tendenze utilizzando dimensioni, metriche, intervalli di date e filtri di segmenti selezionati. |
| Segmenti e intervalli di date | Crea e aggiorna segmenti riutilizzabili e intervalli di date laddove consentito dalle autorizzazioni del prodotto. |
| Progetti Workspace | Scopri e descrivi i progetti Analysis Workspace. |

Per un elenco completo e aggiornato degli strumenti, consulta [Riferimento per gli strumenti MCP di Adobe Analytics](https://developer.adobe.com/analytics-mcp/docs/aa/reference){target="_blank"}.

## Esempi di prompt {#mcp-use-cases}

| Obiettivo | Esempio di prompt |
| --- | --- |
| Scopri le suite di rapporti | &quot;Elencare le suite di rapporti a cui posso accedere.&quot; |
| Trova componenti | &quot;Trova metriche relative ai ricavi.&quot; |
| Eseguire un rapporto | &quot;Esegui un rapporto con classifica delle visualizzazioni di pagina per pagina per gli ultimi 7 giorni.&quot; |
| Ispezionare un segmento | &quot;Descrivi il segmento `[segment name]` e mostrami la relativa definizione.&quot; |
| Esplora progetti | &quot;Elencare i miei progetti Analysis Workspace relativi all’acquisizione.&quot; |

## Contesto del prodotto e autorizzazioni {#mcp-context}

Il tuo account deve appartenere a un profilo di prodotto Adobe Analytics che include l&#39;elemento di autorizzazione **Accesso MCP**, concesso da un amministratore di sistema o di prodotto in Adobe Admin Console.

Le autorizzazioni per i prodotti sono ancora valide. L’account deve essere in grado di visualizzare le suite di rapporti, i componenti, i rapporti e i progetti interrogati e deve disporre delle autorizzazioni di prodotto appropriate per le operazioni di scrittura, ad esempio la creazione o l’aggiornamento di componenti riutilizzabili.

## Ulteriori informazioni {#mcp-more}

Per il riferimento completo allo strumento e la guida introduttiva, consulta la [documentazione di Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/){target="_blank"}.