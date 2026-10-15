---
description: Scopri in che modo Coworker for teams allega e mantiene automaticamente i metadati C2PA sulle immagini, dalla generazione alla consegna delle e-mail.
title: Metadati C2PA in Collaboratore per team
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 7af4950080b8805d94062567bdf4075d1f57fc13
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 4%
---
# Metadati C2PA in Collaboratore per team {#overview}

Nuove leggi stanno emergendo sulla trasparenza generativa dell’intelligenza artificiale e Adobe sta lavorando per soddisfare i requisiti applicabili in tutte le giurisdizioni. I metadati [C2PA](https://c2pa.org/) sono lo strumento di provenienza utilizzato da Adobe per soddisfare i requisiti di queste normative.

I metadati C2PA sono metadati invisibili e duraturi che registrano il modo in cui un contenuto è stato creato o modificato. Quando generi o modifichi un’immagine con strumenti di intelligenza artificiale generativi in Collaborator for teams, i metadati C2PA vengono automaticamente allegati all’immagine. Non è richiesta alcuna azione da parte tua.

## Metadati C2PA nelle campagne e-mail {#c2pa-metadate-email}

Le immagini inviate nelle campagne e-mail mantengono intatti i metadati C2PA, in modo che i destinatari possano verificare l’origine e l’autenticità di qualsiasi immagine direttamente dall’e-mail consegnata.

## Azioni che associano metadati C2PA {#actions}

La tabella seguente riepiloga quando vengono allegati metadati C2PA, in base all’azione dell’immagine eseguita nella generazione di immagini in Coworker for teams.

| Azione | Descrizione | Metadati C2PA allegati? | Esempio di caso d’uso |
| --- | --- | --- | --- |
| **Generare un&#39;immagine** | Create una nuova immagine da un prompt di testo o da un&#39;immagine di riferimento oppure generate un&#39;immagine simile da una già esistente. | Sempre. L’immagine viene generata dall’intelligenza artificiale generativa, in modo da trasportare sempre nuovi metadati C2PA. | Un’immagine del banner per una campagna e-mail viene generata da un prompt di testo che descrive l’elemento visivo desiderato. |

## Tipi di contenuto e ambito {#content-types}

* **Immagini**: coperte. I metadati C2PA vengono allegati quando le immagini vengono generate con intelligenza artificiale generativa e vengono conservati mediante le operazioni di ritaglio, sovrapposizione di testo e sovrapposizione di immagini eseguite dalla generazione di immagini in Coworker for teams.
* **Testo**: non applicabile. Gli output di solo testo in Collaborator per i team, come la generazione di copie, la traduzione e i suggerimenti di allineamento del brand, non richiedono metadati C2PA.

## Cosa succede quando il contenuto si sposta {#content-moves}

Collaboratore per team mantiene i metadati C2PA associati alle risorse immagine supportate. Se un’immagine contiene metadati C2PA quando viene importata in Collaborator per i team, tali credenziali vengono mantenute quando la risorsa viene utilizzata nei contenuti della campagna generata e nelle esperienze e-mail in uscita.

## Risorse aggiuntive {#resources}

* [Trasparenza dei contenuti di IA generativa](https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/overview/content-transparency){target="_blank"}
* [Linee guida utente per l’intelligenza artificiale generativa di Adobe Experience Cloud](https://www.adobe.com/it/legal/licenses-terms/adobe-dx-gen-ai-user-guidelines.html){target="_blank"}
* [Guardrail e limitazioni](https://experienceleague.adobe.com/it/docs/journey-optimizer/using/content-management/generate-content/gs-generative#generative-guardrails){target="_blank"}
