---
title: Panoramica di Adobe CX Coworker Gateway
description: Adobe CX Coworker Gateway è l'MCP unificato per Adobe CX Enterprise, che offre ai client MCP un'unica connessione agli strumenti di prodotto supportati.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 3%
---
# Adobe CX Coworker Gateway {#mcp-overview}

Adobe CX Coworker Gateway è il protocollo MCP (Unified Model Context Protocol) per Adobe CX Enterprise. Con una connessione, i clienti compatibili con MCP possono accedere agli strumenti di prodotto Adobe che la tua organizzazione e il tuo account sono autorizzati a utilizzare.

>[!IMPORTANT]
>
>Per poter utilizzare gli strumenti di **CX Coworker Gateway**, è necessario che l&#39;organizzazione Adobe sia abilitata.
>
>Se la tua organizzazione non dispone ancora dell&#39;accesso, invia un&#39;e-mail a [cx-coworker-gateway-support@adobe.com](mailto:cx-coworker-gateway-support@adobe.com) per richiedere l&#39;abilitazione per la tua organizzazione.

Utilizzare l&#39;endpoint del gateway di CX Coworker per la configurazione di tutti i client MCP:

```
https://cx-coworker-gateway.adobe.io/mcp
```

Dopo la connessione, l’endpoint espone gli strumenti disponibili all’organizzazione Adobe e le relative credenziali. Le pagine specifiche di questo manuale descrivono le funzioni di ogni strumento di prodotto, i dati a cui può accedere ed eventuali limitazioni specifiche del prodotto.

## Che cos&#39;è Model Context Protocol? {#mcp-what-is}

MCP (Model Context Protocol) è uno standard open source per la connessione di applicazioni AI a sistemi esterni. I client compatibili con MCP come [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] e [!DNL VS Code] possono utilizzare questi strumenti per recuperare il contesto del prodotto, eseguire le operazioni supportate e restituire le risposte in linguaggio naturale.

CX Coworker Gateway fornisce un endpoint gestito per gli strumenti di prodotto CX Coworker Gateway. Invece di aggiungere server di prodotto separati, connettiti una volta all’endpoint e utilizza gli strumenti di prodotto visualizzati per le soluzioni autorizzate.

## Strumenti di prodotto disponibili {#available-product-tools}

I seguenti strumenti di prodotto sono documentati in questa guida:


| Strumenti di prodotto | Cosa espone attraverso l’endpoint | Disponibilità | Documentazione |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Real-Time CDP** | Tipi di pubblico, destinazioni, origini, spazi dei nomi delle identità e stato di attivazione (sola lettura) | Beta | [Strumenti di Real-Time CDP](rtcdp-mcp.md) |
| **Experience Platform** | Schemi, set di dati, governance dei dati, Query Service, eventi di audit, metriche di osservabilità e valutazioni di verifica dello stato della sandbox (sola lettura) | Beta | [Strumenti di Experience Platform](aep-mcp.md) |
| **Journey Optimizer** | Configurazioni di campagne, percorsi e canali (sola lettura); modelli di contenuto, frammenti, pagine di destinazione e contenuto dei messaggi in linea (lettura e scrittura) | Beta | [Strumenti di Journey Optimizer](ajo-mcp.md) |
| **Customer Journey Analytics** | Visualizzazioni dati, dimensioni, metriche, rapporti, segmenti, intervalli di date, progetti e tipi di pubblico (lettura e scrittura) | Disponibile | [Strumenti di Customer Journey Analytics](cja-mcp.md) |
| **Adobe Analytics** | Suite di rapporti, dimensioni, metriche, rapporti, segmenti, intervalli di date e progetti Workspace (lettura e scrittura per i componenti supportati) | Disponibile | [Strumenti di Adobe Analytics](analytics-mcp.md) |
| **Workfront** | Strumenti di gestione del lavoro per progetti, attività e flussi di lavoro di approvazione | Anteprima | [Server MCP Workfront](https://experienceleague.adobe.com/it/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview) |


>[!NOTE]
>
>La disponibilità dello strumento dipende dalle licenze del prodotto, dall’abilitazione dell’organizzazione, dalle autorizzazioni del prodotto e dalle credenziali di Adobe utilizzate per l’autenticazione. In MCP vengono visualizzati solo gli strumenti a cui l’organizzazione e l’account utente hanno diritto di accedere. Consulta [Accedere agli strumenti di CX Coworker Gateway](access.md).



## Introduzione {#mcp-get-started}

1. Esaminare [Accedere agli strumenti di CX Coworker Gateway](access.md) per verificare la disponibilità, l&#39;abilitazione e le autorizzazioni del prodotto.
2. Segui [Installare Adobe per CX Coworker Gateway](install.md) per connettere il client MCP all&#39;endpoint.
3. Rivedi la pagina del prodotto per ogni strumento prodotto che intendi utilizzare.

