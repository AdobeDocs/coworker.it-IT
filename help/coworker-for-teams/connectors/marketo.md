---
description: Scopri come collegare il tuo account Marketo Engage a Collaborator for teams per sincronizzare gli elenchi statici e intelligenti di Marketo.
title: Connetti a Marketo Engage
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%
---
# Connetti a Marketo Engage {#marketo}

Collaboratore per team consente di collegare il tuo account Marketo Engage per richiamare elenchi statici e intelligenti.

>[!PREREQUISITES]
>
>Per utilizzare questo connettore, è necessario disporre innanzitutto di:
>
>* Un account Marketo Engage attivo
>* L&#39;URL dell&#39;**istanza** di Marketo
>* Un [servizio personalizzato](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/custom-services#custom-services-1){target="_blank"} creato per Coworker per i team in Marketo, con [ID client e segreto client](https://experienceleague.adobe.com/en/docs/marketo-developer/marketo/rest/authentication#creating-an-access-token){target="_blank"} disponibili

## Come collegarsi

1. Nella home page di [Collaboratore per team](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, fare clic su **Contesto** e selezionare **Connettori**.

   ![Collaboratore per team ha lasciato la navigazione con il contesto espanso ed i connettori evidenziati](./assets/marketo-1.png)

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
