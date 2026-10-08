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
source-wordcount: '1944'
ht-degree: 1%
---

# Analizzare i dati con Chat con i collaboratori

Le informazioni contenute in questa pagina forniscono una panoramica di Adobe CX Enterprise Coworker Chat e di come possono aiutarti ad analizzare i dati per la tua organizzazione.

Chat con i collaboratori consente ai team di automatizzare le attività dei prodotti Adobe utilizzando il linguaggio naturale, trasformando rapidamente le idee in azioni con una pianificazione flessibile, competenze personalizzabili ed esecuzione intelligente. Per ulteriori informazioni generali su Coworker, vedere [Panoramica di CX Enterprise Coworker](/help/home.md).

>[!VIDEO](https://video.tv.adobe.com/v/3503519/?learn=on&enablevpops)

## Come funziona l’analisi dei dati

Chat con i collaboratori può eseguire analisi avanzate dei dati che in precedenza erano possibili solo in Analysis Workspace. Chat con collaboratori accede ai dati dalle visualizzazioni dati di Customer Journey Analytics o dalle suite di rapporti di Adobe Analytics, consentendoti di esplorare i dati e ottenere risposte con prompt in linguaggio naturale.

La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics. Puoi accedere solo alle visualizzazioni dati, alle suite di rapporti, alle dimensioni, alle metriche e ai segmenti disponibili in Analysis Workspace.

Quando crei una visualizzazione nella chat di Coworker, puoi aprirla in Analysis Workspace in qualsiasi momento per un controllo più manuale.

## Risposte rapide e un lavoro approfondito

Puoi utilizzare Chat con i collaboratori in due modi, a seconda della quantità di analisi necessaria:

* **Risposte rapide** - Fai una domanda diretta in un linguaggio semplice e ottieni una risposta immediata. Gli utenti aziendali utilizzano spesso la chat con collaboratori in questo modo, e gli analisti la utilizzano anche quando hanno bisogno di una risposta rapida per una parte interessata.
* **Lavoro approfondito** - Parla a più riprese con Coworker Chat per indagare su un problema di business, escludere le cause e arrivare a un consiglio. In genere, gli analisti utilizzano questo approccio per esplorare i dati in modo approfondito prima di creare un consiglio.

## Inizia l’analisi in Chat con i collaboratori

Per iniziare, descrivi ciò che desideri sapere in un linguaggio semplice. Chat con collaboratori pianifica l’analisi, esegue query sulle visualizzazioni dati o sulle suite di rapporti e crea visualizzazioni e riepiloghi.

I seguenti casi d’uso sono raggruppati per ciò che desideri eseguire. Ogni gruppo elenca i ruoli più adatti.

### Misurare le prestazioni

**Ideale per:** analista, utente aziendale

| Caso d’uso | Funzione |
| --- | --- |
| [Analizzare i dati di Customer Journey Analytics e Adobe Analytics](/help/chat/use-cases/data-insights/analytics-chat.md)<p>![Analizzare i dati di Customer Journey Analytics e Adobe Analytics](../../assets/coworker-funnel-response-card.png)</p> | Risponde alle domande in linguaggio naturale sulle visualizzazioni di dati o sulle suite di rapporti, crea funnel e altre visualizzazioni e trova dove i clienti abbandonano. Puoi aprire qualsiasi visualizzazione in Analysis Workspace per ulteriori analisi.<p>**Prompt di esempio:** &quot;Mostra visualizzazioni di pagina per gli ultimi 30 giorni&quot;</p><p>Per ulteriori informazioni, vedere [Introduzione all&#39;analisi dei dati con Chat di Collaboratore](/help/chat/use-cases/data-insights/analytics-chat.md).</p> |
| [Confronta prestazioni](#skills-and-limitations) | Confronta le metriche per canali, periodi di tempo o segmenti affiancati.<p>**Prompt di esempio:** &quot;Confronta i ricavi per canale, mese e mese&quot;</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](#skills-and-limitations).</p> |
| [Misura le prestazioni della campagna](/help/chat/use-cases/overview.md#data-insights) | Scopri le prestazioni di campagne, canali e proprietà web in un dato periodo.<p>**Prompt di esempio:** &quot;Quali sono state le prestazioni delle campagne Web di Acrobat il mese scorso?&quot;</p><p>Per ulteriori informazioni, consulta [Informazioni sui dati](/help/chat/use-cases/overview.md#data-insights) nei casi di utilizzo di Chat con coorker.</p> |
| [Analisi funnel](#skills-and-limitations) | Segui i funnel di conversione in più passaggi e osserva il menu a discesa in ogni fase.<p>**Ideale per:** analista</p><p>**Prompt di esempio:** &quot;Passami attraverso il funnel di estrazione&quot;</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](#skills-and-limitations).</p> |

### Scopri perché le metriche sono cambiate

**Ideale per:** analista

| Caso d’uso | Funzione |
| --- | --- |
| [Esplora tendenze e cause principali](/help/chat/use-cases/data-insights/root-cause-analysis.md)<p>![Esplora tendenze e cause principali](../../assets/data-validation-aa-cja/trend-line-card.png)</p> | Identifica le tendenze nei dati di Customer Journey Analytics e Adobe Analytics e i fattori che determinano cambiamenti nelle prestazioni, senza query manuali.<p>**Prompt di esempio:** &quot;Perché le conversioni sono diminuite la settimana scorsa?&quot;</p><p>Per ulteriori informazioni, vedere [Customer Journey Analytics &amp; Coworker](/help/chat/use-cases/data-insights/root-cause-analysis.md).</p> |
| [Analizzare le tendenze e le cause operative](/help/chat/use-cases/overview.md#data-insights) | Esegui query sui dati storici delle serie temporali per tipi di pubblico, set di dati e percorsi e identifica la causa di un cambiamento.<p>**Ideale per:** Amministratore, Analista</p><p>**Prompt di esempio:** &quot;Mostra le tendenze delle dimensioni del pubblico negli ultimi 90 giorni&quot;</p><p>Per ulteriori informazioni, consulta [Informazioni sui dati](/help/chat/use-cases/overview.md#data-insights) nei casi di utilizzo di Chat con coorker.</p> |

### Previsione delle prestazioni future

**Ideale per:** analista

| Caso d’uso | Funzione |
| --- | --- |
| [Metriche di previsione](#skills-and-limitations) | Progetta i valori delle metriche future da dati storici Customer Journey Analytics o Adobe Analytics, ad esempio se sei sulla buona strada per raggiungere un obiettivo di ricavi.<p>**Prompt di esempio:** &quot;Sessioni di previsione per i prossimi 30 giorni&quot;</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](#skills-and-limitations).</p> |

### Condividere informazioni con le parti interessate

**Ideale per:** analista, utente aziendale

| Caso d’uso | Funzione |
| --- | --- |
| [Creare riepiloghi esecutivi e digest KPI](#skills-and-limitations) | Creare riepiloghi sulle prestazioni pronti per le parti interessate, consigli e descrizioni della presentazione.<p>**Prompt di esempio:** &quot;Dammi un riepilogo esecutivo del mese scorso&quot;</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](#skills-and-limitations).</p> |

### Pianificare l’implementazione o l’aggiornamento

**Ideale per:** Amministratore

| Caso d’uso | Funzione |
| --- | --- |
| [Pianifica l&#39;implementazione](/help/chat/use-cases/data-insights/implementation-guide.md)<p>![Pianifica l&#39;implementazione](../../assets/ui-guide-6.png)</p> | Crea un piano personalizzato e dettagliato per l’implementazione di Customer Journey Analytics, l’aggiornamento da Adobe Analytics o la configurazione di Content Analytics, Marketing Campaign Analytics o Streaming Media Collection su Edge. I piani includono dettagli quali proprietari, stime dello sforzo, dipendenze e passaggi di convalida.<p>**Prompt di esempio:** &quot;Aiutami a pianificare la mia implementazione di Customer Journey Analytics&quot;</p><p>Per ulteriori informazioni, consulta [Pianificare l&#39;implementazione con Coworker](/help/chat/use-cases/data-insights/implementation-guide.md).</p> |
| [Generare un elenco di controllo dell&#39;implementazione](/help/chat/use-cases/data-insights/intelligent-checklist.md)<p>![Generare un elenco di controllo dell&#39;implementazione](../../assets/data-validation-aa-cja/date-detail.png)</p> | Trasforma il piano di implementazione di Customer Journey Analytics in un elenco di controllo in Progetti coworking, in cui il team può assegnare passaggi, tenere traccia dello stato e aggiungere gate di approvazione.<p>Per ulteriori informazioni, vedere [Generare un elenco di controllo dell&#39;implementazione con Progetti coworking](/help/chat/use-cases/data-insights/intelligent-checklist.md).</p> |

### Conferma l’accuratezza dei dati

**Ideale per:** Amministratore

| Caso d’uso | Funzione |
| --- | --- |
| [Convalida dati durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md)<p>![Convalida dati durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](../../assets/data-validation-aa-cja/trend-bar-card.png)</p> | Confronta dimensioni, metriche e tendenze tra le suite di rapporti di Adobe Analytics e le visualizzazioni dati di Customer Journey Analytics, quindi consiglia di apportare correzioni per supportare l’aggiornamento.<p>**Ideale per:** Amministratore, Analista</p><p>**Prompt di esempio:** &quot;Confronta la suite di rapporti AA con la visualizzazione dati di CJA&quot;</p><p>Per ulteriori informazioni, vedere [Convalidare i dati con Coworker durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).</p> |
| [Convalida l&#39;implementazione di Streaming Media](/help/chat/use-cases/data-insights/streaming-media-validation.md)<p>![Convalida l&#39;implementazione di Streaming Media](../../assets/ui-guide-8.png)</p> | Controlla lo stream di dati, lo schema, il set di dati, la visualizzazione dati e i dati della sessione per verificare che il tracciamento dei contenuti multimediali in streaming sia configurato e che la raccolta dei dati sia corretta.<p>**Prompt di esempio:** &quot;L&#39;implementazione dei contenuti multimediali in streaming è complessivamente valida?&quot;</p><p>Per ulteriori informazioni, consulta [Convalidare l&#39;implementazione di Streaming Media con Coworker](/help/chat/use-cases/data-insights/streaming-media-validation.md).</p> |
| [Convalida qualità set di dati per Customer Journey Analytics](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md)<p>![Convalida qualità set di dati per Customer Journey Analytics](../../assets/data-validation-aep/dataset-validation.png)</p> | Identifica i set di dati che alimentano i rapporti di Customer Journey Analytics, quindi controlla gli schemi, la qualità dell’identità e la qualità dei campi in modo da poter risolvere i problemi prima di creare dashboard.<p>Per ulteriori informazioni, vedere [Convalidare i dati di Customer Journey Analytics con l&#39;abilità di convalida dei dati in Coworker](/help/chat/use-cases/data-insights/validate-dataset-quality-for-cja.md).</p> |
| [Convalida dati dopo l&#39;acquisizione in Experience Platform](/help/chat/use-cases/data-insights/data-validation-aep.md)<p>![Convalida dati dopo l&#39;acquisizione in Experience Platform](../../assets/data-validation-aep/null-values.png)</p> | Esegue controlli statistici e semantici sui set di dati e sui campi di Experience Platform per individuare problemi di qualità dei dati, ad esempio valori non validi o problemi di mappatura.<p>**Prompt di esempio:** &quot;Convalida il set di dati Elettronica campione 1000&quot;</p><p>Per ulteriori informazioni, consulta [Convalidare i dati di Experience Platform con Coworker](/help/chat/use-cases/data-insights/data-validation-aep.md).</p> |

### Automatizzare le analisi ripetute

**Ideale per:** analista

| Caso d’uso | Funzione |
| --- | --- |
| [Creare abilità Customer Journey Analytics personalizzate](#skills-and-limitations) | Trasforma un’analisi ripetuta in un’abilità riutilizzabile che persiste nelle sessioni.<p>**Prompt di esempio:** &quot;Trasforma questa analisi settimanale dei ricavi in un&#39;abilità riutilizzabile&quot;</p><p>Per ulteriori informazioni, consulta [Abilità e limitazioni](#skills-and-limitations).</p> |

Per ulteriori informazioni su questi casi d&#39;uso, incluse le abilità utilizzate e ulteriori richieste di esempio, vedi [Casi d&#39;uso approfondimenti dati](/help/chat/use-cases/overview.md#data-insights).

## Abilità e limitazioni

Per l’analisi dei dati Customer Journey Analytics o Adobe Analytics sono disponibili le seguenti competenze.

| Competenza | Utilizzala per | Autorizzazioni richieste | Fuori ambito |
| --- | --- | --- | --- |
| `cja`, `aa` | Eseguire query sulle visualizzazioni dati di Customer Journey Analytics (`cja`) o sulle suite di rapporti di Adobe Analytics (`aa`) in tempo reale:<ul><li>Metriche pull, dimensioni, segmenti, visualizzazioni dati e suite di rapporti</li><li>Confrontare canali, periodi di tempo o segmenti uno accanto all’altro</li><li>Eseguire analisi di abbandono e funnel in più passaggi</li><li>Metriche di previsione basate sulle tendenze storiche</li></ul> | Accesso in visualizzazione alla visualizzazione dati o alla suite di rapporti in cui si desidera eseguire la query | <ul><li>Creazione o modifica di componenti di visualizzazioni dati o suite di rapporti</li><li>Dati esterni alle visualizzazioni dati o alle suite di rapporti a cui hai accesso</li><li>Modellazione predittiva oltre la previsione delle metriche</li></ul> |
| `cja-root-cause-analysis`, `aa-root-cause-analysis` | Analizzare il motivo per cui una metrica è cambiata invece di segnalare semplicemente la modifica:<ul><li>Analizzare una modifica in una metrica nota in un periodo noto</li><li>Superare le quote e i segmenti che hanno contribuito al cambiamento</li></ul> | Accesso alla visualizzazione dati o alla suite di rapporti in fase di analisi | <ul><li>Rilevamento delle anomalie non richieste (nessun avviso automatico o in tempo reale)</li><li>Analisi della causa principale per le metriche esterne a una visualizzazione dati o a una suite di rapporti a cui hai accesso</li></ul> |
| `cja-executive-summary` | Creare riepiloghi dei dati pronti per le parti interessate:<ul><li>Riepiloga le prestazioni in un periodo specificato</li><li>Generare consigli prescrittivi in base ai dati</li><li>Contenuto struttura per una presentazione o una lettura da parte delle parti interessate</li></ul> | Accesso in visualizzazione alle visualizzazioni dati o alle suite di rapporti incluse nel riepilogo | <ul><li>Creazione della presentazione diapositive o del file di presentazione finale</li><li>Riepiloghi che si estendono su visualizzazioni dati o suite di rapporti a cui non hai accesso</li></ul> |
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

Per impostare la chat di Coworker e seguire un esempio di lavoro, vedere [Introduzione all&#39;analisi dei dati con la chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).


