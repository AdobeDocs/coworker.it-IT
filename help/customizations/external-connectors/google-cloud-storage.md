---
title: Connettore esterno archiviazione Google Cloud
description: Scopri come configurare il connettore esterno Google Cloud Storage in CX Enterprise Coworker con la tua app Google OAuth e come accedere per leggere i dati del bucket in chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Questo connettore è in versione beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 70782269f48e3ff87ca95a1341ee74b02da1d7f4
workflow-type: tm+mt
source-wordcount: '2408'
ht-degree: 1%
---

# Connettore esterno Google Cloud Storage {#google-cloud-storage}

Utilizza il connettore esterno [!DNL Google Cloud Storage] per leggere i dati di [!DNL Cloud Storage] in Adobe CX Enterprise Coworker. Dopo aver configurato il connettore, chiedi a Collaboratore di elencare i bucket in un progetto noto, elencare gli oggetti per prefisso, esaminare i metadati di bucket e oggetti e leggere i file approvati. Il connettore è un server MCP ospitato da [!DNL Google].

>[!AVAILABILITY]
>
>Il connettore esterno [!DNL Google Cloud Storage] è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.

## Configurazione del connettore {#connector-configuration}

Il processo di configurazione del connettore è costituito da tre parti separate:

* Preparazione **[!DNL Google Cloud]:** Un amministratore [!DNL Google Cloud] prepara la fatturazione, l&#39;API [!DNL Cloud Storage] e i ruoli di Identity and Access Management (IAM) per i membri. L’amministratore prepara anche un client OAuth di proprietà della tua organizzazione.
* **Configurazione organizzazione:** Un amministratore di Coworker configura il connettore una sola volta per l&#39;intera organizzazione. L’amministratore registra l’URL di reindirizzamento di Collaborator, immette le credenziali del client OAuth e seleziona gli strumenti che i membri possono utilizzare.
* **Accesso membro:** Ogni membro effettua l&#39;accesso con il proprio account [!DNL Google]. I membri possono accedere solo ai bucket e agli oggetti consentiti da [!DNL Google Cloud] IAM per il proprio account.

Il connettore è di sola lettura. Richiede l&#39;ambito `https://www.googleapis.com/auth/devstorage.read_only` e offre solo strumenti di lettura. La tua organizzazione fornisce la propria applicazione OAuth [!DNL Google]. Non esiste alcuna applicazione OAuth gestita da Adobe per questo connettore.

Il salvataggio della configurazione dell&#39;organizzazione non comporta l&#39;accesso ad alcun membro né la concessione di autorizzazioni [!DNL Cloud Storage]. Ogni membro deve disporre già dell&#39;accesso IAM richiesto e deve effettuare l&#39;accesso separatamente.

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di disporre dei seguenti elementi:

* **Per la preparazione [!DNL Google Cloud]:** un progetto con fatturazione e API [!DNL Cloud Storage] abilitate, bucket che contengono dati approvati, concessioni IAM per i membri e un client OAuth [!DNL Google] di tipo **[!UICONTROL applicazione Web]**.
* **Per la configurazione dell&#39;organizzazione:** un account con l&#39;autorizzazione per gestire i connettori dell&#39;organizzazione in Coworker. È inoltre necessario disporre dell&#39;ID client OAuth e del segreto client o dei segreti dell&#39;organizzazione esistenti che li contengono.
* **Per l&#39;accesso dei membri:** Un account [!DNL Google] consentito dal pubblico dell&#39;applicazione OAuth e da [!DNL Google Cloud] IAM.

Conoscere l&#39;ID progetto e i bucket che i membri intendono leggere. Il connettore non dispone di strumenti per elencare i progetti. Il client OAuth può appartenere a un progetto diverso dai bucket.

## Prepara Google Cloud {#prepare-google-cloud}

Prima di configurare il connettore in Collaborator, preparare il progetto [!DNL Google Cloud] e l&#39;accesso dei membri. Se l&#39;accesso a [!DNL Google] è riuscito, non vengono concesse le autorizzazioni di archiviazione.

### Preparare il progetto e IAM {#prepare-project-iam}

Un amministratore [!DNL Google Cloud] completa i seguenti passaggi:

1. Seleziona o crea un progetto nella [console Google Cloud](https://console.cloud.google.com/).
1. Collega un account di fatturazione per ogni progetto che contiene contenitori.

   L’accesso in sola lettura non è gratuito. Possono essere applicati costi di storage, funzionamento, recupero e rete. Per ulteriori informazioni, consulta [Prezzi archiviazione cloud](https://cloud.google.com/storage/pricing).

1. Abilita l&#39;**[!UICONTROL API di archiviazione cloud]** in ogni progetto rilevante. Se il client OAuth appartiene a un progetto separato, abilita anche l’API in tale progetto.
1. Concedere ai membri i ruoli con privilegi minimi nella tabella seguente. Preferisci un gruppo gestito a un singolo account.

| Ruolo | Dove concedere | Scopo |
| --- | --- | --- |
| [!UICONTROL Utente strumento MCP] (`roles/mcp.toolUser`) | Progetto utilizzato per le chiamate MCP | Effettuare chiamate allo strumento MCP (`mcp.tools.call`). |
| [!UICONTROL Visualizzatore bucket di archiviazione] (`roles/storage.bucketViewer`) o un ruolo di sola lettura personalizzato | Progetto contenente i bucket | Elencare i bucket e leggere i metadati del bucket (`storage.buckets.list` e `storage.buckets.get`). |
| [!UICONTROL Visualizzatore oggetti di archiviazione] (`roles/storage.objectViewer`) | Ogni bucket autorizzato o il progetto se i membri possono leggerne tutti i bucket | Elencare gli oggetti, leggere i metadati degli oggetti e leggere il contenuto degli oggetti (`storage.objects.list` e `storage.objects.get`). |

Non concedere a [!UICONTROL Amministratore archiviazione] solo bucket di elenco. I membri che non dispongono dell&#39;autorizzazione per elencare i bucket possono comunque leggere un bucket autorizzato quando forniscono il nome. Per ulteriori informazioni, vedere [Ruoli IAM di archiviazione cloud](https://docs.cloud.google.com/storage/docs/access-control/iam-roles) nella documentazione di [!DNL Google Cloud].

[!DNL Google] offre inoltre un criterio di negazione IAM facoltativo che blocca gli strumenti MCP di lettura-scrittura per altri client MCP. Il connettore di Collaborator utilizza già una selezione di strumenti di sola lettura e un ambito di sola lettura. Esaminare gli effetti a livello di progetto con l&#39;amministratore [!DNL Google Cloud] prima di applicare il criterio. Per ulteriori informazioni, vedere [Impedire l&#39;utilizzo dello strumento MCP di lettura/scrittura](https://docs.cloud.google.com/mcp/prevent-read-write-tool-use).

### Impostazioni della connessione {#connection-settings}

Il collaboratore utilizza le seguenti impostazioni di connessione. Questi valori non vengono immessi nella finestra di dialogo di impostazione.

| Impostazione | Valore |
| --- | --- |
| URL del server MCP | `https://storage.googleapis.com/storage/mcp` (solo endpoint globale) |
| Trasporto | HTTP semplificabile |
| Server di autorizzazione | `https://accounts.google.com/` |
| Ambito richiesto | `https://www.googleapis.com/auth/devstorage.read_only` |

Per ulteriori informazioni, vedere [Utilizzare il server MCP remoto di archiviazione cloud](https://docs.cloud.google.com/storage/docs/use-cloud-storage-mcp) e [Eseguire l&#39;autenticazione sui server MCP di Google](https://docs.cloud.google.com/mcp/authenticate-mcp) nella documentazione di [!DNL Google Cloud].

## Configurare il connettore per l’organizzazione {#configure-organization}

Gli amministratori rendono il connettore [!DNL Google Cloud Storage] disponibile a tutti gli utenti dell&#39;organizzazione. Le modifiche apportate alla pagina dell’organizzazione vengono applicate a tutti i membri dell’organizzazione.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Organizzazione]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Nella scheda **[!UICONTROL Google Cloud Storage]**, seleziona **[!UICONTROL Configura]**.

   Se il connettore è già configurato, apri invece la configurazione salvata.

1. Nella finestra di dialogo **[!UICONTROL Configura Google Cloud Storage per la tua organizzazione]**, in **[!UICONTROL La tua applicazione Google]**, copia l&#39;**[!UICONTROL URL di reindirizzamento]** completo.

   L’URL di reindirizzamento varia a seconda dell’ambiente e dell’area geografica. Copia sempre il valore esatto dalla finestra di dialogo. Non utilizzare l’URL della pagina del Collaboratore nel browser, l’URL del server MCP o un URL di reindirizzamento da un altro ambiente.

1. Prepara il client OAuth per l&#39;organizzazione nella [piattaforma Google Auth](https://console.cloud.google.com/auth/overview):

   1. Configura **[!UICONTROL Branding]** e **[!UICONTROL Pubblico]** per la tua organizzazione. Per un’app esterna in fase di test, aggiungi i membri desiderati come utenti di test. Completare i requisiti di pubblicazione e verifica di [!DNL Google] applicabili prima di un utilizzo più ampio.
   1. In **[!UICONTROL Accesso ai dati]**, includere l&#39;ambito `https://www.googleapis.com/auth/devstorage.read_only`. Il connettore non ha bisogno di ambiti di lettura-scrittura o di controllo completo.
   1. In **[!UICONTROL Client]**, creare o selezionare un client OAuth con **[!UICONTROL Tipo applicazione]** impostato su **[!UICONTROL Applicazione Web]**.
   1. Aggiungere l&#39;URL di reindirizzamento copiato in **[!UICONTROL URI di reindirizzamento autorizzati]**. Se un client serve più ambienti, registra l’URL di reindirizzamento di ciascun ambiente.
   1. Ottieni il **[!UICONTROL ID client]** e il **[!UICONTROL segreto client]** tramite il processo di gestione dei segreti approvato della tua organizzazione.

   I membri autorizzano questa applicazione OAuth di proprietà della tua organizzazione. Non inserire credenziali nelle chat, nei biglietti e nella documentazione.

1. In **[!UICONTROL Da cui provengono le credenziali]**, selezionare una delle opzioni seguenti:

   * **[!UICONTROL Immetti nuovo]:** Immetti **[!UICONTROL ID client Google OAuth]** e **[!UICONTROL Segreto client Google OAuth]**. I valori immessi vengono memorizzati come segreti dell&#39;organizzazione.
   * **[!UICONTROL Usa un segreto esistente]:** Seleziona i segreti organizzazione salvati che contengono l&#39;ID client e il segreto client.

   Non utilizzare segreti personali per un connettore organizzazione.

   ![Configura Google Cloud Storage per la tua organizzazione, la finestra di dialogo mostra un URL di reindirizzamento reindirizzato, le opzioni Enter new (Inserisci nuovo) e Use an existing secret (Utilizza un segreto esistente), i campi Google OAuth client ID (ID client OAuth) e client secret (Prima che le persone possano accedere).](./assets/google-cloud-storage/org-configure.png){width="500" zoomable="yes"}

1. Espandere **[!UICONTROL Sfoglia e leggi (5 di 5)]**. Mantenere selezionati tutti e cinque gli strumenti o selezionare solo gli strumenti necessari ai membri. È necessario selezionare almeno uno strumento. Per ulteriori informazioni, vedere [Strumenti disponibili](#available-tools).

   In **[!UICONTROL Accesso e autorizzazioni]**, controlla **[!UICONTROL Accesso in sola lettura]** e **[!UICONTROL Ogni persona firma separatamente]** avvisi. Quindi seleziona **[!UICONTROL Salva connessione]**.

   ![Sezione Strumenti disponibili per gli utenti con tutti e cinque gli strumenti Sfoglia e Leggi selezionati, seguiti dall&#39;accesso in sola lettura e da Ogni utente firma in avvisi separati.](./assets/google-cloud-storage/org-tools.png){width="500" zoomable="yes"}

1. Rivedi i dettagli del connettore **[!UICONTROL google-cloud-storage]** salvato.

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Source]** | URL del server MCP, `https://storage.googleapis.com/storage/mcp`. |
   | **[!UICONTROL Authentication]** | Metodo di autenticazione `google-cloud-storage_login`. |
   | **[!UICONTROL Connessione]** | Il tuo stato di accesso. |
   | **[!UICONTROL Strumenti]** | Strumenti selezionati per i membri, con **[!UICONTROL Seleziona tutti]** e **[!UICONTROL Cancella]** controlli e un conteggio degli strumenti selezionati. |

   ![Dettagli del connettore di archiviazione google-cloud salvati che mostrano l&#39;origine, il metodo di autenticazione, un collegamento Non connesso con un pulsante di accesso e cinque dei cinque strumenti selezionati.](./assets/google-cloud-storage/org-details.png){width="700" zoomable="yes"}

Lo stato **[!UICONTROL Non connesso]** nei dettagli del connettore fa riferimento alla tua connessione e non all&#39;organizzazione. Il salvataggio della configurazione dell’organizzazione non comporta l’accesso dell’utente o di alcun membro e non conferma l’accesso a un bucket. Per utilizzare il connettore, seguire i passaggi descritti in [Accedi come membro](#sign-in-as-a-member).

Per cambiare gli strumenti disponibili per i membri in un secondo momento, aggiornare la selezione nella pagina dei dettagli del connettore, quindi selezionare **[!UICONTROL Salva selezione strumento]**. I membri non possono modificare la selezione dello strumento.

Per interrompere l&#39;offerta del connettore all&#39;organizzazione, selezionare **[!UICONTROL Rimuovi]** nella pagina dei dettagli del connettore.

### Strumenti disponibili {#available-tools}

Il connettore [!DNL Google Cloud Storage] fornisce i seguenti strumenti di sola lettura nel gruppo **[!UICONTROL Sfoglia e leggi]**:

| Strumento | Descrizione | Autorizzazione necessaria |
| --- | --- | --- |
| `list_buckets` | Elencare i bucket in un progetto [!DNL Google Cloud] noto, con filtro dei prefissi e impaginazione. | `storage.buckets.list` sul progetto |
| `list_objects` | Elencare oggetti e prefissi in un bucket autorizzato. L&#39;elenco non è ricorsivo per impostazione predefinita. | `storage.objects.list` nel bucket |
| `get_bucket_metadata` | Leggi la configurazione del bucket, ad esempio posizione, classe di archiviazione, conservazione e controllo delle versioni. | `storage.buckets.get` |
| `get_object_metadata` | Leggi dimensioni dell’oggetto, tipo di contenuto, timestamp, generazione e metadati personalizzati. | `storage.objects.get` |
| `read_object` | Leggi testo o contenuti binari supportati, fino a 8 MB per oggetto. | `storage.objects.get` |

Ogni chiamata allo strumento richiede anche l&#39;autorizzazione `mcp.tools.call`, in genere tramite il ruolo [!UICONTROL Utente strumento MCP] nel progetto pertinente.

Il connettore non offre lo strumento `read_text` obsoleto o gli strumenti `write_text`, `create_bucket`, `delete_object` e `delete_bucket`. Non è possibile attivare gli strumenti di scrittura. Gli strumenti aggiunti da [!DNL Google] al server in seguito non diventano automaticamente disponibili, anche quando si selezionano tutti e cinque gli strumenti.

## Accedi come membro {#sign-in-as-a-member}

Dopo che un amministratore ha configurato il connettore, ogni membro accede con il proprio account [!DNL Google]. Non è necessario il segreto client OAuth per accedere.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Utente]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Nella scheda **[!UICONTROL Google Cloud Storage]**, seleziona **[!UICONTROL Accedi]**.

   Prima dell&#39;accesso, nella scheda viene visualizzato **[!UICONTROL Accesso non effettuato]**. Se nella scheda è visualizzato **[!UICONTROL Non configurato]**, chiedere all&#39;amministratore di [configurare il connettore](#configure-organization).

1. Nella schermata [!DNL Google] **[!UICONTROL Scegli un account]**, seleziona l&#39;account con l&#39;accesso IAM richiesto oppure seleziona **[!UICONTROL Usa un altro account]**. Completa tutti i passaggi di accesso richiesti dalla tua organizzazione, ad esempio Single Sign-On (SSO) o Multi-Factor Authentication (MFA).

   Questo account può essere diverso da quello utilizzato per Collaboratore.

   ![Google Scegliere una schermata dell&#39;account con account con account di cui è stato eseguito il redact e l&#39;opzione Usa un altro account.](./assets/google-cloud-storage/member-choose-account.png){width="500" zoomable="yes"}

1. Se [!DNL Google] mostra **[!UICONTROL Google non ha verificato questa app]**, conferma l&#39;app e il relativo proprietario con l&#39;amministratore.

   Se la tua organizzazione approva l&#39;utilizzo di questa app, seleziona **[!UICONTROL Continua]**. In caso contrario, seleziona **[!UICONTROL Torna alla sicurezza]** e chiedi al proprietario dell&#39;app di risolvere i requisiti di pubblico, pubblicazione o verifica.

   ![Schermata Google che indica che Google non ha verificato l&#39;app perché è in fase di test, con le opzioni Continua e Torna a protezione.](./assets/google-cloud-storage/member-unverified-app.png){width="500" zoomable="yes"}

   Rivedi il nome dell&#39;app e l&#39;accesso richiesto nella schermata di consenso, quindi seleziona **[!UICONTROL Continua]**. Il connettore richiede **[!UICONTROL Visualizza i dati in Google Cloud Storage]**, che corrisponde all&#39;ambito di sola lettura.

   Nelle schermate, l’app si chiama adobe.io. L’app dell’organizzazione mostra il proprio nome. Questo nome non significa che Adobe fornisca l’app OAuth.

   >[!IMPORTANT]
   >
   >Continua solo se riconosci l’app e l’organizzazione approva l’accesso richiesto.

   ![Schermata di consenso di Google in cui un&#39;app di esempio denominata adobe.io richiede l&#39;accesso per visualizzare i dati in Google Cloud Storage, con un account ridotto e i pulsanti Annulla e Continua.](./assets/google-cloud-storage/member-consent.png){width="500" zoomable="yes"}

1. Torna a Collaboratore e conferma che l’accesso è stato completato. Rivedi **[!UICONTROL Strumenti abilitati dall&#39;amministratore]** nei dettagli del connettore. Puoi utilizzare solo gli strumenti abilitati dall’amministratore.

Se la connessione termina o la sessione scade, accedi di nuovo. Quando un amministratore effettua l&#39;accesso, gli altri membri non vengono connessi.

## Controllare l’accesso al bucket {#check-bucket-access}

Se l’accesso o l’elenco di strumenti è stato completato correttamente, non viene confermato che è possibile accedere a un bucket specifico. [!DNL Google] non richiede l&#39;autenticazione per elencare gli strumenti del server. Per confermare l’accesso, avvia una nuova chat e immetti un prompt di sola lettura. Sostituisci i segnaposto con risorse approvate.

Esempio di prompt:

* &quot;Elencare i bucket nel progetto `YOUR_PROJECT_ID`.&quot;
* &quot;Elenca fino a 25 oggetti in `reports/` nel bucket `YOUR_BUCKET`. Controllare le dimensioni e il tipo di contenuto di `reports/example.txt`, quindi leggere i primi 4096 byte e riepilogarli.&quot;

Conferma che il risultato includa il bucket o l’oggetto previsto. Per elencare gli oggetti nei prefissi nidificati, richiedere esplicitamente un elenco ricorsivo. Controllare i metadati dell&#39;oggetto prima di leggere un oggetto.

## Limiti e gestione dei dati {#limits-data-handling}

Quando utilizzi il connettore, tieni presenti i limiti e le considerazioni seguenti sulla gestione dei dati:

* **ID progetto:** Specifica un ID progetto nella richiesta. Il connettore non può elencare i progetti.
* **Prefissi:** I prefissi degli oggetti sono nomi letterali, non cartelle reali. Le inserzioni non sono ricorsive per impostazione predefinita e restituiscono risultati nelle pagine.
* **Dimensioni pagina:** Una pagina elenco può contenere fino a 1.000 elementi. Utilizza una pagina di piccole dimensioni, ad esempio da 25 a 100, e un prefisso stretto.
* **Dimensione oggetto:** La dimensione massima dell&#39;oggetto per una lettura è di 8 MB. La sola lettura di una parte di un oggetto più grande non supera questo limite. Il supporto per i file binari dipende dal modello e dal client.
* **Costi e quote:** è possibile applicare costi di archiviazione, richiesta, recupero e rete. [!DNL Google] applica anche le quote al server MCP. Per ulteriori informazioni, vedere [Quote MCP di archiviazione cloud](https://docs.cloud.google.com/storage/quotas#gcs-mcp).
* **Gestione dati:** Il contenuto, i nomi e i metadati personalizzati dell&#39;oggetto immettono la conversazione con il collaboratore. Utilizza solo dati approvati.
* **I registri di controllo:** [!DNL Cloud Storage] letture vengono visualizzati in [!DNL Cloud Audit Logs] solo quando i registri di accesso ai dati applicabili sono abilitati.

Il connettore non può caricare, sovrascrivere, creare o eliminare file o bucket. Non è inoltre possibile salvare i riepiloghi in [!DNL Cloud Storage].

## Risolvere i problemi di accesso {#troubleshoot-access}

Se l&#39;accesso o l&#39;accesso non riesce, verifica quanto segue con il tuo amministratore:

| Problema | Cosa controllare |
| --- | --- |
| La scheda mostra **[!UICONTROL Non configurato]** | Salva la connessione dell&#39;organizzazione attiva. |
| `redirect_uri_mismatch` | Registra l&#39;**[!UICONTROL URL di reindirizzamento]** esatto dalla finestra di dialogo di Coworker nel client OAuth **[!UICONTROL applicazione Web]**. |
| `invalid_client` | Controlla il tipo di client, l’ID client, il segreto client e i segreti dell’organizzazione selezionati. |
| `access_denied` o un avviso di app non verificato | Rivolgiti al proprietario dell’app per verificare il pubblico, l’idoneità degli utenti ai test e lo stato di verifica. Non approvare un&#39;app sconosciuta. |
| HTTP 401 o sessione terminata | Accedi di nuovo. |
| `mcp.tools.call` è negato | Controllare il ruolo [!UICONTROL Utente strumento MCP] ed eventuali criteri di negazione IAM applicabili. |
| L’elenco bucket è negato, ma un bucket noto è leggibile | Controllare l&#39;autorizzazione `storage.buckets.list` per il progetto. Le sole autorizzazioni degli oggetti non consentono di elencare i bucket in un progetto. |
| Metadati bucket negati | Verificare l&#39;autorizzazione `storage.buckets.get`. |
| Lettura o elenco oggetti negato | Controllare il ruolo [!UICONTROL Visualizzatore oggetti di archiviazione] nel bucket e l&#39;account [!DNL Google] con cui è stato eseguito l&#39;accesso. |
| `SERVICE_DISABLED` | Abilita l&#39;API [!DNL Cloud Storage] nel progetto denominato nell&#39;errore. |
| HTTP 403 che richiede la fatturazione | Verifica la fatturazione del progetto che contiene i bucket, incluso il progetto nella richiesta `list_buckets`. |
| `OutOfRange` in lettura | L&#39;oggetto supera il limite di 8 MB. Utilizza un’alternativa approvata all’esterno di questo connettore. |
| Manca uno strumento | Controlla la selezione dello strumento salvata dall’amministratore. Gli strumenti obsoleti e di scrittura non sono disponibili. |
| Una richiesta di caricamento, sovrascrittura, creazione o eliminazione non riesce | Il connettore è di sola lettura e non supporta queste azioni. |
