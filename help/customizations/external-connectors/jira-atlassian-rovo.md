---
title: Connettore esterno Jira/Atlassian Rovo
description: Scopri come configurare il connettore esterno Jira/Atlassian Rovo in CX Enterprise Coworker e come accedere con Atlassian per leggere e cercare gli elementi di lavoro Jira.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Questo connettore è in versione beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 92e7715a5eb7ab4f8feb7348384c94fabc1b78cf
workflow-type: tm+mt
source-wordcount: '1482'
ht-degree: 1%
---

# Connettore esterno Jira/Atlassian Rovo {#jira-atlassian-rovo}

Utilizza il connettore esterno [!DNL Jira] / [!DNL Atlassian Rovo] per leggere e cercare gli elementi di lavoro [!DNL Jira] in Adobe CX Enterprise Coworker. Dopo aver configurato il connettore, chiedi al collega di trovare gli elementi di lavoro, leggerne i dettagli e cercare con Jira Query Language (JQL). Il connettore è un server MCP ospitato da [!DNL Atlassian].

>[!AVAILABILITY]
>
>Il connettore esterno [!DNL Jira] / [!DNL Atlassian Rovo] è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.

## Configurazione del connettore {#connector-configuration}

Il processo di configurazione del connettore è costituito da tre parti separate:

* Preparazione **[!DNL Atlassian]:** Un amministratore organizzazione [!DNL Atlassian] consente al dominio URL di reindirizzamento di Coworker e rivede i criteri di accesso MCP.
* **Configurazione organizzazione:** Un amministratore di Coworker configura il connettore una sola volta per l&#39;intera organizzazione. L&#39;amministratore sceglie gli strumenti di sola lettura che i membri possono utilizzare.
* **Accesso membro:** Ogni membro effettua l&#39;accesso con il proprio account [!DNL Atlassian]. I membri possono accedere solo ai dati [!DNL Jira] che il loro account dispone dell&#39;autorizzazione per visualizzare.

Il salvataggio della configurazione dell&#39;organizzazione non comporta l&#39;accesso ad alcun membro né la concessione di autorizzazioni [!DNL Jira]. Ogni membro deve effettuare l&#39;accesso separatamente.

Il connettore non dispone di un account di servizio condiviso o di un&#39;opzione token API. L&#39;applicazione OAuth viene registrata automaticamente con [!DNL Atlassian], pertanto non si immette un ID client o un segreto client.

Anche se il nome del connettore include [!DNL Atlassian Rovo], il connettore richiede solo l&#39;accesso in lettura e ricerca a [!DNL Jira]. Non richiede l&#39;accesso [!DNL Confluence], specifico per [!DNL Rovo], in scrittura o distruttivo. Altre funzionalità MCP [!DNL Atlassian] non sono necessariamente disponibili tramite questo connettore.

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di disporre dei seguenti elementi:

* **Per la configurazione dell&#39;organizzazione:** un account con l&#39;autorizzazione per gestire i connettori dell&#39;organizzazione in Coworker, in un&#39;organizzazione in cui è disponibile il connettore [!DNL Jira] / [!DNL Atlassian Rovo].
* **Per [!DNL Atlassian] preparazione:** Amministratore dell&#39;organizzazione [!DNL Atlassian] che può approvare l&#39;accesso MCP e il dominio URL di reindirizzamento di Coworker.
* **Per l&#39;accesso membro:** account [!DNL Atlassian] con accesso ai siti, ai progetti e agli elementi di lavoro [!DNL Jira] previsti.
* **Per l&#39;accesso alla rete:** [!DNL Atlassian] IP e criteri dell&#39;app che consentono la connessione. In caso di esito positivo, l’accesso non conferma che le richieste di strumenti siano consentite.
* **[!DNL Rovo]abilitato:** [!DNL Rovo] abilitato per l&#39;organizzazione [!DNL Atlassian] e i siti [!DNL Jira] previsti prima che i membri utilizzino il connettore. Per ulteriori informazioni, vedere [Come abilitare Rovo](https://www.atlassian.com/software/rovo/guides/admin-guide/rovo-activation) nella documentazione di [!DNL Atlassian].

## Prepara accesso [!DNL Atlassian] {#prepare-atlassian}

Prima che i membri effettuino l&#39;accesso, l&#39;amministratore dell&#39;organizzazione [!DNL Atlassian] prepara l&#39;accesso in [!DNL Atlassian Administration]:

1. Aprire [!DNL Atlassian Administration] e selezionare l&#39;organizzazione desiderata.

1. Seleziona **[!UICONTROL Connettori]** > **[!UICONTROL Server MCP Atlassian]** > **[!UICONTROL Aggiungi dominio]**.

1. Aggiungi il dominio dell&#39;**[!UICONTROL URL di reindirizzamento]** visualizzato nella finestra di dialogo di configurazione di Collaborator. Per la finestra di dialogo, consulta [Configurare il connettore per la tua organizzazione](#configure-organization).

   Segui le regole del formato di dominio [!DNL Atlassian] invece di incollare l&#39;URL completo. Per ulteriori informazioni, vedere [Domini server MCP Atlassian disponibili](https://support.atlassian.com/security-and-access-policies/docs/available-atlassian-mcp-server-domains/) nella documentazione di [!DNL Atlassian].

1. Esaminare i gruppi di autorizzazioni MCP, i criteri dell&#39;app e i elenchi Consentiti di IP con l&#39;amministratore [!DNL Atlassian]. Per ulteriori informazioni, vedere la seguente documentazione di [!DNL Atlassian]:

   * [Strumenti MCP Atlassian supportati](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/), per i gruppi di autorizzazioni e gli ambiti richiesti da ogni strumento
   * [Controlla le impostazioni del server MCP di Atlassian](https://support.atlassian.com/security-and-access-policies/docs/control-atlassian-mcp-server-settings/) per l&#39;autenticazione e la inserisce nell&#39;elenco Consentiti di IP

Utilizza sempre l’URL di reindirizzamento mostrato nella finestra di dialogo Collaboratore per l’ambiente che stai configurando. Non copiare un URL di reindirizzamento da un altro ambiente.

## Configurare il connettore per l’organizzazione {#configure-organization}

Gli amministratori rendono il connettore [!DNL Jira] / [!DNL Atlassian Rovo] disponibile a tutti gli utenti dell&#39;organizzazione. Le modifiche apportate alla pagina dell’organizzazione vengono applicate a tutti gli utenti dell’organizzazione.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Organizzazione]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Nella scheda **[!UICONTROL Jira / Atlassian Rovo]**, seleziona **[!UICONTROL Configura]**. I membri non possono configurare o rimuovere questa connessione.

1. Nella finestra di dialogo **[!UICONTROL Connetti Jira / Atlassian Rovo]**, controlla il **[!UICONTROL URL server]**, `https://mcp.atlassian.com/v2/mcp` corretto.

   Rivedere l&#39;**[!UICONTROL URL di reindirizzamento]** e assicurarsi che un amministratore di [!DNL Atlassian] approvi il dominio, come descritto in [Preparare l&#39;accesso ad Atlassian](#prepare-atlassian). Non immetti credenziali OAuth.

1. In **[!UICONTROL Strumenti disponibili per gli utenti]**, scegliere gli strumenti che i membri possono utilizzare. Per ulteriori informazioni, vedere [Strumenti disponibili](#available-tools).

   Lo strumento di individuazione del sito `getAccessibleAtlassianResources` è obbligatorio e rimane abilitato. Gli altri cinque strumenti sono facoltativi. Per bloccare uno strumento facoltativo per tutti gli utenti dell’organizzazione, rimuovilo. Per ripristinare gli strumenti rimossi, selezionare **[!UICONTROL Ripristina tutti gli strumenti]**. È possibile salvare la configurazione con solo l&#39;individuazione del sito abilitata, ma i membri non possono quindi leggere o cercare elementi di lavoro.

   ![Connessione della finestra di dialogo di Jira/Atlassian Rovo che mostra l&#39;URL del server, un URL di reindirizzamento reindirizzato e sei strumenti disponibili per gli utenti, con lo strumento getAccessibleAtlassianResources richiesto e cinque strumenti facoltativi.](./assets/jira-atlassian-rovo/org-configure.png){width="500" zoomable="yes"}

1. Selezionare **[!UICONTROL Salva connessione]**, quindi esaminare i dettagli della connessione.

   Il connettore richiede i seguenti ambiti OAuth quando ogni membro effettua l’accesso:

   | Portata | Scopo |
   | --- | --- |
   | `read:me`, `read:account` | Supporta l&#39;autorizzazione con l&#39;account [!DNL Atlassian] del membro. |
   | `read:jira:agent-interface` | Lettura dei dati di [!DNL Jira]. |
   | `search:jira:agent-interface` | Cerca dati [!DNL Jira]. |
   | `offline_access` | Aggiorna il token di accesso. |

   Il timeout dello strumento è di 60 secondi. La prima connessione e l&#39;individuazione dello strumento possono richiedere più tempo.

### Strumenti disponibili {#available-tools}

Il connettore [!DNL Jira] / [!DNL Atlassian Rovo] fornisce i seguenti strumenti di sola lettura:

| Strumento | Descrizione | Controllo amministratore |
| --- | --- | --- |
| `getAccessibleAtlassianResources` | Trova i siti [!DNL Atlassian] e gli ID cloud a cui puoi accedere. Gli strumenti [!DNL Jira] richiedono questo strumento. | Obbligatorio |
| `atlassianUserInfo` | Ottenere le informazioni sull&#39;account dell&#39;utente connesso. | Facoltativo |
| `getJiraIssue` | Ottieni un elemento di lavoro [!DNL Jira] per ID o chiave. | Facoltativo |
| `searchJiraIssuesUsingJql` | Cerca [!DNL Jira] elementi di lavoro con JQL. | Facoltativo |
| `discover` | Trova ulteriori operazioni dello strumento e i relativi schemi di input. | Facoltativo |
| `executeRead` | Eseguire le operazioni di lettura trovate tramite `discover`, ad esempio la lettura di commenti, registri delle modifiche, progetti, bacheche e sprint. | Facoltativo |

>[!IMPORTANT]
>
>Gli strumenti `discover` e `executeRead` consentono ai membri di accedere come gruppo a ulteriori operazioni di lettura consentite. Non è possibile disattivare singole operazioni. Se questo accesso non è accettabile per la tua organizzazione, rimuovi entrambi gli strumenti. Il connettore non include operazioni di scrittura (`executeWrite`) o operazioni distruttive (`executeDestructive`).

La rimozione degli strumenti opzionali ne limita la disponibilità in Collaborator. Non riduce gli ambiti OAuth richiesti dal connettore al momento dell’accesso.

Ogni strumento necessita di [!DNL Atlassian] gruppi di autorizzazioni e ambiti specifici. Per ulteriori informazioni, vedere [Strumenti MCP Atlassian supportati](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/) nella documentazione di [!DNL Atlassian].

## Accedi come membro {#sign-in-as-a-member}

Dopo che un amministratore ha configurato il connettore, ogni membro accede con il proprio account [!DNL Atlassian]. Per accedere non è necessario un ID client, un segreto client o un token di accesso.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Utente]**, quindi seleziona **[!UICONTROL Connettori esterni]**.

1. Trova la scheda **[!UICONTROL Jira / Atlassian Rovo]**. Se nella scheda è visualizzato **[!UICONTROL Non configurato]** e **[!UICONTROL Non ancora disponibile. L&#39;amministratore deve configurarlo.]**, chiedi all&#39;amministratore di [configurare il connettore](#configure-organization). Impossibile configurare il connettore.

1. Seleziona **[!UICONTROL Accedi]** e utilizza l&#39;account [!DNL Atlassian] che ha accesso al sito [!DNL Jira] previsto. Completa eventuali richieste di Single Sign-On (SSO), autenticazione a più fattori (MFA) e richieste di consenso. Prima del consenso, controlla l’accesso di lettura e ricerca richiesto.

   >[!IMPORTANT]
   >
   >Continua solo se riconosci l’app e l’organizzazione approva l’accesso richiesto.

1. Torna a Collaboratore e apri i dettagli del connettore. La connessione è di sola lettura per i membri ed è possibile visualizzare gli strumenti abilitati dall&#39;amministratore. Seleziona **[!UICONTROL Verifica connessione]** per confermare la connessione.

1. Se necessario, esegui una piccola verifica di sola lettura, come descritto in [Verifica l&#39;accesso Jira](#check-access).

Se il test ha esito positivo, non viene confermato che è possibile accedere a ogni sito, progetto o elemento di lavoro [!DNL Jira].

## Controlla l&#39;accesso a [!DNL Jira] {#check-access}

Per confermare che il connettore possa leggere i dati, avvia una chat e immetti un prompt di sola lettura.

Esempio di prompt:

* &quot;Cerca in Jira fino a cinque elementi di lavoro assegnati a me, ordinati in base all’ultimo aggiornamento. Includi le chiavi e i collegamenti. Non modificare nulla.&quot;

Affinché la richiesta funzioni, l&#39;amministratore deve attivare uno strumento di ricerca e l&#39;account [!DNL Jira] deve disporre dell&#39;autorizzazione per visualizzare gli elementi di lavoro.

## Risolvere i problemi di accesso {#troubleshoot-access}

Se l&#39;accesso o l&#39;accesso non riesce, verifica quanto segue con il tuo amministratore:

| Problema | Cosa controllare |
| --- | --- |
| L&#39;accesso è bloccato per il client o il dominio | Verificare che il dominio dell&#39;URL di reindirizzamento per l&#39;ambiente sia approvato in [!DNL Atlassian Administration], nelle impostazioni del **[!UICONTROL server MCP Atlassian]**. |
| Il consenso ha esito positivo, ma le chiamate allo strumento vengono negate | Controlla le tue autorizzazioni di [!DNL Jira], i gruppi di autorizzazioni MCP di [!DNL Atlassian], i criteri delle app e gli IP. Per i gruppi di autorizzazioni necessari per ogni strumento, vedere [Strumenti MCP Atlassian supportati](https://support.atlassian.com/atlassian-ai-gateway/docs/supported-tools/). |
| La ricerca JQL non riesce, ma altre letture funzionano | Verificare che l&#39;amministratore abbia abilitato `searchJiraIssuesUsingJql` e che la connessione richieda l&#39;ambito `search:jira:agent-interface`. |
| Il consenso restituisce `invalid_request` | Chiedere all&#39;amministratore di confermare che la connessione richiede `read:me` e `read:account` oltre agli ambiti [!DNL Jira]. |
| Dopo una modifica vengono ancora visualizzati ambiti meno recenti | Un override del provider di autenticazione `jira_login` obsoleto a livello di utente può avere la precedenza sulla connessione dell&#39;organizzazione. Chiedere a un amministratore di aggiornare o rimuovere solo la sostituzione obsoleta, quindi accedere di nuovo. |
| Manca uno strumento | Chiedere all&#39;amministratore di controllare la selezione dello strumento. Ulteriori operazioni di lettura richiedono sia `discover` che `executeRead`, gli ambiti richiesti e le autorizzazioni corrette. |
| **[!UICONTROL La connessione di prova]** è lenta o scaduta | L&#39;individuazione dello strumento può richiedere più tempo del timeout dello strumento di 60 secondi. Prima di modificare le credenziali, verificare se il problema è l&#39;individuazione lenta o un errore di accesso. |

Quando richiedi assistenza, non condividere password, token, codici di autorizzazione o URL di consenso. Non includerli nelle schermate o nei ticket di supporto.
