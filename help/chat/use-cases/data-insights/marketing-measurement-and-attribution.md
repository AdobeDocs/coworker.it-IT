---
title: Misurare l’impatto e l’attribuzione del marketing con le chat dei collaboratori
description: Utilizza Chat con collaboratori per misurare l’impatto incrementale di ciascun canale, individuare la destinazione della spesa, creare scenari di budget what-if e verificare la qualità del modello di marketing.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 5973a87d21b23d7621366108716cbd476e6f66ae
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 2%
---

# Panoramica sulla misurazione e l’attribuzione marketing

<!-- FLAG: Confidence: High for the first sentence and "Best for" (carried over from analytics-overview.md). Medium for the second sentence, which summarizes the row descriptions from the slides. -->

Utilizza Adobe CX Enterprise Coworker Chat per comprendere l’impatto incrementale di ogni canale e campagna di marketing, in modo da allocare la spesa per ottimizzare il ROI. Prima di eseguire l&#39;impegno, è possibile vedere come funzionano i canali, dove la spesa aggiuntiva non viene più pagata e come si confrontano le diverse allocazioni di budget.

La misurazione e l’attribuzione del marketing sono uno dei numerosi domini di analisi disponibili nella chat di Collaborator. Per visualizzare tutti i domini, vedere [Avviare l&#39;analisi in Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md#start-analyzing-in-coworker-chat) in Analizzare i dati con Chat di Coworker.

**Ideale per:** analista, utente aziendale

## Prerequisiti

<!-- FLAG: Confidence: High for the shared bullets (sourced from analytics-chat.md and the Skills and limitations table). They're confirmed for Measure campaign performance only; whether the marketing mix modeling use cases also need a data view or report suite connection is unknown. Low for the "Additional prerequisite" notes on the four marketing mix modeling rows in the Use cases table: incremental impact, response curves, budget scenarios, and model retraining describe a marketing mix model, but no source names the product or data that these use cases need. It could be Adobe Mix Modeler or Marketing Campaign Analytics (listed as an implementation path in implementation-guide.md). Confirm with the PM before publishing. -->

Per utilizzare i casi d’uso in questa pagina, è necessario:

* Chat con collaboratori connessa alle visualizzazioni dati di Customer Journey Analytics o alle suite di rapporti di Adobe Analytics. Vedi [Introduzione all&#39;analisi dei dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Accesso alle visualizzazioni dati o alle suite di rapporti che desideri analizzare. La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics.

## Casi d’uso

| Caso d’uso | Funzione |
| --- | --- |
| Scopri l’impatto incrementale di ogni canale | Mostra il valore incrementale di ciascun canale, il modo in cui i canali si amplificano a vicenda e il ruolo dei fattori esterni.<p>**Richieste di esempio:**</p><ul><li>&quot;Quali canali hanno determinato le conversioni più incrementali?&quot;</li><li>&quot;In che modo la ricerca a pagamento e la visualizzazione si amplificano a vicenda?&quot;</li></ul><p>**Prerequisito aggiuntivo:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche un modello di misurazione di marketing addestrato. *[Requisiti di prodotto e installazione da confermare.]*</p> |
| Trovare dove la spesa inizia a saturare<p>![Trovare il punto in cui la spesa inizia a saturare](assets/marketing-measurement.png)</p> | Mostra le curve di risposta che mostrano dove la spesa aggiuntiva smette di pagare.<p>**Richieste di esempio:**</p><ul><li>&quot;Dove la spesa per la ricerca a pagamento inizia a saturare?&quot;</li><li>&quot;Mostra curve di risposta per ciascun canale&quot;</li></ul><p>**Prerequisito aggiuntivo:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche un modello di misurazione di marketing addestrato. *[Requisiti di prodotto e installazione da confermare.]*</p> |
| Creare scenari di budget what-if | Confronta le opzioni di allocazione per supportare le decisioni di pianificazione.<p>**Ideale per:** utente aziendale</p><p>**Richieste di esempio:**</p><ul><li>&quot;Creare scenari di budget per il prossimo trimestre&quot;</li><li>&quot;Cosa succede se sposto il 10% della spesa dal display alla ricerca?&quot;</li></ul><p>**Prerequisito aggiuntivo:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche un modello di misurazione di marketing addestrato. *[Requisiti di prodotto e installazione da confermare.]*</p> |
| Controllare la qualità del modello e quando riqualificarsi | Esamina la qualità del modello, i dettagli di formazione e le metriche di punteggio in modo da sapere quanto considerare attendibile una risposta.<p>**Ideale per:** analista</p><p>**Richieste di esempio:**</p><ul><li>&quot;Ci sono altri fattori di cui abbiamo bisogno per questo modello?&quot;</li><li>&quot;Questo modello deve essere riqualificato?&quot;</li></ul><p>**Prerequisito aggiuntivo:** Oltre ai [prerequisiti generali](#prerequisites), questo caso d&#39;uso richiede anche un modello di misurazione di marketing addestrato. *[Requisiti di prodotto e installazione da confermare.]*</p> |
| [Misura le prestazioni della campagna](/help/chat/use-cases/workflows.md#data-insights) | Scopri le prestazioni di campagne, canali e proprietà web in un dato periodo.<p>**Prompt di esempio:** &quot;Quali sono state le prestazioni delle campagne Web di Acrobat il mese scorso?&quot;</p><p>Per ulteriori informazioni, consulta [Informazioni sui dati](/help/chat/use-cases/workflows.md#data-insights) nei casi di utilizzo di Chat con coorker.</p> |

## Abilità utilizzate

<!-- FLAG: Confidence: High for Measure campaign performance (workflows.md lists `cja`, `aa`, `dx-api`, and `knowledge-graph` for "Campaign performance"). `dx-api` and `knowledge-graph` aren't in the Skills and limitations table on analytics-overview.md. Low for the other four use cases: no source names their skills. Get the skill IDs from the PM, replace the placeholder row, and add the skills to the Skills and limitations table. -->

Per i casi d’uso descritti in questo articolo, il collaboratore utilizza le seguenti competenze. Per un elenco di tutte le abilità di analisi, incluse le autorizzazioni necessarie e quelle che non coprono, consulta [Abilità e limitazioni](/help/chat/use-cases/data-insights/analytics-overview.md#skills-and-limitations) in Analizzare i dati con Chat con collaboratori.

| Competenza | Utilizzato per |
| --- | --- |
| `cja`, `aa`, `dx-api`, `knowledge-graph` | Misurare le prestazioni della campagna |
| *[Abilità da confermare]* | Scopri l&#39;impatto incrementale di ogni canale<br>Scopri dove la spesa inizia a saturare<br>Crea scenari di budget ipotetici<br>Controlla la qualità del modello e quando riqualificarti |

## Suggerimenti per ottenere risultati migliori

<!-- FLAG: Confidence: Medium. The first two bullets are adapted from the best practices in analytics-overview.md. The third bullet is inferred from the sample prompts. -->

* Denomina i canali, le campagne e l’intervallo di date che desideri analizzare.
* Fai riferimento a qualsiasi ipotesi già in tuo possesso, ad esempio due canali che lavorano insieme, in modo che Chat con i collaboratori possa convalidarla o escluderla.
* Indicare lo spostamento di budget specifico che si desidera verificare durante la creazione di scenari di simulazione, ad esempio lo spostamento del 10% della spesa da un canale all&#39;altro.

## Passaggi successivi

* Per una panoramica dell&#39;analisi dei dati con Chat di Coworker, inclusi gli altri domini di analisi e le best practice, consulta [Analizzare i dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-overview.md).
* Per impostare la chat di Coworker e seguire un esempio di lavoro, vedere [Introduzione all&#39;analisi dei dati con la chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
