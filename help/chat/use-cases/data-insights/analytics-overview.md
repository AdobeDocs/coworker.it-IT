---
title: Analizzare i dati di Customer Journey Analytics con la chat del collaboratore
description: Scopri come utilizzare Adobe CX Enterprise Coworker Chat per analizzare i dati di Customer Journey Analytics, creare funnel e individuare i punti di contatto dei clienti nel percorso.
hold: true
product_v2:
  internal-label: CX Enterprise Coworker
feature_v2:
  internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '2354'
ht-degree: 0%
---

Adobe CX Enterprise Coworker Chat consente ai team di automatizzare le attività dei prodotti Adobe utilizzando il linguaggio naturale, trasformando rapidamente le idee in azioni con una pianificazione flessibile, competenze personalizzabili ed esecuzione intelligente. Per ulteriori informazioni generali su Coworker, vedere [Panoramica di CX Enterprise Coworker](/help/home.md).

## Analisi dei dati con Chat collaboratore

Chat con i collaboratori può eseguire analisi avanzate dei dati che in precedenza erano possibili solo in Analysis Workspace. Chat con collaboratori accede ai dati dalle visualizzazioni dati di Customer Journey Analytics o dalle suite di rapporti di Adobe Analytics, consentendoti di esplorare tali dati e ottenere risposte alle richieste in linguaggio naturale.

Quando crei una visualizzazione nella chat di Coworker, puoi aprirla in Analysis Workspace in qualsiasi momento per un controllo più manuale.

Le informazioni seguenti forniscono una panoramica su come analizzare i dati in Chat con collaboratori.

## Inizia l’analisi in Chat con i collaboratori

Per iniziare, descrivi ciò che desideri sapere in un linguaggio semplice. Chat con collaboratori pianifica l’analisi, esegue query sulle visualizzazioni dati o sulle suite di rapporti e crea visualizzazioni e riepiloghi.

Di seguito sono riportati alcuni esempi di casi di utilizzo. Puoi chiedere di qualsiasi dato a cui disponi dell’autorizzazione di accesso

### Casi d’uso principali

<!-- The following cards link to each of the stand-alone articles in this folder -->

<!--
CARDS

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze Customer Journey Analytics and Adobe Analytics data}
  {description = Answers natural-language questions about your data views or report suites, builds funnels and other visualizations, and finds where customers drop off. You can open any visualization in Analysis Workspace for further analysis.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Identifies trends in your Customer Journey Analytics and Adobe Analytics data and the factors that drive changes in performance, without manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze Customer Journey Analytics and Adobe Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizzare i dati di Customer Journey Analytics e Adobe Analytics">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analizzare i dati di Customer Journey Analytics e Adobe Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizzare i dati di Customer Journey Analytics e Adobe Analytics">Analizzare i dati di Customer Journey Analytics e Adobe Analytics</a>
                    </p>
                    <p class="is-size-6">Risponde alle domande in linguaggio naturale sulle visualizzazioni di dati o sulle suite di rapporti, crea funnel e altre visualizzazioni e trova dove i clienti abbandonano. Puoi aprire qualsiasi visualizzazione in Analysis Workspace per ulteriori analisi.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Esplorare tendenze e cause profonde">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Esplorare tendenze e cause profonde"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Esplorare tendenze e cause profonde">Esplora tendenze e cause principali</a>
                    </p>
                    <p class="is-size-6">Identifica le tendenze nei dati di Customer Journey Analytics e Adobe Analytics e i fattori che determinano cambiamenti nelle prestazioni, senza query manuali.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide
  {title = Plan your implementation}
  {description = Creates a personalized, step-by-step plan for implementing Customer Journey Analytics, upgrading from Adobe Analytics, or setting up Content Analytics, Marketing Campaign Analytics, or Streaming Media collection on the Edge. Plans include details such as owners, effort estimates, dependencies, and validation steps.}
  {cta = Read}
  {image = ../../assets/ui-guide-6.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist
  {title = Generate an implementation checklist}
  {description = Turns your Customer Journey Analytics implementation plan into a checklist in Coworker Projects, where your team can assign steps, track status, and add approval gates.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/date-detail.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Plan your implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Pianificare l’implementazione">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-6.png" alt="Pianificare l’implementazione"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" title="Pianificare l’implementazione">Pianifica l'implementazione</a>
                    </p>
                    <p class="is-size-6">Crea un piano personalizzato e dettagliato per l’implementazione di Customer Journey Analytics, l’aggiornamento da Adobe Analytics o la configurazione di Content Analytics, Marketing Campaign Analytics o Streaming Media Collection su Edge. I piani includono dettagli quali proprietari, stime dello sforzo, dipendenze e passaggi di convalida.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/implementation-guide" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Generate an implementation checklist">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Generare un elenco di controllo per l’implementazione">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/date-detail.png" alt="Generare un elenco di controllo per l’implementazione"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" title="Generare un elenco di controllo per l’implementazione">Generare un elenco di controllo dell'implementazione</a>
                    </p>
                    <p class="is-size-6">Trasforma il piano di implementazione di Customer Journey Analytics in un elenco di controllo in Progetti coworking, in cui il team può assegnare passaggi, tenere traccia dello stato e aggiungere gate di approvazione.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/intelligent-checklist" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data when upgrading from Adobe Analytics to Customer Journey Analytics}
  {description = Compares dimensions, metrics, and trends between your Adobe Analytics report suites and Customer Journey Analytics data views, then recommends fixes to support your upgrade.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}

* https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation
  {title = Validate your Streaming Media implementation}
  {description = Checks your datastream, schema, dataset, data view, and session data to confirm that streaming media tracking is configured and collecting data correctly.}
  {cta = Read}
  {image = ../../assets/ui-guide-8.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data when upgrading from Adobe Analytics to Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Convalidare i dati durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Convalidare i dati durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Convalidare i dati durante l’aggiornamento da Adobe Analytics a Customer Journey Analytics">Convalida dati durante l'aggiornamento da Adobe Analytics a Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Confronta dimensioni, metriche e tendenze tra le suite di rapporti di Adobe Analytics e le visualizzazioni dati di Customer Journey Analytics, quindi consiglia di apportare correzioni per supportare l’aggiornamento.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate your Streaming Media implementation">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Convalidare l’implementazione di Streaming Media">
                        <img class="is-bordered-r-small" src="../../assets/ui-guide-8.png" alt="Convalidare l’implementazione di Streaming Media"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" title="Convalidare l’implementazione di Streaming Media">Convalida l'implementazione di Streaming Media</a>
                    </p>
                    <p class="is-size-6">Controlla lo stream di dati, lo schema, il set di dati, la visualizzazione dati e i dati della sessione per verificare che il tracciamento dei contenuti multimediali in streaming sia configurato e che la raccolta dei dati sia corretta.</p>
                </div>
                <a href="https://experienceleague.adobe.com/en/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/streaming-media-validation" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate dataset quality for Customer Journey Analytics}
  {description = Identifies the datasets that feed your Customer Journey Analytics reporting, then checks schemas, identity quality, and field quality so you can resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep
  {title = Validate data after ingestion into Experience Platform}
  {description = Runs statistical and semantic checks on Experience Platform datasets and fields to find data quality issues, such as invalid values or mapping problems.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/null-values.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate dataset quality for Customer Journey Analytics">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Convalidare la qualità del set di dati per Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Convalidare la qualità del set di dati per Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Convalidare la qualità del set di dati per Customer Journey Analytics">Convalida qualità set di dati per Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Identifica i set di dati che alimentano i rapporti di Customer Journey Analytics, quindi controlla gli schemi, la qualità dell’identità e la qualità dei campi in modo da poter risolvere i problemi prima di creare dashboard.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data after ingestion into Experience Platform">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Convalidare i dati dopo l’acquisizione in Experience Platform">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/null-values.png" alt="Convalidare i dati dopo l’acquisizione in Experience Platform"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" title="Convalidare i dati dopo l’acquisizione in Experience Platform">Convalida dati dopo l'acquisizione in Experience Platform</a>
                    </p>
                    <p class="is-size-6">Esegue controlli statistici e semantici sui set di dati e sui campi di Experience Platform per individuare problemi di qualità dei dati, ad esempio valori non validi o problemi di mappatura.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aep" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

Per ulteriori informazioni su questi casi d&#39;uso, incluse le abilità che utilizzano e i prompt di esempio, vedi [Casi d&#39;uso Approfondimenti dati](/help/chat/use-cases/overview.md#data-insights).

### Introduzione

Chat con i collaboratori può anche aiutarti a:

* **Confronta prestazioni**: confronta le metriche tra canali, periodi di tempo o segmenti affiancati.
* **Misura le prestazioni della campagna**: scopri le prestazioni di campagne, canali e proprietà web in un determinato periodo di tempo.
* **Analizzare i funnel**: scorri i funnel di conversione in più passaggi e visualizza il menu a discesa in ogni fase.
* **Metriche di previsione**: proietta i valori delle metriche future dai dati storici di Customer Journey Analytics o Adobe Analytics, ad esempio se sei sulla buona strada per raggiungere un obiettivo di ricavi.
* **Creare riepiloghi esecutivi e digest di KPI**: generare riepiloghi delle prestazioni pronti per le parti interessate, consigli e descrizioni della presentazione.
* **Analizza le tendenze operative e le cause**: esegui una query sui dati cronologici delle serie temporali per tipi di pubblico, set di dati e percorsi e identifica la causa di una modifica.
* **Creare abilità Customer Journey Analytics personalizzate**: trasforma un&#39;analisi ripetuta in un&#39;abilità riutilizzabile che persiste nelle sessioni.

<!--
CARDS

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat
  {title = Analyze data with Coworker Chat}
  {description = Ask questions in natural language to build funnels, create visualizations, and find where customers drop off in the journey.}
  {cta = Read}
  {image = ../../assets/coworker-funnel-response-card.png}

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis
  {title = Explore trends and root causes}
  {description = Investigate changes in your Customer Journey Analytics data and uncover what drives them, without writing manual queries.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-line-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Analyze data with Coworker Chat">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizzare i dati con Chat con i collaboratori">
                        <img class="is-bordered-r-small" src="../../assets/coworker-funnel-response-card.png" alt="Analizzare i dati con Chat con i collaboratori"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" title="Analizzare i dati con Chat con i collaboratori">Analizzare i dati con Chat collaboratore</a>
                    </p>
                    <p class="is-size-6">Poni domande in linguaggio naturale per creare funnel, visualizzazioni e scoprire dove i clienti abbandonano il percorso.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/analytics-chat" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Explore trends and root causes">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Esplorare tendenze e cause profonde">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-line-card.png" alt="Esplorare tendenze e cause profonde"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" title="Esplorare tendenze e cause profonde">Esplora tendenze e cause principali</a>
                    </p>
                    <p class="is-size-6">Analizza le modifiche apportate ai dati Customer Journey Analytics e scopri cosa li alimenta, senza dover scrivere query manuali.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/root-cause-analysis" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->

<!--
CARDS

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja
  {title = Validate Customer Journey Analytics data}
  {description = Check dataset quality with the data validation skill and resolve issues before you build dashboards.}
  {cta = Read}
  {image = ../../assets/data-validation-aep/dataset-validation.png}

* https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja
  {title = Validate data during your upgrade}
  {description = Compare Adobe Analytics and Customer Journey Analytics data to confirm that your upgrade is on track.}
  {cta = Read}
  {image = ../../assets/data-validation-aa-cja/trend-bar-card.png}
-->
<!-- START CARDS HTML - DO NOT MODIFY BY HAND -->
<div class="columns">
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate Customer Journey Analytics data">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Convalidare dati Customer Journey Analytics">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aep/dataset-validation.png" alt="Convalidare dati Customer Journey Analytics"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" title="Convalidare dati Customer Journey Analytics">Convalida dati Customer Journey Analytics</a>
                    </p>
                    <p class="is-size-6">Prima di creare le dashboard, controlla la qualità del set di dati con l’abilità di convalida dei dati e risolvi i problemi.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/validate-dataset-quality-for-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
    <div class="column is-half-tablet is-half-desktop is-one-third-widescreen" aria-label="Validate data during your upgrade">
        <div class="card" style="height: 100%; display: flex; flex-direction: column; height: 100%;">
            <div class="card-image">
                <figure class="image x-is-16by9">
                    <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Convalidare i dati durante l’aggiornamento">
                        <img class="is-bordered-r-small" src="../../assets/data-validation-aa-cja/trend-bar-card.png" alt="Convalidare i dati durante l’aggiornamento"
                             style="width: 100%; aspect-ratio: 16 / 9; object-fit: cover; overflow: hidden; display: block; margin: auto;">
                    </a>
                </figure>
            </div>
            <div class="card-content is-padded-small" style="display: flex; flex-direction: column; flex-grow: 1; justify-content: space-between;">
                <div class="top-card-content">
                    <p class="headline is-size-6 has-text-weight-bold">
                        <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" title="Convalidare i dati durante l’aggiornamento">Convalida dei dati durante l'aggiornamento</a>
                    </p>
                    <p class="is-size-6">Confronta i dati di Adobe Analytics e Customer Journey Analytics per verificare che l’aggiornamento sia in linea.</p>
                </div>
                <a href="https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/coworker/chat/use-cases/data-insights/data-validation-aa-cja" class="spectrum-Button spectrum-Button--outline spectrum-Button--primary spectrum-Button--sizeM" style="align-self: flex-start; margin-top: 1rem;">
                    <span class="spectrum-Button-label has-no-wrap has-text-weight-bold">Letto</span>
                </a>
            </div>
        </div>
    </div>
</div>
<!-- END CARDS HTML - DO NOT MODIFY BY HAND -->



## Layout della tabella dei casi d’uso chiave

<!-- The following table are links to each of the stand-alone articles in this folder -->

| Caso d’uso | Descrizione |
| --- | --- |
| [Analizzare i dati di Customer Journey Analytics e Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md) | Risponde alle domande in linguaggio naturale sulle visualizzazioni di dati o sulle suite di rapporti, crea funnel e altre visualizzazioni e trova dove i clienti abbandonano. Puoi aprire qualsiasi visualizzazione in Analysis Workspace per ulteriori analisi. |
| [Esplora tendenze e cause principali](/help/chat/use-cases/data-insights/root-cause-analysis.md) | Identifica le tendenze nei dati di Customer Journey Analytics e Adobe Analytics e i fattori che determinano cambiamenti nelle prestazioni, senza query manuali. |
| [Pianifica l&#39;implementazione](/help/chat/use-cases/data-insights/implementation-guide.md) | Crea un piano personalizzato e dettagliato per l’implementazione di Customer Journey Analytics, l’aggiornamento da Adobe Analytics o la configurazione di Content Analytics, Marketing Campaign Analytics o Streaming Media Collection su Edge. I piani includono dettagli quali proprietari, stime dello sforzo, dipendenze e passaggi di convalida. |
| [Generare un elenco di controllo dell&#39;implementazione](/help/chat/use-cases/data-insights/intelligent-checklist.md) | Trasforma il piano di implementazione di Customer Journey Analytics in un elenco di controllo in Progetti coworking, in cui il team può assegnare passaggi, tenere traccia dello stato e aggiungere gate di approvazione. |
| [Convalida dati durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md) | Confronta dimensioni, metriche e tendenze tra le suite di rapporti di Adobe Analytics e le visualizzazioni dati di Customer Journey Analytics, quindi consiglia di apportare correzioni per supportare l’aggiornamento. |
| [Convalida l&#39;implementazione di Streaming Media](/help/chat/use-cases/data-insights/streaming-media-validation.md) | Controlla lo stream di dati, lo schema, il set di dati, la visualizzazione dati e i dati della sessione per verificare che il tracciamento dei contenuti multimediali in streaming sia configurato e che la raccolta dei dati sia corretta. |
| [Convalida qualità set di dati per Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md) | Identifica i set di dati che alimentano i rapporti di Customer Journey Analytics, quindi controlla gli schemi, la qualità dell’identità e la qualità dei campi in modo da poter risolvere i problemi prima di creare dashboard. |
| [Convalida dati dopo l&#39;acquisizione in Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md) | Esegue controlli statistici e semantici sui set di dati e sui campi di Experience Platform per individuare problemi di qualità dei dati, ad esempio valori non validi o problemi di mappatura. |

Per ulteriori informazioni su questi casi d&#39;uso, incluse le abilità che utilizzano e i prompt di esempio, vedi [Casi d&#39;uso Approfondimenti dati](/help/chat/use-cases/overview.md#data-insights).

