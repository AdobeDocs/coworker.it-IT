---
title: Convalidare l’implementazione di Streaming Media con Collaboratore
description: Scopri in che modo l’abilità di Convalida di contenuti multimediali in streaming di Collaboratore controlla la configurazione, le sessioni e i registri per verificare che l’implementazione sia tracciata correttamente.
hold: true
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '1301'
ht-degree: 0%
---

# Convalidare l’implementazione di Streaming Media con Collaboratore

Collaboratore include un’abilità di convalida dei contenuti multimediali in streaming che controlla l’implementazione di Adobe Streaming Media (Video and Audio Analytics) su Edge Network, alimentando Customer Journey Analytics e/o Adobe Analytics. Invece di fare riferimento incrociato manualmente ad Assurance, alla configurazione dei set di dati, ai gruppi di campi dello schema XDM, alla configurazione della visualizzazione dati di Customer Journey Analytics e ai registri di rete non elaborati, puoi ottenere un singolo rapporto di convalida.

Se implementi o risolvi problemi di tracciamento dei contenuti multimediali in streaming, puoi utilizzare questa abilità per confermare che l’implementazione sia configurata correttamente, raccogliere i dati come previsto e acquisire ciò che intendevi tracciare, il tutto all’interno di una singola conversazione di Chat con collaboratori.

>[!NOTE]
>
>Considera i seguenti aspetti:
>
>* Questa abilità fa parte di un flusso di lavoro facoltativo più ampio: implementazione personalizzata o passaggi di aggiornamento (vedi [Pianificare l&#39;implementazione con Coworker](./implementation-guide.md)), implementazione (vedi [Generare una lista di controllo dell&#39;implementazione con progetti Coworker](./intelligent-checklist.md)) e convalida (questa abilità). Non è necessario utilizzare tutte e tre le fasi. Ad esempio, puoi convalidare l’implementazione di Streaming Media senza mai generare un piano o un elenco di controllo.
>* Questa abilità convalida e diagnostica i problemi. Non corregge la configurazione o i dati. Utilizza i risultati per guidare il tuo rimedio.

Utilizza questa abilità per:

* Esegui un controllo della configurazione nello stream di dati, nello schema XDM, nel set di dati e nella visualizzazione dati di Customer Journey Analytics, con il primo punto di controllo interrotto contrassegnato come causa probabile.

  Questa funzione è attualmente disponibile in modo limitato.

* Convalida un ID di sessione video specifico e verifica esattamente l’hop, l’acquisizione del set di dati o la mappatura Customer Journey Analytics in cui si è verificata una discrepanza.

* Convalida una sessione da un registro Charles o HAR caricato, o da un elenco URL più semplice, senza bisogno di una sessione live di Assurance.

  Questa funzione è attualmente disponibile in modo limitato.

* Ottieni un controllo di integrità complessivo con un singolo prompt, senza richiedere alcun ID sessione o registro, che raccoglie la configurazione e un esempio di sessioni recenti.

## Prima di iniziare

<!-- FLAG: General access prerequisite is inferred, not stated explicitly in source docs. Per-mode inputs (session ID, log file) are directly sourced from Functional Requirements. -->

### Informazioni necessarie

Per convalidare l’implementazione di Streaming Media, devi effettuare le seguenti operazioni:

* Accedi a Coworker con i dati Adobe Experience Platform e Customer Journey Analytics della tua organizzazione connessi.

* Per la convalida dell’ID sessione, specifica l’ID sessione video da controllare.

* Per una convalida basata su registro, un file di registro Charles o HAR o un elenco URL più semplice in formato .txt, .md o .json.

Non è richiesto alcun input specifico per un controllo della configurazione o per un controllo dello stato complessivo. Il collaboratore legge la configurazione esistente ed elenca automaticamente le sessioni recenti.

### Limitazioni

Prima di usare questa abilità, tieni presente quanto segue:

* **Solo diagnostica**: questa abilità non corregge la configurazione o i dati. Identifica i problemi, apporti la modifica.
* **Solo Streaming Media**: questa abilità riguarda le implementazioni di Streaming Media su Edge Network. I set di dati non multimediali e le implementazioni standard di Analytics per web o app sono coperti da altre competenze di convalida di Collaboratore.
* **Solo su richiesta**: questa abilità non fornisce un monitoraggio continuo o in tempo reale. Eseguilo quando vuoi un controllo, anziché come avviso continuo.
* **Nessun crawler predefinito**: questa abilità non scansiona il sito o l&#39;app per te. Se desideri convalidare la copertura scansionata, fornisci come prova un output crawler o headless tramite browser.
* **Solo implementazioni di Edge Network**: i percorsi di implementazione legacy di Media SDK e solo Analytics non sono supportati.
* **Funzionalità più ampie non sono ancora incluse**: la convalida del flusso di eventi live e heartbeat, la convalida del playbook del cliente o dello scenario, l&#39;aggregazione cronologica di più piattaforme e la convalida dell&#39;attivazione a valle di Real-Time CDP o Adobe Journey Optimizer sono pianificate per le versioni successive.

## Avviare una sessione di convalida

1. Accedi a Collaboratore.

1. Seleziona [!UICONTROL **Nuova chat**].

1. Nel campo di testo, descrivi ciò che desideri convalidare. Ad esempio:

   **Chiedi conferma**

   > Convalida #123. ID sessione video

   La richiesta viene indirizzata all’abilità Convalida contenuti multimediali in streaming, che esegue la modalità di convalida corrispondente.

1. (Condizionale) Se l’abilità richiede ulteriori informazioni, ad esempio un ID sessione o un file di registro, forniscila quando richiesto.

## Scegli la modalità di convalida

L’abilità Convalida contenuti multimediali in streaming include quattro modalità.

### Audit della configurazione

Questa funzione è attualmente disponibile in modo limitato.

Convalida l’intero flusso di Adobe Experience Platform da Datastream alla visualizzazione dati di Customer Journey Analytics, inclusi lo schema XDM, il set di dati e tutte le regole di preparazione dati o i campi derivati di Customer Journey Analytics. Il collaboratore segnala una scorecard di esito positivo/negativo per hop e contrassegna il primo punto di controllo interrotto come causa probabile.

Esempio di prompt:

* Convalida la configurazione dei contenuti multimediali in streaming per visualizzazione dati, set di dati e flusso di dati.
* Controlla la fine della configurazione del file multimediale in streaming.
* Il mio flusso di dati di analisi dei contenuti multimediali è configurato correttamente per Customer Journey Analytics?

### Convalida dell’ID sessione

Esegui il controllo incrociato delle righe del set di dati di Adobe Experience Platform con la visualizzazione dati di Customer Journey Analytics per una sessione video specifica e specifica se un gap è un problema di acquisizione del set di dati o un problema di mappatura Customer Journey Analytics.

Esempio di prompt:

* Convalida #123. ID sessione video
* Perché la sessione abc-123 non viene visualizzata in Customer Journey Analytics?
* Confronta la sessione xyz tra il set di dati e la visualizzazione dati di Customer Journey Analytics.

### Convalida basata su registro

Questa funzione è attualmente disponibile in modo limitato.

Convalida una sessione da un registro Charles o HAR che carichi, o da un elenco URL più semplice, senza necessità di una sessione live di Assurance. Il collaboratore convalida i pattern degli endpoint, i codici di risposta, la sequenza degli eventi e la frequenza di ping e indica quali controlli sono stati eseguiti con la massima affidabilità, con un’affidabilità ridotta o sono stati saltati.

Esempio di prompt:

* Convalida i registri allegati dei dati multimediali in streaming.
* Controlla questo registro Charles per #456. ID sessione
* Convalida questo elenco di URL in base ai ping previsti per i file multimediali.

### Dashboard di convalida

Ottieni un controllo di integrità complessivo con un singolo prompt. Collaboratore esegue il rollup del controllo della configurazione e di un controllo della sessione campionato leggero in un unico stato e dichiara esplicitamente che i controlli basati su registro non venivano eseguiti se non veniva fornito alcun registro.

Esempio di prompt:

* Verifica i dati multimediali in streaming.
* Dammi un rapporto sulla mia implementazione di Streaming Media.
* In generale, quanto è valida l’implementazione di contenuti multimediali in streaming?

## Esaminare i risultati

Ogni modalità restituisce i risultati in un formato adatto alla convalida.

**Risultati controllo configurazione**

Una scorecard pass/fail per hop che copre lo stream di dati, lo schema XDM, il set di dati, la visualizzazione dati di Customer Journey Analytics e le regole dei campi derivato o di preparazione dati. Coworker identifica il primo hop non riuscito come causa principale probabile.

**Risultati convalida ID sessione**

Riepilogo dei rapporti solo per Customer Journey Analytics, inclusi ID sessione, metadati di contenuto, conteggi di righe per tipo di evento, valori delle metriche chiave e una nota sull’integrità. Se esiste un gap, Collaboratore identifica se si è verificato al momento dell’acquisizione del set di dati o al passaggio di mappatura di Customer Journey Analytics.

>[!NOTE]
>
>Per impostazione predefinita, gli ID sessione e i valori di identità autenticata sono esclusi da qualsiasi riepilogo esportato o condiviso.

**Risultati della convalida basata su log**

Una convalida strutturale e in sequenza del registro caricato, che include pattern di endpoint, codici di risposta, ordine degli eventi e cadenza di ping. Il collaboratore indica quali controlli sono stati eseguiti con attendibilità totale, quali con attendibilità ridotta e quali sono stati ignorati, a seconda che sia stata fornita un’acquisizione completa del registro o un elenco URL più semplice.

**Risultati dashboard**

Un singolo stato consolidato denominato &quot;Configurazione + Dati Disponibili&quot;, che combina i risultati del controllo della configurazione con un controllo campionato delle sessioni recenti. Il collaboratore assegna un nome alle sessioni campionate e dichiara esplicitamente che i controlli basati sul registro non sono stati eseguiti perché non è stato fornito alcun registro.

## Funzionamento della convalida

Ogni modalità è mappata su un motore dedicato:

* **Motore di convalida della configurazione**: legge lo stream di dati, lo schema XDM, il set di dati e la configurazione della visualizzazione dati di Customer Journey Analytics e la valuta in base a un set fisso di punti di controllo.
* **Motore di controllo incrociato sessione**: dato un ID sessione, esegue una query sul set di dati e sulla visualizzazione dati di Customer Journey Analytics, calcola il numero di righe e il tipo previsti per la sessione e confronta i risultati effettivi a ogni hop.
* **Parser e convalida del registro**: analizza il registro o l&#39;elenco URL caricato, ricostruisce la sequenza e la tempistica delle richieste e applica controlli strutturali, di sequenziamento e a livello di rete.
* **Motore di aggregazione dashboard**: esegue il motore di convalida della configurazione e un&#39;esecuzione campionata del motore di controllo incrociato della sessione e li combina in un unico stato quando non è stato fornito un ID sessione, un registro o un playbook.
