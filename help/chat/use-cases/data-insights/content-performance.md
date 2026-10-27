---
title: Analizzare le prestazioni di contenuti e Creative con Chat con i collaboratori
description: Utilizza Chat con collaboratori per individuare i contenuti vincenti in comune, attribuire i ricavi alle immagini visualizzate dai clienti e confrontare i contenuti creativi tra canali e pubblico.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 8e88ec793bd4ae6fe4692c1d5107fe01fe14bf7f
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 1%
---

# Panoramica sulle prestazioni dei contenuti

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilizza la chat di Adobe CX Enterprise Coworker per capire quali contenuti hanno vinto e perché, fino agli attributi di ciascuna risorsa, in modo da poter investire in ciò che funziona. Oltre ai file su cui sono stati effettuati clic, puoi vedere quali immagini, messaggi e temi generano coinvolgimento e ricavi tra canali e pubblico.

Le prestazioni dei contenuti sono uno dei numerosi domini di analisi disponibili in Chat con coorker. Per visualizzare tutti i domini, vedere [Avviare l&#39;analisi in Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) in Analizzare i dati con Chat di Coworker.

**Ideale per:** utente aziendale

## Prerequisiti

<!-- FLAG: Confidence: High for the first two bullets (sourced from analytics-chat.md and the Skills and limitations table). High for the third bullet: attribute-level and asset analysis needs Content Analytics components, which are available only in data views that are configured for Content Analytics (report/report.md in analytics-platform.en). This applies whichever skill runs the analysis. It's a shared bullet rather than a table row because it applies to every use case on this page. The SME confirmed (October 2026) that the skill doesn't support paid media yet, so the paid channel use case was rewritten for web and mobile. Support is planned, either in this skill or in a separate add-on skill (not decided). When it ships, consider restoring paid channels to that row with an "Additional prerequisite" note: paid media needs the Paid Media channel enabled in Content Analytics through an Experience Platform paid media source connector, such as Meta Ads or Google Ads, and comparing paid creative with on-site revenue needs custom tracking-key mapping (config/paid-media.md in analytics-platform.en). -->

Per utilizzare i casi d’uso in questa pagina, è necessario:

* Chat con collaboratori connessa alle visualizzazioni dati di Customer Journey Analytics o alle suite di rapporti di Adobe Analytics. Vedi [Introduzione all&#39;analisi dei dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accesso alle visualizzazioni dati o alle suite di rapporti che desideri analizzare. La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics.
* Una visualizzazione dati configurata per Content Analytics. Vedere [Configurare Content Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/configuration/configuration) nella guida di Customer Journey Analytics.

## Casi d’uso

| Caso d’uso | Funzione |
| --- | --- |
| Trovare i contenuti vincenti in comune<p>![Trovare i contenuti vincenti in comune](assets/content-performance.png)</p> | Mostra quali immagini e messaggi funzionano a livello di attributo, non solo quali file hanno ricevuto un clic.<p>**Richieste di esempio:**</p><ul><li>&quot;Quali caratteristiche hanno in comune le immagini dalle prestazioni migliori?&quot;</li><li>&quot;Quali attributi di contenuto sono più determinanti per il coinvolgimento?&quot;</li></ul> |
| Attribuisci i ricavi ai contenuti visualizzati dai clienti | Associa l’esposizione delle immagini a ricavi, conversioni e coinvolgimento con l’attribuzione algoritmica.<p>**Ideale per:** analista, utente aziendale</p><p>**Richieste di esempio:**</p><ul><li>&quot;Quali immagini hanno determinato i maggiori ricavi nell&#39;ultimo trimestre?&quot;</li><li>&quot;Quanto costa l&#39;immagine su https://www.example.com/images/spring-sale.jpg?&quot;</li></ul> |
| Confronto tra creatività su web e dispositivi mobili | Mostra quali elementi visivi e temi vincono sul sito e nell’app mobile in un’unica visualizzazione.<p>**Richieste di esempio:**</p><ul><li>&quot;Quali temi creativi vincono nella nostra app mobile e sul nostro sito?&quot;</li><li>&quot;Confronta le prestazioni delle immagini nella nostra app mobile e sul nostro sito&quot;</li></ul> |
| Scopri quali elementi visivi spostano ogni pubblico | Mostra quali elementi visivi funzionano per ogni pubblico per guidare la personalizzazione e i suggerimenti creativi.<p>**Richieste di esempio:**</p><ul><li>&quot;Quali elementi visivi offrono prestazioni migliori per ciascun segmento?&quot;</li><li>&quot;Quali immagini funzionano per i visitatori nuovi?&quot;</li></ul> |

## Abilità utilizzate

<!-- FLAG: Confidence: Medium. The `analyze-content` skill is a foundational skill for content questions, so it's listed for every use case on this page. Confirm with the PM that it covers all four. -->

Per i casi d’uso descritti in questo articolo, il collaboratore utilizza le seguenti competenze. Per un elenco di tutte le abilità di analisi, incluse le autorizzazioni necessarie e quelle che non coprono, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analizzare i dati con Chat con collaboratori.

| Competenza | Utilizzato per |
| --- | --- |
| `cja`,`analyze-content` <br/> (disponibilità limitata) | Scopri quali contenuti vincenti hanno in comune<br>Attribuisci ricavi ai contenuti che i clienti vedono<br>Confronta i contenuti creativi su web e dispositivi mobili<br>Scopri quali elementi visivi spostano ogni pubblico<p>Per ulteriori informazioni, vedere [Poni domande sul contenuto](/help/chat/use-cases/data-insights/ask-content-questions.md).</p> |

## Suggerimenti per ottenere risultati migliori

<!-- FLAG: Confidence: High for the first bullet (SME feedback, October 2026). Medium for the rest: the second and third bullets are adapted from the best practices in analytics-overview.md, and the fourth bullet is inferred from the row descriptions. -->

* Quando chiedi informazioni su un’immagine specifica, includi il relativo URL o ID risorsa. Collaboratore non può identificare un’immagine in base al suo ruolo sulla pagina, ad esempio un’immagine protagonista o un banner.
* Denomina la metrica e l’intervallo di date che desideri analizzare, ad esempio i ricavi dell’ultimo trimestre.
* Specifica i segmenti, i tipi di pubblico o i canali da confrontare.
* Chiedi informazioni sugli attributi del contenuto, ad esempio immagini, temi o messaggi, anziché sui singoli file quando desideri sapere perché il contenuto funziona bene.

## Passaggi successivi

* Per scoprire come Coworker risponde alle domande sul contenuto, consulta [Poni domande sul contenuto](/help/chat/use-cases/data-insights/ask-content-questions.md) (disponibilità limitata).
* Per una panoramica dell&#39;analisi dei dati con Chat di Coworker, inclusi gli altri domini di analisi e le best practice, consulta [Analizzare i dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md).
* Per impostare la chat di Coworker e seguire un esempio di lavoro, vedere [Introduzione all&#39;analisi dei dati con la chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
