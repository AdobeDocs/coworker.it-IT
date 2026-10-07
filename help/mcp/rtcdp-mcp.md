---
title: Strumenti Real-Time CDP in CX Coworker Gateway
description: Scopri come collegare Adobe Real-Time CDP ai client MCP utilizzando il server MCP.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 3%
---
# Strumenti Real-Time CDP in CX Coworker Gateway {#rtcdp-mcp}

È possibile utilizzare gli strumenti del prodotto Real-Time CDP MCP per controllare tipi di pubblico, destinazioni, origini, spazi dei nomi di identità e stato di attivazione da un client compatibile con MCP. Questi strumenti sono disponibili tramite il [gateway di CX Coworker Gateway](overview.md) unificato quando l&#39;organizzazione è abilitata e l&#39;account utente dispone delle autorizzazioni Real-Time CDP richieste.

>[!AVAILABILITY]
>
>Lo strumento del prodotto Real-Time CDP è disponibile in Beta. L’accesso avviene solo su invito e richiede l’abilitazione dell’organizzazione Adobe. Consulta [Accedere agli strumenti di CX Coworker Gateway](access.md).

## Funzionalità principali {#mcp-capabilities}

Gli strumenti di Real-Time CDP forniscono una superficie di monitoraggio e valutazione di sola lettura. Puoi eseguire le seguenti azioni:

* Elenca ed esamina i tipi di pubblico, tra cui lo stato del ciclo di vita, l’origine e lo spazio dei nomi delle identità.
* Esamina i processi di valutazione ed esportazione del pubblico per identificare gli errori recenti.
* Controllare gli account di destinazione configurati, i flussi di destinazione e la cronologia dell&#39;esecuzione dell&#39;attivazione.
* Controlla i connettori di origine, gli account, i flussi e la cronologia delle esecuzioni di acquisizione.
* Elencare gli spazi dei nomi delle identità e i criteri di unione.

>[!IMPORTANT]
>
>Tutti gli strumenti di Real-Time CDP nel Beta corrente sono di sola lettura. La creazione, l’aggiornamento, l’attivazione o l’eliminazione di tipi di pubblico, destinazioni, origini o flussi di dati non è supportata.

## Strumenti disponibili {#mcp-tools}

| Area | Strumento | Descrizione |
| --- | --- | --- |
| Tipi di pubblico | `search_audiences` | Elenca e cerca i tipi di pubblico per nome, tipo di entità, stato del ciclo di vita, spazio dei nomi dell’identità o origine. |
| Tipi di pubblico | `preview_audience_membership` | Stimare la dimensione di un’espressione di segmento PQL o SDD prima di salvarla come pubblico. |
| Tipi di pubblico | `inspect_audience_evaluation_jobs` | Recupera i record del processo di valutazione dei segmenti per diagnosticare i problemi di aggiornamento del pubblico o confermare la cronologia delle valutazioni recenti. |
| Tipi di pubblico | `inspect_audience_export_jobs` | Recupera i record del processo di esportazione del pubblico per confermare i dettagli delle esportazioni completate o dell’errore della superficie. |
| Destinazioni | `search_destination_connectors` | Elenca i tipi di connettore di destinazione disponibili nella piattaforma. |
| Destinazioni | `search_destination_accounts` | Elenca gli account di destinazione autenticati. |
| Destinazioni | `search_destination_input_connections` | Recupera l’input lato Experience Platform di un flusso di destinazione. |
| Destinazioni | `search_destination_output_connections` | Recupera l’endpoint esterno di un flusso di destinazione, inclusi il percorso di destinazione, il formato del file e la configurazione di consegna. |
| Destinazioni | `search_destination_flows` | Elenca e controlla i flussi di attivazione della destinazione configurati, tra cui stato, mappature e pianificazione. |
| Destinazioni e origini | `inspect_flow_runs` | Recupera la cronologia di esecuzione del flusso di origine e di destinazione, inclusi lo stato, la tempistica, i conteggi dei record e i dettagli degli errori. |
| Origini | `search_source_connectors` | Elenca i tipi di connettore di origine disponibili nella piattaforma. |
| Origini | `search_source_accounts` | Elenca gli account di origine autenticati. |
| Origini | `search_source_input_connections` | Recupera ciò che un flusso di origine richiama da un account. |
| Origini | `search_source_output_connections` | Recupera la destinazione del set di dati di Experience Platform per un flusso di origine. |
| Origini | `search_source_flows` | Elenca e controlla le pipeline di acquisizione di origine configurate, tra cui stato, mappature e pianificazione. |
| Identità | `search_identity_namespaces` | Elencare le definizioni dello spazio dei nomi delle identità nella sandbox. |
| Identità | `search_merge_policies` | Elenca i record dei criteri di unione che controllano la modalità di assemblaggio dei profili cliente in tempo reale. |

## Esempi di prompt {#mcp-use-cases}

| Obiettivo | Esempio di prompt |
| --- | --- |
| Elencare tipi di pubblico | &quot;Elenca i miei tipi di pubblico nella sandbox `prod`.&quot; |
| Ispezionare un pubblico | &quot;Visualizza i dettagli e lo stato del ciclo di vita per l&#39;ID pubblico `abc123`.&quot; |
| Diagnosticare i problemi di valutazione | &quot;Mostra i processi di valutazione del pubblico più recenti ed errori di flag.&quot; |
| Controlla processi di esportazione | &quot;Elenca i processi di esportazione del pubblico recenti e mostrami lo stato di ciascuno di essi.&quot; |
| Stimare la dimensione del pubblico | &quot;Stimare la dimensione di questa espressione PQL prima di salvarla: `homeAddress.country = 'US'`.&quot; |
| Rivedi impostazione destinazione | &quot;Elencare i flussi di attivazione di destinazione e mostrare quali sono abilitati o disabilitati.&quot; |
| Esaminare un&#39;esecuzione di attivazione non riuscita | &quot;Visualizza la cronologia di esecuzione per l&#39;ID di flusso `xyz789` e riepiloga eventuali errori.&quot; |
| Rivedi acquisizione origine | &quot;Mostra la cronologia delle esecuzioni recenti per l&#39;ID del flusso di origine `src456` e gli errori dei flag.&quot; |
| Verifica la configurazione dell’identità | &quot;Quali spazi dei nomi di identità sono configurati nella sandbox?&quot; |

## Autorizzazioni {#mcp-context}

L’organizzazione Adobe e il contesto sandbox vengono stabiliti una volta a livello di connessione gateway e si applicano a ogni famiglia di strumenti, in modo da non cambiare organizzazioni o sandbox dagli strumenti Real-Time CDP. Per impostare il contesto per una sessione, vedere [Contesto del prodotto per le chiamate allo strumento](install.md#mcp-connect-params).

L&#39;account utente deve disporre dell&#39;autorizzazione per visualizzare le risorse Real-Time CDP di cui si esegue la query. Il gateway non ignora le autorizzazioni del prodotto.

## Limitazioni note {#mcp-limitations}

| Limitazione | Descrizione | Soluzione alternativa |
| --- | --- | --- |
| Superficie di sola lettura | Gli strumenti di Real-Time CDP espongono solo le API di recupero. Non puoi creare, aggiornare, attivare o eliminare tipi di pubblico, destinazioni, origini o flussi di dati. | Utilizza l’interfaccia utente di Real-Time CDP o le API di Experience Platform per le operazioni di scrittura. |
| Nessuna metrica di coinvolgimento o consegna | Gli strumenti non restituiscono le statistiche di consegna a valle, il coinvolgimento o le metriche di conversione dalle piattaforme di destinazione. | Utilizza gli strumenti di reporting, gli strumenti di Customer Journey Analytics o gli strumenti di Adobe Analytics della piattaforma di destinazione per i dati di coinvolgimento e conversione. |
| La query del segmento deve essere creata esternamente | `preview_audience_membership` richiede un&#39;espressione PQL o SDD valida. Lo strumento non costituisce la query per l’utente. | Crea l’espressione in Segment Builder (Generatore di segmenti) o nell’API del servizio di segmentazione, quindi incollala nel prompt. |
| Impaginazione tramite token di continuazione | Gli strumenti elenco restituiscono risultati impaginati. L’enumerazione completa in sandbox molto grandi richiede il concatenamento di token di continuazione. | Eseguire query limitate utilizzando filtri quali nome, stato, specifica di connessione o intervallo di tempo. |
| Il filtro dell&#39;esecuzione dell&#39;attivazione è basato solo sul tempo | L’ispezione dell’esecuzione dell’attivazione supporta il filtro per stato e marca temporale di completamento, ma non direttamente per tipo di errore o piattaforma di destinazione. | Filtrare per `flowId` prima per eseguire l&#39;ambito in un flusso di destinazione specifico. |

