---
title: Strumenti Journey Optimizer in CX Coworker Gateway
description: Scopri quali strumenti Adobe Journey Optimizer sono disponibili tramite CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 2%
---
# Strumenti Adobe Journey Optimizer in CX Coworker Gateway {#ajo-mcp}

Utilizza gli strumenti del prodotto Adobe Journey Optimizer per controllare campagne, percorsi e configurazioni di canale da un client compatibile con MCP. Questi strumenti sono disponibili tramite [CX Coworker Gateway](overview.md) quando l&#39;organizzazione è abilitata e l&#39;account utente dispone delle autorizzazioni Journey Optimizer richieste.

Per ulteriori informazioni, vedere [Utilizzare i client MCP](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/content-management/combine/ajo-mcp){target="_blank"} nella documentazione di Adobe Journey Optimizer.

Per informazioni sulla creazione, l&#39;analisi e la simulazione di percorsi tramite un&#39;esperienza di tipo conversazionale e attivo, vedere [Journey Agent](https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/agents/ajo-agent).

>[!AVAILABILITY]
>
>Gli strumenti del prodotto Journey Optimizer sono disponibili in Beta. L’accesso avviene solo su invito e richiede l’abilitazione dell’organizzazione Adobe. Consulta [Accedere agli strumenti di CX Coworker Gateway](access.md).

## Funzionalità principali {#mcp-capabilities}

Gli strumenti di Journey Optimizer forniscono una superficie di sola lettura per la revisione della configurazione di campagne, percorsi e canali. Puoi eseguire le seguenti azioni:

- Elencare le campagne Journey Optimizer e filtrare per stato.
- Recupera i dettagli della campagna, tra cui il targeting, la pianificazione, il canale e i metadati di configurazione del contenuto.
- Elenca e controlla i percorsi nella sandbox, incluse le diramazioni, le condizioni e le azioni.
- Elenca le configurazioni del canale per i canali e-mail, SMS, push e WhatsApp.
- Elencare le azioni di marketing disponibili per l’applicazione dei criteri di governance dei dati.
- Controlla la configurazione di campagne, percorsi e canali nel linguaggio naturale senza navigare tra le schermate dei prodotti.

>[!IMPORTANT]
>
>Tutti gli strumenti di Journey Optimizer nel Beta corrente sono di sola lettura. La creazione, l’aggiornamento, l’eliminazione, l’avvio, l’arresto o la pubblicazione di campagne o percorsi non è supportata.

## Strumenti disponibili {#mcp-tools}

| Strumento | Descrizione |
| --- | --- |
| `ajo_campaign_list` | Sfoglia le campagne di marketing Journey Optimizer. Supporta il filtraggio per stato, ad esempio `DRAFT`, `LIVE`, `STOPPED` e `COMPLETED`. |
| `ajo_campaign_get` | Recupera i dettagli e la configurazione per una campagna specifica per ID, inclusi i metadati di targeting del pubblico, pianificazione, canale e impostazioni di contenuto. |
| `ajo_journey_list` | Sfoglia tutti i percorsi nella sandbox di Journey Optimizer. |
| `ajo_journey_get` | Recupera i dettagli completi di un percorso specifico per ID, inclusi rami, condizioni e azioni. |
| Visualizzazione percorso | Rendering della struttura e del flusso di un percorso per un&#39;esplorazione visiva interattiva. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | Visualizza i predefiniti di superficie e le impostazioni di branding per e-mail, SMS, push o [!DNL WhatsApp] canali. |
| `ajo_channel_configuration_resource_list`, `ajo_channel_configuration_resource_get` | Elenca e recupera le risorse di configurazione di supporto a cui fanno riferimento le configurazioni del canale, ad esempio le credenziali push, i sottodomini e-mail, i pool IP, le credenziali SMS e le credenziali [!DNL WhatsApp]. |
| `ajo_marketing_action_list` | Elencare le azioni di marketing disponibili per l’applicazione dei criteri di governance dei dati. |

## Esempi di prompt {#mcp-use-cases}

| Obiettivo | Esempio di prompt |
| --- | --- |
| Panoramica della campagna | &quot;Mostra tutte le campagne Journey Optimizer&quot; |
| Controllo dello stato | &quot;Quali campagne sono attualmente live?&quot; |
| Dettagli della campagna | &quot;Ottenere i dettagli completi della campagna `[campaign ID]`.&quot; |
| Panoramica del percorso | &quot;Mostrami tutti i miei percorsi Journey Optimizer.&quot; |
| Dettagli percorso | &quot;Ottenere tutti i dettagli del percorso `[journey ID]`, incluse le diramazioni e le condizioni.&quot; |
| Pubblico e targeting | &quot;Quale pubblico è destinatario nella campagna `[campaign ID]`?&quot; |
| Pianificazione e tempistica | &quot;Quando è pianificata l&#39;esecuzione della campagna `[campaign ID]`?&quot; |
| Risoluzione dei problemi | &quot;Rivedi la configurazione della campagna `[campaign ID]` e segnala i possibili problemi.&quot; |
| Configurazione dei canali | &quot;Quali configurazioni del canale e-mail sono disponibili?&quot; |
| Audit del canale | &quot;Quali configurazioni di canale sono mancanti o incomplete?&quot; |
| Governance | &quot;Quali azioni di marketing sono disponibili nella sandbox?&quot; |

## Strumenti di gestione dei contenuti {#mcp-content-management}

Oltre a questi strumenti di sola lettura, gli utenti di Journey Optimizer possono individuare e gestire le risorse di contenuto, come modelli di contenuto, frammenti, pagine di destinazione e contenuti di messaggi in linea del percorso o della campagna, direttamente da CX Coworker tramite prompt in linguaggio naturale. Questa funzionalità è basata su un set separato di strumenti MCP di lettura e scrittura per i contenuti Journey Optimizer ed è disponibile per tutti i clienti che hanno accesso a CX Coworker.

Per ulteriori informazioni, consulta [Strumenti di gestione dei contenuti](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/get-started/essentials/ajo-coworker-skills#content-management){target="_blank"} nella documentazione di Adobe Journey Optimizer.

Gli strumenti di gestione dei contenuti consentono di:

- Sfoglia modelli di contenuto, frammenti e pagine di destinazione e recuperane struttura, metadati e stato.
- Recupera il contenuto del messaggio in linea configurato su un nodo di azione di percorso o campagna.
- Crea e aggiorna modelli di contenuto per qualsiasi canale.
- Crea, aggiorna, clona e pubblica frammenti.
- Sostituisci una variante di canale nel messaggio in linea di un percorso o di un nodo di azione della campagna.

>[!IMPORTANT]
>
>A differenza degli strumenti di sola lettura di cui sopra, gli strumenti di gestione dei contenuti supportano le operazioni di scrittura. La ricerca full-text in modelli o frammenti, la convalida di modelli o frammenti, la creazione o la pubblicazione di pagine di destinazione e l’eliminazione di modelli di contenuto, frammenti o pagine di destinazione non sono supportate.

## Contesto del prodotto e autorizzazioni {#mcp-context}

L’account utente deve disporre dell’autorizzazione per visualizzare le campagne Journey Optimizer, i percorsi e le configurazioni di canale su cui esegui la query. MCP non ignora le autorizzazioni del prodotto.

Se la tua organizzazione utilizza più sandbox, specifica il contesto della sandbox o dell’ambiente nel prompt quando sono necessari i risultati di una sandbox specifica.

## Limitazioni note {#mcp-limitations}

| Limitazione | Descrizione | Soluzione alternativa |
| --- | --- | --- |
| Superficie di sola lettura | Gli strumenti di Journey Optimizer espongono solo le operazioni di recupero. Non puoi creare, aggiornare, eliminare, avviare, interrompere o pubblicare campagne o percorsi. | Utilizza l’interfaccia utente o le API di Journey Optimizer per le operazioni di scrittura. |
| Nessun coinvolgimento o metrica delle prestazioni | Gli strumenti non restituiscono dati di reporting come impression, tassi di click-through, conversioni o stati di consegna. | Utilizza gli strumenti di reporting di Journey Optimizer, Customer Journey Analytics o Adobe Analytics per le metriche delle prestazioni. |
| La paginazione dell’elenco delle campagne è limitata | L’elenco delle campagne restituisce la prima pagina dei risultati, fino a 50 campagne ordinate alfabeticamente. I valori di offset e limite non vengono applicati. | Utilizza `Get Campaign` direttamente se l&#39;ID della campagna è noto. Utilizza l’interfaccia utente di Journey Optimizer per la navigazione e il filtraggio completi. |
| Nessun filtro lato server per data, canale o pianificazione | L’elenco delle campagne supporta il filtro dello stato, ma non la data di pubblicazione, la data di pianificazione, il canale o il tipo di campagna. | Utilizza l’elenco delle campagne dell’interfaccia utente di Journey Optimizer per il filtro nativo di data e canale. |
| Recupero del contenuto dei messaggi non disponibile tramite gli strumenti di prodotto | HTML per messaggi, righe dell’oggetto, token di personalizzazione e contenuto dell’offerta non sono disponibili tramite gli strumenti di sola lettura di cui sopra. | Utilizza gli [strumenti di gestione dei contenuti](#mcp-content-management) per recuperare e aggiornare il contenuto dei messaggi in linea o visualizzarlo direttamente nell&#39;interfaccia utente di Journey Optimizer. |