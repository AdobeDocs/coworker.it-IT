---
title: Fai domande sui contenuti con Chat con i collaboratori
description: Chiedi a Coworker Chat i tuoi contenuti in linguaggio semplice, da generale a specifico, e ottieni risposte Content Analytics accurate senza esperienza di analisti.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f1ffc050071fc0ca48ae36c7aea8bc66eff2a147
workflow-type: tm+mt
source-wordcount: '1009'
ht-degree: 2%
---

# Fai domande sul contenuto

<!-- FLAG: Confirm with the PM: (1) availability (GA, beta, or experimental) and whether this page needs an AVAILABILITY note or `hide: true` until launch, and (2) any required Coworker entitlement. Content Analytics itself has no separate permission: users get access through data views that are configured for Content Analytics (Access control section of analytics-platform.en/help/content-analytics/config/configuration.md). -->

Utilizza Adobe CX Enterprise Coworker Chat per ottenere risposte accurate sui contenuti da Adobe Content Analytics. Ponete una domanda specifica, ad esempio &quot;Quali immagini protagonista hanno generato i maggiori ricavi lo scorso trimestre?&quot;, o una domanda generale, come &quot;Quale tipo di contenuto dovrei dare priorità?&quot;. Collaboratore trasforma la tua domanda in un&#39;analisi del suono.

Coworker è consapevole di come i dati di Content Analytics siano strutturati e applica le regole di reporting che farebbe un analista esperto, in modo che gli esperti di marketing e altri utenti aziendali ottengano risultati affidabili senza una profonda esperienza Content Analytics.

Per altri casi di utilizzo delle prestazioni dei contenuti, vedere [Panoramica delle prestazioni dei contenuti](/help/chat/use-cases/data-insights/content-performance.md).

**Ideale per:** utente aziendale, analista

## Prerequisiti

<!-- FLAG: Confidence: High. The first two bullets match the other data insights pages. The third bullet follows the Content Analytics docs in analytics-platform.en: Content Analytics components are available only in data views that are configured for Content Analytics (report/report.md), and there's no separate Content Analytics permission (config/configuration.md). -->

Per porre domande sul contenuto, è necessario:

* Chat con il collaboratore connessa alle visualizzazioni dati di Customer Journey Analytics. Vedi [Introduzione all&#39;analisi dei dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accesso alle visualizzazioni dati che desideri analizzare. La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics.
* Una visualizzazione dati configurata per Content Analytics. Vedere [Configurare Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration) nella guida di Customer Journey Analytics.

## Fai una domanda sui contenuti

1. Accedi a Collaboratore.

1. Seleziona **[!UICONTROL Nuova chat]**.

1. Nel campo di testo, fai una domanda sul contenuto. Ad esempio:

   **Chiedi conferma**

   > Quale tipo di contenuto devo assegnare come priorità?

   <!-- FLAG: The skill includes activation words and phrases, but they weren't provided. Confirm with the PM whether customers need to use specific words to trigger the skill, or whether any content question routes to it automatically. If specific words are needed, list them here. -->

   Collaboratore utilizza l&#39;abilità `analyze-content` per rispondere alle domande sul contenuto.

1. (Condizionale) Se la domanda è aperta a più di un’interpretazione, rispondi alle domande chiarificatrici poste da Collaboratore, ad esempio il tipo di contenuto, il canale o l’intervallo di date desiderato.

1. Esamina i risultati.

1. (Facoltativo) Fai domande di follow-up nella stessa conversazione per approfondire o apri una visualizzazione in Analysis Workspace per un controllo più manuale. Vedi [Aprire una visualizzazione in Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Esempi di prompt

Nella tabella seguente sono riportati esempi di prompt per diversi tipi di domande sui contenuti. Utilizzali come punto di partenza e adattali al tuo contenuto.

| Tipo di domanda | Esempi di prompt |
| --- | --- |
| Ampia o esplorativa | <ul><li>&quot;Che tipo di contenuti dovrei dare priorità?&quot;</li><li>&quot;Come stanno andando i nostri contenuti?&quot;</li></ul> |
| A livello di attributo | <ul><li>&quot;Quali caratteristiche hanno in comune le immagini dalle prestazioni migliori?&quot;</li><li>&quot;Quali attributi di contenuto sono più determinanti per il coinvolgimento?&quot;</li></ul> |
| Ricavi e conversioni | <ul><li>&quot;Quali immagini protagonista hanno registrato i maggiori ricavi nell&#39;ultimo trimestre?&quot;</li><li>&quot;Quanti ricavi sono legati a questo banner?&quot;</li></ul> |
| Canali e pubblico | <ul><li>&quot;Quali temi creativi vincono a pagamento e sul nostro sito?&quot;</li><li>&quot;Quali immagini funzionano per i visitatori nuovi?&quot;</li></ul> |

## In che modo Collaboratore risponde alle domande sui contenuti

<!-- FLAG: Confidence: High for the list of what the skill includes, metric matching, filtering pages by Experience ID, and choosing an attribution model per question (sourced from the PM's skill description and feature summary). Medium for the remaining details, which combine the skill description with the Content Analytics component reference in the Customer Journey Analytics guide. The skill's specific query defaults, attribution models, and visualization rules weren't provided. Confirm with the PM before adding them. -->

Il collaboratore risponde alle domande sul contenuto con l&#39;abilità `analyze-content`, che include il contesto e le protezioni seguenti. L&#39;abilità si abbina all&#39;abilità `cja` ed esegue tutte le query sulle visualizzazioni dati di Customer Journey Analytics tramite gli stessi strumenti di Customer Journey Analytics.

### Interroga i valori predefiniti e chiarisce le domande

Se la domanda tralascia un dettaglio, l’abilità applica un valore predefinito ragionevole. Se l&#39;abilità non è sicura di cosa intendi, pone una domanda chiarificatrice invece di indovinare.

### Corrispondenza delle metriche per risorse ed esperienze

<!-- FLAG: The table covers web and mobile content. Paid media content uses separate summary metrics, such as Impressions, Clicks, and Spend with a reporting-level suffix (for example, Clicks | Asset Summary), that can't be combined with event metrics such as Asset Views (config/paid-media.md in analytics-platform.en). Confirm with the PM how the skill handles paid media, then add a row or note. -->

Content Analytics tiene traccia di due tipi di contenuto: risorse ed esperienze. Ciascuno ha le proprie metriche. L’abilità associa sempre la metrica al tipo di contenuto richiesto.

| Tipo di contenuto | Che cos’è | Metriche utilizzate dall’abilità |
| --- | --- | --- |
| Risorse | Un singolo elemento di contenuto, ad esempio un’immagine | Visualizzazioni risorse, clic su risorse, tasso di click-through risorse (CTR) |
| Esperienze | Tutto il testo di una pagina web o la combinazione di testo, risorse e chiamate all’azione in un’app mobile | Visualizzazioni esperienza, clic su esperienza, tasso di click-through esperienza (CTR) |

### Architettura dei dati di Content Analytics

L’abilità comprende come sono strutturati i dati di Content Analytics. Ad esempio:

* **ID esperienza:** quando chiedi informazioni su una pagina specifica, l&#39;abilità filtra in base al Content Experience ID che identifica tale pagina.
* **Attributi generati dall&#39;intelligenza artificiale:** ogni risorsa ed esperienza è descritta da attributi quali lo stile della fotografia, i colori, il tono e la strategia di persuasione. L’abilità utilizza questi attributi per spiegare perché il contenuto funziona bene, non solo quale contenuto funziona bene.

Per l&#39;elenco completo dei componenti, vedere [Componenti Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/report/components) nella guida di Customer Journey Analytics.

### Attribuzione

L’abilità sceglie il modello di attribuzione adatto alla tua domanda. Ad esempio, a una domanda sui clic su un’immagine viene risposto in modo diverso rispetto a una domanda sulla quantità di ricavi a cui ha contribuito quell’immagine. Per ulteriori informazioni, vedere [Modelli di attribuzione](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/attribution/models#attribution-models) nella guida di Customer Journey Analytics.

### Analisi e flussi di lavoro comuni

L’abilità include istruzioni per le analisi comuni dei contenuti, ad esempio:

* Trovare gli attributi in comune tra le risorse o esperienze dalle prestazioni migliori.
* Associare l’esposizione dei contenuti a conversioni e ricavi.
* Confronto dei contenuti tra canali web, mobili e media a pagamento.
* Confrontare quali contenuti funzionano per diversi tipi di pubblico e segmenti.
* Identificazione di contenuti sovrautilizzati o sottoutilizzati.

### Visualizzazioni

L’abilità seleziona visualizzazioni che corrispondono alla domanda e ai dati, in modo che i risultati siano facili da leggere e condividere.

## Suggerimenti per ottenere risultati migliori

* Inizia a fare il grande se non sei sicuro di cosa chiedere. Un collaboratore può trasformare una domanda generale in un&#39;analisi mirata, e da qui puoi perfezionare.
* Indica se intendi risorse singole, come immagini, o esperienze intere, come le pagine, quando sai quale desideri.
* Denomina la metrica e l’intervallo di date che desideri analizzare, ad esempio i ricavi dell’ultimo trimestre.
* Specifica i segmenti, i tipi di pubblico o i canali da confrontare.
* Chiedi informazioni sugli attributi del contenuto, ad esempio immagini, temi o messaggi, anziché sui singoli file quando desideri sapere perché il contenuto funziona bene.
* Aggiungi la tua visualizzazione dati preferita alla memoria di Chat con collaboratori se analizzi sempre la stessa. Consulta [Aggiungere una visualizzazione dati o una preferenza della suite di rapporti in memoria](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory).

## Passaggi successivi

* Per ulteriori casi di utilizzo delle prestazioni dei contenuti, vedere [Panoramica delle prestazioni dei contenuti](/help/chat/use-cases/data-insights/content-performance.md).
* Per ulteriori informazioni su Content Analytics, consulta [Panoramica di Content Analytics](https://experienceleague.adobe.com/it/docs/analytics-platform/using/content-analytics/content-analytics) nella guida di Customer Journey Analytics.
* Per una panoramica dell&#39;analisi dei dati con Chat di Coworker, incluse le best practice, consulta [Analizzare i dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md).
