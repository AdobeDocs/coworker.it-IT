---
description: Connetti l’account HubSpot a Campagne con Collaboratore utilizzando una chiave di servizio per sincronizzare gli elenchi di contatti, quindi gestisci o disconnetti l’integrazione in qualsiasi momento.
title: Connetti a HubSpot
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '258'
ht-degree: 0%
---
# Connetti a HubSpot {#hubspot}

Campagne Adobe Collaborator consente di collegare l’account HubSpot per richiamare gli elenchi di contatti.

>[!PREREQUISITES]
>
>Per utilizzare questo connettore, è necessario disporre innanzitutto di:
>
>* Un account HubSpot attivo
>* È stata creata una [chiave del servizio](https://developers.hubspot.com/docs/apps/developer-platform/build-apps/authentication/account-service-keys#create-a-service-key) con i seguenti ambiti aggiunti: `crm.objects.contacts.read`, `crm.objects.leads.read`, `crm.schemas.contacts.read`, `crm.lists.read`, `crm.export`

## Come collegarsi

1. Nella home page di [Campagne collaboratori](https://coworker-campaigns.experience.adobe.com/), fare clic su **Personalizza** e selezionare **Connettori**.

   ![Menu Personalizza espanso nella barra laterale con i connettori selezionati](./assets/hubspot-1.png)

1. Fare clic su **Aggiungi integrazione**.

   ![Pulsante Aggiungi integrazione nella schermata Connettori](./assets/hubspot-2.png)

   >[!NOTE]
   >
   >Se questa non è la prima integrazione, il pulsante indicherà &quot;Aggiungi connettore&quot;.

1. Nella riga HubSpot, fai clic su **Connetti**.

   ![Riquadro HubSpot con pulsante Connetti evidenziato](./assets/hubspot-3.png)

1. Viene visualizzata una finestra modale che mostra le autorizzazioni necessarie (elencate nei Prerequisiti nella parte superiore di questo articolo). Fai clic su **Continua**.

1. Immetti la **chiave servizio** dell&#39;HubSpot e fai clic su **Connetti**.

   ![Connetti la finestra di dialogo HubSpot con il campo Chiave servizio e il pulsante Connetti](./assets/hubspot-4.png)

Dopo la connessione, HubSpot viene visualizzato nell’elenco Connettori e può essere selezionato quando si collega un elenco di contatti per la sincronizzazione da HubSpot.

**Per disconnettersi:**

1. Nella schermata Connettori, individua il riquadro HubSpot e fai clic su **Gestisci**.

   ![Schermata Connettori con HubSpot connesso e pulsante Gestisci evidenziato](./assets/hubspot-5.png)

1. Fai clic su **Disconnetti** (al momento non è necessario immettere nuovamente la chiave del servizio).

   ![Finestra di dialogo Gestisci HubSpot con il pulsante Disconnetti evidenziato](./assets/hubspot-6.png)

1. Fai di nuovo clic su **Disconnetti** per confermare.

   ![Finestra di dialogo di conferma della disconnessione con il pulsante Disconnetti evidenziato](./assets/hubspot-7.png)
