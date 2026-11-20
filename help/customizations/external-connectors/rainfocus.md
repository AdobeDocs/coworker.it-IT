---
title: Connettore esterno RainFocus
description: Scopri come impostare il connettore esterno RainFocus in CX Enterprise Coworker per la tua organizzazione e come accedere con RainFocus per utilizzare gli strumenti per i dati evento in chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Questo connettore è in versione beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: e65f811f1e9c27de372ce924301b68f20ab9c1a6
workflow-type: tm+mt
source-wordcount: '2116'
ht-degree: 0%
---

# Connettore esterno RainFocus {#rainfocus}

Utilizza il connettore esterno [!DNL RainFocus] per lavorare con i dati dell&#39;evento [!DNL RainFocus] in Adobe CX Enterprise Coworker. Dopo aver configurato il connettore, chiedere a Collaboratore informazioni sulle sessioni, i partecipanti e gli attributi personalizzati a cui l&#39;account [!DNL RainFocus] può accedere. Il connettore utilizza un profilo MCP [!DNL RainFocus], un server MCP (Model Context Protocol) ospitato da [!DNL RainFocus].

>[!AVAILABILITY]
>
>Il connettore esterno [!DNL RainFocus] è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.

## Configurazione del connettore {#connector-configuration}

Il processo di configurazione del connettore è costituito da tre parti separate:

* Preparazione **[!DNL RainFocus]:** Un amministratore [!DNL RainFocus] esegue il provisioning di un profilo MCP, abilita i relativi strumenti e fornisce l&#39;URL del profilo. Ogni membro ha bisogno di un account [!DNL RainFocus] con il ruolo corretto.
* **Configurazione organizzazione:** L&#39;URL del profilo MCP viene salvato dall&#39;amministratore di un collaboratore una sola volta per l&#39;intera organizzazione. Il connettore abilita un elenco fisso di strumenti di lettura.
* **Accesso membro:** Ogni membro effettua l&#39;accesso con il proprio account [!DNL RainFocus]. I membri possono accedere solo ai dati consentiti dal loro ruolo [!DNL RainFocus] e dal profilo.

Il salvataggio della configurazione dell&#39;organizzazione non comporta l&#39;accesso ad alcun membro, la concessione di autorizzazioni [!DNL RainFocus] o l&#39;esecuzione di uno strumento dati [!DNL RainFocus]. Ogni membro deve effettuare l&#39;accesso separatamente.

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di disporre dei seguenti elementi:

* **Accesso collaboratore:** account amministratore collaboratore con impostazioni di organizzazione attivate, in un&#39;organizzazione in cui è disponibile il connettore [!DNL RainFocus].
* **Un profilo MCP:** Un profilo MCP [!DNL RainFocus] con provisioning e relativo URL di profilo HTTPS completo, fornito dall&#39;amministratore [!DNL RainFocus]. Per ulteriori informazioni, vedere [Ottenere l&#39;URL del profilo MCP](#get-profile-url).
* **Account membri:** Per ogni membro, un account [!DNL RainFocus] con un ruolo di protezione che consente di accedere ai dati necessari.

Non puoi immettere un ID client, un segreto client o un token di accesso in Collaborator. Ogni membro accede a [!DNL RainFocus] con il proprio account.

## Prepara accesso [!DNL RainFocus] {#prepare-rainfocus}

Prima di configurare il connettore in Collaborator, preparare il profilo MCP e l&#39;accesso dei membri in [!DNL RainFocus]. [!DNL RainFocus] è il proprietario del profilo, degli strumenti abilitati, dei ruoli dei membri e di tutti gli addebiti. Cooker memorizza l’URL del profilo e l’elenco degli strumenti per la tua organizzazione, nonché l’accesso di ciascun membro.

### Ottieni l’URL del profilo MCP {#get-profile-url}

[!DNL RainFocus] in genere configura i profili MCP per i propri clienti in base ai loro requisiti. Se l&#39;amministratore di [!DNL RainFocus] configura il profilo, il processo è il seguente:

1. In [!DNL RainFocus], aprire **[!UICONTROL Integration Suite]** > **[!UICONTROL Active Profiles]** > **[!UICONTROL MCP Profiles]**, quindi creare un profilo.
1. Abilita solo gli strumenti necessari per il caso d’uso e lascia disattivati gli altri strumenti.
1. Copia l’URL del server MCP generato. L’URL è specifico per il profilo.

Assegna l’URL completo all’amministratore di Collaborator che configura il connettore. Non indovinare un nome di profilo o generare l’URL da solo. Per ulteriori informazioni, vedere l&#39;annuncio dei profili MCP di [RainFocus](https://www.rainfocus.com/company/news-press/rainfocus-launches-ai-agent-connectivity-for-event-data-with-mcp-profiles/).

### Conferma accesso membro {#confirm-member-access}

Ogni membro accede con il proprio account [!DNL RainFocus]. Il ruolo di protezione dell&#39;account e gli strumenti abilitati nel controllo profilo a cui un membro può accedere. Chiedere all&#39;amministratore di [!DNL RainFocus] di confermare che ogni membro dispone del ruolo con privilegi minimi per le proprie attività.

## Configurare il connettore per l’organizzazione {#configure-organization}

Gli amministratori rendono il connettore [!DNL RainFocus] disponibile a tutti gli utenti dell&#39;organizzazione. Le modifiche apportate alla pagina dell’organizzazione vengono applicate a tutti gli utenti dell’organizzazione. L&#39;ambito **[!UICONTROL Org]** viene visualizzato solo per gli amministratori con le impostazioni dell&#39;organizzazione attivate.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Organizzazione]**, quindi seleziona **[!UICONTROL Connettori esterni]**.
1. Trova la scheda **[!UICONTROL RainFocus]**, che ha un&#39;etichetta Beta e mostra **[!UICONTROL Non configurato]**. Seleziona **[!UICONTROL Configura]**.

1. Nella finestra di dialogo **[!UICONTROL Configura RainFocus]**, immetti l&#39;**[!UICONTROL URL del profilo di sviluppo]**. Utilizza l&#39;URL completo del profilo MCP fornito dall&#39;amministratore [!DNL RainFocus].

   L&#39;URL deve iniziare con `https://`. Non può contenere spazi, barre rovesciate, una stringa di query (`?`), un frammento (`#`), un nome utente o una password, una porta non predefinita o `.` o `..` segmenti di percorso. Se l’URL non corrisponde a una regola, in Collaboratore viene visualizzato un messaggio che descrive la regola. Collaboratore controlla solo il formato dell’URL. Non verifica l’esistenza del profilo o la possibilità di utilizzarlo.

1. Esaminare le sezioni **[!UICONTROL Accesso e autorizzazioni]** e **[!UICONTROL Strumento di lettura corretto di cui è stato eseguito il inserisco nell&#39;elenco Consentiti]**. Il connettore abilita tutti e 10 gli strumenti di lettura e non è possibile aggiungerli, rimuoverli o modificarli in questa finestra di dialogo. Alcuni strumenti restituiscono i dati personali dei partecipanti o le esportazioni in blocco. Per ulteriori informazioni, vedere [Strumenti disponibili](#available-tools).

   ![Imposta la finestra di dialogo RainFocus che mostra il campo URL del profilo di sviluppo vuoto, la sezione Accesso e autorizzazioni, l&#39;elenco Consentiti dello strumento di lettura fisso con 10 strumenti e il pulsante Salva connessione.](./assets/rainfocus/org-configure.png){width="500" zoomable="yes"}

1. Seleziona **[!UICONTROL Salva connessione]**. Quando la connessione viene salvata, non è possibile modificare o annullare il modulo.

Se il salvataggio non riesce, nella finestra di dialogo viene visualizzato **[!UICONTROL Impossibile salvare la connessione]** e viene mantenuto l&#39;URL immesso. Alcune impostazioni potrebbero essere salvate anche quando il salvataggio non riesce. Riapri la configurazione e controllane prima di riprovare. Per evitare modifiche in conflitto, accertarsi che il connettore sia configurato da un solo amministratore alla volta.

### Verifica la configurazione salvata {#verify-configuration}

Dopo aver salvato la connessione, verifica la configurazione:

1. Dopo il salvataggio, la finestra di dialogo apre i dettagli del connettore salvato. Torna all&#39;elenco **[!UICONTROL Connettori esterni]** e verifica che nella scheda **[!UICONTROL RainFocus]** sia visualizzato **[!UICONTROL Configurazione salvata]** e **[!UICONTROL Configurazione vista]**.
1. Ricarica la pagina, quindi seleziona **[!UICONTROL Visualizza configurazione]**.
1. Conferma i seguenti dettagli:

   * **[!UICONTROL Source]** mostra l&#39;URL del profilo immesso.
   * **[!UICONTROL Autenticazione]** presente.
   * **[!UICONTROL Criteri degli strumenti]** > **[!UICONTROL Nomi o modelli di strumenti consentiti]** elenca gli stessi 10 strumenti della sezione [Strumenti disponibili](#available-tools).

1. Per verificare la tua connessione, seleziona **[!UICONTROL Prova]**. Se Coworker ti chiede di accedere, usa il tuo account [!DNL RainFocus], come descritto in [Accedi come membro](#sign-in-as-a-member).

   **[!UICONTROL Test]** elenca gli strumenti del server e aggiorna il conteggio di **[!UICONTROL Strumenti]**. Se il server non restituisce strumenti, i dettagli mostrano **[!UICONTROL 0 strumenti disponibili]**. Se il test non riesce, i dettagli mostrano **[!UICONTROL Connessione non riuscita]**.

   ![Dettagli del connettore rainfocus salvati che mostrano un&#39;origine ridotta, il metodo di autenticazione rainfocus_login, un collegamento Non firmato con un pulsante di accesso e i pulsanti Test e Rimuovi.](./assets/rainfocus/org-details.png){width="700" zoomable="yes"}

I controlli **[!UICONTROL Connessione]**, **[!UICONTROL Test]** e accesso nei dettagli del connettore si applicano solo alla tua connessione. Quando si esegue l&#39;accesso come amministratore, nessun membro è connesso. Un test di successo elenca solo gli strumenti. Il test non esegue uno strumento di dati [!DNL RainFocus] né conferma che un membro possa accedere a dati specifici.

I dettagli del connettore non dispongono di alcuna opzione per modificare l’URL del profilo. **[!UICONTROL Rimuovi]** apre una conferma e quindi rimuove la connessione per l&#39;intera organizzazione. Considera la rimozione come una decisione intenzionale dell’amministratore, non come un passaggio per la risoluzione dei problemi.

### Strumenti disponibili {#available-tools}

Il connettore [!DNL RainFocus] abilita un elenco fisso di 10 strumenti di lettura:

| Strumento | Area dati |
| --- | --- |
| `get_attendeeInfo` | Partecipanti |
| `get_attendee_load` | Partecipanti |
| `get_attendee_search` | Partecipanti |
| `get_attribute_load` | Attributi personalizzati |
| `get_attribute_search` | Attributi personalizzati |
| `get_attributevalue_load` | Attributi personalizzati |
| `get_entityDataDump_attendee` | Partecipanti, esportazione in blocco |
| `get_entityDataDump_session` | Sessioni, esportazione in blocco |
| `get_session_load` | Sessions |
| `get_session_search` | Sessions |

Gli strumenti non inclusi in questo elenco, inclusi quelli aggiunti in seguito da [!DNL RainFocus], non vengono attivati automaticamente. L&#39;elenco non sostituisce i ruoli di sicurezza [!DNL RainFocus] o le impostazioni dello strumento del profilo, che controllano comunque l&#39;accesso ai dati.

>[!IMPORTANT]
>
>Diversi strumenti possono restituire dati personali e informazioni di contatto sui partecipanti. Due strumenti esportano i dati in blocco e i risultati possono essere di grandi dimensioni. Le letture possono anche comportare spese in base ai tuoi termini [!DNL RainFocus]. Rivedi questi strumenti con i proprietari della governance dei dati prima che i membri effettuino l’accesso.

## Accedi come membro {#sign-in-as-a-member}

Dopo che un amministratore ha configurato il connettore, ogni membro accede con il proprio account [!DNL RainFocus]. Per accedere non è necessario un ID client, un segreto client o un token di accesso.

1. Apri **[!UICONTROL Personalizzazioni]**, quindi seleziona **[!UICONTROL Connettori esterni]**. I membri utilizzano l&#39;ambito **[!UICONTROL Utente]** per impostazione predefinita. Trova la scheda **[!UICONTROL RainFocus]**.
1. Se nella scheda è visualizzato **[!UICONTROL Non ancora disponibile. L&#39;amministratore deve configurarlo.]**, chiedi all&#39;amministratore di [configurare il connettore](#configure-organization). I membri non possono immettere il proprio URL di profilo.
1. Controlla lo stato sulla scheda. La scheda mostra **[!UICONTROL Accesso richiesto]**, **[!UICONTROL Connesso]**, **[!UICONTROL Configurato dall&#39;amministratore]** o uno stato di **[!UICONTROL Connessione non riuscita]**.

   **[!UICONTROL La configurazione da parte dell&#39;amministratore]** impedisce a Collaborator di confermare lo stato di accesso. Ciò non significa che hai effettuato l’accesso o la disconnessione.

1. Seleziona **[!UICONTROL Accedi]**. Puoi anche aprire i dettagli della scheda e selezionare **[!UICONTROL Accedi]** nella sezione **[!UICONTROL Connessione]**. Nella finestra [!DNL RainFocus], completare l&#39;accesso, il Single Sign-On (SSO), l&#39;autenticazione a più fattori (MFA) e le richieste di consenso. Controlla l’accesso che approvi.

   Se viene visualizzato **[!UICONTROL Discover authorization]**, Coworker legge i dettagli di accesso del server, non i relativi strumenti. Se l&#39;individuazione non riesce o il pannello richiede un **[!UICONTROL ID client]** o un **[!UICONTROL Segreto client]**, arresta e contatta l&#39;amministratore. Non immettere o indovinare le credenziali.

   ![Dettagli del connettore RainFocus per un membro, con lo stato richiesto per l&#39;accesso, l&#39;URL del server corretto, l&#39;accesso di ogni utente, l&#39;accesso non effettuato in connessione con un pulsante di autorizzazione Discover e i 10 strumenti abilitati dall&#39;amministratore.](./assets/rainfocus/member-details.png){width="700" zoomable="yes"}

1. Torna a Collaboratore e verifica che nello stato sia visualizzato **[!UICONTROL Connesso]**. Una finestra di accesso chiusa da sola non conferma il successo. Se si chiude la finestra in anticipo, non cambia nulla e si può riprovare.
1. Apri i dettagli della scheda per rivedere l’impostazione da parte dell’amministratore. Puoi visualizzare l&#39;**[!UICONTROL URL server]**, **[!UICONTROL Chi firma]**, **[!UICONTROL Autenticazione]** e **[!UICONTROL Strumenti abilitati dall&#39;amministratore]**.
1. Seleziona **[!UICONTROL Test]** sulla scheda o **[!UICONTROL Verifica connessione]** nei dettagli, per verificare la connessione con l&#39;account.

   Un test riuscito mostra che [!DNL RainFocus] ha risposto utilizzando il tuo account, con il numero di strumenti disponibili. Il test elenca solo gli strumenti. Non esegue uno strumento di dati né conferma l’accesso a eventi o record specifici. Per rinnovare l&#39;accesso ed elencare nuovamente gli strumenti, selezionare **[!UICONTROL Aggiorna]**. Se non è possibile rinnovare l&#39;accesso, il pulsante mostra invece **[!UICONTROL Ricarica strumenti]**, in cui sono elencati solo gli strumenti.

1. Se il test non riesce, viene visualizzato **[!UICONTROL Impossibile connettersi a RainFocus]**, con **[!UICONTROL Riprova]** e **[!UICONTROL Dettagli tecnici]**. Se sei disconnesso, accedi di nuovo. Se il problema persiste, contattare l&#39;amministratore.

I membri possono accedere, disconnettersi, testare, aggiornare e visualizzare gli strumenti abilitati. I membri non possono modificare o rimuovere la connessione all’organizzazione, modificare l’URL del profilo o modificare gli strumenti. Ogni membro che apre i dettagli può visualizzare l’URL del profilo. Quando un amministratore effettua l&#39;accesso, gli altri membri non vengono connessi.

Per disconnettere l&#39;account [!DNL RainFocus] dal connettore, selezionare **[!UICONTROL Esci]**. Puoi accedere di nuovo in qualsiasi momento.

## Controlla l’accesso ai dati dell’evento {#check-event-access}

Per confermare che è possibile utilizzare i dati di [!DNL RainFocus], eseguire un controllo di sola lettura con una richiesta ristretta. Utilizzare un evento con cui si è autorizzati a lavorare ed evitare strumenti che restituiscano dati dei partecipanti o esportazioni in blocco per questo controllo. Avvia una chat e immetti un prompt.

Esempio di prompt:

* &quot;Con RainFocus posso trovare fino a cinque sessioni a cui posso accedere. Mostra solo il titolo e l’ID della sessione se tali campi vengono restituiti. Non esportare dati, non restituire informazioni sui partecipanti e non modificare nulla.&quot;

Conferma che il risultato includa le sessioni previste. Un risultato vuoto non significa sempre che il connettore non funziona. Controlla l&#39;account [!DNL RainFocus] con cui hai effettuato l&#39;accesso, il tuo ruolo di sicurezza e gli strumenti abilitati nel profilo. Se un risultato è inaspettatamente grande o include dati sensibili, interrompi e restringi la richiesta.

## Risolvere i problemi di accesso {#troubleshoot-access}

Se non riesci ad accedere ai dati di [!DNL RainFocus], verifica quanto segue con il tuo amministratore:

| Problema | Cosa controllare |
| --- | --- |
| Scheda **[!UICONTROL RainFocus]** mancante | Verifica con il tuo rappresentante Adobe che il connettore sia disponibile per la tua organizzazione. |
| Ambito **[!UICONTROL Org]** mancante | Conferma di essere un amministratore e che le impostazioni dell’organizzazione siano attivate per la tua organizzazione. |
| Collaboratore rifiuta l’URL del profilo | Segui la regola nel messaggio. Utilizza l&#39;URL completo del profilo dal tuo amministratore [!DNL RainFocus] e non indovinare un nome di profilo. |
| **[!UICONTROL Impossibile salvare la connessione]** | Alcune impostazioni potrebbero essere salvate. Riapri la configurazione e controllane prima di riprovare. Verificare che il connettore sia configurato da un solo amministratore alla volta. |
| La scheda mostra **[!UICONTROL Non ancora disponibile. L&#39;amministratore deve configurarlo.]** | Configurazione organizzazione mancante. Chiedi all&#39;amministratore di [configurare il connettore](#configure-organization). |
| L&#39;accesso richiede un **[!UICONTROL ID client]** o **[!UICONTROL Segreto client]** oppure l&#39;individuazione non riesce | Interrompi l’attività e contatta l’amministratore. Non immettere o indovinare le credenziali o registrare un&#39;app. |
| L&#39;accesso non riesce dopo aver approvato l&#39;accesso in [!DNL RainFocus] | Controllare l&#39;account [!DNL RainFocus] e il ruolo di sicurezza utilizzati. Chiedi al tuo rappresentante Adobe e a [!DNL RainFocus] di controllare la configurazione di accesso per il tuo ambiente. Non condividere l’URL di accesso. |
| **[!UICONTROL Test]** riuscito, ma le richieste di dati non riescono | **[!UICONTROL Test]** elenca solo gli strumenti. Controlla il tuo ruolo di sicurezza [!DNL RainFocus], gli strumenti abilitati nel profilo e i filtri richiesti dallo strumento. |
| **[!UICONTROL Impossibile connettersi a RainFocus]** viene visualizzato all&#39;accesso | Seleziona **[!UICONTROL Riprova]**. Se il problema persiste, contattare l&#39;amministratore. |
| Un risultato è inaspettatamente grande o include dati sensibili | Interrompi e restringi la richiesta. Non incollare dati non elaborati di eventi in biglietti o chat. |

Quando contatti il supporto, includi solo il testo dell’errore, l’ora dell’errore e l’ambiente. Non condividere dettagli tecnici, URL di profilo, acquisizioni di accesso, password, token o codici di autorizzazione.
