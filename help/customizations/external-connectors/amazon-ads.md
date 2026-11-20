---
title: Connettore esterno Amazon Ads
description: Scopri come configurare il connettore esterno Amazon Ads in CX Enterprise Coworker per la tua organizzazione e accedere con Amazon per utilizzare gli strumenti Amazon Ads in chat.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Questo connettore è in versione beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 80dda0b442d6c7fe560c965b985f58173b73fe13
workflow-type: tm+mt
source-wordcount: '3078'
ht-degree: 1%
---

# Connettore esterno Amazon Ads {#amazon-ads}

Utilizza il connettore esterno [!DNL Amazon Ads] per lavorare con i dati di [!DNL Amazon Ads] in Adobe CX Enterprise Coworker. Dopo aver configurato il connettore, chiedi al collega a quali account pubblicitari puoi accedere e rivedi campagne, rapporti, fatturazione e altre informazioni sull’account. Il connettore è un server MCP ospitato da [!DNL Amazon].

>[!AVAILABILITY]
>
>Il connettore esterno [!DNL Amazon Ads] è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.

## Configurazione del connettore {#connector-configuration}

Il processo di configurazione del connettore è costituito da tre parti separate:

* Preparazione **[!DNL Amazon]:** Un amministratore dell&#39;account [!DNL Amazon Ads] consente a ogni membro di accedere agli account pubblicitari necessari. Se l’organizzazione utilizza una propria app OAuth, il proprietario dell’app conferma l’approvazione e registra l’URL di reindirizzamento di Collaborator.
* **Configurazione organizzazione:** Un amministratore di Coworker configura il connettore una sola volta per l&#39;intera organizzazione. L’amministratore sceglie un’area geografica, un’applicazione OAuth e gli strumenti che i membri possono utilizzare.
* **Accesso membro:** Ogni membro effettua l&#39;accesso con il proprio account [!DNL Amazon]. I membri possono accedere solo agli account pubblicitari che il loro account [!DNL Amazon] dispone dell&#39;autorizzazione per utilizzare.

Il salvataggio della configurazione dell&#39;organizzazione non comporta l&#39;accesso ad alcun membro né la concessione di autorizzazioni [!DNL Amazon Ads]. Ogni membro deve avere già l&#39;accesso richiesto in [!DNL Amazon Ads] e deve effettuare l&#39;accesso separatamente.

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di disporre dei seguenti elementi:

* **Accesso collaboratore:** account con autorizzazione per la gestione dei connettori organizzazione in un&#39;organizzazione in cui è disponibile il connettore [!DNL Amazon Ads].
* **Account Advertising:** gli account pubblicitari che intendi utilizzare e la relativa area geografica [!DNL Amazon Ads] e i membri con le autorizzazioni necessarie per tali account. Per ulteriori informazioni, vedere [Concedere l&#39;accesso all&#39;account per annunci pubblicitari](#grant-member-access).
* **Decisione su un&#39;applicazione OAuth:** Scegli tra le seguenti opzioni:
  * **Applicazione OAuth gestita da Adobe:** Adobe gestisce la registrazione dell&#39;app e le relative credenziali. L&#39;app gestita deve essere disponibile nel tuo ambiente.
  * **La tua applicazione OAuth:** un&#39;app [!DNL Login with Amazon] approvata per l&#39;API [!DNL Amazon Ads], il relativo ID client OAuth e il segreto client e un amministratore che può modificare il profilo di sicurezza. Un profilo di sicurezza registrato di per sé non concede l&#39;approvazione API [!DNL Amazon Ads].

La configurazione guidata supporta una connessione [!DNL Amazon Ads] e un&#39;area per organizzazione. Ogni membro accede con il proprio account [!DNL Amazon]. L&#39;app gestita da Adobe è una registrazione app condivisa, non un account [!DNL Amazon] condiviso.

## Preparare l’accesso ad Amazon {#prepare-amazon}

Prima di configurare il connettore in Collaborator, preparare l&#39;accesso all&#39;app e all&#39;account in [!DNL Amazon]. L’accesso alla configurazione dell’app e l’accesso ai dati pubblicitari sono separati. I membri che utilizzano il connettore non hanno bisogno dell&#39;autorizzazione per modificare l&#39;app.

### Conferma approvazione app {#confirm-app-approval}

Se utilizzi un&#39;applicazione OAuth personalizzata, chiedi al proprietario dell&#39;app di confermare il profilo di sicurezza [!DNL Login with Amazon] corretto e la relativa approvazione API [!DNL Amazon Ads]. La creazione di un profilo di sicurezza o la visualizzazione dell&#39;app nella console per sviluppatori [!DNL Amazon] non sostituisce l&#39;approvazione API [!DNL Amazon Ads]. Per ulteriori informazioni, consulta [Guida introduttiva di MCP per Amazon Ads](https://advertising.amazon.com/API/docs/en-us/mcp/get-started) e [Connessione al server Ads MCP tramite OAuth](https://advertising.amazon.com/API/docs/en-us/mcp/oauth) nella documentazione di [!DNL Amazon Ads].

Per la tua app, Collaboratore applica automaticamente le seguenti impostazioni. Questi valori non vengono immessi nella finestra di dialogo di impostazione.

| Impostazione | Valore |
| --- | --- |
| URL autorizzazione | `https://lwa.amazon.com/ap/oa` |
| URL token | `https://api.amazon.com/auth/o2/token` |
| Ambito richiesto | `advertising::campaign_management` |
| Chiave bozza per scambio codice (PKCE) | Abilitati |
| Autenticazione client endpoint token | `client_secret_post`, come client riservato |
| Registrazione dinamica del client | Non supportato |
| Timeout del trasporto e dello strumento | HTTP semplificabile, 60 secondi |

Se utilizzi l’applicazione OAuth gestita da Adobe, Adobe gestisce la registrazione dell’app e le relative credenziali. Non è necessario completare questo passaggio o immettere le credenziali dell&#39;app.

### Registra l’URL di reindirizzamento {#register-redirect-url}

Se utilizzi un&#39;applicazione OAuth personalizzata, registra l&#39;URL di reindirizzamento di Coworker nell&#39;app [!DNL Login with Amazon]:

1. In Coworker, apri la finestra di dialogo **[!UICONTROL Configura Amazon Ads per la tua organizzazione]**, come descritto in [Configura il connettore per la tua organizzazione](#configure-organization). Seleziona **[!UICONTROL Utilizza la mia applicazione OAuth]** per visualizzare l&#39;**[!UICONTROL URL di reindirizzamento]**, quindi copia il valore completo.
1. Nella console [Accedi con Amazon](https://developer.amazon.com/loginwithamazon/console/site/lwa/overview.html), individua il profilo di sicurezza per la tua app. Selezionare **[!UICONTROL Gestisci]** > **[!UICONTROL Impostazioni Web]**, quindi selezionare **[!UICONTROL Modifica]**.
1. Aggiungi l&#39;URL di reindirizzamento completo in **[!UICONTROL URL restituiti consentiti]**, quindi salva. Se altri team condividono l’app, mantieni gli URL esistenti e ottieni l’approvazione del proprietario dell’app prima di modificare le impostazioni.
1. Nota l’ID client OAuth e il segreto client dallo stesso profilo di sicurezza. Immettili quando [configuri il connettore](#configure-organization).

Copia sempre l’URL di reindirizzamento dalla finestra di dialogo Collaboratore nell’ambiente che stai configurando. Non creare l’URL da solo, utilizza l’URL della pagina di Collaboratore nel browser o riutilizza un URL di reindirizzamento da un altro ambiente o client MCP. Per ulteriori informazioni, vedere [Registrarsi per l&#39;accesso con Amazon](https://developer.amazon.com/docs/login-with-amazon/register-web.html) nella documentazione di [!DNL Amazon].

>[!NOTE]
>
>Se l&#39;**[!UICONTROL URL di reindirizzamento]** mostra solo il percorso `/connectors/oauth/callback`, l&#39;ambiente non supporta ancora l&#39;accesso per questo connettore. Non registrare un percorso parziale o non indovinare il nome host. Contatta il tuo rappresentante Adobe.

### Concedere l’accesso all’account per annunci pubblicitari {#grant-member-access}

Un amministratore di account [!DNL Amazon Ads] invita ogni membro agli account pubblicitari necessari:

1. Apri la [console Amazon Ads](https://advertising.amazon.com/), quindi seleziona **[!UICONTROL Cambia account]** per scegliere l&#39;account dell&#39;inserzionista o del manager.
1. Seleziona **[!UICONTROL Amministrazione]** > **[!UICONTROL Accesso e impostazioni account]** > **[!UICONTROL Utenti]** > **[!UICONTROL Invita utenti]**. Le opzioni esatte dipendono dal tipo di account. Invita l&#39;account [!DNL Amazon] del membro, con le autorizzazioni minime per le attività che prevede di eseguire.
1. Per un account manager, controlla se l’accesso riguarda l’intero account manager o solo gli inserzionisti collegati selezionati. Chiedere al membro di accettare l&#39;invito con lo stesso account [!DNL Amazon] utilizzato per il collega.
1. Verificare che il membro possa selezionare l&#39;inserzionista in [!DNL Amazon Ads]. Prendi nota del nome account, dell’area geografica e dell’ID dell’inserzionista previsti in un record interno approvato, in modo da poter confermare l’accesso in un secondo momento in Collaboratore.

Scegliere il ruolo meno privilegiato che supporta le attività pianificate. Non concedere all&#39;amministratore l&#39;accesso solo per effettuare un controllo dell&#39;accesso. L&#39;accesso a un&#39;istanza [!DNL Amazon Marketing Cloud] è separato dall&#39;accesso alle campagne pubblicitarie. Per ulteriori informazioni, vedere la seguente documentazione di [!DNL Amazon Ads]:

* [Gestire gli utenti in un account Manager](https://advertising.amazon.com/help/G4M4JGKGV2VAY9JC)
* [Aggiungere o rimuovere utenti dal tuo account](https://advertising.amazon.com/help/GDQVHVQMY9F88PCA)
* [Informazioni sulle autorizzazioni dell’account](https://advertising.amazon.com/help/GM4EFDQQPG9LGL3F)
* [Autorizzazioni API di Amazon Ads](https://advertising.amazon.com/API/docs/en-us/guides/account-management/permissions)

## Configurare il connettore per l’organizzazione {#configure-organization}

Gli amministratori rendono il connettore [!DNL Amazon Ads] disponibile a tutti gli utenti dell&#39;organizzazione. Le modifiche apportate alla pagina dell’organizzazione vengono applicate a tutti gli utenti dell’organizzazione. I membri non possono configurare la connessione all&#39;organizzazione dall&#39;ambito **[!UICONTROL Utente]**.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Organizzazione]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Nella scheda **[!UICONTROL Amazon Ads]**, seleziona **[!UICONTROL Configura]**.

   Viene visualizzata la finestra di dialogo **[!UICONTROL Configura Amazon Ads per l&#39;organizzazione]** con le sezioni **[!UICONTROL Dettagli connessione]**, **[!UICONTROL Strumenti disponibili per gli utenti]** e **[!UICONTROL Accesso e autorizzazioni]**. Dopo aver salvato la configurazione, nella scheda vengono visualizzate **[!UICONTROL Configurazione salvata]** e **[!UICONTROL Configurazione]** modifiche a **[!UICONTROL Visualizza configurazione]**.

1. In **[!UICONTROL Area geografica Amazon Ads]**, seleziona l&#39;area corrispondente ai tuoi account pubblicitari. Collaboratore mostra l’URL del server MCP per l’area sotto la selezione.

   | Area geografica | URL del server MCP |
   | --- | --- |
   | [!UICONTROL America del Nord] (impostazione predefinita) | `https://advertising-ai.amazon.com/mcp` |
   | [!UICONTROL Europa] | `https://advertising-ai-eu.amazon.com/mcp` |
   | [!UICONTROL Estremo Oriente] | `https://advertising-ai-fe.amazon.com/mcp` |

   La configurazione guidata consente di salvare una regione. Per cambiare regione in un secondo momento, rimuovi la connessione e impostala nuovamente. Ogni membro deve quindi effettuare di nuovo l&#39;accesso, quindi pianificare la modifica prima di interrompere una connessione in esecuzione.

1. Seleziona un&#39;applicazione **[!UICONTROL OAuth]**:

   * **[!UICONTROL Applicazione OAuth gestita da Adobe]:** Adobe fornisce l&#39;app [!DNL Amazon Ads], pertanto non è necessario immettere le credenziali dell&#39;app. Ogni membro effettua l&#39;accesso con il proprio account [!DNL Amazon] e autorizza l&#39;app Adobe.

     ![Configura Amazon Ads per la finestra di dialogo dell&#39;organizzazione con l&#39;area Nord America, l&#39;applicazione OAuth gestita da Adobe selezionata e i gruppi di strumenti compressi.](./assets/amazon-ads/org-configure.png){width="500" zoomable="yes"}

   * **[!UICONTROL Usa la mia applicazione OAuth]:** Ogni membro autorizza la tua app dell&#39;organizzazione con il proprio account [!DNL Amazon]. In **[!UICONTROL La tua applicazione Amazon]**, completa i seguenti passaggi:

     1. Verificare che l&#39;**[!UICONTROL URL di reindirizzamento]** sia registrato nell&#39;app. Per ulteriori informazioni, vedere [Registrare l&#39;URL di reindirizzamento](#register-redirect-url).
     1. Immetti l&#39;**[!UICONTROL ID app Amazon]** e il **[!UICONTROL segreto app Amazon]**. Il campo **[!UICONTROL ID app Amazon]** accetta l&#39;ID client OAuth, non un ID inserzionista, un ID account manager o l&#39;ID applicazione [!DNL Amazon]. I valori immessi vengono memorizzati come segreti dell&#39;organizzazione.
     1. Per riutilizzare le credenziali salvate, selezionare **[!UICONTROL Usa un segreto esistente]**. Quindi seleziona il **[!UICONTROL Segreto contenente l&#39;ID app]** e il **[!UICONTROL Segreto contenente il segreto app]**. Se la tua organizzazione non ha ancora segreti, aggiungili in **[!UICONTROL Impostazioni]** > **[!UICONTROL Segreti]**.

     Entrambe le credenziali sono obbligatorie. Immettere i valori delle credenziali solo nei campi protetti. Non immettere un riferimento segreto in un campo di valore normale.

1. In **[!UICONTROL Strumenti disponibili per gli utenti]**, espandi ogni gruppo di strumenti e seleziona gli strumenti necessari per la tua organizzazione. Per impostazione predefinita, sono selezionati solo gli strumenti `ads_accounts-list_ads_accounts` e `ads_accounts-get_ads_account`. Per modificare tutti gli strumenti contemporaneamente, utilizzare **[!UICONTROL Seleziona tutto]** o **[!UICONTROL Cancella tutto]**. È necessario selezionare almeno uno strumento.

   Inizia con i due strumenti dell’account per un controllo del primo accesso. Seleziona gli strumenti di campagna e reporting solo quando l&#39;organizzazione ne ha bisogno e li approva. Per ulteriori informazioni, vedere [Gruppi di strumenti](#tool-groups).

1. Seleziona **[!UICONTROL Salva connessione]**, quindi controlla i dettagli salvati del connettore **[!UICONTROL amazon-ads]**.

   | Impostazione | Descrizione |
   | --- | --- |
   | **[!UICONTROL Source]** | L&#39;URL del server MCP per l&#39;area selezionata. |
   | **[!UICONTROL Authentication]** | Metodo di autenticazione `amazon-ads_login`. |
   | **[!UICONTROL Timeout strumento]** | Tempo di attesa di una risposta dello strumento da parte di Collaboratore. |
   | **[!UICONTROL Connessione]** | L’applicazione OAuth in uso e il tuo stato di accesso. |
   | **[!UICONTROL Strumenti]** | Strumenti selezionati per i membri, con **[!UICONTROL Seleziona tutti]** e **[!UICONTROL Cancella]** controlli e un conteggio degli strumenti selezionati. |

   ![Sono stati salvati i dettagli del connettore amazon-ads che mostrano l&#39;origine Nord America, il metodo di autenticazione, una connessione Firmata con i pulsanti Disconnetti e Aggiorna e due dei 47 strumenti selezionati.](./assets/amazon-ads/org-details.png){width="700" zoomable="yes"}

Il salvataggio non comporta l&#39;accesso né per te né per alcun membro a [!DNL Amazon]. Lo stato **[!UICONTROL Connessione]** nei dettagli del connettore fa riferimento alla tua connessione e non all&#39;organizzazione. Per verificare la connessione, seleziona **[!UICONTROL Accedi]** nella pagina dei dettagli del connettore per accedere con il tuo account [!DNL Amazon], quindi seleziona **[!UICONTROL Prova]**. Il risultato mostra **[!UICONTROL Connessione riuscita]** o **[!UICONTROL Connessione non riuscita]**, con gli strumenti o gli errori restituiti. In caso di esito positivo, il risultato non conferma l’accesso a una specifica operazione dell’inserzionista.

Per cambiare gli strumenti disponibili per i membri in un secondo momento, aggiornare la selezione in **[!UICONTROL Strumenti disponibili]** con **[!UICONTROL Seleziona tutto]** o **[!UICONTROL Cancella]**, quindi selezionare **[!UICONTROL Salva selezione strumenti]**. Almeno uno strumento deve rimanere selezionato. I membri non possono modificare la selezione dello strumento.

Per interrompere l&#39;offerta del connettore all&#39;organizzazione, selezionare **[!UICONTROL Rimuovi]** nella pagina dei dettagli del connettore.

### Gruppi di strumenti {#tool-groups}

Il connettore [!DNL Amazon Ads] organizza i propri strumenti nei seguenti gruppi:

| Gruppo di strumenti | Strumenti | Funzionamento degli strumenti |
| --- | --- | --- |
| [!UICONTROL Gestione campagne e targeting] | 7 | Esegui query su campagne, gruppi di annunci, annunci, destinazioni, portfolio e relative associazioni e verifica l’idoneità del prodotto. |
| [!UICONTROL Account e organizzazione] | 6 | Crea un elenco e ottieni account pubblicitari, collegamenti a inserzionisti e account, account manager e account di test. |
| [!UICONTROL Accesso utente e sicurezza] | 5 | Crea un elenco di utenti, ruoli, autorizzazioni e inviti e ottieni un invito. |
| [!UICONTROL Reporting e analisi] | 1 | Recuperare un rapporto. La creazione del rapporto non è inclusa. |
| [!UICONTROL Amazon Marketing Cloud] | 6 | Leggi i flussi di lavoro e le origini dati, nonché lo stato e gli URL di download delle esecuzioni esistenti. L’esecuzione del flusso di lavoro non è inclusa. |
| [!UICONTROL Riepiloghi di fatturazione e finanziari] | 4 | Leggi fatture, riepiloghi fatture, utilizzo del profilo di fatturazione e notifiche di fatturazione. |
| [!UICONTROL Amazon Live] | 12 | Leggi informazioni su canali, trasmissioni, livestream, contenuti multimediali, carosello e codice promozionale. |
| [!UICONTROL Idoneità e offerte] | 6 | Leggi le informazioni su programma e idoneità del prodotto, offerte e premi di promozione e termini token. |

Gli strumenti in ogni gruppo possono cambiare quando [!DNL Amazon] aggiorna il connettore. La configurazione guidata consente di salvare l&#39;elenco esatto degli utensili selezionati, anche quando selezionate tutti gli strumenti. Gli strumenti non selezionati e quelli aggiunti in seguito dal server non sono disponibili per i membri fino a quando non vengono selezionati.

>[!IMPORTANT]
>
>L&#39;elenco degli strumenti di configurazione è curato per la lettura dei dati, ma il connettore nel suo complesso non è di sola lettura. I membri autorizzano l&#39;ambito `advertising::campaign_management`, che è più ampio dell&#39;elenco di installazione. Quando verifichi la connessione, l’elenco degli strumenti può includere anche gli strumenti restituiti dal server. Prima di selezionare altri strumenti, esaminare la definizione di ogni strumento e le autorizzazioni [!DNL Amazon Ads] dei membri.

## Accedi come membro {#sign-in-as-a-member}

Dopo che un amministratore ha configurato il connettore, ogni membro accede con il proprio account [!DNL Amazon]. Non è necessario un segreto app o un token di accesso per accedere.

>[!NOTE]
>
>Se il connettore indica che l&#39;accesso e **[!UICONTROL Test]** non sono ancora disponibili nel tuo ambiente, fermati qui. La configurazione dell&#39;organizzazione da sola non rende disponibile l&#39;accesso dei membri. Contatta il tuo rappresentante Adobe.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Utente]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Trova la scheda **[!UICONTROL Amazon Ads]**.

1. Se nella scheda è visualizzato **[!UICONTROL Non configurato]**, chiedere all&#39;amministratore di [configurare il connettore](#configure-organization). Impossibile configurare il connettore.

1. Quando nella scheda viene visualizzato **[!UICONTROL Accesso non effettuato]**, selezionare **[!UICONTROL Accesso]**. Consenti l&#39;accesso popup, quindi accedi con l&#39;account [!DNL Amazon] che ha accesso ai tuoi account pubblicitari.

1. Completare le [!DNL Amazon] richieste di autenticazione, ad esempio l&#39;autenticazione a più fattori (MFA) e la richiesta di consenso. Prima di approvare, controlla il nome dell’app e l’accesso richiesto.

   Con l’app gestita da Adobe, autorizzi l’app Adobe. Autorizzi invece l’app con la tua app dell’organizzazione.

   >[!IMPORTANT]
   >
   >Continua solo se riconosci l’app e l’organizzazione approva l’accesso richiesto.

1. Torna a Collaboratore e verifica che nella scheda sia visualizzato **[!UICONTROL Accesso effettuato]**. Seleziona **[!UICONTROL Visualizza dettagli]**, quindi controlla **[!UICONTROL Strumenti abilitati dall&#39;amministratore]**. I membri possono visualizzare gli strumenti ma non possono modificarli o rimuovere la connessione all&#39;organizzazione.

1. Selezionare **[!UICONTROL Test]** per verificare l&#39;individuazione dello strumento e lo stato della connessione.

Un pop-up chiuso da solo non conferma che l’accesso è riuscito. In caso di esito positivo, il test non conferma l&#39;accesso a ogni inserzionista, campagna, report o istanza [!DNL Amazon Marketing Cloud]. Quando un amministratore effettua l&#39;accesso, gli altri membri non vengono connessi.

Per disconnettere l&#39;account [!DNL Amazon] dal connettore, selezionare **[!UICONTROL Esci]**.

## Controlla l&#39;accesso al tuo account pubblicitario {#check-account-access}

Per verificare quali account pubblicitari è possibile utilizzare, eseguire un controllo di sola lettura. Utilizzare un account di test approvato e verificare che l&#39;amministratore abbia abilitato gli strumenti `ads_accounts-list_ads_accounts` e `ads_accounts-get_ads_account`. Quindi avvia una chat e immetti un prompt.

Esempio di prompt:

* &quot;Con Amazon Ads, elenca fino a cinque account pubblicitari a cui posso accedere nell’area configurata. Mostra solo il nome dell&#39;account, l&#39;ID account e l&#39;area geografica se tali campi vengono restituiti. Non creare, aggiornare, eliminare, avviare, eseguire flussi di lavoro, generare rapporti o modificare le autorizzazioni. Se un limite di inserzioni non è supportato, riepiloga solo cinque risultati e non richiedere pagine aggiuntive.&quot;

Conferma che il risultato includa l’account previsto. Per visualizzare ulteriori dettagli, chiedi a Collaboratore di ottenere i dettagli di quell’account, utilizzando l’ID account dal risultato. Non indovinare gli ID account e non richiedere campagne solo per testare l’accesso.

Un elenco di account vuoto non significa sempre che il connettore non funziona. Controlla l&#39;account [!DNL Amazon] con cui hai effettuato l&#39;accesso, gli inviti accettati, gli inserzionisti collegati coperti da un account manager e l&#39;area configurata. Anche un account di test senza campagne può restituire un elenco di campagne vuoto. Se uno strumento di cui hai bisogno non è abilitato, chiedi all’amministratore. Non utilizzare uno strumento che modifichi i dati come sostituto.

## Risolvere i problemi di accesso {#troubleshoot-access}

Se non riesci ad accedere ai dati di [!DNL Amazon Ads], verifica quanto segue con il tuo amministratore:

| Problema | Cosa controllare |
| --- | --- |
| Manca la scheda **[!UICONTROL Amazon Ads]** o **[!UICONTROL Configure]** | Verifica che il connettore sia disponibile per la tua organizzazione e di disporre dell’autorizzazione per gestire i connettori dell’organizzazione. I membri devono attendere la configurazione dell’organizzazione. |
| L’installazione gestita da Adobe viene salvata, ma l’accesso non riesce | Contatta il tuo rappresentante Adobe per verificare che l’app gestita da Adobe sia disponibile nel tuo ambiente. Un salvataggio riuscito non conferma questo comportamento. |
| L&#39;URL di reindirizzamento non corrisponde | Confrontare l&#39;**[!UICONTROL URL di reindirizzamento]** completo dalla finestra di dialogo di Coworker con gli **[!UICONTROL URL restituiti consentiti]** in [!DNL Login with Amazon], inclusi schema, host e percorso. Non utilizzare un URL di reindirizzamento da un altro client, area geografica o ambiente MCP né l’URL della pagina di Collaboratore nel browser. |
| L&#39;**[!UICONTROL URL di reindirizzamento]** mostra solo `/connectors/oauth/callback` | L&#39;ambiente non mostra ancora l&#39;URL di reindirizzamento completo o l&#39;accesso e il **[!UICONTROL test]** del supporto. Non registrare un percorso parziale o non indovinare il nome host. Contatta il tuo rappresentante Adobe. |
| Impossibile salvare la propria configurazione dell’app OAuth | Immetti sia l&#39;ID client OAuth che il segreto client e mantieni selezionato almeno uno strumento. Assicurati che l&#39;**[!UICONTROL ID app Amazon]** sia l&#39;ID client OAuth, non un ID inserzionista o l&#39;ID applicazione [!DNL Amazon]. |
| Autorizzazione del consenso o dell’app non riuscita | Controllare l&#39;approvazione dell&#39;API [!DNL Amazon Ads], il profilo di sicurezza, l&#39;ID client e l&#39;associazione segreta, la registrazione dell&#39;URL di reindirizzamento e l&#39;app visualizzata nella schermata di consenso. Non condividere l’URL del consenso, il codice di autorizzazione o i token quando chiedi aiuto. |
| Si effettua l&#39;accesso, ma gli account o gli strumenti vengono negati o vuoti | Controllare l&#39;account [!DNL Amazon] con cui si è effettuato l&#39;accesso, l&#39;invito accettato, gli inserzionisti collegati coperti da un account manager, l&#39;area configurata e le autorizzazioni necessarie per l&#39;attività. L’accesso all’app o agli strumenti partner non conferma l’accesso dell’inserzionista. L&#39;accesso a [!DNL Amazon Marketing Cloud] è separato. |
| [!DNL Amazon Ads] dice che l&#39;account corrente non può accedere a una pagina | Seleziona **[!UICONTROL Cambia account]** e scegli l&#39;account dell&#39;inserzionista o del manager. Se l’account non è presente, chiedi all’amministratore di verificare di aver accettato l’invito e di essere stato assegnato all’account. Se l’account è presente ma la gestione utente non è disponibile, chiedi all’amministratore di controllare il tuo ruolo. |
| Strumento mancante o non disponibile | Controlla la selezione degli strumenti per la tua organizzazione, gli strumenti restituiti dal server e le autorizzazioni di [!DNL Amazon Ads]. Gli strumenti aggiunti in seguito dal server non vengono selezionati automaticamente. Per impostazione predefinita, sono abilitati solo i due strumenti dell’account. |
| **[!UICONTROL Test]** segnala un connettore personale con lo stesso nome | Un connettore personale con lo stesso nome può avere la precedenza sul connettore dell’organizzazione. Seguire le istruzioni visualizzate per rimuovere o rinominare solo il connettore personale in conflitto, con l&#39;approvazione del proprietario. |
| Il popup di accesso è bloccato, non termina o lo stato non viene aggiornato | Consenti la finestra a comparsa, quindi torna a Collaboratore per controllare lo stato ed eventuali dettagli dell’errore. Non presumere che l’operazione sia riuscita perché il pop-up ha chiuso o mostrato una pagina di destinazione. |
| Uno strumento va in timeout oppure è necessario accedere ripetutamente | Controllare il timeout dello strumento **[!UICONTROL di 60 secondi]**, i dettagli dell&#39;errore, la disponibilità di rete e di [!DNL Amazon] e la configurazione dell&#39;app. |
| Il collaboratore indica che la configurazione non è abilitata o che è ancora in corso la configurazione di un nuovo segreto | Controlla lo stato con il tuo rappresentante Adobe. Non creare le credenziali più volte e non trattare un salvataggio non riuscito come un successo. |

Quando contatti il supporto, includi solo il testo dell’errore, l’ora dell’errore, l’ambiente, l’area selezionata e l’opzione dell’applicazione OAuth. Non condividere segreti dell’app, token di accesso, codici di autorizzazione, intestazione dell’autorizzazione, parametri di query di consenso o reindirizzamento o dati dell’account cliente.
