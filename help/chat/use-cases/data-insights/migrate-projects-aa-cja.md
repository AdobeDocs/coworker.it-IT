---
title: Migrazione di progetti Adobe Analytics a Customer Journey Analytics
description: Utilizza Coworker per convalidare, mappare e migrare i progetti Adobe Analytics Workspace e i relativi componenti in Customer Journey Analytics, quindi controlla lo stato di migrazione.
feature: AI Tools
role: Admin
level: Intermediate
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: Coworker
source-git-commit: 1ec3a8bf6dff44df068529cf1f7ceb699a027d65
workflow-type: tm+mt
source-wordcount: '1785'
ht-degree: 1%
---

# Migrazione di progetti Adobe Analytics a Customer Journey Analytics con Collaboratore

<!-- FLAG: Confidence: High for the conversation flow, which is sourced from screenshots of the Coworker UI (October 2026) and the aa-mcp tool descriptions. The component migration tools run through the aa-mcp integration; there's no dedicated skill yet. Medium for statements that Coworker shares mappings and migration rules with migrations in the Adobe Analytics user interface; the user believes this is likely. Confirm with engineering. -->

Utilizza Adobe CX Enterprise Coworker per migrare i progetti Adobe Analytics e i relativi componenti a Customer Journey Analytics in un’unica conversazione.

Collaboratore verifica che le dimensioni e le metriche del progetto siano mappate alla visualizzazione dati di Customer Journey Analytics, consente di mappare eventuali altre, quindi ricrea il progetto in Customer Journey Analytics.

<!-- FLAG: Add the planned general availability date when it's confirmed. -->

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo è nella fase di test limitato del rilascio e potrebbe non essere ancora disponibile nell’ambiente. Questa nota verrà rimossa quando la funzionalità sarà generalmente disponibile.

>[!IMPORTANT]
>
>Prima di eseguire la migrazione di qualsiasi progetto, leggere [Preparare la migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration) nella documentazione di Adobe Analytics. Spiega come prepararsi per una migrazione, cosa è incluso, quali elementi causano errori e come le mappature influiscono sull’intera organizzazione. Queste informazioni si applicano alle migrazioni in Collaborator.

## Differenze rispetto alla migrazione nell’interfaccia utente di Adobe Analytics

<!-- FLAG: Add rows as differences are confirmed. Who can migrate and How you migrate: SME Scott Tomko (October 2026); Coworker matches the Analytics 2.0 Component Migration APIs, and functionally both methods do much the same thing. Project owner: Coworker behavior is from a test conversation (October 2026); the Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. Mapping dimensions and metrics: Confidence Medium for the Coworker column, which is based on the aa-mcp tool descriptions and a test conversation, not on an observed failed validation. Confirm that Coworker suggests and updates mappings, and whether it asks for confirmation before it updates a mapping. The Adobe Analytics user interface behavior is from component-migration.md in the Adobe Analytics docs. -->

La migrazione di progetti con Collaborator differisce dalla migrazione nell’interfaccia utente di Adobe Analytics nei seguenti modi:

| | Collaboratore | Interfaccia utente di Adobe Analytics |
| --- | --- | --- |
| **Chi può migrare i progetti** | Amministratori Adobe Analytics e utenti con l&#39;autorizzazione [!UICONTROL **Migrazione componenti**] | Solo amministratori di Adobe Analytics |
| **Proprietario progetto** | Utente che esegue la migrazione | Utente specificato nel campo [!UICONTROL **Proprietario progetto**] |
| **Mappatura di dimensioni e metriche** | Collaboratore convalida il progetto ed elenca come vengono mappate ciascuna dimensione e metrica. Per ogni elemento che non può essere mappato automaticamente, Collaboratore suggerisce una dimensione o una metrica nella visualizzazione dati e aggiorna la mappatura. | Nella sezione [!UICONTROL **Mappa schema**], seleziona ogni dimensione o metrica con uno stato [!UICONTROL **Non mappato**] e mappala manualmente. |
| **Migrazione in corso** | Descrivi ciò che desideri in un prompt. Il collega fa il lavoro, facendo qualche domanda lungo la strada. Ad esempio, puoi creare un progetto con i componenti a cui hai dato il nome, quindi eseguirne la migrazione. Vedi [Inizia da componenti specifici](#start-from-specific-components). | Crea un progetto in Analysis Workspace, aggiungi i componenti di cui vuoi eseguire la migrazione e salva il progetto. Quindi, in [!UICONTROL **Migrazione componenti**], seleziona il progetto, specifica un proprietario del progetto, mappa lo schema per ogni suite di rapporti e seleziona [!UICONTROL **Migra**]. |

## Prerequisiti

<!-- FLAG: Confidence: High for the Adobe Analytics MCP and permission bullets, which come from the release announcement and SME Scott Tomko (October 2026): like the Analytics 2.0 Component Migration APIs, Coworker lets non-admins with the Component Migration permission migrate projects, while the Adobe Analytics UI is admin-only. Open question: Coworker makes the user who runs the migration the owner of the new project, but the aa-mcp tool description says the owner "should be an admin" and the Adobe Analytics component migration docs say the owner must be a Customer Journey Analytics administrator. Confirm whether a non-admin who runs a migration needs Customer Journey Analytics admin rights, or whether Coworker assigns a different owner. -->

Per migrare i progetti con Collaboratore, è necessario:

* Accesso ad Adobe Analytics MCP. Gli strumenti di migrazione dei componenti vengono abilitati automaticamente per i clienti con accesso MCP di Adobe Analytics. Per verificare che [!UICONTROL **aa-mcp**] sia connesso, vedere [Introduzione all&#39;analisi dei dati con Chat di Coworker](/help/chat/use-cases/data-insights/analytics-chat.md).

* Diritti di amministratore di Adobe Analytics o l&#39;autorizzazione [!UICONTROL **Migrazione componenti**] in Admin Console. Non è necessario essere un amministratore.

* [prerequisiti](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#prerequisites) per la migrazione dei componenti nella documentazione di Adobe Analytics.

* Progetto che utilizza suite di rapporti di base. Impossibile migrare le suite di rapporti virtuali.<!-- FLAG: Sourced from Coworker's response in the UI. The Adobe Analytics component migration docs don't mention virtual report suites. Confirm, and consider adding it to those docs. -->

## Rivedi le mappature delle suite di rapporti prima della migrazione

<!-- FLAG: Confidence: Medium. The recommendation to review mappings before the first migration from a report suite is inferred from the Adobe Analytics guidance to decide mappings as an organization; Coworker also validates mappings during each migration. Confirm with Scott. -->

È consigliabile rivedere il modo in cui le dimensioni e le metriche di una suite di rapporti vengono mappate prima della prima migrazione da tale suite di rapporti. Le mappature si applicano a ogni progetto migrato dalla tua organizzazione, pertanto la loro impostazione consente di superare la convalida nei progetti successivi. Per informazioni sulla scelta dei mapping, vedere [Decidere come organizzazione la mappatura dei componenti](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#decide-as-an-organization-how-you-will-map-components) nella documentazione di Adobe Analytics.

Per rivedere i mapping, seleziona [!UICONTROL **Rivedi solo i mapping**] nella scheda [!UICONTROL **Ambito**] oppure chiedi direttamente al collaboratore:

**Richieste**

* &quot;Mostra come le dimensioni e le metriche nella suite di rapporti sono mappate alla visualizzazione dati&quot;
* &quot;Quali dimensioni e metriche nella suite di rapporti non sono mappate alla visualizzazione dati?&quot;

Puoi anche chiedere a Collaboratore di aggiornare le mappature.

Se salti questa revisione, Collaboratore [controlla comunque i mapping per ogni progetto di cui esegui la migrazione](#review-the-validation-results-and-mappings).

## Avviare una migrazione

<!-- FLAG: Confidence: High that migration works at the project level and that components migrate with their project (component-migration.md in the Adobe Analytics docs), and that components that already exist in Customer Journey Analytics aren't re-created (prepare-component-migration.md). Medium-low for when to use each method and for combining them; this guidance is inferred and isn't in the Adobe Analytics docs. Confirm with Scott. Also confirm whether Coworker creates a project automatically when you ask it to migrate only components (for example, "Migrate my Spring sale segments to CJA"), or whether you must ask it to create the project. -->

Cooker esegue sempre la migrazione di un progetto e dei relativi componenti associati. Per migrare componenti specifici, chiedi a Collaboratore di aggiungerli a un nuovo progetto, quindi esegui la migrazione del progetto.

I componenti già esistenti in Customer Journey Analytics non vengono ricreati, pertanto puoi utilizzare entrambi i metodi. Ad esempio, esegui prima la migrazione dei progetti più importanti, quindi esegui la migrazione di tutti i componenti rimanenti. Scegli da dove iniziare in base a ciò che desideri in Customer Journey Analytics:

* **Esegui la migrazione di un progetto** se desideri mantenere i pannelli e le visualizzazioni del progetto in Customer Journey Analytics. Vedi [Inizia da un progetto](#start-from-a-project).
* **Esegui la migrazione di componenti specifici** quando desideri componenti quali segmenti, metriche calcolate o intervalli di date in Customer Journey Analytics, ma non è necessario nessuno dei progetti che li utilizzano. Ad esempio, puoi pianificare la creazione di nuovi progetti in Customer Journey Analytics che li includono. Vedi [Inizia da componenti specifici](#start-from-specific-components).

### Iniziare da un progetto

Per eseguire la migrazione di un progetto e dei relativi componenti:

1. Accedi a Collaboratore.

1. Seleziona **[!UICONTROL Nuova chat]**.

1. Nel campo di testo, richiedi a Collaboratore di eseguire la migrazione del progetto. Ad esempio:

   **Chiedi conferma**

   > Desidero migrare i componenti da Adobe Analytics a Customer Journey Analytics.

   Collaboratore descrive cosa può migrare e avvia un questionario.

1. Nella scheda [!UICONTROL **Ambito**], seleziona una delle opzioni seguenti, quindi [!UICONTROL **Successivo**]:

   <!-- FLAG: Confidence: Medium for the "Plan a full upgrade" description. It likely hands off to the implementation guide skill and leaves the migration flow. Confirm with engineering. Also confirm what the Source & target tab asks; it was skipped in the screenshots. The Next and Submit buttons on the first questionnaire's Source & target and Review tabs are assumed to work like the second questionnaire. -->

   | Opzione | Descrizione |
   | --- | --- |
   | [!UICONTROL **Progetto AA specifico**] | Esegui la migrazione di un progetto a cui hai dato un nome. Segui i passaggi rimanenti in questa sezione. |
   | [!UICONTROL **Rivedi solo mappature**] | Verifica il modo in cui le metriche e le dimensioni di una suite di rapporti si associano a una visualizzazione dati, senza eseguire alcuna migrazione. Consulta [Rivedi i mapping delle suite di rapporti prima della migrazione](#review-report-suite-mappings-before-you-migrate). |
   | [!UICONTROL **Pianifica un aggiornamento completo**] | Ottieni un piano completo per passare da Adobe Analytics a Customer Journey Analytics. Vedi [Pianifica la tua implementazione con Coworker](/help/chat/use-cases/data-insights/implementation-guide.md). |

1. (Facoltativo) Rispondi alle domande nella scheda [!UICONTROL **Source &amp; target**], quindi seleziona [!UICONTROL **Next**].

1. Nella scheda [!UICONTROL **Rivedi**], conferma le risposte, quindi seleziona [!UICONTROL **Invia**].

   Collaboratore controlla le aziende Adobe Analytics a cui hai accesso e quante suite di rapporti di base hanno ciascuna, quindi avvia un secondo questionario.

1. Rispondi alle seguenti domande, selezionando [!UICONTROL **Successivo**] dopo ciascuna:

   | Scheda | Domanda | Contesto aggiuntivo |
   | --- | --- | --- |
   | [!UICONTROL **Progetto**] | Qual è il nome del progetto AA di cui vuoi eseguire la migrazione? | Un nome parziale va bene. |
   | [!UICONTROL **Suite di rapporti**] | Quale suite di rapporti utilizza il progetto? | Seleziona una suite di rapporti dall’elenco o digita il nome di un’altra suite. |
   | [!UICONTROL **Visualizzazione dati**] | In quale visualizzazione dati di CJA eseguire la migrazione? | (Facoltativo) Digita il nome di una visualizzazione dati o lasciala vuota e Collaboratore consiglia di usare visualizzazioni dati corrispondenti. |

1. Nella scheda [!UICONTROL **Rivedi**], conferma le risposte, quindi seleziona [!UICONTROL **Invia**].

   Per saltare il questionario in qualsiasi momento, selezionare [!UICONTROL **Ignora questionario**] e descrivere ciò che si desidera invece nella chat.

1. Continua con [Rivedi i risultati e i mapping della convalida](#review-the-validation-results-and-mappings).

### Iniziare da componenti specifici

<!-- FLAG: Sourced from a prompt that SME Scott Tomko ran in Coworker (October 2026). The example is generalized; the original prompt named a customer. Coworker may ask a few questions along the way. Confirm what happens to the project that Coworker creates in Adobe Analytics, and to its migrated copy in Customer Journey Analytics, if you only wanted the components. -->

Per eseguire la migrazione di componenti specifici:

1. Chiedi a Collaboratore di creare un progetto con questi componenti e quindi eseguirne la migrazione. Ad esempio:

   **Chiedi conferma**

   > Voglio migrare tutti i miei segmenti di Analytics con &quot;Spring sale&quot; (Vendita primaverile) nel nome a CJA. Crea un nuovo progetto Workspace con tutti questi segmenti aggiunti, quindi migra il progetto in CJA.

   Il progetto viene creato in Adobe Analytics.

1. Continuare con la sezione seguente [Esaminare i risultati e i mapping della convalida](#review-the-validation-results-and-mappings).

## Esamina i risultati della convalida e le mappature

<!-- FLAG: Confidence: Medium for the steps that fix a failed validation. They're based on the aa-mcp tool descriptions and on a test conversation where validation passed only after the project's panel was switched to a base report suite. Confirm how Coworker presents a failed validation, and whether it asks for confirmation before it updates a mapping. -->

Il collaboratore convalida il progetto in base alla visualizzazione dati selezionata, quindi segnala se è possibile eseguire la migrazione del progetto. I risultati elencano ogni dimensione e metrica nel progetto e la dimensione o metrica Customer Journey Analytics a cui è mappata. Ad esempio:

* **Metrica:** Occorrenze diventa Eventi
* **Dimension:** ora di permanenza

Per i componenti e gli elementi del progetto migrati, vedi [Comprendere cosa è incluso in una migrazione](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-what-is-included-in-a-migration) nella documentazione di Adobe Analytics.

Se la convalida non viene superata:

* **Dimensioni o metriche che non possono essere mappate automaticamente:** Collaboratore suggerisce una dimensione o una metrica nella visualizzazione dati a cui mappare ciascuna, aggiorna la mappatura, quindi convalida di nuovo il progetto. Puoi anche indicare al collega a quale dimensione o metrica mapparla, ad esempio &quot;Mappa le visualizzazioni di pagina su web.webPageDetails.pageViews.value&quot;.

* **Elementi non supportati:** Rimuovi eventuali elementi non supportati dal progetto in Adobe Analytics. Ad esempio, assicurati che ogni pannello utilizzi una suite di rapporti di base anziché una suite di rapporti virtuale. Quindi chiedi a Collaboratore di controllare di nuovo il progetto. Per un elenco degli elementi non supportati, vedere [Comprendere gli elementi non supportati che causano errori](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration#understand-unsupported-elements-that-cause-errors) nella documentazione di Adobe Analytics.

Per controllare le mappature per un&#39;intera suite di rapporti prima della migrazione, vedi [Rivedere le mappature delle suite di rapporti prima della migrazione](#review-report-suite-mappings-before-you-migrate).

## Migrare il progetto

1. Al termine della convalida, viene richiesto se creare la versione Customer Journey Analytics del progetto nella visualizzazione dati selezionata. Seleziona [!UICONTROL **Sì, esegui la migrazione**], quindi seleziona [!UICONTROL **Invia**].

   Per interrompere la migrazione senza eseguire la migrazione, selezionare [!UICONTROL **No, interrompere qui**].

   Collaboratore ricrea il progetto in Customer Journey Analytics, con te come proprietario del progetto. Il progetto Adobe Analytics originale non cambia.

1. Continua con la seguente sezione, [Verifica lo stato della migrazione](#check-the-migration-status).

## Controllare lo stato della migrazione

Le migrazioni vengono eseguite in background, pertanto il nuovo progetto potrebbe non essere pronto immediatamente.

1. Chiedi al collaboratore di controllare lo stato della migrazione:

   **Chiedi conferma**

   > Verifica stato

   <!-- FLAG: The Failed row links to Retry a failed migration in the Adobe Analytics docs, but those steps use the Component migration page in the Adobe Analytics UI, which is admin-only. A non-admin with the Component Migration permission can't follow them. Confirm with Scott whether Coworker can retry a failed migration (for example, "Retry the migration"). If so, replace the link with a prompt. -->

   Il collaboratore segnala uno dei seguenti stati:

   | Stato | Che cosa significa |
   | --- | --- |
   | In coda | La migrazione è in attesa di inizio. |
   | Avviato | Migrazione in corso. |
   | Completato | Migrazione completata. In Collaboratore viene fornito un riepilogo di ciò che è stato migrato, inclusi il nome del progetto e la visualizzazione dati. |
   | Non riuscito | Migrazione non riuscita. Puoi riprovare la migrazione. Consulta [Riprovare una migrazione non riuscita](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/component-migration#retry-a-failed-migration) nella documentazione di Adobe Analytics. |

1. Al termine della migrazione, apri il nuovo progetto dall’elenco dei progetti in Customer Journey Analytics Workspace.

1. (Facoltativo) Trasferisci la proprietà del progetto a qualsiasi utente in Customer Journey Analytics. Per ulteriori informazioni, consulta [Trasferire risorse](https://experienceleague.adobe.com/it/docs/analytics-platform/using/tools/asset-transfer/transfer-assets).

Al termine di una migrazione, Collaboratore può suggerire un altro progetto di cui eseguire la migrazione successiva.

## Suggerimenti per ottenere risultati migliori

* Lascia vuota la visualizzazione dati nel questionario se non sai quale utilizzare. Collaboratore suggerisce visualizzazioni dati che corrispondono alla suite di rapporti.
* Dopo la migrazione, confronta i dati di Adobe Analytics e Customer Journey Analytics per verificare che i rapporti corrispondano. Consulta [Convalidare i dati con Coworker durante l&#39;aggiornamento da Adobe Analytics a Customer Journey Analytics](/help/chat/use-cases/data-insights/data-validation-aa-cja.md).

## Passaggi successivi

* Per eseguire la migrazione di progetti nell&#39;interfaccia utente di Adobe Analytics, consulta [Migrazione di componenti e progetti da Adobe Analytics a Customer Journey Analytics](https://experienceleague.adobe.com/it/docs/analytics/admin/admin-tools/component-migration/component-migration) nella documentazione di Adobe Analytics.
* Per gli altri casi di utilizzo relativi all&#39;implementazione e all&#39;amministrazione, vedere [Panoramica sull&#39;implementazione e l&#39;amministrazione intelligente](/help/chat/use-cases/data-insights/data-governance-and-validation.md).
