---
description: Inserire qui la descrizione.
title: Sottodominio
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: d36bbe844cff08b2c820418121dea794a7a347c2
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 4%
---
# Aggiungere un sottodominio e i mittenti {#subdomain-senders}

Un sottodominio è una divisione del dominio che può essere utilizzata per isolare i brand o vari tipi di traffico (ad esempio, comunicazioni di marketing).

Utilizziamo il dominio &quot;mybrand.com&quot;, utilizzato per inviare comunicazioni di marketing. In questa situazione, puoi impostare un sottodominio specifico:

* sottodominio &quot;marketing.mybrand.com&quot; per le e-mail di ricerca di potenziali clienti.

In questo modo potrai preservare la reputazione del tuo dominio e di altri sottodomini. Ad esempio, se il sottodominio &quot;marketing.mybrand.com&quot; finisse per essere aggiunto come elenco Bloccati di un provider di servizi Internet a causa di pratiche di recapito non valide, ciò impedirebbe l’aggiunta dell’intero dominio &quot;mybrand.com&quot; e di qualsiasi altro sottodominio creato.

>[!IMPORTANT]
>
>Come parte della versione di prova gratuita, sono consentiti al massimo due sottodomini.

## Aggiungere un sottodominio

1. Fai clic sul tuo nome nella parte inferiore del menu di navigazione a sinistra.

   SCHERMATA

1. Fare clic su **Impostazioni**.

   SCHERMATA

1. In _Workspace_, selezionare **Domini e mittenti**.

   SCHERMATA

1. Fare clic su **Aggiungi sottodominio**.

   SCHERMATA

1. Immetti il sottodominio e fai clic su **Avanti**.

   SCHERMATA

1. Fai clic sull’icona Copia PIC accanto ai valori applicabili da aggiungere al provider DNS.

   SCHERMATA

   >[!NOTE]
   >
   >Se il provider DNS ti consente di caricare i campi in blocco, puoi fare clic su **Esporta CSV** per esportare tutti i campi.

1. Dopo aver immesso le informazioni nel provider DNS, fare clic su **Ho aggiunto questi record** in Campagne Coworker per continuare.

   SCHERMATA

   >[!NOTE]
   >
   >La propagazione delle modifiche DNS può richiedere fino a 30 minuti. Se in una delle righe viene visualizzata una X rossa invece di un segno di spunta verde, Campagne coworking eseguiranno il controllo ogni due minuti fino al completamento.

1. Quando tutti i record vengono convalidati, nella parte inferiore della finestra viene visualizzata una tabella di _Record di convalida_. Scorri verso il basso, copia tutti i valori elencati e aggiungili al provider DNS.

   SCHERMATA

1. Al termine, fai clic su **Ho aggiunto questo record** (o **questi record** se sono presenti più record) in Campagne di Coworker per continuare.

   SCHERMATA

1. Inserisci il nome del mittente, il prefisso e-mail, il nome del destinatario della risposta e l&#39;indirizzo e-mail di risposta, quindi fai clic su **Fine e configura**.

   SCHERMATA

1. Il nuovo sottodominio viene visualizzato nell’elenco. Lo stato è _In corso_, poiché il completamento del processo può richiedere da alcuni minuti a due ore.

   SCHERMATA

1. Al termine del processo, lo stato diventa _Verificato_.

   SCHERMATA

## Come aggiungere un mittente

Testo

