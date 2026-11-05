---
title: Analizzare le cause principali con Adobe Analytics e Customer Journey Analytics
description: Utilizza Adobe CX Enterprise Coworker per analizzare le modifiche delle metriche, identificare dimensioni e segmenti contribuenti e testare ipotesi in Adobe Analytics e CJA.
feature: AI Tools
role: User
level: Beginner
doc-type: Feature Video
duration: 186
last-substantial-update: 2026-08-10T00:00:00.000Z
jira: KT-22082
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 7e096fc9cda2157c02501ee909a80bf4df9a2f32
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 0%
---

# Analizzare le cause principali con [!DNL Adobe Analytics] e [!DNL Customer Journey Analytics]

Utilizza Adobe CX Enterprise Coworker Chat per scoprire perché una metrica è cambiata in Adobe Analytics o Customer Journey Analytics (CJA). Collaboratore analizza la modifica specificata, le superfici che contribuiscono alle dimensioni e ai segmenti e consente di testare le ipotesi utilizzando un linguaggio naturale.

## Utilizzare i dati di Customer Journey Analytics per l&#39;analisi della causa principale

Il video seguente illustra come Coworker combina l’intelligenza artificiale conversazionale con Customer Journey Analytics. Scopri come porre domande in linguaggio naturale, visualizzare i risultati, identificare tendenze significative e individuare fattori che determinano le prestazioni senza creare query manuali.

>[!VIDEO](https://video.tv.adobe.com/v/3496847/?learn=on&enablevpops)

### Prerequisiti

Prima di iniziare:

1. **Accesso a Chat con i collaboratori e connessione a Customer Journey Analytics.** Verifica che la tua organizzazione abbia configurato l’integrazione richiesta.
1. **Avere accesso alla visualizzazione dati di CJA che si desidera analizzare.** Il collaboratore può utilizzare solo le visualizzazioni dati e i componenti disponibili.
1. **Scegliere la visualizzazione dati contenente la metrica e le dimensioni pertinenti.** Se puoi accedere a più visualizzazioni dati, assegna un nome a quella che desideri che sia utilizzata da Collaboratore.
1. **Identificare la modifica che si desidera esaminare.** Specifica la metrica, l’intervallo di date e il periodo di confronto. Puoi anche fornire dimensioni, segmenti o un’ipotesi per concentrare l’analisi.

### Richieste di esempio per Customer Journey Analytics

Sostituisci il testo tra parentesi con i nomi dei componenti e i periodi di tempo dalla visualizzazione dati.

* Nella visualizzazione dati **[nome visualizzazione dati]**, perché **[metrica]** è cambiata durante **[intervallo date]** rispetto a **[intervallo date di confronto]**? Suddividi la modifica per **[dimensione]** e mostra i segmenti che hanno contribuito di più.
* Nella visualizzazione dati **[nome visualizzazione dati]**, **[la dimensione o il segmento]** ha contribuito alla riduzione di **[metrica]** da **[intervallo di date A]** a **[intervallo di date B]**? Confrontare i valori di entrambi i periodi e spiegare cosa è cambiato.
* Nella visualizzazione dati **[nome visualizzazione dati]**, confrontare **[metrica]** per **[segmento A]** e **[segmento B]** durante **[intervallo date]**. Quali sono le dimensioni che hanno contribuito maggiormente alla differenza?
* Nella visualizzazione dati **[nome visualizzazione dati]**, verifica questa ipotesi: **[indica la tua ipotesi]**. Analizza **[metric]** per **[intervallo di date]** e mostra le dimensioni o i segmenti che lo supportano o non lo supportano.

## Utilizzare i dati di Adobe Analytics per l’analisi della causa principale

Il collaboratore può indagare il motivo per cui una metrica è cambiata in una suite di rapporti di Adobe Analytics. Utilizza l&#39;abilità `aa-root-cause-analysis` per analizzare una modifica specificata e identificare le dimensioni e i segmenti che vi hanno contribuito.

### Prerequisiti

Prima di iniziare:

1. **Accedi a Chat con i collaboratori e connetti Adobe Analytics.** In Coworker, vai a **Personalizzazioni > Integrazioni** e verifica che l&#39;integrazione `aa-mcp` sia elencata e connessa. Se non è disponibile, chiedi all’amministratore di controllare la configurazione della tua organizzazione. Per istruzioni sulla configurazione, consulta [Introduzione all&#39;analisi dei dati con Chat di Coworker](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat).
1. **Accesso in visualizzazione alla suite di rapporti di Adobe Analytics che desideri analizzare.** Coworker eredita le autorizzazioni di Adobe Analytics e può utilizzare solo le suite di rapporti e i componenti disponibili in Analysis Workspace.
1. **Scegliere la suite di rapporti contenente i dati rilevanti.** Se puoi accedere a più suite di rapporti, dai un nome alla suite di rapporti che desideri che sia utilizzata da Collaboratore.
1. **Identificare la modifica che si desidera esaminare.** Specifica la metrica e il periodo di tempo. Per un’analisi più mirata, includi un periodo di confronto, dimensioni o segmenti rilevanti e qualsiasi ipotesi desideri che sia testata da Cooker.

### Richieste di esempio per Adobe Analytics

Sostituisci il testo tra parentesi con i nomi dei componenti e i periodi di tempo della suite di rapporti.

* Nella suite di rapporti **[nome suite di rapporti]**, perché **[metrica]** è cambiata durante **[intervallo di date]** rispetto a **[intervallo di date di confronto]**? Suddividi la modifica per **[dimensione]** e mostra i segmenti che hanno contribuito di più.
* Nella suite di rapporti **[nome suite di rapporti]**, **[dimensione o segmento]** ha contribuito alla riduzione di **[metrica]** da **[intervallo di date A]** a **[intervallo di date B]**? Confrontare i valori di entrambi i periodi e spiegare cosa è cambiato.
* Nella suite di rapporti **[nome suite di rapporti]**, confronta **[metrica]** per **[segmento A]** e **[segmento B]** durante **[intervallo di date]**. Quali sono le dimensioni che hanno contribuito maggiormente alla differenza?

## Risorse correlate

* [Analizzare i dati con Adobe CX Enterprise Coworker Chat](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-overview)
* [Introduzione all’analisi dei dati con Chat per collaboratori](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat)
