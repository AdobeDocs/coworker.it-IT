---
title: Convalidare i dati Customer Journey Analytics con l’abilità di convalida dei dati in Collaboratore
description: Scopri come convalidare i dati di Customer Journey Analytics utilizzando l’abilità di convalida dei dati in Collaborator e risolvere i problemi prima di creare dashboard.
feature: AI Tools
role: User
level: Beginner, Intermediate
doc-type: Feature Video
duration: 330
last-substantial-update: 2026-09-16
jira: KT-22622
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%
---
# Convalidare i dati Customer Journey Analytics con l&#39;abilità di convalida dei dati in [!DNL Coworker]

La qualità dei dati è alla base di un reporting accurato in Adobe Customer Journey Analytics (CJA). Prima di creare metriche, dashboard, segmenti o percorsi di clienti, è fondamentale capire se i dati Adobe Experience Platform (AEP) sottostanti possono essere attendibili.

Questo video illustra come utilizzare l&#39;abilità di convalida dei dati **in Coworker** per valutare rapidamente la qualità dei set di dati che supportano l&#39;implementazione di Customer Journey Analytics, senza scrivere query o esaminare manualmente i dati.

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## Scopri i set di dati alla base dei rapporti di CJA

Scopri come Collaboratore può identificare:

- Quali set di dati sono collegati a Customer Journey Analytics
- Le connessioni e le visualizzazioni dati associate a una sandbox specifica
- I set di dati alimentano attivamente il reporting
- Caratteristiche principali dei set di dati, ad esempio lo stato di streaming e gli spazi dei nomi delle identità

Comprendendo esattamente quali set di dati alimentano i rapporti, puoi concentrare gli sforzi di convalida laddove sono più importanti.

## Esplorare gli schemi di set di dati e i campi disponibili

Scopri come controllare gli schemi di set di dati direttamente da Adobe Experience Platform.

Il collaboratore recupera i dettagli e le superfici dello schema:

- Campi Commerce e transazione
- Informazioni prodotto
- Dati interazione web
- Campi di identità
- Attributi della campagna e del marketing
- Dimensioni geografiche e del dispositivo

Fornisce un inventario dei campi disponibili per l’analisi ed evidenzia la differenza tra i campi esistenti in uno schema e i campi che contengono dati utilizzabili.

## Convalida qualità identità

I dati di identità sono essenziali per Customer Journey Analytics in quanto supportano la generazione di rapporti a livello di persona e l’analisi del percorso cross-channel.

In questo video vedrai come Collaboratore:

- Convalida i campi di identità
- Verifica la completezza dei dati e dei valori Null
- Valuta la qualità dell’identificatore
- Superfici con attributi di identità mancanti o non disponibili

La convalida dell’esempio mostra che le identità ECID ed e-mail sono completamente popolate e valide nell’esempio, mentre non è stato possibile recuperare l’ID di Analytics. Questo fornisce un segnale utile quando decidi quali identificatori possono supportare l’unione e il reporting dei profili.

## Analizzare la qualità dei singoli campi

Un campo può esistere in un set di dati ma non essere ancora idoneo per il reporting.

Guarda come Collaboratore convalida un campo di tracciamento delle campagne e genera rapporti:

- Tassi di popolazione
- Percentuali nulle
- Coerenza dei dati
- Rilevamento di valori non valido

Nell’esempio, i valori del codice di tracciamento presenti sono puliti e coerenti, ma approssimativamente l’85% delle righe sono nulle. Questo rivela un importante punto cieco nella generazione di rapporti prima che una dimensione CJA o una metrica di campagna venga generata sul campo.

## Eseguire la convalida del set di dati basato sull’intelligenza artificiale

Invece di convalidare i singoli campi uno alla volta, Collaboratore può valutare un intero set di dati.

Scoprirai in che modo l’abilità di Convalida dati:

- Seleziona campi importanti per la convalida
- Valuta completezza e qualità
- Confronta l’integrità dei dati tra campi diversi
- Evidenzia i punti di forza e i potenziali rischi di reporting

I risultati della convalida forniscono una mappa della redditività per CJA. Campi puliti come il nome della pagina web e il codice e-mail possono essere pronti per la generazione di rapporti, mentre campi sparsi come il valore di acquisto, il nome della campagna e il codice di tracciamento richiedono indagini.

## Identificare i rischi di ricavi e attribuzione

Il video illustra inoltre come la convalida dei dati possa individuare i problemi che influiscono sull’accuratezza della generazione di rapporti, tra cui:

- Dati sparsi della campagna
- Informazioni di attribuzione mancanti
- Valori transazione incompleti
- Divari nella misurazione dei ricavi

Nel set di dati visualizzato, i conteggi di acquisto sono disponibili, ma gli importi degli ordini non sono popolati in modo affidabile. Si tratta di un problema da esaminare prima di considerare attendibili i rapporti sui ricavi.

## Perché la convalida dei dati è importante per Customer Journey Analytics

Customer Journey Analytics è affidabile solo quanto i dati alla base.

La convalida dei set di dati prima della creazione dei rapporti consente ai team di:

- Aumentare la fiducia nei risultati di analisi
- Migliorare le procedure di governance dei dati
- Riduzione degli errori di reporting
- Identificare prima i problemi di implementazione
- Risolvere i problemi relativi alle metriche impreviste in modo più efficiente

Con Coworker, questi controlli possono essere avviati utilizzando prompt del linguaggio naturale, rendendo la convalida dei dati più accessibile agli utenti tecnici e non tecnici.

