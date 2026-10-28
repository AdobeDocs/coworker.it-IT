---
description: Scopri come collegare i team di Coworker for al tuo account Salesforce per accedere ai lead e ai contatti.
title: Connetti a Salesforce
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 312450e09d9252f17cb2b5d471ee33e1a22b9a05
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 0%
---
# Connetti a Salesforce {#salesforce}

Collaboratore per team consente di collegare il tuo account Salesforce per accedere ai lead e ai contatti.

>[!PREREQUISITES]
>
>Per utilizzare questo connettore, è necessario disporre innanzitutto di:
>
>* Un account Salesforce attivo
>* Le seguenti autorizzazioni in Salesforce: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* L&#39;URL dell&#39;istanza di Salesforce, [l&#39;ID client e il segreto client](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key){target="_blank"} sono utili

## Come collegarsi

1. Nella home page di [Collaboratore per team](https://coworker-campaigns.experience.adobe.com/){target="_blank"}, fare clic su **Contesto** e selezionare **Connettori**.

   ![Collaboratore per team ha lasciato la navigazione con il contesto espanso ed i connettori evidenziati](./assets/salesforce-1.png)

1. Fare clic su **Aggiungi integrazione**.

   ![Pulsante Aggiungi integrazione nella schermata Connettori](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >Se questa non è la prima integrazione, il pulsante indicherà &quot;Aggiungi connettore&quot;.

1. Nella riga Salesforce, fai clic su **Connetti**.

   ![Riquadro connettore Salesforce con pulsante Connetti](./assets/salesforce-3.png)

1. Immetti l&#39;**URL istanza**, l&#39;**ID client** e il **Segreto client** di Salesforce. Fai clic su **Connetti**.

   >[!NOTE]
   >
   >* In Salesforce, ID client = Chiave consumer e Segreto client = Segreto consumer.
   >
   >* Mentre ti trovi nell&#39;account Salesforce, puoi trovare l&#39;URL dell&#39;istanza nella barra degli indirizzi del browser oppure accedendo a **Configurazione** > **Impostazioni società** > **Dominio personale**.

   ![Connetti la finestra di dialogo di Salesforce con campi quali URL istanza, ID client e Segreto client](./assets/salesforce-4.png)

Dopo la connessione, Salesforce viene visualizzato nell&#39;elenco Connettori e può essere selezionato quando si collega un elenco di lead o contatti da sincronizzare da Salesforce.

**Per disconnettersi:**

1. Nella schermata Connettori, individua il riquadro Salesforce e fai clic su **Gestisci**.

   ![Schermata Connettori con Salesforce connesso con il pulsante Gestisci evidenziato](./assets/salesforce-5.png)

1. Fai clic su **Disconnetti** (al momento non è necessario immettere nuovamente il segreto client).

   ![Finestra di dialogo Gestisci Salesforce con il pulsante Disconnetti evidenziato](./assets/salesforce-6.png)

1. Fai di nuovo clic su **Disconnetti** per confermare.

   ![Finestra di dialogo di conferma della disconnessione con il pulsante Disconnetti evidenziato](./assets/salesforce-7.png)
