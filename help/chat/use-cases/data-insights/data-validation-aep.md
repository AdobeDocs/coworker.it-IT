---
title: Convalidare i dati di Experience Platform con il collaboratore
description: Scopri come utilizzare l’abilità di convalida dei dati di CX Enterprise Coworker per verificare la qualità dei set di dati e dei campi Adobe Experience Platform tramite chat.
feature: AI Tools
role: User
level: Intermediate
doc-type: Tutorial
last-substantial-update: 2026-08-27T00:00:00.000Z
jira: PLAT-302857
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1054'
ht-degree: 0%
---

# Convalidare i dati di Experience Platform con Collaboratore

Il collaboratore include l’abilità Convalida dati che controlla la qualità dei dati dei set di dati di Experience Platform. Puoi utilizzarlo per eseguire convalide statistiche e semantiche sui set di dati, analizzare i campi dei set di dati e identificare i problemi di qualità dei dati, il tutto tramite una singola conversazione con Chat per collaboratori.

I data engineer, gli amministratori di dati e i tecnici dell’implementazione lo utilizzano per controlli di qualità rapidi, senza query SQL o gerarchie di schemi complesse.

Utilizza questa abilità per:

* Convalida i campi di identità ed evento chiave dopo una nuova implementazione o un aggiornamento dell’implementazione.
* Esamina un problema di mappatura sospetto esaminando i valori principali di un campo e i valori non validi.
* Esegui controlli di gestione dei dati continui sui set di dati critici per rilevare tempestivamente le regressioni.

<!--TODO: skill display name "Data Validation skill" confirmed via the published KT-22622 video page (validate-dataset-quality-for-cja.md, merged 2026-09-16). Still need the technical skill ID from engineering (Petru Adrian Snep) for the use-cases overview table row. That page didn't add one either.-->

>[!NOTE]
>
>Questa abilità è di sola lettura. Non modifica dati, schemi o mappature.

## Prima di iniziare

Per convalidare i dati con Collaboratore, è necessario:

* Nome o ID del set di dati da convalidare.
* (Facoltativo) Il nome di un campo specifico da convalidare, se non desideri che l’abilità selezioni automaticamente i campi.

## Avviare una sessione di convalida

1. Accedi a Collaboratore.

1. Seleziona [!UICONTROL **Nuova chat**].

1. Nel campo di testo, richiedi all’agente di convalidare un campo o un set di dati. Ad esempio:

   **Chiedi conferma**

   > Convalida set di dati &quot;Electronics Sample 1000&quot;

   ![La schermata iniziale della chat di Coworker con la richiesta Convalida set di dati Elettronica campione 1000 immessa nel campo del messaggio.](../../assets/data-validation-aep/start-session.png)

   >[!TIP]
   >
   >Anteponi al nome del set di dati la parola &quot;set di dati&quot; in modo che l’abilità possa identificarlo correttamente. Ad esempio, utilizza &quot;Validate the dataset Electronics Sample 1000&quot; invece di &quot;Validate Electronics Sample 1000&quot;.

   La richiesta viene indirizzata all’abilità Convalida dati, che analizza un campione del set di dati e restituisce i risultati nella stessa conversazione.

## Scegli cosa convalidare

Puoi convalidare un singolo campo o un intero set di dati.

>[!BEGINTABS]

>[!TAB Convalida campo]

Convalida un campo specifico in un set di dati. Questa opzione fornisce:

* Conteggio nullo e conteggio valori distinti.
* Valori distinti principali e relative frequenze.
* Convalida semantica basata sull’intelligenza artificiale che contrassegna i valori che non corrispondono al formato previsto del campo, in base ai metadati del campo e ai relativi valori effettivi.

Esempio di prompt:

* Convalida il campo e-mail nel set di dati Customers_2024.
* Convalida lo stato del campo per il set di dati customer_events_2024.
* Convalida il campo person.address.city per il set di dati dei clienti.

>[!TAB Convalida set di dati]

Convalida fino a cinque campi in un set di dati alla volta. Puoi specificare i campi autonomamente oppure consentire all’abilità di analizzare il set di dati e selezionare automaticamente i campi più rilevanti. Questa opzione restituisce le stesse informazioni della convalida del campo, in ogni campo convalidato.

Esempio di prompt:

* Convalida il set di dati di Customer Data 2024.
* Convalida campi e-mail, telefono per Customers_2024.
* Riepilogare nome, cognome, data di nascita per i dati del cliente.

>[!ENDTABS]

## Esaminare i risultati

Per ogni campo convalidato, i risultati vengono visualizzati sotto forma di riga in una tabella con le colonne seguenti:

| Colonna | Descrizione |
| --- | --- |
| [!UICONTROL Nome campo] | Nome del campo. |
| [!UICONTROL Percorso campo] | Percorso completo del campo nello schema. |
| [!UICONTROL Tipo di campo] | Tipo di dati del campo. |
| [!UICONTROL Valori validi] | Percentuale di valori campionati che superano la convalida. |
| [!UICONTROL Valori distinti] | Percentuale di valori campionati distinti. |
| [!UICONTROL Valori nulli] | Percentuale di valori campionati che sono nulli. |
| [!UICONTROL Primi 5 valori distinti] | I cinque valori più comuni e le loro frequenze. |
| [!UICONTROL Primi 5 valori non validi] | I cinque valori non validi più comuni, con una spiegazione per ciascuno, ad esempio &quot;non un formato e-mail valido&quot;. |
| [!UICONTROL insight aggiuntivo] | Breve nota in linguaggio naturale sulla qualità del campo. |

Sotto i risultati, in Collaborator viene aggiunto un elenco **Passaggi successivi** in cui vengono suggeriti prompt di follow-up, ad esempio la convalida di un altro campo o la riesecuzione del set di dati.

Quando si convalida un singolo campo, Collaboratore restituisce anche un grafico:

![Chat collaboratore che mostra un grafico ad anello e un riepilogo scritto per il campo Marchio, con valori validi al 79,5%, valori nulli al 20,5% e nessun valore non valido rilevato.](../../assets/data-validation-aep/null-values.png)

Selezionare [!UICONTROL **Grafico**] o [!UICONTROL **Tabella**] per passare da una visualizzazione all&#39;altra degli stessi risultati.

Quando convalidi un set di dati, i risultati vengono visualizzati in una tabella con una riga per campo. I campi a cui si assegna il nome vengono visualizzati come specificati:

![Tabella chat di collaborazione con titolo Convalida campo 1000 campione elettronica, che mostra i risultati della convalida per i campi Categoria, Marchio e Prezzo indicati dall&#39;utente nel prompt.](../../assets/data-validation-aep/field-validation.png)

I campi selezionati dall’abilità vengono visualizzati automaticamente nello stesso modo:

![Tabella chat collaboratore con i risultati della convalida per cinque campi selezionati automaticamente nel set di dati Electronics Sample 1000: Categoria, Marchio, Prezzo, Inventario e Condizione.](../../assets/data-validation-aep/dataset-validation.png)

Seleziona [!UICONTROL **CSV**] per scaricare la tabella dei risultati completa.

## Controlli eseguiti dalla convalida dei dati

L’abilità esegue i seguenti tipi di controlli su ciascun campo e set di dati:

* **Controlli di completezza**: conteggi e percentuali nulli e mancanti.
* **Controlli di distribuzione**: valori distinti principali e relative distribuzioni e rilevamento di elevata cardinalità.
* **Controlli semantici rispetto allo schema**: utilizza il nome, il tipo e la descrizione del campo XDM per dedurre l&#39;aspetto di un valore valido, quindi contrassegna le anomalie.
* **Controlli in base al tipo di dati**, se applicabile:
  * E-mail: plausibilità del formato e del dominio.
  * Telefono: preparazione al formato, ad esempio E.164.
  * Date e timestamp: controlli di formato di base, ad esempio ISO-8601.

Questi controlli combinano le statistiche deterministiche con la convalida semantica assistita da LLM per rilevare i valori che hanno un aspetto errato anche quando tecnicamente corrispondono allo schema.

## Limitazioni

Prima di convalidare i dati, tieni presenti le seguenti limitazioni. Questi vincoli bilanciano le prestazioni con le funzionalità e impostano le aspettative per l’analisi e le informazioni che puoi aspettarti.

* **Solo campionamento**: l&#39;abilità convalida un campione del set di dati (in genere le 1.000 righe più recenti), non l&#39;intero set di dati. Le scansioni complete dei set di dati non sono disponibili.
* **Limite conteggio campi**: quando convalidi un set di dati, l&#39;abilità analizza fino a cinque campi per richiesta. Puoi specificare questi campi o lasciare che siano selezionati automaticamente dall’abilità.
* **Semantica probabilistica**: il rilevamento di valori non validi si basa in parte sull&#39;inferenza basata su LLM, che a volte può perdere errori sottili o valori limite del flag.
* **Sola lettura**: l&#39;abilità non modifica i dati o il relativo schema. Evidenzia potenziali problemi ma non esegue correzioni automatizzate.

Se le tue esigenze di convalida sono più esaustive o richiedono una logica di business complessa, completa questi risultati con strumenti aggiuntivi come le convalide di Query Service o Preparazione dati.

**Informazioni correlate**

* [Convalidare i dati da Adobe Analytics a Customer Journey Analytics durante l&#39;aggiornamento](./data-validation-aa-cja.md)
* [Convalidare i dati Customer Journey Analytics con l’abilità di Convalida dati in Collaboratore](./validate-dataset-quality-for-cja.md)
* [Convalidare i dati (Assistente AI)](https://experienceleague.adobe.com/it/docs/cx-enterprise-ai/experience-cloud-ai/agents/data-validation)
* [Considera attendibile il tuo reporting Customer Journey Analytics: abilità di convalida dei dati in Adobe CX Coworker](https://www.youtube.com/watch?v=gCSm_QYSYhk) (video)
