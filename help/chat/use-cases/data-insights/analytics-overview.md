---
title: Analizzare i dati di Analytics con Adobe CX Enterprise Coworker Chat
description: Utilizza Adobe CX Enterprise Coworker Chat per analizzare i dati di Customer Journey Analytics e Adobe Analytics, trovare le cause principali e aprire i risultati in Analysis Workspace.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: f1ffc050071fc0ca48ae36c7aea8bc66eff2a147
workflow-type: tm+mt
source-wordcount: '1358'
ht-degree: 1%
---

# Analizzare i dati con Chat con i collaboratori

Le informazioni contenute in questa pagina forniscono una panoramica di Adobe CX Enterprise Coworker Chat e di come possono aiutarti ad analizzare i dati per la tua organizzazione.

Chat con i collaboratori consente ai team di automatizzare le attività dei prodotti Adobe utilizzando il linguaggio naturale, trasformando rapidamente le idee in azioni con una pianificazione flessibile, competenze personalizzabili ed esecuzione intelligente. Per ulteriori informazioni generali su Coworker, vedere [Panoramica di CX Enterprise Coworker](/help/home.md).

## Come funziona l’analisi dei dati

Chat con i collaboratori può eseguire analisi avanzate dei dati che in precedenza erano possibili solo in Analysis Workspace. Chat con collaboratori accede ai dati dalle visualizzazioni dati di Customer Journey Analytics o dalle suite di rapporti di Adobe Analytics, consentendoti di esplorare i dati e ottenere risposte con prompt in linguaggio naturale.

La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics. Puoi accedere solo alle visualizzazioni dati, alle suite di rapporti, alle dimensioni, alle metriche e ai segmenti disponibili in Analysis Workspace.

Quando crei una visualizzazione nella chat di Coworker, puoi aprirla in Analysis Workspace in qualsiasi momento per un controllo più manuale. Vedi [Aprire una visualizzazione in Analysis Workspace](/help/chat/use-cases/data-insights/analytics-chat.md#open-a-visualization-in-analysis-workspace).

## Risposte rapide e un lavoro approfondito

Puoi utilizzare Chat con i collaboratori in due modi, a seconda della quantità di analisi necessaria:

* **Risposte rapide** - Fai una domanda diretta in un linguaggio semplice e ottieni una risposta immediata. Gli utenti aziendali utilizzano spesso la chat con collaboratori in questo modo, e gli analisti la utilizzano anche quando hanno bisogno di una risposta rapida per una parte interessata.
* **Lavoro approfondito** - Parla a più riprese con Coworker Chat per indagare su un problema di business, escludere le cause e arrivare a un consiglio. In genere, gli analisti utilizzano questo approccio per esplorare i dati in modo approfondito prima di creare un consiglio.

## Inizia l’analisi in Chat con i collaboratori

Per iniziare, descrivi ciò che desideri sapere in un linguaggio semplice. Chat con collaboratori pianifica l’analisi, esegue query sulle visualizzazioni dati o sulle suite di rapporti e crea visualizzazioni e riepiloghi.

I seguenti casi d’uso sono raggruppati per dominio di analisi. Ogni dominio ha la propria pagina con casi d’uso, prompt di esempio, prerequisiti e competenze da utilizzare.

| Dominio | Che cosa puoi fare | Ideale per |
| --- | --- | --- |
| [Implementazione e amministrazione intelligenti](/help/chat/use-cases/data-insights/data-governance-and-validation.md) | Imposta, esegui la migrazione e gestisci l’implementazione di e assicurati di poter considerare attendibili i dati dietro ogni risposta. | Amministrazione |
| [Analisi Percorso](/help/chat/use-cases/data-insights/journey-analysis.md) | Scopri dove i clienti abbandonano il percorso per la conversione e perché, su canali, dispositivi e segmenti. | Analista, utente aziendale |
| [Analisi del pubblico e dei segmenti](/help/chat/use-cases/data-insights/audience-and-segment-analysis.md) | Scopri quali gruppi di clienti si comportano in modo diverso e come, in modo da poterti concentrare su quelli più importanti. | Analista, utente aziendale |
| [Prestazioni aziendali](/help/chat/use-cases/data-insights/business-performance.md) | Comprendere il comportamento dell’azienda, perché una metrica è stata spostata, dove si sta dirigendo e cosa fare dopo. | Analista, utente aziendale |
| [Prestazioni contenuto](/help/chat/use-cases/data-insights/content-performance.md) | Scopri quali contenuti vincono e perché, fino agli attributi di ciascuna risorsa, in modo da poter investire in ciò che funziona. | Utente aziendale |
| [Misurazione e attribuzione marketing](/help/chat/use-cases/data-insights/marketing-measurement-and-attribution.md) | Comprendi l’impatto incrementale di ogni canale e campagna di marketing in modo da allocare la spesa per ottimizzare il ROI. | Analista, utente aziendale |

## Abilità e limitazioni

Per l’analisi dei dati Customer Journey Analytics o Adobe Analytics sono disponibili le seguenti competenze.

| Competenza | Utilizzala per | Autorizzazioni richieste | Fuori ambito |
| --- | --- | --- | --- |
| `cja`, `aa` | Eseguire query sulle visualizzazioni dati di Customer Journey Analytics (`cja`) o sulle suite di rapporti di Adobe Analytics (`aa`) in tempo reale:<ul><li>Metriche pull, dimensioni, segmenti, visualizzazioni dati e suite di rapporti</li><li>Confrontare canali, periodi di tempo o segmenti uno accanto all’altro</li><li>Eseguire analisi di abbandono e funnel in più passaggi</li><li>Metriche di previsione basate sulle tendenze storiche</li></ul> | Accesso in visualizzazione alla visualizzazione dati o alla suite di rapporti in cui si desidera eseguire la query | <ul><li>Creazione o modifica di componenti di visualizzazioni dati o suite di rapporti</li><li>Dati esterni alle visualizzazioni dati o alle suite di rapporti a cui hai accesso</li><li>Modellazione predittiva oltre la previsione delle metriche</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Analizzare il motivo per cui una metrica è cambiata invece di segnalare semplicemente la modifica:<ul><li>Analizzare una modifica in una metrica nota in un periodo noto</li><li>Superare le quote e i segmenti che hanno contribuito al cambiamento</li></ul> | Accesso alla visualizzazione dati o alla suite di rapporti in fase di analisi | <ul><li>Rilevamento delle anomalie non richieste (nessun avviso automatico o in tempo reale)</li><li>Analisi della causa principale per le metriche esterne a una visualizzazione dati o a una suite di rapporti a cui hai accesso</li></ul> |
| `cja-executive-summary` | Creare riepiloghi dei dati pronti per le parti interessate:<ul><li>Riepiloga le prestazioni in un periodo specificato</li><li>Generare consigli prescrittivi in base ai dati</li><li>Contenuto struttura per una presentazione o una lettura da parte delle parti interessate</li></ul> | Accesso in visualizzazione alle visualizzazioni dati o alle suite di rapporti incluse nel riepilogo | <ul><li>Creazione della presentazione diapositive o del file di presentazione finale</li><li>Riepiloghi che si estendono su visualizzazioni dati o suite di rapporti a cui non hai accesso</li></ul> |
| `analyze-content`<!-- FLAG: Confirm the Out of scope items with the PM. --> | Rispondi a domande generali o specifiche sui contenuti utilizzando i dati di Content Analytics in Customer Journey Analytics:<ul><li>Scopri quali risorse ed esperienze hanno in comune le migliori prestazioni</li><li>Collegare l’esposizione dei contenuti a conversioni e ricavi</li><li>Confrontare i contenuti tra canali e pubblico</li></ul>Per ulteriori informazioni, vedere [Poni domande sul contenuto](/help/chat/use-cases/data-insights/ask-content-questions.md). | Accesso in visualizzazione a una visualizzazione dati configurata per Content Analytics | <ul><li>Configurazione di Content Analytics</li><li>Contenuto che Content Analytics non raccoglie</li></ul> |
| `aa-cja-validation` | Confrontare, controllare e riconciliare i dati tra [!DNL Adobe Analytics] e Customer Journey Analytics:<ul><li>Confrontare i valori delle metriche tra una suite di rapporti e una visualizzazione dati</li><li>Segnala le discrepanze tra le due origini dati</li></ul> | Accesso di visualizzazione alla suite di rapporti [!DNL Adobe Analytics] e alla visualizzazione dati Customer Journey Analytics confrontata | <ul><li>Risoluzione della causa sottostante di una discrepanza di dati</li><li>Convalida di origini dati diverse da [!DNL Adobe Analytics] e Customer Journey Analytics</li></ul> |
| `cja-skill-creator` | Trasforma un’analisi già eseguita in un’abilità riutilizzabile:<ul><li>Convertire un&#39;analisi completata in un&#39;abilità riutilizzabile denominata</li><li>Rendere disponibile un’abilità salvata nelle sessioni di chat future</li></ul> | Gestire le abilità | <ul><li>Condivisione automatica di un’abilità salvata con altri utenti (le librerie di abilità a livello di organizzazione richiedono l’impostazione dell’amministratore)</li><li>Modifica dei componenti della visualizzazione dati o della suite di rapporti a riferimenti di abilità</li></ul> |

## Best practice per l’analisi dei dati con Chat con collaboratori

### Best practice a livello di organizzazione

* Nominare un analista della tua organizzazione come campione di collaborazione.

* Crea una libreria di prompt esaminati e competenze correlate con i dati e i componenti disponibili per gli utenti.

* Crea una o più abilità per indirizzare Chat con i collaboratori affinché utilizzino solo i componenti che desideri siano utilizzati nelle analisi. Questo aiuta Chat collaboratore a fornire agli utenti della tua organizzazione i dati più rilevanti.

* Insegnare agli utenti quando chiedere a Chat con i collaboratori una risposta rapida rispetto a quando utilizzarla per un lavoro approfondito.

### Best practice a livello di utente

* Utilizza la modalità piano.

  Questa modalità è particolarmente utile per le attività complesse, ma può anche produrre risultati migliori per le attività semplici, perché consente a Collaboratore di porre domande di follow-up prima di agire. Per ulteriori informazioni, vedere [Modalità pianificazione](/help/chat/ui-guide.md#plan-mode).

* Quando crei un prompt, specifica il più possibile:

  * Denomina le dimensioni, le metriche e l’intervallo di date che desideri analizzare.
  * Fai riferimento ai componenti in base al loro nome esatto.
  * Specifica i segmenti, i tipi di pubblico, i canali o i dispositivi da includere, escludere o confrontare.
  * Specifica se desideri un tipo di visualizzazione specifico, ad esempio una tabella funnel, di tendenza o di coorte.
  * Chiedi i passaggi successivi consigliati se desideri che Chat con collaboratori suggerisca domande di follow-up.
  * Richiedi un orizzonte di previsione, ad esempio &quot;prossimi 30 giorni&quot; durante la proiezione delle metriche.
  * Fai riferimento a qualsiasi ipotesi già in tuo possesso, in modo che Chat con i collaboratori possa convalidarla o escluderla.
  * Se desideri una suddivisione di una modifica metrica, chiedi le dimensioni che contribuiscono.
  * Specifica il pubblico per un riepilogo, ad esempio la leadership o il team marketing, e se prevedi di presentare i risultati, richiedi una presentazione diapositive.
  * Denomina la suite di rapporti e la visualizzazione dati specifiche che desideri confrontare durante la convalida dei dati.
  * Completa prima un’analisi, quindi chiedi a Chat collaboratore di salvarla come abilità, assegnandogli un nome chiaro e descrittivo e annotando con quale frequenza intendi riutilizzarla.

* Aggiungere le indicazioni standard alla memoria Chat di Collaborator. Ad esempio, se utilizzi sempre dati provenienti dalle stesse visualizzazioni di dati o suite di rapporti, aggiungilo alla memoria. Per ulteriori informazioni, consulta [Aggiungere una visualizzazione dati o una preferenza per la suite di rapporti in memoria](/help/chat/use-cases/data-insights/analytics-chat.md#add-a-data-view-or-report-suite-preference-in-memory) in Introduzione all&#39;analisi dei dati con Chat con collaboratori.

## Passaggi successivi

* Per impostare la chat di Coworker e seguire un esempio di lavoro, vedere [Introduzione all&#39;analisi dei dati con la chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).
* Per visualizzare ogni flusso di lavoro di Chat con i collaboratori e le relative competenze, consulta [Flussi di lavoro di Chat con i collaboratori](/help/chat/use-cases/workflows.md).


