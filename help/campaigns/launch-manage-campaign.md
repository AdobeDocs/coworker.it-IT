---
description: Scopri come avviare una campagna, pianificare quando viene avviata e con quale frequenza e interrompere definitivamente una campagna in tempo reale che sta inviando attivamente.
title: Avviare e gestire una campagna
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%
---
# Avviare e gestire una campagna {#launch-campaign}

Dopo aver creato la campagna, scopri come avviarla, pianifica quando viene avviata e, se necessario, interrompila.

>[!AVAILABILITY]
>
>Launch campaign è attualmente disponibile solo per gli utenti nelle aree geografiche del Nord America.

## Avviare una campagna

1. Nella campagna completata, fai clic su **Rivedi e avvia**.

   >[!NOTE]
   >
   >Se manca qualcosa, viene visualizzata una finestra di dialogo in cui sono elencati gli elementi da completare. Apportare le correzioni e selezionare di nuovo **Rivedi e avvia**.

1. Dopo che la campagna ha superato il controllo di fattibilità, si apre la finestra di dialogo di lancio con un’anteprima dell’e-mail e del pubblico.

1. Rivedi la pianificazione mostrata nella finestra di dialogo. Per modificarlo, usa le opzioni di pianificazione descritte in [Pianifica all&#39;avvio di una campagna](#schedule-when-a-campaign-launches), quindi fai clic su **Salva**.

1. Al termine, fai clic su **Avvia campagna**.

>[!NOTE]
>
>- Non è possibile avviare una campagna con un pubblico di esempio (non reale), bozze di e-mail non ancora verificate o impostazioni di invio non configurate.
>
>- Se pianifichi una campagna, puoi comunque modificarla prima del suo lancio. Non è necessario passare alla modalità bozza.

## Pianificare l’avvio di una campagna {#schedule-when-a-campaign-launches}

Quando avvii una campagna, puoi scegliere esattamente quando viene avviata: immediatamente, in una data e un’ora future specifiche o in una pianificazione ricorrente. Puoi anche tornare più tardi e modificare la pianificazione di una campagna già avviata o pianificata.

### Prerequisiti

La campagna deve essere pronta per il lancio (configurazione completa).

### Pianificare una campagna al lancio

1. Dalla campagna, fai clic su **Rivedi e avvia**.

1. Nella finestra di dialogo di avvio, scegli un’opzione di pianificazione:
   - **Ora**: la campagna inizia l&#39;invio subito dopo il lancio.
   - **Pianifica una volta**: scegli una **data di inizio** futura (data e ora insieme).
   - **Ricorrente**: scegli una **Frequenza** (Giornaliera, Settimanale o Mensile) e un&#39;ora di inizio, quindi imposta il criterio di ricorrenza (vedi campi di seguito).

1. Se è selezionata l&#39;opzione Ricorrente, scegliere se la campagna termina **Mai** o **In una data** e scegliere una data di fine, se applicabile.

1. Conferma di avviare la campagna con la pianificazione selezionata.

### Modificare una pianificazione esistente

1. Apri la campagna e vai alle relative impostazioni.

1. Individuare la sezione relativa alla programmazione e selezionare il sintetico della programmazione corrente.

1. Aggiorna la pianificazione utilizzando le stesse opzioni descritte in precedenza.

1. Salva la modifica.

### Campi di input

| Campo | Descrizione | Obbligatorio |
| --- | --- | --- |
| Modalità Schedule | Scelta tra Now (Ora), Schedule (Pianifica) una volta o Recurring (Ricorrente) | Sì |
| Data di inizio | Data e ora di inizio della campagna (modalità Pianifica una volta) | Sì, per programmare una volta |
| Frequenza | Giornaliero, Settimanale o Mensile (modalità Ricorrente) | Sì, per ricorrente |
| Ora di inizio | Ora del giorno inviata dalla campagna ricorrente | Sì, per ricorrente |
| Giorni della settimana | Giorni in cui si ripete la campagna | Sì, per frequenza settimanale |
| Giorno del mese | Giorno del mese in cui si ripete la campagna | Sì, per frequenza mensile |
| Fine campagna | Mai, o in una data di fine specifica | Sì, per ricorrente |

### Aspetti da considerare

- È possibile impostare l’esecuzione di campagne ricorrenti per un periodo di tempo indefinito o fino a una data di fine specifica. Le campagne una tantum e immediate non dispongono di un’opzione di data di fine, in quanto vengono eseguite una volta.
- La pianificazione non supporta intervalli di ripetizione personalizzati, ad esempio &quot;ogni 2 settimane&quot; o &quot;ogni 3 giorni&quot;. Inoltre, non supporta la ricorrenza mensile relativa, ad esempio &quot;il secondo lunedì del mese&quot;.

## Interrompere una campagna {#stop-campaign}

Puoi interrompere una campagna che invia attivamente (una campagna &quot;live&quot;) direttamente dalla pagina dei dettagli della campagna.

>[!CAUTION]
>
>L’arresto di una campagna è permanente. I destinatari cessano immediatamente di avanzare nella campagna e la campagna non può essere ripresa o riavviata in un secondo momento. Per inviare di nuovo, devi creare una nuova campagna e avviarla.

<!--

### Prerequisites

- [NEEDS INPUT - to confirm with engineer: does stopping a campaign require a specific role or permission, or can any user with campaign access do this?]

-->

### Come interrompere una campagna

1. Apri una campagna attualmente live.

1. Nell&#39;intestazione dei dettagli della campagna fare clic su **Interrompi campagna**.

1. Fai clic su **Interrompi** per confermare.
