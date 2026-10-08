---
title: Dati onboarding con il collaboratore
description: Scopri come utilizzare l’abilità di onboarding dei dati in CX Coworker per integrare nuove origini dati in Adobe Experience Platform tramite un flusso di lavoro conversazionale.
hide: true
source-git-commit: 8f7d5307b1928c052f020ca5e7aae3feee7af03e
workflow-type: tm+mt
source-wordcount: '557'
ht-degree: 2%
---

# Dati onboarding con il collaboratore

>[!AVAILABILITY]
>
>L’abilità di onboarding dei dati è in versione beta. La documentazione e le funzionalità sono soggette a modifiche.
>
>L’abilità di onboarding dei dati è disponibile per i clienti che hanno accesso ad Adobe CX Enterprise Coworker, dove deve essere abilitata anche per la tua organizzazione. <!-- VERIFY BEFORE PUBLISH: confirm exact permission/entitlement name with Umesh Gohil, PLAT-296546. -->

Utilizza l’abilità di onboarding dei dati in CX Coworker per integrare nuovi dati in Adobe Experience Platform tramite un unico flusso di lavoro di conversazione. Invece di navigare in più schermate per connettere un’origine e creare uno schema manualmente, descrivi l’intento e Collaboratore ti guida attraverso la selezione dell’origine, la qualità dei dati, l’arricchimento semantico, la mappatura dello schema, la creazione di schemi e la creazione di flussi di dati.

<!-- VERIFY BEFORE PUBLISH: confirm the loaded skill name ("Onboard Data to Experience Platform") and the exact post-landing prompt/flow with Umesh Gohil once flag access is arranged. -->

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di avere:

- Accesso a Adobe Experience Platform e all’organizzazione e alla sandbox appropriate.
- Accedi ad Adobe CX Enterprise Coworker con l’abilità di onboarding dei dati abilitata per la tua organizzazione.
- Autorizzazione a creare schemi in Adobe Experience Platform.

Per istruzioni sull&#39;installazione dei plug-in, consulta la [Guida dell&#39;interfaccia utente di Coworker](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Utilizzare l’abilità di onboarding dei dati {#use-the-data-onboarding-skill}

Oggi, l’abilità di onboarding dei dati inizia dalla creazione dello schema nell’interfaccia utente di Experience Platform, che apre Collaboratore con l’intento già compilato.

Per utilizzare l’abilità di onboarding dei dati:

1. In Adobe Experience Platform, passa a **[!UICONTROL Schemi]**, quindi seleziona **[!UICONTROL Crea schema]**.
1. Nella finestra di dialogo **[!UICONTROL Crea schema]**, seleziona **[!UICONTROL Dati incorporati con IA]**, quindi seleziona **[!UICONTROL Seleziona]**.

   ![Finestra di dialogo Crea schema con dati onboard con opzione AI selezionata.](./assets/data-onboarding-skill/create-a-schema-dialog.png)

1. CX Coworker si apre in una nuova scheda del browser con un prompt precompilato dall’intento di creazione dello schema, quindi non è necessario aggiornarlo.
1. Scegliere un&#39;origine da cui eseguire l&#39;onboarding quando richiesto, ad esempio [!DNL Amazon S3], [!DNL Data Landing Zone], [!DNL Delta Share] o [!DNL Marketo].

   <!-- VERIFY BEFORE PUBLISH: screenshot of the Coworker landing/session-start state does not exist yet anywhere. Capture once flag access is confirmed. -->

1. Continua la conversazione con Collaborator attraverso la revisione della qualità dei dati, l’arricchimento semantico, la mappatura dello schema e la creazione di schemi, confermando ogni passaggio mentre procedi.

Per ulteriori informazioni sull&#39;utilizzo di CX Coworker, vedere la [Guida dell&#39;interfaccia utente di Coworker](https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Casi d’uso supportati {#supported-use-cases}

Esplora le parti del flusso di lavoro di onboarding che l’abilità di onboarding dei dati ti aiuta a completare.

### Selezionare e connettere un&#39;origine

Invece di individuare e configurare manualmente un connettore di origine, descrivi i dati da inserire e lascia che sia Collaborator a identificare la sorgente corretta.

### Verificare la qualità dei dati

I segnali di qualità dei dati per l’origine selezionata vengono messi in superficie dal collaboratore prima che venga eseguito il commit a uno schema, in modo da poter individuare i problemi in una fase precedente del processo.

### Arricchire i dati semanticamente

Coworker suggerisce un significato semantico per i campi in arrivo, riducendo il lavoro manuale di mappatura dei campi non elaborati alle definizioni standard.

### Mappare e creare uno schema

I campi revisionati vengono mappati da Collaborator su uno schema nuovo o esistente e vengono creati direttamente in Adobe Experience Platform nell’ambito della stessa conversazione.

### Creare un flusso di dati

Cooker completa l’onboarding creando il flusso di dati necessario per inserire i dati su base continuativa.

## Passaggi successivi {#next-steps}

Dopo aver letto questa guida, scopri come avviare l’abilità di onboarding dei dati dalla creazione dello schema e cosa ti aiuta a ottenere in CX Coworker.

Per la procedura dell&#39;interfaccia utente di Experience Platform e gli scenari di accesso/idoneità, vedi [Dati onboard con IA](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/schemas#data-onboarding-skill) nella guida dell&#39;interfaccia utente degli schemi.
