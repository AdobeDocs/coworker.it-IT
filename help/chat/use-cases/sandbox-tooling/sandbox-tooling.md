---
title: Abilità degli strumenti sandbox
description: Scopri come utilizzare le competenze agente Sandbox Tooling per replicare i metadati dell’oggetto in ambienti sandbox.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%
---

# Competenze degli agenti di gestione degli strumenti sandbox

>[!AVAILABILITY]
>
>Le abilità di agente sandbox sono disponibili per tutti i clienti con accesso ad Adobe CX Enterprise Coworker. Per utilizzare tutte le funzionalità disponibili, è necessario disporre delle seguenti autorizzazioni:
>
>**Gestisci sandbox** o **Visualizza-sandbox**: queste autorizzazioni ti consentono di utilizzare le abilità agente Sandbox per visualizzare le sandbox direttamente in Coworker.
>
>**Gestisci-pacchetto**: questa autorizzazione consente di utilizzare le abilità agente Sandbox per creare pacchetti direttamente in Coworker.

>[!NOTE]
>
>Al momento puoi utilizzare le abilità agente sandbox per individuare, creare pacchetti e migrare oggetti schema e pubblico. Il supporto per altri tipi di oggetti verrà aggiunto nelle versioni future.

Utilizza le abilità agente sandbox per spostare i metadati dell’oggetto, inclusi schemi e tipi di pubblico, tra gli ambienti Adobe Experience Platform descrivendo cosa desideri eseguire in linguaggio naturale. Utilizzando CX Coworker, puoi scoprire i metadati richiesti, identificare automaticamente le dipendenze, creare pacchetti di migrazione ed eseguire la migrazione degli oggetti tramite un’esperienza di conversazione.

>[!VIDEO](https://video.tv.adobe.com/v/3496706?learn=on)

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di avere:

- Accesso a Adobe Experience Platform e all’organizzazione e alla sandbox appropriate.
- Accedere agli oggetti che si desidera individuare o migrare.
- Il plug-in Adobe CXO installato in CX Coworker.

Per istruzioni sull&#39;installazione dei plug-in, consulta la [Guida dell&#39;interfaccia utente di Coworker](https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Usa abilità agente sandbox {#use-sandbox-tooling-agentic-skills}

Interagisci con le abilità degli agenti sandbox tramite CX Coworker utilizzando il linguaggio naturale. Descrivi il tuo obiettivo il più chiaramente possibile. Richieste specifiche producono i risultati migliori, mentre richieste vaghe o troppo brevi possono restituire risultati di qualità inferiore o non richiamare l’agente.

Per utilizzare le abilità agente sandbox:

1. Passa a **[!UICONTROL CX Coworker]**.
1. Immettere una descrizione chiara di ciò che si desidera eseguire. Ad esempio:

   *&quot;Sposta il membro dello schema Fedeltà Platinum dalla sandbox corrente alla sandbox demo Acme.&quot;*

1. Esamina la tabella dei risultati, che mostra le sandbox di origine e di destinazione. Quando sei pronto a continuare, seleziona **[!UICONTROL Procedi]**, quindi seleziona **[!UICONTROL Invia]** per confermare.

   ![I risultati della richiesta con Processo selezionato, evidenziando Invia.](./assets/sandbox-tooling/results-proceed.png)

1. Seleziona uno o più oggetti di cui vuoi eseguire la migrazione, quindi seleziona **[!UICONTROL Invia]**.

   ![Pagina di selezione oggetti con l&#39;evidenziazione Invia.](./assets/sandbox-tooling/object-selection.png)

1. Esaminare gli oggetti e le dipendenze identificati dall&#39;agente e confermare le azioni dell&#39;operazione: *Crea nuovo* o *Usa esistente*. Quando sei pronto per iniziare la migrazione, seleziona **[!UICONTROL Procedi]**, quindi seleziona **[!UICONTROL Invia]** per confermare. Il completamento della migrazione potrebbe richiedere alcuni minuti.

   ![Conferma la pagina del piano d&#39;azione evidenziando Invia.](./assets/sandbox-tooling/action-plan.png)

1. Al termine della migrazione, gli oggetti selezionati saranno disponibili nella sandbox di destinazione.

   ![Pagina Trasferimento completato che mostra lo stato della richiesta.](./assets/sandbox-tooling/transfer-complete.png)

Per ulteriori informazioni sull&#39;utilizzo di CX Coworker, vedere la [Guida dell&#39;interfaccia utente di Coworker](https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/ui-guide).

## Casi d’uso supportati {#supported-use-cases}

Scopri i modi più comuni per utilizzare le competenze degli agenti sandbox per semplificare la gestione delle sandbox e la migrazione dei metadati.

### Spostare i metadati dell’oggetto tra sandbox

In qualità di amministratore sandbox che gestisce più sandbox di Adobe Experience Platform, puoi migrare i metadati dell’oggetto utilizzando richieste in linguaggio naturale anziché navigare manualmente nell’interfaccia utente.

Utilizzando CX Coworker, puoi migrare i metadati dell’oggetto, inclusi schemi, tipi di pubblico e risorse di configurazione correlate, da una sandbox all’altra descrivendo la migrazione in linguaggio naturale. Sandbox Tooling Agent Skills identifica e crea automaticamente un pacchetto delle dipendenze richieste, contribuendo a garantire una migrazione affidabile.

Ad esempio:

- &quot;Sposta lo schema Luma Loyalty Members Platinum dalla sandbox corrente alla sandbox di produzione.&quot;

### Promuovi i tipi di pubblico tra sandbox

In qualità di amministratore sandbox, puoi promuovere i tipi di pubblico tra ambienti senza ricrearli o riconfigurarli manualmente.

Ad esempio:

- &quot;Promuovi il pubblico &quot;Nome pubblico&quot; nella sandbox di staging.&quot;

Le abilità agente sandbox Tooling identificano il pubblico specificato, ne convalidano le dipendenze e migrano tutti gli oggetti richiesti nella sandbox di destinazione.

## Esempi di prompt {#example-prompts}

Utilizza i seguenti prompt come esempi quando interagisci con le abilità agente Sandbox.

### Richieste schema

Utilizza questi prompt quando conosci il nome dello schema e la sandbox di destinazione.

- &quot;Sposta lo schema &quot;Nome schema&quot; dalla sandbox corrente alla sandbox di produzione.&quot;

### Prompt del pubblico

Utilizza questi prompt quando conosci il nome del pubblico.

- &quot;Promuovi il pubblico &quot;Nome pubblico&quot; nella sandbox di staging.&quot;

## Passaggi successivi {#next-steps}

Dopo aver letto questa guida, scopri come utilizzare le abilità agente Sandbox per individuare, creare pacchetti e migrare gli oggetti supportati tra le sandbox.

Per ulteriori informazioni sugli strumenti sandbox, consulta la [Guida agli strumenti sandbox](https://experienceleague.adobe.com/it/docs/experience-platform/sandbox/ui/sandbox-tooling).

