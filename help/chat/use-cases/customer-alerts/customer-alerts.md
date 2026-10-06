---
title: Abilità di avviso cliente
description: Scopri come utilizzare le abilità di avviso dei clienti in CX Coworker per rivedere, analizzare e assegnare priorità alle attività di avviso tramite conversazioni in linguaggio naturale.
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1014'
ht-degree: 4%
---

# Competenze di avviso cliente

>[!AVAILABILITY]
>
> Le abilità di avviso del cliente sono disponibili per tutti i clienti con accesso ad Adobe CX Enterprise Coworker.
>
> Per utilizzare le Abilità per gli avvisi dei clienti, devi avere accesso agli avvisi di Adobe Experience Platform e alle risorse associate a tali avvisi.

Utilizza le abilità di avviso del cliente in CX Coworker per trasformare l’attività di avviso in un briefing operativo personalizzato. Rivedi gli avvisi recenti, individua i problemi ad alta priorità, capisci quali risorse sono interessate e concentra gli sforzi di indagine attraverso conversazioni in linguaggio naturale.

Le abilità di avviso del cliente consentono di passare dai segnali di avviso a informazioni fruibili senza rivedere manualmente le visualizzazioni degli avvisi o correlare le informazioni tra più interfacce. Inizia con una domanda ampia sulle recenti attività di avviso, quindi utilizza le domande di follow-up per identificare pattern di avviso ricorrenti, analizzare gli oggetti interessati e concentrarsi sugli avvisi di tua proprietà.

Per informazioni sugli avvisi dei clienti, consulta la [Panoramica sugli avvisi dei clienti](https://experienceleague.adobe.com/it/docs/experience-platform/observability/alerts/overview).

## Prerequisiti {#prerequisites}

Prima di iniziare, assicurati di avere:

- Accesso a Adobe Experience Platform.
- Autorizzazione a visualizzare gli avvisi relativi alla tua organizzazione.
- Il plug-in Adobe CXO installato in CX Coworker.

Per istruzioni sull&#39;installazione dei plug-in, consulta la [Guida dell&#39;interfaccia utente di Coworker](../../ui-guide.md).

## Utilizza le abilità di avviso del cliente {#use-customer-alert-skills}

Interagisci con le abilità di avviso del cliente tramite CX Coworker utilizzando richieste in linguaggio naturale. Poni domande su attività di avviso, abbonamenti, tendenze degli avvisi o oggetti interessati. Continua la conversazione con le domande di follow-up per perfezionare i risultati e focalizzare l’analisi.

Per utilizzare le Abilità per gli avvisi dei clienti:

1. Passa a **[!UICONTROL CX Coworker]**.

1. Immettere una domanda o una richiesta relativa agli avvisi. Ad esempio:

   *&quot;Elencare tutti gli avvisi attivati nelle ultime 24 ore?&quot;*

   ![La prima domanda posta in CX Coworker](./assets/alerts/initial-question.png)

1. Rivedi i risultati restituiti dalle abilità di avviso del cliente.

   ![La tabella dei risultati è stata restituita dalla domanda iniziale.](./assets/alerts/results-table.png)

1. Affina i risultati con le domande di follow-up. Ad esempio:

   *&quot;Mostra i primi 3 tipi di avvisi attivati nelle ultime 24 ore.&quot;*

   ![Risultati perfezionati che mostrano i primi tre tipi di avvisi.](./assets/alerts/alert-types.png)

1. Continuare a restringere l&#39;ambito fino a identificare gli avvisi, i modelli o gli oggetti interessati che richiedono attenzione. Ad esempio:

   *&quot;Elenca i primi 5 oggetti interessati dagli avvisi di gravità elevata&quot;*

   ![Risultati perfezionati che mostrano i primi cinque oggetti interessati.](./assets/alerts/objects-impacted.png)

Le abilità di avviso del cliente mantengono un contesto conversazionale che consente di passare dall’attività di avviso a un’indagine mirata senza ripetere le richieste precedenti.

## Casi d’uso supportati {#supported-use-cases}

Utilizza le abilità di avviso del cliente per monitorare l’attività operativa, esaminare i problemi e concentrarsi sugli avvisi più rilevanti per il tuo ruolo.

### Rivedi attività di avviso

Rivedere lo stato di avviso corrente o analizzare l&#39;attività di avviso cronologico in un determinato periodo di tempo.

Ad esempio:

- &quot;Quali avvisi sono stati attivati nelle ultime 24 ore?&quot;
- &quot;Mostra gli avvisi attivi degli ultimi sette giorni&quot;

### Identificare i pattern ricorrenti degli avvisi

Esaminare la cronologia degli avvisi per identificare i tipi di avvisi che si verificano più frequentemente nell&#39;organizzazione. Invece di rivedere un numero elevato di singoli eventi di avviso, utilizza le abilità di avviso del cliente per riepilogare i pattern ricorrenti ed evidenziare le aree che possono richiedere attenzione.

Ad esempio:

- &quot;Visualizza i primi 3 tipi di avviso attivati.&quot;
- &quot;Quali tipi di avvisi si sono verificati più frequentemente questo mese?&quot;

### Concentrarsi su questioni ad alta priorità

Limitare i risultati a un livello di gravità specifico per dare priorità agli sforzi di indagine.

Ad esempio:

- &quot;Mostra solo avvisi con priorità elevata.&quot;
- &quot;Quali avvisi critici sono stati attivati questa settimana?&quot;

### Comprendere il raggio di impatto degli avvisi

Identifica gli oggetti più frequentemente interessati e capisce da dove iniziare l’indagine.

Le abilità di avviso del cliente analizzano l’attività di avviso e presentano gli oggetti associati a avvisi ricorrenti o di alta gravità, consentendoti di concentrarsi sulle aree con il maggiore impatto operativo.

Ad esempio:

- &quot;Quali sono i primi 5 oggetti interessati?&quot;
- &quot;Quali oggetti sono associati agli avvisi con maggiore gravità?&quot;

### Connettere i tipi di avviso agli oggetti interessati

Comprendere come l’attività di avviso influisce su risorse specifiche.

Le abilità di avviso del cliente collegano gli oggetti interessati ai tipi di avviso che li hanno attivati, consentendo di identificare i modelli e determinare la probabile origine dei problemi operativi.

Ad esempio:

- &quot;Quali tipi di avviso hanno interessato più spesso questo set di dati?&quot;
- &quot;Mostra la relazione tra i tipi di avviso e gli oggetti interessati.&quot;
- &quot;Quale tipo di avviso ha interessato più frequentemente l’oggetto maggiormente interessato?&quot;

### Concentrati sugli avvisi personali

Analizza gli avvisi a cui sei abbonato e sei responsabile del monitoraggio.

Utilizza l&#39;esperienza [!DNL My Alerts] per rivedere le attività recenti, assegnare la priorità ai problemi di alta gravità e focalizzare l&#39;analisi operativa sugli avvisi più rilevanti per il tuo ruolo.

Ad esempio:

- &quot;Visualizzami gli avvisi di alta gravità a cui mi abbono&quot;.
- &quot;Quali avvisi da [!DNL My Alerts] sono stati attivati questa settimana?&quot;
- &quot;È necessario prestare attenzione a uno degli avvisi sottoscritti?&quot;

### Gestire gli abbonamenti agli avvisi

Controlla e gestisci gli abbonamenti agli avvisi tramite conversazioni in linguaggio naturale.

Ad esempio:

- &quot;A quali avvisi sono abbonato?&quot;
- &quot;Iscrivetemi a questo avviso.&quot;
- &quot;Rimuovi la sottoscrizione all&#39;avviso.&quot;

## Esempi di prompt {#example-prompts}

Utilizza i seguenti prompt come esempi quando interagisci con le abilità di avviso del cliente.

### Prompt attività avvisi

- &quot;Cosa è successo nelle ultime 24 ore?&quot;
- &quot;Quali avvisi sono stati attivati nelle ultime 24 ore?&quot;
- &quot;Mostra tutti gli avvisi attivati questa settimana&quot;.
- &quot;Sono presenti avvisi attivi?&quot;

### Prompt delle tendenze degli avvisi

- &quot;Visualizza i primi 3 tipi di avviso attivati.&quot;
- &quot;Quali tipi di avvisi si sono verificati più frequentemente questo mese?&quot;
- &quot;Quali pattern di allarme si sono verificati negli ultimi sette giorni?&quot;

### Richieste di analisi della gravità

- &quot;Mostra solo avvisi con priorità elevata.&quot;
- &quot;Mostra gli avvisi critici degli ultimi 30 giorni&quot;
- &quot;Quali avvisi di alta gravità si sono verificati più frequentemente?&quot;

### Prompt dell’analisi di impatto

- &quot;Quali sono i primi 5 oggetti interessati?&quot;
- &quot;Quali oggetti sono associati al maggior numero di avvisi?&quot;
- &quot;Mostra la relazione tra i tipi di avviso e gli oggetti interessati.&quot;
- &quot;Quale tipo di avviso ha interessato più frequentemente l’oggetto maggiormente interessato?&quot;

### I miei prompt di Alert

- &quot;Visualizzami gli avvisi di alta gravità a cui mi abbono&quot;.
- &quot;Quali avvisi da [!DNL My Alerts] sono stati attivati questa settimana?&quot;
- &quot;Al momento sono attivi alcuni degli avvisi a cui mi sono iscritto?&quot;
- &quot;È necessario prestare attenzione a uno degli avvisi sottoscritti?&quot;

### Prompt di gestione delle sottoscrizioni

- &quot;A quali avvisi sono abbonato?&quot;
- &quot;Iscrivetemi a questo avviso.&quot;
- &quot;Rimuovi la sottoscrizione all&#39;avviso.&quot;

## Passaggi successivi {#next-steps}

Dopo aver letto questa guida, sarai in grado di utilizzare le abilità di segnalazione clienti in CX Coworker per rivedere l’attività di segnalazione, analizzare le tendenze degli avvisi, gestire gli abbonamenti agli avvisi e analizzare i problemi operativi attraverso conversazioni in linguaggio naturale.

Per ulteriori informazioni sugli avvisi, vedere [Panoramica sugli avvisi dei clienti](https://experienceleague.adobe.com/it/docs/experience-platform/observability/alerts/overview).
