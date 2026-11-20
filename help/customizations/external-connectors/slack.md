---
title: Connettore esterno Slack
description: Scopri come configurare il connettore esterno Slack in CX Enterprise Coworker con la tua app Slack e come accedere per utilizzare le conversazioni Slack in chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Questo connettore è in versione beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 877954880bf6fda5151dcb343af92888db21cef4
workflow-type: tm+mt
source-wordcount: '2268'
ht-degree: 0%
---

# Connettore esterno Slack {#slack}

Utilizza il connettore esterno [!DNL Slack] per lavorare con le tue conversazioni di [!DNL Slack] in Adobe CX Enterprise Coworker. Dopo aver configurato il connettore, chiedi a Collaboratore di cercare messaggi e file, leggere i canali e i thread e trovare le persone. Puoi anche inviare messaggi e risposte, se l’amministratore abilita questi strumenti. Il connettore utilizza il server MCP (Model Context Protocol) remoto ufficiale ospitato da [!DNL Slack].

>[!AVAILABILITY]
>
>Il connettore esterno [!DNL Slack] è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.

## Configurazione del connettore {#connector-configuration}

Il processo di configurazione del connettore è costituito da tre parti separate:

* **[!DNL Slack]preparazione app:** Il proprietario di un&#39;app [!DNL Slack] prepara un&#39;app idonea, registra l&#39;URL di reindirizzamento di Coworker e imposta gli ambiti utente. Adobe non fornisce un&#39;app [!DNL Slack] gestita.
* **Configurazione organizzazione:** Un amministratore di Coworker configura il connettore una sola volta per l&#39;intera organizzazione. L’amministratore immette le credenziali dell’app e sceglie gli ambiti OAuth dell’utente e gli strumenti che i membri possono utilizzare.
* **Accesso membro:** Ogni membro effettua l&#39;accesso con il proprio account [!DNL Slack]. I membri possono accedere solo al contenuto a cui può accedere il loro account [!DNL Slack].

Il connettore non utilizza un bot condiviso o un&#39;identità [!DNL Slack] condivisa. Il collaboratore invia messaggi e risposte come membro che ha effettuato l&#39;accesso. Il salvataggio della configurazione dell&#39;organizzazione non comporta l&#39;accesso ad alcun membro né la concessione dell&#39;accesso [!DNL Slack] aggiuntivo. Ogni membro deve effettuare l&#39;accesso separatamente.

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di disporre dei seguenti elementi:

* **Accesso collaboratore:** account con autorizzazione per la gestione dei connettori organizzazione in un&#39;organizzazione in cui è disponibile il connettore [!DNL Slack].
* **Un&#39;app [!DNL Slack]:** Un&#39;app interna o un&#39;app [!DNL Slack Marketplace] approvata per la tua area di lavoro. È inoltre necessario un proprietario dell’app che possa confermare gli ambiti utente approvati e modificare le impostazioni dell’app.
* **Credenziali app:** l&#39;ID client e il segreto client dell&#39;app, condivisi tramite il processo approvato per la gestione delle credenziali.
* **Uno strumento e una decisione di ambito:** gli strumenti di lettura, messaggistica e bozza che l&#39;organizzazione intende abilitare e gli ambiti OAuth dell&#39;utente che intende richiedere.
* **Area di lavoro di prova o canale:** Luogo in cui verificare la connessione con i membri che accettano di verificarla. Non inviare messaggi di test nei canali del cliente o di produzione.

>[!IMPORTANT]
>
>Non condividere mai segreti client, token di accesso o altre credenziali in schermate, chat o ticket di supporto. Immettere le credenziali solo nei campi protetti della finestra di dialogo di configurazione.

## Preparare l’app Slack {#prepare-slack-app}

Prima di configurare il connettore in Collaborator, il proprietario dell&#39;app prepara l&#39;app [!DNL Slack]. Potrebbe essere necessario approvare anche un amministratore dell’app dell’area di lavoro o dell’organizzazione. Per i requisiti di [!DNL Slack], vedi [Server MCP Slack](https://docs.slack.dev/ai/slack-mcp-server/) nella documentazione per gli sviluppatori di [!DNL Slack].

### Scegli un’app idonea {#choose-eligible-app}

[!DNL Slack] supporta il proprio server MCP solo per le app e le applicazioni personalizzate interne pubblicate in [!DNL Slack Marketplace]. Le app non elencate distribuite all&#39;esterno dell&#39;organizzazione non possono utilizzare il server MCP [!DNL Slack]. L’attivazione della distribuzione pubblica da sola non rende idonea un’app.

1. Scegli l’area di lavoro o l’organizzazione proprietaria dell’app e il proprietario dell’app.
1. In [Gestione app Slack](https://api.slack.com/apps), crea una nuova app in tale area di lavoro. Per riutilizzare un’app idonea esistente, devi prima ottenere l’approvazione del relativo proprietario.
1. Nelle impostazioni dell&#39;app, seleziona **[!UICONTROL Informazioni di base]** > **[!UICONTROL Credenziali app]**. Nota l&#39;**[!UICONTROL ID client]** e il **[!UICONTROL Segreto client]**.

   Immetti solo questi due valori in Collaboratore. Non utilizzare l’ID app, il segreto di firma, un token bot o un token a livello di app.

### Registra l’URL di reindirizzamento {#register-redirect-url}

Registra l&#39;URL di reindirizzamento di Coworker nell&#39;app [!DNL Slack]:

1. In Coworker aprire la finestra di dialogo **[!UICONTROL Connetti Slack]**, come descritto in [Configurare il connettore per l&#39;organizzazione](#configure-organization). Copia il valore completo dell&#39;**[!UICONTROL URL di reindirizzamento]**.

   Puoi aprire la finestra di dialogo per copiare l’URL prima di completare o salvare la configurazione.

1. Nelle impostazioni dell&#39;app [!DNL Slack], seleziona **[!UICONTROL OAuth e autorizzazioni]**. In **[!UICONTROL URL di reindirizzamento]**, aggiungere l&#39;URL di reindirizzamento completo, quindi salvare.

Copia sempre l’URL di reindirizzamento dalla finestra di dialogo Collaboratore nell’ambiente che stai configurando. Registra lo schema esatto, il nome host, la porta, se presente, e il percorso. Non generare l’URL personalmente o non riutilizzare un URL di reindirizzamento da un altro ambiente. Se utilizzi più di un ambiente, registra separatamente ciascun URL di reindirizzamento.

### Impostare gli ambiti utente {#set-user-scopes}

Il connettore utilizza gli ambiti OAuth dell’utente, che autorizzano l’account di ciascun membro. Non utilizza ambiti bot.

1. Nelle impostazioni dell&#39;app [!DNL Slack], seleziona **[!UICONTROL OAuth e autorizzazioni]** > **[!UICONTROL Ambiti]** > **[!UICONTROL Ambiti token utente]**.
1. Aggiungi gli ambiti utente approvati dalla tua organizzazione. Confrontali con gli [ambiti predefiniti](#review-scopes) in Collaborator e aggiungi solo gli ambiti che intendi richiedere.

   Gli ambiti predefiniti sono il set di funzionalità predefinito di Coworker e non il minimo richiesto da [!DNL Slack]. Utilizzare gli ambiti `search:read.*` granulari, non l&#39;ambito `search:read` precedente. In un manifesto dell&#39;app, gli ambiti utente appartengono a `oauth_config.scopes.user`, non a `oauth_config.scopes.bot`.

L&#39;ambito utente `chat:write` consente a Collaboratore di inviare messaggi come membro connesso. Se la tua organizzazione non prevede di inviare messaggi, omettilo.

L&#39;area di lavoro o l&#39;organizzazione [!DNL Slack] Enterprise potrebbe richiedere l&#39;approvazione dell&#39;app e la revisione dell&#39;ambito. L&#39;approvazione dell&#39;app non sostituisce il consenso di ciascun membro. Un criterio che consente solo [!DNL Slack Marketplace] app può bloccare un&#39;app interna. Per ulteriori informazioni, consulta [Gestire l&#39;approvazione dell&#39;app per la tua area di lavoro](https://slack.com/help/articles/222386767-Manage-app-approval-for-your-workspace).

Se l&#39;app utilizza le restrizioni degli indirizzi IP consentite, [!DNL Slack] le applica anche alle richieste MCP. Contatta il tuo rappresentante Adobe per confermare gli indirizzi da consentire. Non indovinare gli intervalli di indirizzi IP. Alcune funzionalità, ad esempio la ricerca semantica, possono dipendere dal piano [!DNL Slack].

### Verifica impostazioni app irreversibili {#review-irreversible-settings}

Coworker si connette come client OAuth riservato con l’ID client e il segreto client. Alcune impostazioni dell&#39;app [!DNL Slack] non possono essere annullate. Prima di modificarle, esaminare quanto segue:

* **Proof Key for Code Exchange (PKCE):** Non attivare l&#39;impostazione PKCE [!DNL Slack] per questo connettore senza conferma. [!DNL Slack] documenta che questa impostazione cambia l&#39;app in un client pubblico e solo il supporto di [!DNL Slack] può annullarla. Per ulteriori informazioni, vedere [Utilizzo di PKCE](https://docs.slack.dev/authentication/using-pkce/).
* **Rotazione token:** La rotazione token [!DNL Slack] non può essere disattivata dopo l&#39;attivazione. Contatta il rappresentante Adobe prima di attivarla per questa app. Per ulteriori informazioni, vedere [Utilizzo della rotazione dei token](https://docs.slack.dev/authentication/using-token-rotation/).

### Funzioni bot non richieste {#bot-features-not-required}

Il connettore non necessita di funzionalità bot. Non sono necessari ambiti token bot, URL di richiesta [!DNL Events API], URL di richiesta interattività, webhook in ingresso, comandi barra, [!DNL Socket Mode] o token a livello di app. Se un’app esistente utilizza queste funzioni per un altro scopo, mantienile.

Il server MCP [!DNL Slack] non supporta la registrazione client dinamica o eventi inviati dal server (SSE). Collaboratore utilizza l’app registrata e il trasporto HTTP Streamable.

## Configurare il connettore per l’organizzazione {#configure-organization}

Gli amministratori rendono il connettore [!DNL Slack] disponibile a tutti gli utenti dell&#39;organizzazione. Le modifiche apportate alla pagina dell’organizzazione vengono applicate a tutti gli utenti dell’organizzazione. Completa [Prepara l&#39;app Slack](#prepare-slack-app) prima dell&#39;accesso dei membri.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Organizzazione]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Nella scheda **[!UICONTROL Slack]**, seleziona **[!UICONTROL Configura]**.

   Viene visualizzata la finestra di dialogo **[!UICONTROL Connetti Slack]**. Il connettore utilizza l&#39;URL fisso del server MCP [!DNL Slack], `https://mcp.slack.com/mcp`. Utilizza l’ambito dell’organizzazione per questa configurazione, non una connessione personale.

1. Verificare che l&#39;**[!UICONTROL URL di reindirizzamento]** in **[!UICONTROL applicazione Slack]** sia registrato nell&#39;app, come descritto in [Registrare l&#39;URL di reindirizzamento](#register-redirect-url). Quindi immetti **[!UICONTROL ID client]** e **[!UICONTROL Segreto client]** dell&#39;app. Entrambi i campi sono obbligatori.

   Non immettere l&#39;ID app, il segreto di firma o un token bot. Le credenziali vengono archiviate come segreti e non come impostazioni del connettore di testo normale.

   ![Finestra di dialogo Connetti Slack che mostra la sezione dell&#39;applicazione Slack con un URL reindirizzato, campi ID client e segreto client vuoti, gli ambiti OAuth utente predefiniti e i primi strumenti disponibili per gli utenti.](./assets/slack/org-configure.png){width="500" zoomable="yes"}

1. Rivedi gli **[!UICONTROL ambiti OAuth utente]**. Per ulteriori informazioni, consulta [Rivedere gli ambiti OAuth dell&#39;utente](#review-scopes).

1. In **[!UICONTROL Strumenti disponibili per gli utenti]**, rimuovere gli strumenti che i membri non devono utilizzare. Deve rimanere almeno uno strumento. Per ulteriori informazioni, vedere [Strumenti disponibili](#available-tools).

1. Rivedi **[!UICONTROL Accesso e autorizzazioni]**, quindi seleziona **[!UICONTROL Salva connessione]**. La scheda **[!UICONTROL Slack]** mostra **[!UICONTROL Configurazione salvata]**.

   La finestra di dialogo mostra anche il metodo **[!UICONTROL Authentication]**, il tipo **[!UICONTROL Connection]** e il timeout dello strumento **[!UICONTROL 5&rbrace;.]** Il collaboratore non salva la configurazione quando un campo delle credenziali o l’elenco degli ambiti è vuoto.

   Ricarica la pagina, seleziona **[!UICONTROL Visualizza configurazione]** e verifica che la configurazione e la selezione dello strumento siano state salvate prima dell&#39;accesso dei membri.

   ![Finestra di dialogo Connetti Slack che mostra gli ambiti OAuth dell&#39;utente, tutti i 16 strumenti disponibili per gli utenti, l&#39;avviso di accesso e autorizzazioni e le impostazioni di autenticazione OAuth, connessione HTTP e timeout dello strumento di 60 secondi.](./assets/slack/org-scopes-tools.png){width="500" zoomable="yes"}

Il salvataggio non comporta l&#39;accesso né per te né per alcun membro a [!DNL Slack]. Per verificare la connessione, accedere come utente, come descritto in [Accedere come membro](#sign-in-as-a-member).

### Rivedi gli ambiti OAuth dell&#39;utente {#review-scopes}

Il campo **[!UICONTROL Ambiti OAuth utente]** è obbligatorio. Separa gli ambiti con spazi o virgole e abbina gli ambiti utente approvati per la tua app. Per impostazione predefinita, il campo contiene i seguenti 22 ambiti:

```text
search:read.public search:read.private search:read.im search:read.mpim search:read.files search:read.users channels:history groups:history im:history mpim:history channels:read groups:read im:read mpim:read users:read users:read.email files:read canvases:read lists:read emoji:read reactions:read chat:write
```

L&#39;area di lavoro potrebbe non approvare tutti gli ambiti predefiniti. Rivedi gli ambiti richiesti con il proprietario dell’app.

>[!IMPORTANT]
>
>Gli ambiti predefiniti includono contenuto privato, ad esempio canali privati, messaggi di gruppo e messaggi diretti. Includono anche `chat:write`, che consente a Coworker di inviare messaggi e risposte come membro che ha effettuato l&#39;accesso. Decidi esplicitamente se l’organizzazione abilita gli strumenti di invio dei messaggi. La rimozione di uno strumento non ne rimuove gli ambiti OAuth. Se non si desidera che i membri inviino messaggi, rimuovere lo strumento `slack_send_message` e l&#39;ambito `chat:write`.

La selezione dello strumento e gli ambiti OAuth sono indipendenti. Quando restringi l’accesso, controlla sia l’elenco degli strumenti che il campo ambito. Uno strumento abilitato non concede a un membro un accesso [!DNL Slack] superiore a quello del suo account.

### Strumenti disponibili {#available-tools}

Il connettore [!DNL Slack] fornisce i seguenti 16 strumenti. Per impostazione predefinita, tutti i membri sono disponibili.

| Funzionalità | Strumento |
| --- | --- |
| Ricerca | `slack_search_public` |
| Ricerca | `slack_search_public_and_private` |
| Ricerca | `slack_search_channels` |
| Ricerca | `slack_search_users` |
| Leggi conversazioni | `slack_read_channel` |
| Leggi conversazioni | `slack_read_thread` |
| Leggi conversazioni | `slack_list_channel_members` |
| Leggi conversazioni | `slack_list_user_channels` |
| Lettura di contenuti e profili | `slack_read_canvas` |
| Lettura di contenuti e profili | `slack_read_user_profile` |
| Lettura di contenuti e profili | `slack_read_file` |
| Lettura di contenuti e profili | `slack_read_list` |
| Emoji e reazioni | `slack_search_emojis` |
| Emoji e reazioni | `slack_get_reactions` |
| Messaggi e bozze | `slack_send_message` |
| Messaggi e bozze | `slack_send_message_draft` |

Il connettore non è di sola lettura. I membri possono inviare messaggi e risposte se non si rimuove lo strumento `slack_send_message`. Non sono incluse la creazione di canali, i messaggi pianificati, i caricamenti di file, l’aggiunta di reazioni e le modifiche all’area di lavoro o all’elenco.

## Accedi come membro {#sign-in-as-a-member}

Dopo che un amministratore ha configurato il connettore, ogni membro accede con il proprio account [!DNL Slack]. Non è necessario il segreto client per accedere.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Utente]**, quindi seleziona **[!UICONTROL Connettori esterni]**.

1. Trova la scheda **[!UICONTROL Slack]**. Se nella scheda è visualizzato **[!UICONTROL Non configurato]** e **[!UICONTROL Non ancora disponibile. L&#39;amministratore deve configurarlo.]**, chiedi all&#39;amministratore di [configurare il connettore](#configure-organization).

   Non chiedere o copiare il segreto client dell’organizzazione.

1. Dopo che l&#39;amministratore ha configurato il connettore, nella scheda **[!UICONTROL Slack]** è visualizzato **[!UICONTROL Accesso richiesto]**. Seleziona **[!UICONTROL Accedi]** sulla scheda.

   Puoi anche aprire i dettagli del connettore **[!UICONTROL Slack]**. Prima dell&#39;accesso, nella sezione **[!UICONTROL Connessione]** è visualizzato **[!UICONTROL Accesso non effettuato]**, con un pulsante **[!UICONTROL Accesso]**.

   ![Dettagli del connettore Slack per un membro, con lo stato richiesto per l&#39;accesso, il pulsante Verifica connessione, l&#39;URL del server, l&#39;accesso di ogni utente, la connessione Non effettuato con un pulsante di accesso e gli strumenti abilitati dall&#39;amministratore.](./assets/slack/member-details.png){width="700" zoomable="yes"}

1. Completa l&#39;autorizzazione [!DNL Slack] con l&#39;account [!DNL Slack] e l&#39;area di lavoro che intendi utilizzare. Esamina le autorizzazioni richieste ed eventuali requisiti di approvazione dell’area di lavoro.

   >[!IMPORTANT]
   >
   >Continua solo se riconosci l’app e l’organizzazione approva l’accesso richiesto.

1. Torna a Collaboratore e controlla lo stato della connessione. Seleziona **[!UICONTROL Verifica connessione]**, quindi [verifica l&#39;accesso a Slack](#check-access) prima di utilizzare la connessione.

1. Rivedi attentamente le azioni di messaggistica. Il collaboratore invia messaggi e risposte come account [!DNL Slack].

In qualità di membro, è possibile verificare la connessione o disconnettersi, ma non modificare le impostazioni dell&#39;organizzazione. È possibile accedere solo al contenuto consentito da [!DNL Slack] e dagli ambiti concessi. Questo contenuto include conversazioni private solo quando il tuo account [!DNL Slack] può accedervi.

Per disconnettere l&#39;account [!DNL Slack] dal connettore, selezionare **[!UICONTROL Esci]**.

## Verifica l’accesso a Slack {#check-access}

Per confermare che il connettore può leggere il contenuto di [!DNL Slack], avviare una chat e immettere un prompt di sola lettura. Verificare che l&#39;amministratore abbia abilitato lo strumento `slack_list_user_channels`.

Esempio di prompt:

* &quot;Con Slack, elenca fino a cinque canali a cui appartengo. Mostra solo i nomi dei canali. Non inviare messaggi, non creare bozze e non modificare nulla.&quot;

Se la tua organizzazione abilita gli strumenti di messaggistica, verifica l’invio solo in un canale riservato ai test e con l’approvazione. Chiedere a un secondo membro di accedere separatamente e confermare che ogni membro visualizzi solo il proprio contenuto [!DNL Slack].

## Risolvere i problemi di accesso {#troubleshoot-access}

Se la configurazione, l’accesso o l’accesso non riescono, verifica quanto segue con il tuo amministratore:

| Problema | Cosa controllare |
| --- | --- |
| Impossibile salvare la configurazione | Immetti sia l&#39;ID client che il segreto client, mantieni almeno un ambito OAuth utente e mantieni almeno uno strumento. Non immettere un ID app, un segreto di firma o un token bot. |
| **[!UICONTROL URL di reindirizzamento]** mancante oppure [!DNL Slack] segnala una mancata corrispondenza di reindirizzamento | Confrontare l&#39;URL di reindirizzamento completo dalla finestra di dialogo di Collaborator, inclusi schema, host, porta e percorso, con gli **[!UICONTROL URL di reindirizzamento]** salvati nell&#39;app [!DNL Slack]. Se l’URL non è presente o se i valori sono diversi, contatta il rappresentante Adobe. |
| [!DNL Slack] accesso o richieste non riuscite | Controllare l&#39;approvazione dell&#39;app, gli ambiti utente concessi, l&#39;account e l&#39;area di lavoro [!DNL Slack] con cui hai effettuato l&#39;accesso ed eventuali restrizioni di indirizzi IP per l&#39;app. Se le richieste continuano a non riuscire, esci e accedi di nuovo. |
| Azione di lettura o invio non disponibile | Controllare la selezione dello strumento dell&#39;organizzazione, gli ambiti richiesti e concessi e le autorizzazioni [!DNL Slack] del membro. Queste impostazioni sono indipendenti. |
| Un membro non può modificare le impostazioni dell&#39;app | Questo comportamento è previsto per una connessione gestita dall’organizzazione. Chiedi all’amministratore. I membri non immettono mai il segreto client dell’organizzazione. |
