---
title: Rilevare le anomalie di Experience Platform con il collaboratore
description: Scopri come rilevare le anomalie in Adobe Experience Platform con Chat con coorker. Esplora i prompt per le metriche di acquisizione, segmentazione e attivazione della destinazione.
feature: AI Tools
role: User
level: Intermediate
doc-type: Tutorial
jira: PLAT-313965
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 1%
---

# Rilevare le anomalie di Experience Platform

Utilizza la chat di [!DNL Adobe CX Enterprise Coworker] per identificare picchi e cadute nelle metriche Adobe Experience Platform supportate. Chiedi informazioni sui flussi di dati e sui tipi di pubblico per trovare le deviazioni da una linea di base.

Inizia con una domanda ampia, quindi concentrati su un flusso o un pubblico che ha bisogno di attenzione. Esamina la metrica riportata e la relativa linea di base prima di decidere cosa analizzare.

>[!AVAILABILITY]
>
>La disponibilità del rilevamento delle anomalie è limitata. La disponibilità generale è prevista per il primo trimestre del 2027.

>[!NOTE]
>
>Il rilevamento delle anomalie fornisce informazioni senza modificare i dati o la configurazione.

## Abilità diagnostiche disponibili

Utilizza il plug-in `baseline-anomalies` per rilevare anomalie, confrontare le tendenze e rivedere lo stato del flusso o gli errori del processo corrente. Per impostazione predefinita, il plug-in è configurato con l&#39;offerta Experience Platform e Apps in [!DNL Coworker].

Scegliere il tipo di domanda in base alle informazioni necessarie.

| Competenza | Scopo |
| --- | --- |
| [!UICONTROL Anomalie del flusso di ricerca delle anomalie della linea di base] | Rileva picchi o cadute nel volume dei record e nei record con errori tra le fasi di acquisizione, segmentazione, esportazione e destinazione. |
| [!UICONTROL Anomalie del pubblico di ricerca delle anomalie della linea di base] | Rileva picchi o cadute nei conteggi dei profili di pubblico realizzati e picchi nei conteggi dei profili usciti. |
| [!UICONTROL Anomalie linea di base: riepilogo andamento flusso] | Confronta le velocità effettive di flusso recenti e tipiche senza un verdetto di anomalia. |
| [!UICONTROL Anomalie previste riepilogo tendenze pubblico] | Confronta i conteggi di profili qualificati e in uscita recenti e tipici per la segmentazione batch, senza un verdetto di anomalie o un intervallo previsto. |
| [!UICONTROL Anomalie nella linea di base Ispezionare l&#39;integrità del flusso] | Verifica i conteggi di esecuzioni deduplicate completate e non riuscite, più i totali dei record non riusciti per attività o flusso. |
| [!UICONTROL Processi non riusciti nella ricerca delle anomalie della linea di base] | Esaminare i processi attualmente non riusciti e i relativi motivi di errore, escludendo gli errori recuperati e i dettagli per i singoli record. |

I riepiloghi delle tendenze descrivono le modifiche, ma non determinano se si tratta di anomalie. Se hai bisogno di una valutazione a picco o a caduta, utilizza le domande relative alle anomalie.

## Prima di iniziare

Il plug-in è configurato per impostazione predefinita. Per verificarne lo stato prima di porre domande diagnostiche, eseguire la procedura seguente.

1. Vai a **[!UICONTROL Personalizzazioni]**.

1. Selezionare **[!UICONTROL Plug-in]**.

1. Apri **[!UICONTROL baseline-anomalies]** e verifica che il suo stato sia **[!UICONTROL Active]**.

Identifica la sandbox e l’area da controllare. Per una risorsa specifica, tieni pronto il relativo flusso, segmento o nome o identificatore di destinazione.

Per istruzioni generali sulla chat, vedere [Introduzione alla chat](/help/chat/ui-guide.md).

## Richiedi informazioni sulle anomalie

Descrivere l&#39;area o la risorsa che si desidera controllare e il periodo di tempo che si desidera esaminare.

Utilizzare i prompt di esempio riportati di seguito come punto di partenza. Sostituisci i nomi di esempio con i nomi della tua organizzazione.

| Obiettivo | Esempio di prompt |
| --- | --- |
| Controllo tra aree supportate | Ci sono anomalie nelle ultime 24 ore? |
| Controlla acquisizione | Ci sono anomalie con la mia acquisizione nelle ultime 24 ore? |
| Controlla un flusso specifico | Sono presenti anomalie nel flusso di acquisizione di CustomerImport nelle ultime 24 ore? |
| Controllare la segmentazione | Ci sono anomalie nella segmentazione nelle ultime 24 ore? |
| Controlla un segmento specifico | Ci sono anomalie con i membri fedeltà del segmento nelle ultime 24 ore? |
| Verifica attivazione destinazione | Ci sono anomalie nell’attivazione della destinazione nelle ultime 24 ore? |
| Verifica i picchi di profilo realizzati | Esiste oggi un picco nei profili realizzati da parte di un pubblico? |
| Verifica anomalie record non riuscite | I record non riusciti sono eccessivamente elevati per il flusso CustomerImport? |

La domanda generale verifica sia i flussi di dati che i tipi di pubblico. Conferma la sandbox e il periodo di tempo identificati nella risposta.

<!-- Author review: Confirm exact supported time windows, defaults, time zone handling, and data freshness. -->

## Verifica risultati anomalie

Confrontare il valore riportato con la relativa previsione per la risorsa e il periodo di tempo interessati. Utilizza la differenza per identificare ciò che necessita di ulteriori indagini, anziché trattare un’anomalia come causa confermata.

Ad esempio, una diminuzione dei record di input per l’acquisizione identifica una modifica del volume. Questo cambiamento da solo non spiega perché sono arrivati meno record.

I risultati possono essere visualizzati sotto forma di tabelle o di riepilogo scritto. Le tabelle possono raggruppare le anomalie in [!UICONTROL Rischio elevato] e [!UICONTROL Rischio Medium].

![I risultati delle anomalie raggruppano picchi e cali del volume di acquisizione e di destinazione in base al rischio medio e alto, con i nomi e i valori delle risorse eliminati.](assets/anomaly-detection/anomaly-detection-results.png){width="900" zoomable="yes"}

Questo esempio raggruppa le anomalie di flusso in base al rischio e suggerisce di esaminare i conteggi di esecuzione o la cronologia delle tendenze. I nomi e i valori delle risorse vengono eliminati.

| Dettagli risultato | Cosa rivedere |
| --- | --- |
| [!UICONTROL Quando (UTC)] | L’ora dell’evento o l’intervallo di tempo in Coordinated Universal Time. |
| [!UICONTROL Fase] | La fase di elaborazione interessata, ad esempio l’acquisizione o la destinazione. |
| [!UICONTROL Flusso] | Il flusso interessato, identificato per nome o identificatore. |
| [!UICONTROL Cos&#39;è successo] | La modifica rilevata, ad esempio un picco o una caduta del volume. |
| [!UICONTROL Effettivi e previsti] | Il valore osservato rispetto al valore basale o all’intervallo atteso. |

Rivedi la spiegazione insieme al gruppo di rischi. Per le anomalie del pubblico, Alta indica un ampio scostamento dalla norma. Medium indica una partenza chiara ma moderata. Vengono restituite solo le anomalie High e Medium.

I risultati del pubblico escludono le anomalie di Medium quando la cronologia della linea di base è altamente variabile. Qualsiasi anomalia restituita con una cronologia altamente variabile ha quindi un livello di rischio elevato.

Utilizza i livelli di rischio per dare priorità alle indagini, non per stabilire una causa principale.

Ad esempio, una risposta identifica 10 record di input rispetto a un intervallo previsto da uno a quattro come picco di rischio medio. Il livello abituale è di circa un record, quindi la deviazione è grande rispetto alla linea di base. Il volume assoluto rimane piccolo.

Controlla gli orari degli eventi prima di trattare un’anomalia storica come problema corrente. Un evento che si è verificato nelle ultime 24 ore non stabilisce se la condizione sottostante è stata recuperata.

<!-- Author review: Confirm flow risk tier definitions and whether persistence is reported. -->

### Baseline e intervalli previsti

I confronti orari per anomalie utilizzano la stessa ora nei 14 giorni precedenti. Questo spiega i pattern tipici per ora, ma non tiene conto di una stagionalità più ampia.

Per le anomalie del pubblico, l’intervallo previsto si centra sulla mediana e si allarga in base alla variazione dei conteggi storici. Se il limite inferiore calcolato è negativo, l’intervallo utilizza il conteggio storico più basso. L’intervallo può quindi estendersi oltre la mediana che al di sotto di essa.

I conteggi dei profili realizzati superiori all’intervallo previsto sono picchi. I conteggi al di sotto dell’intervallo sono delle gocce. Un conteggio pari a zero quando i profili sono normalmente presenti corrisponde a un calo di rischio elevato.

I conteggi dei profili in uscita producono solo verdetti picco. Un numero inferiore di uscite viene trattato come normale, non come anomalie di caduta.

### Nessuna anomalia restituita

Una risposta può segnalare che non sono state restituite anomalie High o Medium per il pubblico e il periodo richiesti.

![Un riepilogo delle anomalie del pubblico non segnala alcuna anomalia di tipo Elevato o Medium nell&#39;arco di 168 ore e include un avviso relativo alla cronologia esclusa.](assets/anomaly-detection/anomaly-detection-no-anomalies.png){width="900" zoomable="yes"}

Questo esempio include un avviso relativo a una cronologia insufficiente o per lo più pari a zero. Non conferma che ogni ora sia stata valutata o che questo pubblico sia stato escluso. Il nome e l’identificatore del pubblico vengono oscurati.

### Cronologia linea di base insufficiente

La cronologia della linea di base influisce sulla possibilità o meno di valutare le anomalie in un pubblico.

Il rilevamento delle anomalie del pubblico non valuta le righe con meno di cinque giorni di cronologia o una cronologia contenente per lo più zeri.

>[!IMPORTANT]
>
>L’assenza di anomalie segnalate non significa che ogni risorsa sia stata valutata. La risposta potrebbe non confermare se un pubblico è stato valutato o saltato.

<!-- Author review: Confirm flow minimum history requirements and whether audience evaluation status or excluded resources can be retrieved. -->

## Affina la domanda

Concentrare la domanda successiva sulla risorsa interessata. Ad esempio, dopo un ampio controllo dell’acquisizione, chiedi informazioni sulle anomalie per un flusso denominato.

Dopo aver chiesto informazioni sulle ultime 24 ore, prolunga il periodo con questo follow-up:

```text
What about in the past two weeks?
```

La risposta di può identificare anomalie storiche anche quando non ne è stata rilevata alcuna nelle ultime 24 ore.

Per un’indagine più approfondita, chiedi informazioni sui conteggi delle esecuzioni dei flussi, sulle tendenze del flusso, sulle tendenze del pubblico o sui processi attualmente non riusciti. Puoi anche chiedere informazioni sui singoli lavori mentre indaghi.

Scegli la domanda successiva in base alle informazioni necessarie. I riepiloghi sulle tendenze e sullo stato non forniscono verdetti sulle anomalie.

| Obiettivo | Esempio di prompt | Cosa aspettarsi |
| --- | --- | --- |
| Rivedere le tendenze del pubblico | Com&#39;è cambiato il pubblico nell&#39;ultima settimana? | Conteggi di profili qualificati e in uscita recenti e tipici per la segmentazione batch, senza un intervallo previsto. |
| Analizzare le tendenze del flusso | Com’è cambiato il volume di acquisizione nell’ultima settimana? | Velocità effettiva recente rispetto alla velocità effettiva tipica, senza un verdetto di anomalia. |
| Verifica stato del flusso | Quante esecuzioni sono riuscite o non sono riuscite per i flussi di acquisizione nelle ultime 24 ore? | I conteggi delle esecuzioni deduplicati e i totali dei record aggregati non riusciti, senza motivi di errore. |
| Analizza processi non riusciti | Quali processi di esportazione non sono riusciti nelle ultime 24 ore e perché? | Processi il cui stato più recente non è riuscito nell&#39;ambito richiesto, con motivi di errore del processo. |
| Esaminare un errore di flusso | Qual è l’errore nel flusso CustomerImport? | Motivi di errore per i processi attualmente non riusciti associati al flusso, senza dettagli per i singoli record. |

La cronologia delle tendenze del pubblico viene mantenuta per circa due settimane, o 336 ore. Il valore tipico è la mediana di quell’ora rispetto ai 14 giorni precedenti.

Per i processi attualmente non riusciti, un risultato vuoto indica che nessun processo attualmente non riesce nell’ambito richiesto. Ciò non significa che non si siano verificati errori durante il periodo richiesto. I processi non riusciti e quelli successivi sono esclusi.

Continua a indagare con le abilità di verifica stato, oppure utilizza le abilità di avviso per abilitare un avviso per una risorsa supportata. Queste azioni utilizzano competenze separate, non il rilevamento delle anomalie in sé.

Per i flussi di lavoro degli avvisi correlati, vedi [Competenze per gli avvisi ai clienti](/help/chat/use-cases/customer-alerts/customer-alerts.md).

<!-- Author review: Validate a complete public example response and the supported alert assets and setup before adding an alert procedure. -->

## Riferimento metrica

La versione limitata include le sette metriche seguenti per l’acquisizione, la segmentazione e l’attivazione della destinazione. Utilizzare questo riferimento per identificare i conteggi associati a ciascuna area.

| Area | Identificatore della metrica | Conteggio misurato |
| --- | --- | --- |
| Acquisizione | `input_record_count` | Numero di record di input per un flusso di acquisizione. |
| Acquisizione | `failed_record_count` | Numero di record non riusciti per un flusso di acquisizione. |
| Segmentazione | `__segment_{segment_id}__realized_profiles` | Numero di profili idonei per un segmento. |
| Segmentazione | `__segment_{segment_id}__exited_profiles` | Numero di profili che escono da un segmento. |
| Attivazione destinazione | `{destination}_input_record_count` | Numero di record di input per una destinazione. |
| Attivazione destinazione | `{destination}_skipped_record_count` | Numero di record ignorati per una destinazione. |
| Attivazione destinazione | `{destination}_output_record_count` | Numero di record di output per una destinazione. |

<!-- Author review: Confirm metric aggregation intervals and identifier visibility. -->

## Ambito di applicazione e limitazioni

Utilizza il rilevamento delle anomalie per identificare le deviazioni, non per confermare una causa principale o ripristinare una risorsa.

Puoi chiedere informazioni su flussi, segmenti e destinazioni per nome o identificatore. Il rilevamento delle anomalie di flusso copre le fasi di acquisizione, segmentazione, esportazione e destinazione.

Utilizza l’abilità del processo non riuscito per i processi attualmente non riusciti e i relativi motivi di errore. Gli errori recuperati sono esclusi. La diagnostica dei processi non include dettagli per singoli record o verdetti di anomalie.

L&#39;integrità del flusso fornisce conteggi aggregati, non motivi di errore. I riepiloghi delle tendenze descrivono valori recenti e tipici, non verdetti di anomalie. I riepiloghi delle tendenze del pubblico coprono solo la segmentazione batch.

Il rilevamento delle anomalie non modifica i dati o la configurazione. Utilizza abilità separate per le azioni di allarme supportate e per indagini più approfondite.

<!-- Author review: Confirm job identifier support and any recommendation capabilities before adding examples. -->
