---
title: Generare un elenco di controllo dell’implementazione nei progetti di collaborazione
description: Scopri in che modo Progetti coorker genera un elenco di controllo per l’implementazione precompilato dal piano Guide all’implementazione, con passaggi da assegnare e tracciare.
hold: true
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 1%
---

# Generare un elenco di controllo per l’implementazione con Progetti del collaboratore

I progetti collaboratore possono generare un progetto Elenco di controllo dell’implementazione, precompilato con i passaggi ordinati del piano della guida all’implementazione per Customer Journey Analytics, un aggiornamento da Adobe Analytics a Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) o Streaming Media. Cooker automatizza o fornisce assistenza con il maggior numero di passaggi tecnicamente possibile, in modo che tu e il tuo team possiate trovare un’unica posizione tracciabile in cui lavorare attraverso l’implementazione.

Se stai conducendo un’implementazione, eseguendo passaggi tecnici o semplicemente hai bisogno di visibilità sull’avanzamento, puoi utilizzare questo elenco di controllo per assegnare lavoro, tenere traccia dello stato e collaborare con il team, senza uscire da Collaboratore.

>[!NOTE]
>
>Considera i seguenti aspetti:
>
>* Questa funzione fa parte di un flusso di lavoro facoltativo più ampio: implementazione personalizzata o passaggi di aggiornamento (vedi [Pianificare l&#39;implementazione con Coworker](./implementation-guide.md)), implementazione (questa lista di controllo) e convalida (ad esempio, [Convalidare l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](./data-validation-aa-cja.md) o [Convalidare l&#39;implementazione di Streaming Media](./streaming-media-validation.md)). Non è necessario utilizzare tutte e tre le fasi, ma la generazione di questo elenco di controllo richiede un piano di guida all’implementazione completato.
>* I passaggi eseguiti o assistiti da Collaboratore includono automaticamente un segnale di affidabilità o di verifica. Rivedi questi passaggi prima di contrassegnarli come completati: in Collaboratore non vengono presentati risultati automatizzati come fatti verificati.

Utilizzare questo elenco di controllo per:

* Avvia un’implementazione o una migrazione con un set di passaggi precompilato e ordinato per il percorso del prodotto, invece di assemblare manualmente un piano.

* Controlla lo stato dell’implementazione a metà, compresi gli elementi bloccati e quelli successivi, senza chiedere direttamente al lead dell’implementazione.

* Pianifica un’implementazione multi-piattaforma o multi-regione, in cui le fasi vengono eseguite in parallelo o in più fasi anziché su una singola linea retta.

* Se possibile, lascia che sia Collaborator a eseguire direttamente i passaggi, ad esempio eseguire un controllo di convalida tra le configurazioni di Adobe Analytics e Customer Journey Analytics.

* Introdurre i gate di approvazione per i passaggi che richiedono l’approvazione prima che il team possa procedere.


## Prima di iniziare

<!-- FLAG: Open question — release note confirms a "predefined playbook" transforms the guide plan into a Coworker Project, but it's unconfirmed whether Coworker runs that playbook automatically or the user has to trigger/follow it manually. Written below as if Coworker does it automatically; verify before publishing. Exact UI mechanics also unconfirmed since Coworker Projects platform documentation doesn't exist yet. -->

### Informazioni necessarie

Per generare un elenco di controllo dell’implementazione, è necessario:

* Una conversazione completata sulla guida all’implementazione per il percorso del prodotto. Vedi [Pianifica la tua implementazione con Coworker](./implementation-guide.md). Coworker trasforma automaticamente questo piano in un progetto Coworker, utilizzando un playbook predefinito, senza dover esportare nulla da solo.

* Accedi ai progetti di collaborazione nella tua organizzazione.

### Limitazioni

Prima di utilizzare questa funzione, tieni presente quanto segue:

* **Il contenuto della guida non è di proprietà**: questa funzionalità utilizza i piani dalle abilità della guida all&#39;implementazione. Non crea né gestisce il contenuto sottostante.
* **Il comportamento di sincronizzazione non è ancora completamente definito**: l&#39;elenco di controllo è destinato a rimanere sincronizzato con gli aggiornamenti al piano della guida all&#39;implementazione, ma il meccanismo di sincronizzazione esatto è ancora in fase di definizione. Controlla manualmente la disponibilità di aggiornamenti del piano guida se l’implementazione si estende su un lungo arco temporale.
* **Richiede progetti Coworker**: questa funzionalità dipende dalla disponibilità della piattaforma Progetti Coworker nell&#39;organizzazione.

## Generare un elenco di controllo

<!-- FLAG: Best guess, not confirmed by source docs. Coworker Projects UI isn't documented in this repo yet — verify exact navigation and UI labels once available. -->

1. Accedi a Collaboratore.

1. Seleziona [!UICONTROL **Progetti**] nella barra di navigazione.

1. Seleziona [!UICONTROL **Nuovo progetto**], quindi seleziona il playbook predefinito che corrisponde al piano della guida all&#39;implementazione.

   Collaboratore trasforma il piano in un progetto precompilato con i passaggi ordinati per il percorso.

## Esaminare i risultati

Collaboratore genera l’elenco di controllo dell’implementazione come progetto collaboratore dal quale tu e il tuo team potete lavorare.

**Visualizzazione progetto**

Il progetto raggruppa i passaggi di implementazione ordinati dal piano. Per ogni passaggio è possibile:

* Assegna un proprietario
* Stato dell’aggiornamento, ad esempio in corso o completato
* Contrassegna un passaggio come non applicabile o saltalo se non si applica alla tua implementazione
* Aggiungere commenti e collaborare con il team
* Richiedi approvazione prima che un passaggio sia considerato completo, per i passaggi che richiedono l’approvazione

**Passaggi automatizzati e assistiti**

Se tecnicamente fattibile, Customer Workfront esegue o assiste direttamente un passaggio, ad esempio la configurazione di visualizzazione o i dati sullo stato da Adobe Analytics o Customer Journey Analytics. Questi passaggi includono un segnale di affidabilità o di verifica, come descritto sopra.

**Esportazioni**

Esporta l’elenco di controllo o il relativo avanzamento a livello di riepilogo in Jira, Workfront o Excel, in modo da poterlo inserire nel flusso di lavoro di gestione dei progetti esistente.

**Elenchi di controllo multipli**

Se gestisci più implementazioni simultanee, ad esempio più suite di rapporti, aree geografiche o marchi, puoi gestire più progetti Elenco di controllo dell’implementazione invece di limitarti a uno solo.
