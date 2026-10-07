---
title: Accedere agli strumenti di CX Coworker Gateway
description: Prima di utilizzare gli strumenti gateway di Adobe CX Coworker, è necessario verificare la disponibilità del prodotto, l'abilitazione dell'organizzazione e le autorizzazioni.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 4%
---
# Accedere agli strumenti di CX Coworker Gateway {#mcp-access}

Adobe CX Enterprise espone gli strumenti di prodotto attraverso un unico MCP. L’accesso viene valutato in base agli strumenti del prodotto: l’organizzazione Adobe deve essere abilitata per gli strumenti del prodotto pertinenti e l’account utente deve disporre delle autorizzazioni del prodotto necessarie per visualizzare o modificare i dati del prodotto esposti da tali strumenti.

>[!IMPORTANT]
>
>Prima di poter utilizzare gli strumenti di CX Coworker Gateway, è necessario abilitare l&#39;organizzazione Adobe. Se la tua organizzazione non dispone ancora dell’accesso, contatta il team del tuo account Adobe per richiedere l’abilitazione per la tua organizzazione.

## Requisiti di accesso {#mcp-requirements}


| Strumenti di prodotto | Disponibilità | Requisiti di accesso |
| --- | --- | --- |
| Real-Time CDP | Beta | Licenza Real-Time CDP attiva, abilitazione di Beta per la tua organizzazione Adobe e autorizzazioni per visualizzare i tipi di pubblico, le destinazioni, le origini, l’identità e le risorse di attivazione di cui hai query. |
| Experience Platform | Beta | Licenza Experience Platform attiva, abilitazione di Beta per la tua organizzazione Adobe e autorizzazioni per visualizzare schemi, set di dati, governance, servizio query, controllo e risorse sandbox oggetto della query. |
| Journey Optimizer | Beta | Licenza Journey Optimizer attiva, abilitazione di Beta per la tua organizzazione Adobe e autorizzazioni per visualizzare campagne, percorsi e configurazioni di canali. |
| Customer Journey Analytics | Disponibile | Licenza Active Customer Journey Analytics e un profilo di prodotto che include l&#39;elemento di autorizzazione **MCP Access** in Adobe Admin Console. Le autorizzazioni per i prodotti determinano ancora quali visualizzazioni dati, componenti, rapporti, progetti e tipi di pubblico puoi accedere o modificare. |
| Adobe Analytics | Disponibile | Licenza Adobe Analytics attiva e profilo di prodotto che include l&#39;elemento di autorizzazione **Accesso MCP** in Adobe Admin Console. Le autorizzazioni per i prodotti determinano ancora le suite di rapporti, i componenti, i rapporti, i segmenti, gli intervalli di date e i progetti a cui puoi accedere o modificare. |
| Workfront | Anteprima | Licenza Active Workfront e abilitazione MCP di Workfront. Consulta la [documentazione di Workfront MCP](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview). |
| Target | Beta | Licenza di Active Target con un&#39;organizzazione Adobe Experience Platform. Consulta la [documentazione di Target MCP](https://experienceleague.adobe.com/en/docs/target/using/mcp/target-mcp-get-started). |



>[!NOTE]
>
>MCP mette in evidenza solo gli strumenti che l’organizzazione e le credenziali sono autorizzate a utilizzare. Se dopo l’accesso manca uno strumento prodotto, conferma le autorizzazioni per il contratto di licenza del prodotto, l’abilitazione dell’organizzazione e le autorizzazioni per gli utenti.

## Richiedi accesso {#mcp-request}

Per gli strumenti di prodotto Beta o a rilascio limitato, contatta il rappresentante del tuo account Adobe e specifica quali strumenti di prodotto Adobe per CX Coworker Gateway desideri utilizzare. Il tuo rappresentante può coordinare l’abilitazione del prodotto e confermare quando l’organizzazione Adobe è pronta.

Per gli strumenti di prodotto generalmente disponibili che utilizzano l&#39;elemento di autorizzazione **Accesso MCP**, chiedere a un amministratore di sistema o di prodotto di aggiungere il proprio account a un profilo di prodotto che includa l&#39;accesso MCP.

## Abilitazione nel prodotto {#mcp-product-enablement}

Alcuni prodotti richiedono l’abilitazione interna al prodotto o autorizzazioni specifiche per il prodotto, oltre all’accesso MCP. Ad esempio:

- Adobe Analytics e Customer Journey Analytics richiedono l&#39;elemento di autorizzazione **Accesso MCP** in Adobe Admin Console.
- Gli strumenti MCP di Workfront sono abilitati dalle impostazioni Workfront.
- Gli strumenti dei prodotti Beta richiedono l’abilitazione dell’organizzazione Adobe prima che vengano visualizzati tramite MCP.

Visita la pagina del prodotto relativa allo strumento prodotto che intendi utilizzare per autorizzazioni, requisiti contestuali e limitazioni specifiche del prodotto.

## Prima dell’installazione {#mcp-prerequisites}

Prima di collegare il client MCP, verificare che:

- L’organizzazione Adobe è abilitata per gli strumenti di prodotto necessari.
- Il tuo account utente dispone delle autorizzazioni di prodotto necessarie per i dati e le operazioni che intendi utilizzare.
- Si dispone dell&#39;accesso a un client MCP supportato come [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] o [!DNL VS Code].
- Per l&#39;installazione aziendale, è possibile gestire connettori o app personalizzate nelle impostazioni dell&#39;organizzazione del client MCP.

Successivo: [Installare Adobe CX Coworker Gateway](install.md).