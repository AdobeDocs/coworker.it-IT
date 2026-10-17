---
title: Analizzare le prestazioni di contenuti e Creative con Chat con i collaboratori
description: Utilizza Chat con collaboratori per individuare i contenuti vincenti in comune, attribuire i ricavi alle immagini visualizzate dai clienti e confrontare i contenuti creativi tra canali e pubblico.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: e3d485f7cd1c45bf3fd1217ffcceeccfd4242c7b
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%
---

# Panoramica sulle prestazioni dei contenuti

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilizza la chat di Adobe CX Enterprise Coworker per capire quali contenuti hanno vinto e perché, fino agli attributi di ciascuna risorsa, in modo da poter investire in ciò che funziona. Oltre ai file su cui sono stati effettuati clic, puoi vedere quali immagini, messaggi e temi generano coinvolgimento e ricavi tra canali e pubblico.

Le prestazioni dei contenuti sono uno dei numerosi domini di analisi disponibili in Chat con coorker. Per visualizzare tutti i domini, vedere [Avviare l&#39;analisi in Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) in Analizzare i dati con Chat di Coworker.

**Ideale per:** utente aziendale

## Prerequisiti

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). Low for the third bullet: the attribute-level and image exposure descriptions suggest that these use cases rely on Content Analytics data in Customer Journey Analytics, and implementation-guide.md lists Content Analytics as an implementation path, but no source confirms this. It's a shared bullet rather than a table row because it would apply to every use case on this page. The paid channel row ("Compare Meta ad creative to our web banners") may need an additional data source, which would become an "Additional prerequisite" note on that row in the Use cases table. Confirm with the PM. -->

Per utilizzare i casi d’uso in questa pagina, è necessario:

* Chat con collaboratori connessa alle visualizzazioni dati di Customer Journey Analytics o alle suite di rapporti di Adobe Analytics. Vedi [Introduzione all&#39;analisi dei dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accesso alle visualizzazioni dati o alle suite di rapporti che desideri analizzare. La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics.
* Content Analytics è configurato in Customer Journey Analytics in modo che Chat con collaboratori possa analizzare gli attributi del contenuto e l’esposizione delle immagini. Per pianificare un&#39;implementazione di Content Analytics, consulta [Pianificare l&#39;implementazione con Coworker](/help/chat/use-cases/data-insights/implementation-guide.md).

## Casi d’uso

| Caso d’uso | Funzione |
| --- | --- |
| Trovare i contenuti vincenti in comune<p>![Trovare i contenuti vincenti in comune](assets/content-performance.png)</p> | Mostra quali immagini e messaggi funzionano a livello di attributo, non solo quali file hanno ricevuto un clic.<p>**Richieste di esempio:**</p><ul><li>&quot;Quali caratteristiche hanno in comune le immagini dalle prestazioni migliori?&quot;</li><li>&quot;Quali attributi di contenuto sono più determinanti per il coinvolgimento?&quot;</li></ul> |
| Attribuisci i ricavi ai contenuti visualizzati dai clienti | Associa l’esposizione delle immagini a ricavi, conversioni e coinvolgimento con l’attribuzione algoritmica.<p>**Ideale per:** analista, utente aziendale</p><p>**Richieste di esempio:**</p><ul><li>&quot;Quali immagini protagonista hanno registrato i maggiori ricavi nell&#39;ultimo trimestre?&quot;</li><li>&quot;Quanti ricavi sono legati a questo banner?&quot;</li></ul> |
| Confrontare i contenuti creativi tra canali a pagamento e canali di proprietà | Mostra quali elementi visivi e temi vincono su canali web, mobili e a pagamento in un’unica visualizzazione.<p>**Richieste di esempio:**</p><ul><li>&quot;Quali temi creativi vincono a pagamento e sul nostro sito?&quot;</li><li>&quot;Confronto tra Meta e i nostri banner Web&quot;</li></ul> |
| Scopri quali elementi visivi spostano ogni pubblico | Mostra quali elementi visivi funzionano per ogni pubblico per guidare la personalizzazione e i suggerimenti creativi.<p>**Richieste di esempio:**</p><ul><li>&quot;Quali elementi visivi offrono prestazioni migliori per ciascun segmento?&quot;</li><li>&quot;Quali immagini funzionano per i visitatori nuovi?&quot;</li></ul> |

<!--
HIDDEN until the skills are confirmed. To publish, remove this comment wrapper.

## Skills used

FLAG: Confidence: Low. No source in the repo (workflows.md, the Skills and limitations table, or any data insights article) names the skills behind these use cases. Get the skill IDs from the PM, replace the placeholder rows, and add the skills to the Skills and limitations table on analytics-overview.md so that the link above the table covers them. When you unhide this section, wrap this FLAG note in its own HTML comment.

Coworker uses the following skills for the use cases described in this article. For a list of all analytics skills, including the permissions they require and what they don't cover, see [Skills and limitations](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analyze data with Coworker Chat.

| Skill | Used for |
| --- | --- |
| *[Skill to be confirmed]* | Find what winning content has in common<br>Attribute revenue to the content customers see<br>Compare creative across paid and owned channels<br>Know which visuals move each audience |

-->

## Suggerimenti per ottenere risultati migliori

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the row descriptions. -->

* Denomina la metrica e l’intervallo di date che desideri analizzare, ad esempio i ricavi dell’ultimo trimestre.
* Specifica i segmenti, i tipi di pubblico o i canali da confrontare.
* Chiedi informazioni sugli attributi del contenuto, ad esempio immagini, temi o messaggi, anziché sui singoli file quando desideri sapere perché il contenuto funziona bene.

## Passaggi successivi

* Per una panoramica dell&#39;analisi dei dati con Chat di Coworker, inclusi gli altri domini di analisi e le best practice, consulta [Analizzare i dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md).
* Per impostare la chat di Coworker e seguire un esempio di lavoro, vedere [Introduzione all&#39;analisi dei dati con la chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
