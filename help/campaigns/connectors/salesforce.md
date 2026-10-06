---
description: Descrizione
title: Connetti a Salesforce
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 12ee914ed944c82694b9373f611e19cf040e2229
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%
---
# Connetti a Salesforce {#salesforce}

Campagne Adobe Collaborator consente di collegare il tuo account Salesforce per accedere ai lead e ai contatti.

>[!PREREQUISITES]
>
>Per utilizzare questo connettore, è necessario disporre innanzitutto di:
>
>* Un account Salesforce attivo
>* Le seguenti autorizzazioni in Salesforce: `api`, `sobjects.Contact.read`, `sobjects.Campaign.read`, `sobjects.CampaignMember.read`
>* L&#39;URL dell&#39;istanza di Salesforce, [l&#39;ID client e il segreto client](https://help.salesforce.com/s/articleView?id=xcloud.remoteaccess_oauth_client_credentials_flow.htm&type=5#:~:text=DESCRIPTION-,client_id,-The%20consumer%20key) sono utili

## Come collegarsi

1. Nella home page di [Campagne collaboratori](https://coworker-campaigns.experience.adobe.com/), fare clic su **Personalizza** e selezionare **Connettori**.

   ![Navigazione a sinistra delle campagne di collaborazione con Personalizza espanso ed evidenziati i connettori](./assets/salesforce-1.png)

1. Fare clic su **Aggiungi integrazione**.

   ![Pulsante Aggiungi integrazione nella schermata Connettori](./assets/salesforce-2.png)

   >[!NOTE]
   >
   >Se questa non è la prima integrazione, il pulsante indicherà &quot;Aggiungi connettore&quot;.

1. Nella riga Salesforce, fai clic su **Connetti**.

   ![](./assets/salesforce-3.png)

1. Immetti l&#39;**URL istanza**, l&#39;**ID client** e il **Segreto client** di Salesforce. Fai clic su **Connetti**.

   >[!NOTE]
   >
   >* In Salesforce, ID client = Chiave consumer e Segreto client = Segreto consumer.
   >
   >* Mentre ti trovi nell&#39;account Salesforce, puoi trovare l&#39;URL dell&#39;istanza nella barra degli indirizzi del browser oppure accedendo a **Configurazione** > **Impostazioni società** > **Dominio personale**.

   ![](./assets/salesforce-4.png)

Dopo la connessione, Salesforce viene visualizzato nell&#39;elenco Connettori e può essere selezionato quando si collega un elenco di lead o contatti da sincronizzare da Salesforce.

**Per disconnettersi:**

1. Nella schermata Connettori, individua il riquadro Salesforce e fai clic su **Gestisci**.

   ![](./assets/salesforce-5.png)

1. Fai clic su **Disconnetti** (al momento non è necessario immettere nuovamente il segreto client).

   ![](./assets/salesforce-6.png)

1. Fai di nuovo clic su **Disconnetti** per confermare.

   ![](./assets/salesforce-7.png)
