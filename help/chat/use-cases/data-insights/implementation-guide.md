---
title: Pianificare l’implementazione di Customer Journey Analytics o Streaming Media con Collaboratore
description: Scopri in che modo le competenze della guida all’implementazione di Coworker trasformano una conversazione di individuazione in un piano di implementazione personalizzato e ordinato con elenchi di controllo esportabili.
hold: true
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '1239'
ht-degree: 1%
---

# Pianificare l’implementazione con Collaboratore

Adobe CX Enterprise Coworker include cinque guide all’implementazione, una per ogni superficie di prodotto: Customer Journey Analytics, un aggiornamento da Adobe Analytics a Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) e Streaming Media. Ogni abilità trasforma una breve conversazione di individuazione in un piano di implementazione personalizzato e in base alle dipendenze, completo di una checklist interattiva e di esportazioni pronte all’uso, il tutto all’interno di una singola conversazione con Chat di Collaboratore.

Se stai preparando o eseguendo la migrazione a uno di questi prodotti, puoi usare queste abilità per ottenere un piano ordinato e dettagliato, senza dover esaminare manualmente i requisiti di implementazione di Adobe o creare un piano di progetto da zero.

>[!NOTE]
>
>Considera i seguenti aspetti:
>
>* Queste abilità della guida all&#39;implementazione fanno parte di un flusso di lavoro facoltativo più ampio: implementazione personalizzata o passaggi di aggiornamento (queste guide), implementazione (vedi [Generare un elenco di controllo per l&#39;implementazione con progetti Coworker](./intelligent-checklist.md)) e convalida (ad esempio, [Convalidare l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](./data-validation-aa-cja.md) o [Convalidare l&#39;implementazione di Streaming Media](./streaming-media-validation.md)). Non è necessario utilizzare tutte e tre le fasi. Ad esempio, puoi convalidare i dati senza mai generare un piano o un elenco di controllo.
>* Queste abilità non accedono ai sistemi Adobe né apportano modifiche. Consente di pianificare l’implementazione. Non lo eseguono né lo verificano rispetto a un tenant live.

Utilizza queste abilità per:

* Ottieni un piano personalizzato e ordinato per l’implementazione di Customer Journey Analytics da zero, inclusi proprietari, stime dello sforzo e dipendenze per ogni passaggio.

* Ottieni un piano di migrazione per l’aggiornamento da Adobe Analytics a Customer Journey Analytics, inclusi la mappatura della parità delle funzioni di Adobe Analytics, la sequenza di retrocompilazione cronologica e un gate di convalida prima di smantellare Adobe Analytics.

* Ottieni una pianificazione guidata per l’implementazione di Content Analytics (ACA), che include licenze, ambito di privacy e PII e la configurazione guidata.

* Ottieni un piano di onboarding per Marketing Campaign Analytics (MCA) che si adatta al percorso di acquisizione, sia che si utilizzino i connettori di origine di Adobe, che si utilizzi un set di dati personalizzato o un approccio ibrido.

* Ottieni un piano di implementazione per la raccolta di contenuti multimediali in streaming su Edge, che include la configurazione dello stream di dati, l’implementazione di SDK/API per piattaforma e il modello di evento multimediale.

## Prima di iniziare

<!-- FLAG: Best guess, not confirmed by source docs. Requirements doc doesn't state explicit prerequisites for starting a discovery conversation — verify with skills-overview.md or SME before publishing. -->

### Informazioni necessarie

Per avviare una conversazione sulla guida all’implementazione, è necessario:

* Quale dei cinque percorsi di implementazione si applica all’utente: Customer Journey Analytics (net-new), un aggiornamento da Adobe Analytics a Customer Journey Analytics, Content Analytics (ACA), Marketing Campaign Analytics (MCA) o Streaming Media.

* Dettagli di base sull’ambiente corrente, ad esempio se disponi di un’implementazione Adobe Analytics esistente, lo stato delle licenze o il percorso di acquisizione dati pianificato. La conversazione di individuazione richiede questi dettagli, ma la loro preparazione accelera il processo.

### Limitazioni

Prima di utilizzare queste abilità, tieni presenti le seguenti limitazioni:

* **Solo pianificazione**: queste abilità non accedono ai sistemi Adobe né apportano modifiche. Non eseguono l’implementazione né la verificano rispetto a un tenant live.
* **Una superficie di prodotto per abilità**: ogni abilità copre un singolo percorso di implementazione. Se la richiesta si applica a una superficie di prodotto diversa, l’abilità ti indirizza a quella corretta invece di rispondere direttamente.
* **Non è un&#39;esperienza di tracciamento dei progetti**: queste abilità generano un piano ed esportano, ma non tengono traccia dello stato in corso, della collaborazione o delle approvazioni da sole. Per tenere traccia del piano nel tempo, trasformalo in un progetto Collaboratore utilizzando un playbook predefinito. Consulta [Generare un elenco di controllo dell&#39;implementazione con Progetti coworking](./intelligent-checklist.md).

## Avviare una sessione di pianificazione dell’implementazione

1. Accedi a Collaboratore.

1. Seleziona [!UICONTROL **Nuova chat**].

1. Nel campo di testo, descrivi l’implementazione o la migrazione da pianificare. Ad esempio:

   **Chiedi conferma**

   > Aiutami a pianificare la mia implementazione di Customer Journey Analytics.

   La richiesta viene indirizzata all’abilità della guida all’implementazione corrispondente, che avvia una conversazione di individuazione interattiva.

1. (Condizionale) Se l’abilità non è in grado di determinare quale percorso di implementazione si applica all’utente, risponde alla domanda chiarificatrice che fa, quindi continua.

## Scegli il percorso di implementazione

Ogni abilità della guida all’implementazione copre una singola superficie di prodotto.

### Customer Journey Analytics

Ottieni un piano di implementazione personalizzato e ordinato per rendere Customer Journey Analytics operativo da zero, senza un’implementazione Adobe Analytics esistente per la migrazione. Il piano include proprietari, stime dell&#39;impegno e dipendenze per ogni passaggio.

Esempio di prompt:

* Aiutami a pianificare la mia implementazione di Customer Journey Analytics.
* Sto alzando la Customer Journey Analytics da zero. Generami un piano di implementazione.

### Aggiornamento da Adobe Analytics a Customer Journey Analytics

Ottieni un piano di migrazione che mappa la parità delle funzioni di Adobe Analytics su Customer Journey Analytics, sequenze di retrocompilazione cronologica e include una convalida e un gate a esecuzione parallela prima di smantellare Adobe Analytics.

Esempio di prompt:

* Aiutami a pianificare l’aggiornamento da Adobe Analytics a Customer Journey Analytics.
* Crea un piano di migrazione da Adobe Analytics a Customer Journey Analytics.

### Content Analytics (ACA)

Ottieni una pianificazione guidata per l’implementazione di Content Analytics (ACA), che include licenze, ambito di privacy e PII e la configurazione guidata. Poiché ACA non dispone di copertura DULE, CMK o HIPAA, il piano include i passaggi di controllo della privacy.

Esempio di prompt:

* Aiutami a pianificare la mia implementazione di Content Analytics.
* Generami un piano di implementazione di ACA.

### Marketing Campaign Analytics (MCA)

Ottieni un piano di onboarding per Marketing Campaign Analytics (MCA) Essentials che si adatta al percorso di acquisizione, sia che si utilizzino i connettori di origine di Adobe, un set di dati personalizzato o un approccio ibrido, in modo che i passaggi di mappatura e allineamento dei dati di funnel corrispondano all’ambiente.

Esempio di prompt:

* Aiutami a pianificare la mia implementazione di Marketing Campaign Analytics.
* Crea un piano di onboarding MCA utilizzando un set di dati personale.

### Contenuti multimediali in streaming

Ottieni un piano di implementazione per la raccolta di contenuti multimediali in streaming su Edge, che copre la configurazione dello stream di dati, l’implementazione di SDK/API per piattaforma e il modello di evento multimediale, in modo da instrumentare correttamente sessioni, ping e completamenti per il reporting di Customer Journey Analytics e/o Adobe Analytics.

Esempio di prompt:

* Aiutami a pianificare la mia implementazione di Streaming Media.
* Crea un piano per la strumentazione di Streaming Media su Edge.

## Esaminare i risultati

Collaboratore restituisce il piano di implementazione come un elenco di controllo interattivo e un riepilogo nella stessa conversazione.

**Elenco di controllo interattivo**

Elenco di controllo di HTML che raggruppa i passaggi di implementazione in fasi e milestone. Per ogni passaggio, l’elenco di controllo include:

* Stima dello sforzo
* Un proprietario principale ed eventuali proprietari di supporto
* Forti dipendenze da altri passaggi
* Indica se il passaggio può essere ignorato
* Un collegamento alla documentazione pertinente di Experience League o developer.adobe.com

**Esportazioni**

Scarica il piano nel formato adatto al tuo flusso di lavoro:

| Esporta | Cosa include |
| --- | --- |
| CSV | Un elenco semplice di passaggi |
| CSV Jira-import | Passaggi formattati con punti del brano, priorità ed etichette per l’importazione in Jira |
| CSV WORKFRONT | Passaggi formattati con durate e predecessori per l’importazione in Workfront |
| Markdown | Elenco di controllo da incollare nella documentazione o nei wiki |

**Riepilogo in-chat**

Insieme all’elenco di controllo, Collaboratore fornisce un riepilogo in tre parti direttamente nella conversazione:

1. Panoramica del piano
1. Tabella completa dei passaggi
1. Collegamenti di download per ogni esportazione

## Come viene creato il piano

Ogni abilità della guida all’implementazione segue lo stesso processo in quattro fasi:

* **Individuazione**: in una conversazione in staging vengono poste da 5 a 9 serie di domande, specifiche per il percorso di implementazione, per conoscere l&#39;ambiente e gli obiettivi.
* **Calcola**: un LLM determina quali passaggi condizionali e sostituzioni di dipendenza applicare alle risposte. Non scrive il piano in sé.
* **Assembla ed esegui rendering**: un processo deterministico risolve le dipendenze tra le fasi, le ordina, calcola il percorso critico (la catena più lunga di fasi dipendenti) e genera l&#39;elenco di controllo e le esportazioni.
* **Consegna**: in Collaborator sono disponibili collegamenti per il download e un riepilogo in-chat del piano.

Questa combinazione di scoperta guidata e assemblaggio deterministico significa che il piano viene generato in modo coerente dalle risposte, piuttosto che dalla mano libera scritta.
