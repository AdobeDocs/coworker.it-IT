---
title: Connettore esterno Infobip Observe
description: Scopri come impostare il connettore esterno Infobip Observe in CX Enterprise Coworker per la tua organizzazione e come accedere con Infobip per utilizzare gli strumenti Observe.
role: Admin, User
level: Beginner
badgeBeta: label="Beta" type="Informative" tooltip="Questo connettore è in versione beta."
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
hide: true
source-git-commit: 382a5f6fd629b8b10468c0cfe4d41f050a7f3725
workflow-type: tm+mt
source-wordcount: '1458'
ht-degree: 1%
---

# Connettore esterno Infobip Observe {#infobip-observe}

Utilizza il connettore esterno [!DNL Infobip Observe] per esaminare il traffico e i costi di [!DNL Infobip] in Adobe CX Enterprise Coworker. Dopo aver configurato il connettore, chiedi al collega le metriche del traffico, l’utilizzo della fatturazione, i registri dei messaggi e i codici di stato e di errore. Il connettore è il server MCP (Model Context Protocol) [!DNL Observe] ospitato da [!DNL Infobip].

>[!AVAILABILITY]
>
>Il connettore esterno [!DNL Infobip Observe] è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.

## Configurazione del connettore {#connector-configuration}

Il processo di configurazione del connettore è costituito da due parti separate:

* **Configurazione organizzazione:** Un amministratore configura il connettore una sola volta per l&#39;intera organizzazione e approva gli strumenti che i membri possono utilizzare.
* **Accesso membro:** Ogni membro effettua l&#39;accesso con il proprio account [!DNL Infobip]. I membri possono accedere solo ai dati che il loro account [!DNL Infobip] dispone dell&#39;autorizzazione per utilizzare.

Al connettore non è associata alcuna organizzazione condivisa. Ogni membro che utilizza il connettore effettua l&#39;accesso separatamente. Il salvataggio della configurazione dell&#39;organizzazione non comporta l&#39;accesso ad alcun membro né la concessione di ulteriori autorizzazioni [!DNL Infobip].

## Prerequisiti {#prerequisites}

Il connettore funziona solo con il server MCP [!DNL Infobip] [!DNL Observe]. Non si connette ai server MCP di messaggistica, provisioning o gestione account di [!DNL Infobip].

Prima di iniziare, assicurati di disporre dei seguenti elementi:

* **Accesso collaboratore:** account con autorizzazione per la gestione dei connettori organizzazione in un&#39;organizzazione in cui è disponibile il connettore [!DNL Infobip Observe].
* Account **[!DNL Infobip]:** account [!DNL Infobip] approvato con accesso a [!DNL Observe] nel data center previsto. [!DNL Infobip] offre [!DNL Observe] MCP come funzionalità di accesso anticipato. Conferma l&#39;adesione e l&#39;idoneità dell&#39;account con [!DNL Infobip].
* **Identità membro:** membri con i propri account [!DNL Infobip] e le autorizzazioni per accedere ai dati previsti.
* **Ambito approvato per il test:** Ambito di test approvato e dati non sensibili prima di eseguire query sui registri di fatturazione, traffico o messaggi.

Per testare il connettore, è possibile registrarsi per un account di prova gratuito [!DNL Infobip]. Un account di prova non garantisce l&#39;isolamento dei dati o l&#39;azzeramento dei costi. Per ulteriori informazioni, vedere [Utilizzo dei server MCP di Infobip](https://www.infobip.com/docs/mcp/using-mcp){target="_blank"} e [Osservare MCP](https://www.infobip.com/docs/mcp/observe-mcp){target="_blank"} nella documentazione di [!DNL Infobip].

>[!IMPORTANT]
>
>Non condividere mai password, chiavi API, token, codici di autorizzazione o URL di consenso e callback in schermate, chat o ticket di supporto.

## Modello di connessione e accesso {#connection-model}

Il collaboratore applica automaticamente le seguenti impostazioni. Non crei un&#39;app OAuth né immetti le credenziali dell&#39;app.

| Impostazione | Valore |
| --- | --- |
| URL server | `https://mcp.infobip.com/observe` |
| Trasporto | HTTP semplificabile |
| Individuazione server di autorizzazione | `https://mcp.infobip.com/observe/.well-known/oauth-authorization-server` |
| Accedi | Ogni membro accede con OAuth utilizzando la registrazione client dinamica |
| Configurazione OAuth | Individuato automaticamente. Gli amministratori non immettono un ID client, un segreto client, ambiti o endpoint OAuth. |
| Selezione dello strumento | Quattro strumenti approvati. Gli amministratori possono restringere la selezione. |

L&#39;individuazione di [!DNL Infobip] e il consenso di ciascun membro determinano l&#39;accesso ricevuto da Collaborator. [!DNL Infobip] documenta gli ambiti `billing:usage:view`, `metrics:manage`, `messages-api:manage` e `error-codes:read` per [!DNL Observe] MCP. Rivedi l’accesso richiesto nella schermata di consenso prima di approvare.

[!DNL Infobip] supporta anche l&#39;autenticazione della chiave API per [!DNL Observe] MCP in altri client MCP. Cooker non utilizza le chiavi API per questo connettore. I membri effettuano l’accesso solo con OAuth.

## Configurare il connettore per l’organizzazione {#configure-organization}

Gli amministratori rendono il connettore [!DNL Infobip Observe] disponibile a tutti gli utenti dell&#39;organizzazione. Le modifiche apportate alla pagina dell’organizzazione vengono applicate a tutti gli utenti dell’organizzazione. I membri non possono configurare la connessione dell&#39;organizzazione.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Organizzazione]**, quindi seleziona **[!UICONTROL Connettori esterni]**.

1. Trovare **[!UICONTROL Infobip Observe]**, quindi selezionare **[!UICONTROL Configure]**.

1. Nella finestra di dialogo **[!UICONTROL Connetti Infobip Observe]**, controlla il **[!UICONTROL URL server]**, `https://mcp.infobip.com/observe` corretto.

   Non è necessario immettere un ID client OAuth, un segreto client o ambiti.

1. In **[!UICONTROL Strumenti disponibili per gli utenti]**, esaminare i quattro strumenti selezionati inizialmente. Rimuovi gli strumenti che i membri dell’organizzazione non devono utilizzare. Deve rimanere almeno uno strumento.

   Per ulteriori informazioni, vedere [Strumenti disponibili](#available-tools).

   ![Finestra di dialogo Connect Infobip Observe che mostra l&#39;URL del server, i quattro strumenti disponibili per gli utenti, l&#39;avviso di accesso e autorizzazioni e le impostazioni di autenticazione OAuth, connessione HTTP e timeout dello strumento di 60 secondi.](./assets/infobip-observe/org-configure.png){width="500" zoomable="yes"}

1. Seleziona **[!UICONTROL Salva connessione]**. Quindi riapri la configurazione per verificare che la selezione dello strumento persista.

Il salvataggio non comporta l&#39;accesso né per te né per alcun membro a [!DNL Infobip]. Per controllare la connessione, accedere come descritto in [Accedere come membro](#sign-in-as-a-member).

Per rendere nuovamente disponibili tutti e quattro gli strumenti dopo averne rimossi, selezionare **[!UICONTROL Ripristina tutti gli strumenti]**. Questa opzione ripristina solo i quattro strumenti approvati. Collaboratore non abilita gli strumenti aggiunti in seguito da [!DNL Infobip]. Non è possibile salvare la configurazione senza aver selezionato alcuno strumento.

### Strumenti disponibili {#available-tools}

Il connettore [!DNL Infobip Observe] fornisce i seguenti strumenti. [!DNL Infobip] può modificare i limiti di ogni strumento, quindi controlla la documentazione di [!DNL Infobip] prima di fare affidamento su di essi.

| Strumento | Scopo | Limiti |
| --- | --- | --- |
| `get_traffic_performance_metrics` | Metriche aggregate di traffico, consegna e coinvolgimento. | Fino a 366 giorni di dati. Le finestre orarie coprono fino a 14 giorni e quelle giornaliere fino a 93 giorni. Restituisce i dati per l&#39;account connesso per impostazione predefinita. Includi esplicitamente i conti secondari. |
| `get_billing_usage_costs` | Utilizzo e costi allineati con le fatture. | I due mesi di calendario corrente e precedente. Include la gerarchia completa dell’account per impostazione predefinita. I dati per un mese sono provvisori fino al quinto giorno del mese successivo. |
| `get_message_logs` | Registra i singoli messaggi. | Le ultime 48 ore. I registri possono includere identificatori dei destinatari, informazioni personali e contenuto dei messaggi. |
| `look_up_status_and_error_codes` | Descrizione dello stato noto e nomi dei codici di errore. | Fino a 50 nomi per richiesta. [!DNL Infobip] può omettere nomi sconosciuti dai risultati. |

I risultati sono limitati a un centro dati [!DNL Infobip]. La selezione degli strumenti controlla quali strumenti possono essere utilizzati dai membri in Collaborator. Non limita l&#39;accesso [!DNL Infobip] concesso dai membri all&#39;accesso, la gerarchia di account o le autorizzazioni applicate da [!DNL Infobip].

>[!IMPORTANT]
>
>I registri dei messaggi possono contenere dati personali, ad esempio identificatori dei destinatari e contenuto del messaggio. Per impostazione predefinita, le informazioni di fatturazione sono riservate e coprono l’intera gerarchia dell’account. Abilita questi strumenti solo quando l’organizzazione ne approva l’utilizzo. Utilizza filtri di account e query limitate esplicite e approvate.

## Accedi come membro {#sign-in-as-a-member}

Dopo che un amministratore ha configurato il connettore, ogni membro accede con il proprio account [!DNL Infobip]. L&#39;accesso appartiene solo a te. Gli altri membri non utilizzano le credenziali dell&#39;utente.

1. Apri **[!UICONTROL Personalizzazioni]**, seleziona **[!UICONTROL Utente]**, quindi seleziona **[!UICONTROL Connettori esterni]**. Trova **[!UICONTROL Infobip Observe]**.

   Se nella scheda è visualizzato **[!UICONTROL Non configurato]** e **[!UICONTROL Non ancora disponibile. L&#39;amministratore deve configurarlo.]**, chiedi all&#39;amministratore di [configurare il connettore](#configure-organization).

1. Seleziona **[!UICONTROL Accedi]** e utilizza l&#39;account [!DNL Infobip] previsto. Completa l’SSO (Single Sign-On), l’autenticazione a più fattori (MFA) e richiede il consenso. Prima di approvare, controlla l’accesso richiesto, l’account e il centro dati.

1. Torna a Collaboratore e apri i dettagli del connettore. Rivedi gli strumenti abilitati dall’amministratore.

   I membri possono visualizzare gli strumenti ma non modificare la configurazione dell&#39;organizzazione.

1. Seleziona **[!UICONTROL Verifica connessione]**.

   Un test riuscito conferma che Collaboratore può connettersi ed elencare gli strumenti. Non conferma che tutti gli strumenti vengano eseguiti correttamente.

1. Se si dispone dell&#39;autorizzazione e l&#39;amministratore ha abilitato lo strumento `look_up_status_and_error_codes`, eseguire la ricerca in [Verificare la connessione](#check-connection).

1. Per disconnettere l&#39;account [!DNL Infobip] dal connettore, selezionare **[!UICONTROL Esci]**.

   La disconnessione non revoca necessariamente l&#39;accesso concesso in [!DNL Infobip].

## Verifica la connessione {#check-connection}

Per verificare che il connettore funzioni con l’account, esegui una ricerca di sola lettura. Verificare che l&#39;amministratore abbia abilitato lo strumento `look_up_status_and_error_codes`. Quindi avvia una chat e immetti un prompt.

Esempio di prompt:

* &quot;Utilizzando Infobip Observe, cerca il codice di stato NO_ERROR e descrivi cosa significa. Non eseguire query sulle metriche del traffico, sulla fatturazione o sui registri dei messaggi.&quot;

Verificare che il risultato includa una descrizione di `NO_ERROR` senza un messaggio di errore. Una ricerca riuscita non conferma che gli strumenti di registro del traffico, di fatturazione o dei messaggi funzionino per il tuo account. Non eseguire query sui registri di fatturazione o di messaggio solo per verificare la connessione.

## Risolvere i problemi di accesso {#troubleshoot-access}

Se non riesci ad accedere ai dati di [!DNL Infobip], verifica quanto segue con il tuo amministratore:

| Problema | Cosa controllare |
| --- | --- |
| Connettore **[!UICONTROL Infobip Observe]** mancante | Verifica che il connettore sia disponibile per la tua organizzazione e di disporre dell’autorizzazione per gestire i connettori dell’organizzazione. Se necessario, contatta il rappresentante Adobe. |
| Consenso o accesso non riuscito | Controlla l&#39;account [!DNL Infobip] utilizzato, il tuo diritto a [!DNL Observe] e il data center. Non condividere l’URL del consenso, l’URL di callback o i codici di autorizzazione quando chiedi aiuto. |
| L&#39;accesso ha esito positivo, ma uno strumento non riesce | Controllare le autorizzazioni [!DNL Infobip] effettive, l&#39;account e il data center con cui hai effettuato l&#39;accesso e l&#39;errore restituito da [!DNL Infobip]. In caso di esito positivo, l’accesso non conferma che uno strumento sia in esecuzione correttamente. |
| Strumento non disponibile | Controlla gli strumenti abilitati dall’amministratore. I nuovi strumenti di [!DNL Infobip] non vengono abilitati automaticamente. |
| Impossibile salvare la configurazione | Mantieni almeno uno strumento selezionato. Per interrompere l’offerta del connettore, rimuovilo. |
| I risultati della fatturazione includono account imprevisti | Per impostazione predefinita, i risultati della fatturazione includono la gerarchia completa dei conti. Arresta, quindi controlla i filtri e le autorizzazioni dell’account approvati. |
| I registri dei messaggi mostrano dati sensibili | Interrompere la query e limitare le query successive a dati approvati e non sensibili. Non incollare i registri non elaborati nelle chat o nei ticket di supporto. |
| La ricerca del codice di stato ha esito positivo, ma un’altra richiesta non riesce | Esaminare separatamente la richiesta non riuscita. Una ricerca corretta non conferma il funzionamento di tutti gli strumenti o account. |
