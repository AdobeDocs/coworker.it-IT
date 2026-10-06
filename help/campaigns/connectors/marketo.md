---
description: Scopri come collegare il tuo account Marketo Engage alle campagne di Coworker per sincronizzare gli elenchi statici e intelligenti di Marketo.
title: Connetti a Marketo Engage
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 0%
---
# Connetti a Marketo Engage {#marketo}

Campagne Adobe Coworker consente di collegare il tuo account Marketo Engage per richiamare elenchi statici e intelligenti.

>[!PREREQUISITES]
>
>Per utilizzare questo connettore, è necessario disporre innanzitutto di:
>
>* Un account Marketo Engage attivo
>* L&#39;URL dell&#39;**istanza** di Marketo
>* Un [servizio personalizzato](https://experienceleague.adobe.com/it/docs/marketo-developer/marketo/rest/custom-services#custom-services-1) creato per le campagne Coworker in Marketo, con [ID client e segreto client](https://experienceleague.adobe.com/it/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token) disponibili

## Come collegarsi

1. Nella home page di [Campagne collaboratori](https://coworker-campaigns.experience.adobe.com/), fare clic su **Personalizza** e selezionare **Connettori**.

   ![Navigazione a sinistra delle campagne di collaborazione con Personalizza espanso ed evidenziati i connettori](./assets/marketo-1.png)

1. Fare clic su **Aggiungi integrazione**.

   ![Pulsante Aggiungi integrazione nella schermata Connettori](./assets/marketo-2.png)

   >[!NOTE]
   >
   >Se questa non è la prima integrazione, il pulsante indicherà &quot;Aggiungi connettore&quot;.

1. Nella riga Marketo, fai clic su **Connetti**.

   ![Riquadro connettore Marketo con pulsante Connetti](./assets/marketo-3.png)

1. Immetti l&#39;**URL istanza**, l&#39;**ID client** e il **Segreto client** di Marketo. Fai clic su **Connetti**.

   >[!NOTE]
   >
   >Puoi trovare l’URL dell’istanza di Marketo nella barra degli indirizzi del browser quando visualizzi la pagina My Marketo.

   ![Connetti la finestra di dialogo di Marketo con campi quali URL istanza, ID client e Segreto client](./assets/marketo-4.png)

Dopo la connessione, Marketo viene visualizzato nell&#39;elenco Connettori e può essere selezionato quando si collega un elenco di contatti per la sincronizzazione da Marketo.

**Per disconnettersi:**

1. Nella schermata Connettori, individua il riquadro Marketo e fai clic su **Gestisci**.

   ![Schermata Connettori con il riquadro Marketo che mostra un pulsante Stato connesso e Gestisci](./assets/marketo-5.png)

1. Fai clic su **Disconnetti** (al momento non è necessario immettere nuovamente il segreto client).

   ![Finestra di dialogo Gestisci Marketo con i campi URL istanza e ID client e un pulsante Disconnetti](./assets/marketo-6.png)

   >[!NOTE]
   >
   >Dopo la prima aggiunta dell&#39;URL dell&#39;istanza, per impostazione predefinita viene utilizzato l&#39;URL dell&#39;endpoint REST, che termina con `*.mktorest.com`.

1. Fai di nuovo clic su **Disconnetti** per confermare.

   ![Finestra di conferma disconnessione connessione](./assets/marketo-7.png)
