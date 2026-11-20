---
title: Connettore esterno BigQuery Google
description: Scopri come configurare il connettore esterno Google BigQuery in CX Enterprise Coworker con la tua app Google OAuth e come accedere per eseguire query sui dati BigQuery in chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Questo connettore è in versione beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: a7c55df451e12b78e68050118f649952b705f4a9
workflow-type: tm+mt
source-wordcount: '2213'
ht-degree: 0%
---

# Connettore esterno BigQuery Google {#google-bigquery}

Utilizza il connettore esterno [!DNL Google BigQuery] per esplorare ed eseguire query sui dati di [!DNL BigQuery] in Adobe CX Enterprise Coworker. Dopo aver configurato il connettore, chiedere a Collaboratore di elencare set di dati e tabelle, spiegare uno schema di tabella ed eseguire query SQL di sola lettura. Il connettore è un server MCP (Model Context Protocol) ospitato da [!DNL Google] in `https://bigquery.googleapis.com/mcp`.

>[!AVAILABILITY]
>
>Il connettore esterno [!DNL Google BigQuery] è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.

## Configurazione del connettore {#connector-configuration}

Il processo di configurazione del connettore è costituito da tre parti separate:

* Preparazione **[!DNL Google Cloud]:** Un amministratore [!DNL Google Cloud] prepara un progetto di query, abilita l&#39;API [!DNL BigQuery] e concede ai membri i ruoli di Identity and Access Management (IAM) richiesti.
* **Configurazione organizzazione:** Un amministratore di Coworker configura il connettore una sola volta per l&#39;intera organizzazione. L&#39;amministratore connette l&#39;app OAuth [!DNL Google] dell&#39;organizzazione e seleziona gli strumenti che i membri possono utilizzare.
* **Accesso membro:** Ogni membro effettua l&#39;accesso con il proprio account [!DNL Google]. I membri possono accedere solo ai progetti e ai set di dati a cui può accedere la loro identità [!DNL Google].

Il connettore utilizza un’app OAuth di proprietà della tua organizzazione. Adobe non fornisce un&#39;app OAuth [!DNL Google] per questo connettore. Il salvataggio della configurazione dell&#39;organizzazione non comporta l&#39;accesso ad alcun membro né la concessione di autorizzazioni [!DNL BigQuery]. L&#39;accesso riuscito a [!DNL Google] non concede l&#39;accesso al set di dati, perché [!DNL Google Cloud] IAM controlla l&#39;accesso ai tuoi dati.

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di disporre dei seguenti elementi:

* **Per [!DNL Google Cloud] preparazione:** Un amministratore [!DNL Google Cloud] che può abilitare le API, concedere ruoli IAM e creare un client OAuth in [!DNL Google Auth Platform].
* **Per la configurazione dell&#39;organizzazione:** un account con l&#39;autorizzazione per gestire i connettori dell&#39;organizzazione in Coworker. Sono inoltre necessari l&#39;ID client e il segreto client di un client applicazione Web OAuth [!DNL Google] o i segreti organizzazione esistenti che li contengono.
* **Per l&#39;accesso dei membri:** un&#39;identità [!DNL Google] consentita dal pubblico dell&#39;app OAuth e con i ruoli IAM richiesti.

Conoscere l&#39;ID del progetto di query e i set di dati che i membri devono leggere. Il progetto di query esegue i processi di query e ne paga il costo. I dati possono risiedere in un progetto diverso e anche il client OAuth può appartenere a un progetto separato. Per un progetto pilota, un progetto può contenere il client OAuth, i processi di query e i set di dati.

## Prepara [!DNL Google Cloud] {#prepare-google-cloud}

Prima di configurare il connettore in Collaborator, preparare l&#39;accesso al progetto e ai membri in [!DNL Google Cloud]. La creazione dell’app OAuth e la concessione dell’accesso ai dati sono attività separate. I membri che utilizzano il connettore non hanno bisogno dell’autorizzazione per modificare l’app OAuth.

### Prepara il progetto di query {#prepare-query-project}

Un amministratore [!DNL Google Cloud] prepara il progetto che esegue i processi di query:

1. Nella [console Google Cloud](https://console.cloud.google.com/), seleziona o crea un progetto.
1. Abilitare l&#39;API [!DNL BigQuery], se non è già abilitata. L&#39;abilitazione dell&#39;API abilita anche il server MCP remoto [!DNL BigQuery].
1. Scegli la fatturazione o la [sandbox BigQuery](https://docs.cloud.google.com/bigquery/docs/sandbox), quindi imposta le [quote di query personalizzate](https://docs.cloud.google.com/bigquery/docs/custom-quotas) giornaliere appropriate nel progetto di query.

>[!IMPORTANT]
>
>Le query di sola lettura possono comunque comportare costi aggiuntivi. I costi di [!DNL BigQuery] dipendono dai byte analizzati da una query, non dal numero di righe restituite. Una clausola `LIMIT` controlla le righe restituite, ma in genere non riduce i byte analizzati. Utilizzare esecuzioni a secco, colonne esplicite, filtri di partizione e quote di query giornaliere per controllare i costi.

Per ulteriori informazioni, vedere [Utilizzare il server MCP remoto BigQuery](https://docs.cloud.google.com/bigquery/docs/use-bigquery-mcp) nella documentazione di [!DNL Google Cloud].

### Concedi ruoli IAM {#grant-iam-roles}

Concedi i seguenti ruoli alle identità [!DNL Google] dei membri. Se possibile, utilizza un gruppo gestito e preferisci l’accesso ai dati a livello di set di dati.

| Ruolo | Dove concederlo | Scopo |
| --- | --- | --- |
| [!UICONTROL Utente strumento MCP] (`roles/mcp.toolUser`) | Progetti utilizzati per le chiamate MCP | Effettuare chiamate allo strumento MCP. |
| [!UICONTROL Utente processo BigQuery] (`roles/bigquery.jobUser`) | Il progetto di query | Eseguire processi di query. |
| [!UICONTROL Visualizzatore dati BigQuery] (`roles/bigquery.dataViewer`) | I set di dati o i progetti di dati autorizzati | Lettura di dati e metadati. |

Non concedere a [!UICONTROL BigQuery Data Editor], [!UICONTROL BigQuery Data Owner] o [!UICONTROL BigQuery Admin] solo l&#39;utilizzo di questo connettore di sola lettura. Come ulteriore misura di salvaguardia, prendere in considerazione un [criterio di negazione per gli strumenti MCP in lettura-scrittura](https://docs.cloud.google.com/mcp/prevent-read-write-tool-use). Chiedere all&#39;amministratore di [!DNL Google Cloud] di rivedere prima l&#39;ambito del criterio di negazione, in quanto può influire su altri client e servizi MCP [!DNL Google]. Per ulteriori informazioni, consulta [Ruoli e autorizzazioni IAM BigQuery](https://docs.cloud.google.com/bigquery/docs/access-control).

## Configurare il connettore per l’organizzazione {#configure-organization}

Gli amministratori rendono il connettore [!DNL Google BigQuery] disponibile a tutti gli utenti dell&#39;organizzazione. Le modifiche apportate alla pagina dell’organizzazione vengono applicate a tutti gli utenti dell’organizzazione.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Organizzazione]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Nella scheda **[!UICONTROL Google BigQuery]**, seleziona **[!UICONTROL Configura]**.

   Se il connettore è già configurato, la scheda mostra invece **[!UICONTROL Visualizza configurazione]**.

1. Nella finestra di dialogo **[!UICONTROL Configura BigQuery Google per l&#39;organizzazione]**, copia il **[!UICONTROL URL di reindirizzamento]** in **[!UICONTROL Applicazione Google]**.

   L’URL di reindirizzamento varia tra ambienti e aree geografiche, pertanto copia sempre il valore esatto dalla finestra di dialogo. Non utilizzare l&#39;URL della pagina del Collaboratore nel browser o l&#39;URL del server MCP [!DNL BigQuery]. Se un client OAuth serve più ambienti, registra separatamente ogni URL di reindirizzamento richiesto.

1. In [Google Auth Platform](https://console.cloud.google.com/auth/overview), prepara il client OAuth della tua organizzazione:

   1. Configura **[!UICONTROL Branding]** e **[!UICONTROL Pubblico]**. Per un’app esterna in fase di test, aggiungi i membri desiderati come utenti di test. Completare i requisiti di pubblicazione e verifica di [!DNL Google] prima di un utilizzo più ampio.
   1. In **[!UICONTROL Accesso ai dati]**, aggiungere l&#39;ambito `https://www.googleapis.com/auth/bigquery`.
   1. In **[!UICONTROL Client]**, creare o selezionare un client OAuth con il tipo di applicazione **[!UICONTROL Applicazione Web]**.
   1. Aggiungere l&#39;URL di reindirizzamento copiato in **[!UICONTROL URI di reindirizzamento autorizzati]**.
   1. Ottieni il **[!UICONTROL ID client]** e il **[!UICONTROL segreto client]** tramite il processo di gestione dei segreti approvato della tua organizzazione.

   I membri autorizzano questa app di proprietà della tua organizzazione, non un&#39;app fornita da Adobe. Mantieni il client segreto fuori da schermate, chat e documentazione.

1. In **[!UICONTROL Da cui provengono le credenziali]**, selezionare una delle opzioni seguenti:

   * **[!UICONTROL Immetti nuovo]:** Immetti **[!UICONTROL ID client Google OAuth]** e **[!UICONTROL Segreto client Google OAuth]**. I valori immessi vengono memorizzati come segreti dell&#39;organizzazione.
   * **[!UICONTROL Usa un segreto esistente]:** Seleziona i segreti organizzazione salvati che contengono l&#39;ID client e il segreto client.

   Non utilizzare segreti personali per un connettore organizzazione.

   ![Configura BigQuery Google per la finestra di dialogo dell&#39;organizzazione che mostra la sezione dei dettagli della connessione con un URL reindirizzato e i campi delle credenziali, tutti e sette gli strumenti Esplora e Query selezionati e le tre notifiche di accesso e autorizzazioni.](./assets/google-bigquery/org-configure.png){width="500" zoomable="yes"}

1. Espandere il gruppo di strumenti **[!UICONTROL Esplora ed esegui query]**. Mantenere selezionati tutti e sette gli strumenti o selezionare solo gli strumenti necessari ai membri. È necessario selezionare almeno uno strumento. Per ulteriori informazioni, vedere [Strumenti disponibili](#available-tools).

   Rivedi gli avvisi in **[!UICONTROL Accesso e autorizzazioni]**:

   * **[!UICONTROL Strumenti di sola lettura]:** L&#39;ambito OAuth è ampio e non impedisce di apportare modifiche. Mantieni i ruoli IAM dei membri di sola lettura.
   * **[!UICONTROL Le query di sola lettura possono comportare costi]:** Utilizzare esecuzioni a secco e quote di query. Una clausola `LIMIT` controlla le righe restituite, non necessariamente i byte analizzati.
   * **[!UICONTROL Ogni persona effettua l&#39;accesso separatamente]:** Ogni membro ha bisogno dei ruoli IAM richiesti.

   Seleziona **[!UICONTROL Salva connessione]**. La scheda organizzazione mostra **[!UICONTROL Configurazione salvata]** e **[!UICONTROL Configurazione vista]**.

Il salvataggio della configurazione non comporta l&#39;accesso a te o a un membro a [!DNL Google]. Inoltre, il salvataggio non conferma che tutti possano eseguire query su un set di dati. Per utilizzare il connettore, seguire i passaggi descritti in [Accedi come membro](#sign-in-as-a-member).

### Strumenti disponibili {#available-tools}

Il connettore [!DNL Google BigQuery] fornisce i seguenti strumenti di sola lettura:

| Strumento | Descrizione |
| --- | --- |
| `list_dataset_ids` | Elencare i set di dati in un progetto specificato. |
| `get_dataset_info` | Leggi i metadati di un set di dati. |
| `list_table_ids` | Elencare le tabelle e le viste in un set di dati. |
| `get_table_info` | Leggi lo schema e i metadati di una tabella. |
| `execute_sql_readonly` | Eseguire query SQL di sola lettura o un&#39;esecuzione di prova per stimare i byte analizzati da una query. |
| `get_query_results` | Recuperare i risultati di una query o controllare una query a esecuzione prolungata. |
| `get_job` | Controllare lo stato, gli errori e le statistiche di un processo di query. |

Per i flussi di lavoro di query, mantieni `execute_sql_readonly`, `get_query_results` e `get_job` selezionati insieme, in modo che Coworker possa seguire un processo di query a esecuzione prolungata. Collaboratore non offre gli strumenti `execute_sql` e `cancel_job` dal server MCP [!DNL BigQuery]. Gli strumenti aggiunti da [!DNL Google] al server in un secondo momento non vengono attivati automaticamente. Per informazioni dettagliate sullo strumento, vedi [Riferimento MCP BigQuery](https://docs.cloud.google.com/bigquery/docs/reference/mcp).

Quando utilizzate gli strumenti, tenete presenti i seguenti limiti:

* [!DNL Google] documenta un limite di 3.000 righe per i risultati delle query e un timeout predefinito di tre minuti. Non utilizzare il connettore per esportare tabelle complete.
* Gli strumenti non possono elencare i progetti. Nella richiesta, specifica un ID progetto noto.
* SQL di sola lettura non supporta istruzioni che modificano dati o risorse o query in [!DNL Google Drive] tabelle esterne.
* Nella chat possono essere visualizzati i risultati della query, gli schemi, gli elenchi di accesso ai set di dati e le istruzioni SQL. Assicurati che l’accesso segua i criteri di gestione dei dati della tua organizzazione.

## Accedi come membro {#sign-in-as-a-member}

Dopo che un amministratore ha configurato il connettore, ogni membro accede con il proprio account [!DNL Google]. Non è necessario il segreto client OAuth per accedere.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Utente]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Nella scheda **[!UICONTROL Google BigQuery]**, che mostra **[!UICONTROL Accesso non effettuato]**, seleziona **[!UICONTROL Accesso]**.

   Se la scheda indica che un amministratore deve configurare il connettore, chiedere all&#39;amministratore di [configurare il connettore](#configure-organization).

1. Nella schermata [!DNL Google] **[!UICONTROL Scegli un account]**, seleziona l&#39;account con l&#39;accesso IAM richiesto oppure seleziona **[!UICONTROL Usa un altro account]**. Quindi completa tutti i passaggi di accesso richiesti dalla tua organizzazione, ad esempio Single Sign-On (SSO) o Multi-Factor Authentication (MFA).

   Questo account può essere diverso da quello utilizzato per Collaboratore.

   ![Google Scegliere una schermata dell&#39;account con tre account eliminati e l&#39;opzione Usa un altro account.](./assets/google-bigquery/member-choose-account.png){width="500" zoomable="yes"}

1. Se [!DNL Google] mostra **[!UICONTROL Google non ha verificato questa app]**, conferma l&#39;app e il relativo proprietario con l&#39;amministratore. Continua solo se i criteri dell&#39;organizzazione per le app di prova lo consentono. In caso contrario, seleziona **[!UICONTROL Torna alla sicurezza]** e chiedi al proprietario dell&#39;app di risolvere i requisiti di pubblico, pubblicazione o verifica.

   ![Google non ha verificato l&#39;avviso relativo all&#39;app con un&#39;e-mail del proprietario dell&#39;app, un collegamento Avanzato e un pulsante Torna a protezione.](./assets/google-bigquery/member-unverified-app.png){width="500" zoomable="yes"}

   Nella schermata di consenso, controlla il nome dell’app e l’accesso richiesto. Quindi seleziona **[!UICONTROL Continua]** per completare il flusso di consenso [!DNL Google].

   [!DNL Google] richiede l&#39;autorizzazione per visualizzare e gestire i tuoi dati di [!DNL BigQuery] e per visualizzare l&#39;indirizzo di posta elettronica del tuo account di [!DNL Google]. Questo è l&#39;ambito [!DNL BigQuery] standard, anche se Coworker offre solo strumenti di sola lettura.

   Nelle schermate, l’app si chiama adobe.io. L’app dell’organizzazione mostra il proprio nome. Questo nome non significa che Adobe fornisca l’app OAuth.

   >[!IMPORTANT]
   >
   >Continua solo se riconosci l’app e l’organizzazione approva l’accesso richiesto.

   ![Schermata di consenso di Google in cui un&#39;app di esempio denominata adobe.io richiede l&#39;accesso per visualizzare e gestire i dati in Google BigQuery, con un avviso di app non verificata, un account con stato di errore e i pulsanti Annulla e Continua.](./assets/google-bigquery/member-consent.png){width="500" zoomable="yes"}

1. Torna a Collaboratore, quindi controlla **[!UICONTROL Strumenti abilitati dall&#39;amministratore]** nei dettagli del connettore. I membri possono visualizzare gli strumenti, ma non possono modificarne la selezione. Per verificare la connessione, selezionare **[!UICONTROL Test]**.

   ![dettagli del connettore google-bigquery per un membro, con uno stato Connesso, l&#39;origine, il metodo di autenticazione, il timeout dello strumento, una connessione Firmato con i pulsanti degli strumenti Disconnetti e Ricarica e un messaggio di chiusura della connessione e i primi strumenti attivati dall&#39;amministratore.](./assets/google-bigquery/member-details.png){width="700" zoomable="yes"}

Se l’accesso, il test o l’elenco di strumenti è stato completato correttamente, non viene confermato che è possibile eseguire query su un set di dati specifico. Per confermare l&#39;accesso, [verifica l&#39;accesso BigQuery](#check-bigquery-access). Se Collaboratore dice che la connessione è terminata, effettua di nuovo l&#39;accesso.

## Controlla l&#39;accesso a [!DNL BigQuery] {#check-bigquery-access}

Per confermare che puoi leggere i tuoi dati, avvia una nuova chat e immetti un prompt di sola lettura. Sostituire i segnaposto con progetti e tabelle a cui può accedere l&#39;identità [!DNL Google].

Esempio di prompt:

* &quot;Elencare i set di dati nel progetto `YOUR_PROJECT_ID`.&quot;
* &quot;Utilizzando `YOUR_QUERY_PROJECT_ID` per i processi di query, controllare lo schema di `YOUR_DATA_PROJECT.YOUR_DATASET.YOUR_TABLE`, stimare l&#39;analisi con un&#39;esecuzione in prova, quindi restituire un riepilogo aggregato.&quot;

Conferma che i risultati includano i set di dati o i dati previsti. Preferisci colonne esplicite, aggregati e filtri di partizione alle richieste di contenuti non elaborati. La denominazione di un progetto in una richiesta non modifica l’identità di accesso o non ti concede l’accesso a tale progetto.

## Risolvere i problemi di accesso {#troubleshoot-access}

Se l&#39;accesso o l&#39;accesso non riesce, verifica quanto segue con il tuo amministratore:

| Problema | Cosa controllare |
| --- | --- |
| La scheda indica che il connettore non è configurato o che un amministratore deve configurarlo | La configurazione dell’organizzazione viene salvata per l’organizzazione attiva. |
| `redirect_uri_mismatch` | L&#39;**[!UICONTROL URL di reindirizzamento]** esatto dalla finestra di dialogo di Coworker è registrato in **[!UICONTROL URI di reindirizzamento autorizzati]** nel client dell&#39;applicazione Web. |
| `invalid_client` | L’ID client e il segreto client appartengono al client dell’applicazione web e i segreti dell’organizzazione selezionati sono corretti. |
| `access_denied` o un avviso che [!DNL Google] non ha verificato l&#39;app | Il proprietario dell’app controlla il pubblico, l’idoneità degli utenti di prova e lo stato di verifica. Non approvare un&#39;app non riconosciuta. |
| Connessione terminata o token scaduto | Accedi di nuovo come membro. |
| Autorizzazione negata per `mcp.tools.call` | Il ruolo [!UICONTROL Utente dello strumento MCP] ed eventuali criteri di negazione IAM applicabili. |
| Autorizzazione negata per `bigquery.jobs.create` | Il ruolo [!UICONTROL Utente processo BigQuery] nel progetto di query. |
| Accesso negato per una tabella | Il ruolo [!UICONTROL Visualizzatore dati BigQuery] nel set di dati e l&#39;account [!DNL Google] con cui hai effettuato l&#39;accesso. |
| `SERVICE_DISABLED` | L&#39;API [!DNL BigQuery] è abilitata nel progetto identificato dall&#39;errore. |
| È stata superata la quota di query giornaliera | Quota di query del progetto, con l&#39;amministratore del progetto. |
| Richiesta di inserimento, aggiornamento, eliminazione, creazione o eliminazione di dati non riuscita | Il connettore è di sola lettura e non supporta modifiche ai dati o alle risorse. |

Quando contatti il supporto, non condividere segreti client, token di accesso, codici di autorizzazione o dati dei clienti.
