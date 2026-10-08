---
title: Introduzione all’analisi dei dati con Chat per collaboratori
description: Scopri come utilizzare Adobe CX Enterprise Coworker Chat per analizzare i dati di Customer Journey Analytics, creare funnel e individuare i punti di contatto dei clienti nel percorso.
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 2bf31c1348054a16ba7e7c0c26c0ff913634aa27
workflow-type: tm+mt
source-wordcount: '2094'
ht-degree: 4%
---
# Introduzione all’analisi dei dati con Chat per collaboratori

Configura Adobe CX Enterprise Coworker Chat per analizzare le visualizzazioni dati di Customer Journey Analytics o le suite di rapporti di Adobe Analytics, quindi segui un esempio funzionante. Per una panoramica delle operazioni che è possibile eseguire con Chat con Coworker, inclusi casi d&#39;uso, competenze e best practice, consulta [Analizzare i dati con Chat con Coworker](/help/chat/use-cases/data-insights/analytics-overview-v2.md).

Prima di iniziare, scopri l’interfaccia e le opzioni di configurazione di Chat per collaboratori, quindi assicurati che Cooker sia connesso a Customer Journey Analytics o Adobe Analytics e alle relative visualizzazioni dati o suite di rapporti.

## Prima di iniziare

### Accesso ai dati e autorizzazioni

La chat per collaboratori eredita le autorizzazioni da Customer Journey Analytics o Adobe Analytics. Puoi accedere solo alle visualizzazioni dati, alle suite di rapporti, alle dimensioni, alle metriche e ai segmenti disponibili in Analysis Workspace.

### Opzioni di interfaccia e configurazione

Prima di utilizzare Chat con collaboratori con i dati di Customer Journey Analytics o Adobe Analytics, scopri come accedere e gestire le opzioni di configurazione per le seguenti funzioni:

* Input chat
* Conversazioni
* Marketplace
* Server MCP
* Memoria
* Plug-in
* Competenza
* E altro ancora

Per ulteriori informazioni, consulta la [Guida dell&#39;interfaccia utente di Chat per collaboratori](/help/chat/ui-guide.md).

## Verifica che Chat con i collaboratori sia connessa a Customer Journey Analytics

In Chat con collaboratori, verifica che Coworker sia connesso a Customer Journey Analytics:

1. Seleziona l&#39;icona MCP nella barra a sinistra, quindi accertati che [!UICONTROL **cja-mcp**] sia disponibile nell&#39;elenco dei server MCP connessi.

   ![L&#39;icona MCP è evidenziata nella barra a sinistra di Collaboratore](../../assets/coworker-mcp-cja.png)

1. (Condizionale) Se [!UICONTROL **cja-mcp**] non è ancora connesso, selezionare [!UICONTROL **Aggiungi server MCP**], specificare cja nel campo [!UICONTROL **Nome server**] e selezionarlo quando viene visualizzato, quindi selezionare [!UICONTROL **Aggiungi server**].

## Connettersi alla giusta visualizzazione dati o suite di rapporti

Una visualizzazione dati è un contenitore in Customer Journey Analytics che determina il modo in cui i dati vengono interpretati. Una suite di rapporti è un contenitore in Adobe Analytics che contiene i dati raccolti dai siti e dalle app.

Potresti avere accesso a varie visualizzazioni dati in Customer Journey Analytics o a suite di rapporti in Adobe Analytics. Ciascuno può contenere dimensioni e metriche diverse che possono essere utilizzate da Collaboratore durante l’analisi dei dati.

### Decidere quali visualizzazioni dati o suite di rapporti utilizzare

Comunica al collega i tipi di domande a cui desideri rispondere e chiedi a quali visualizzazioni di dati o suite di rapporti hai accesso e a quali forniscano tali informazioni. Puoi anche [impostare la visualizzazione dati o la suite di rapporti come preferenza in memoria](#add-a-data-view-or-report-suite-preference-in-memory).

**Utente:**

>[!BEGINSHADEBOX]

Sono interessato a capire dove i clienti abbandonano nel percorso dei clienti. A quali visualizzazioni dati in Customer Journey Analytics posso accedere per rispondere a questa domanda?

>[!ENDSHADEBOX]

**Risposta chat collaboratore:**

>[!BEGINSHADEBOX]

Puoi accedere a tre visualizzazioni dati. La visualizzazione dati `Customer lifecycle` contiene le dimensioni e le metriche seguenti, che sono le migliori per rispondere alla domanda.

>[!ENDSHADEBOX]

**Utente:**

>[!BEGINSHADEBOX]

Bene, usiamo quella visualizzazione dati.

>[!ENDSHADEBOX]

**Risposta chat collaboratore:**

>[!BEGINSHADEBOX]

Ok, utilizzerò la visualizzazione dati `Customer lifecycle` per rispondere a domande future in questa sessione di chat.

>[!ENDSHADEBOX]

### Aggiungere una visualizzazione dati o una preferenza della suite di rapporti in memoria

La chat di Coworker contiene una funzione di memoria che ti consente di fornire accesso a informazioni che si estendono su tutte le chat. È buona prassi aggiungere le visualizzazioni dati o le suite di rapporti preferite come preferenze nella memoria di Coworker.

1. In Chat con collaboratori, nella barra di navigazione a sinistra, seleziona l’icona Memoria.

1. Nella sezione [!UICONTROL **Preferenze memorizzate**] della pagina Memoria specificare una o più visualizzazioni dati o suite di rapporti che si desidera utilizzare nelle chat di Coworker Chat.

   ![Sezione memoria nella barra a sinistra](../../assets/coworker-memory.png)

## Esempio: individuare il punto di partenza dei clienti

Puoi chiedere a Chat con i colleghi di utilizzare i tuoi dati per analizzare qualsiasi domanda di business.

Ad esempio, in qualità di responsabile marketing, merchandiser o lead di crescita, potresti voler capire dove i clienti abbandonano il percorso di acquisto, perché lo hanno fatto e cosa si può fare per aumentare i tassi di conversione.

>[!NOTE]
>
>Le figure seguenti sono dati di esempio illustrativi per un retailer fittizio, [!DNL TechPulse Electronics], utilizzato per mostrare la forma della conversazione.

### I tipi di domande che è possibile porre

Non è necessario sapere cos’è una &quot;visualizzazione di abbandono&quot; o quale metrica entra in quale slot. Descrivi invece il risultato a cui tieni in considerazione in un linguaggio semplice:

* &quot;Dove stiamo perdendo la gente sulla via dell&#39;acquisto?&quot;
* &quot;Qual è il mio funnel di conversione completo, dalla visualizzazione del prodotto al pagamento?&quot;
* &quot;Quali canali di marketing perdono di più tra il carrello e l’acquisto?&quot;
* &quot;L’abbandono del carrello è peggiore su dispositivi mobili o desktop?&quot;
* &quot;Le persone dei social network a pagamento si convertono in modo diverso rispetto alle persone delle e-mail?&quot;

### La conversazione

#### &#x200B;1. Inizia con la domanda di business

**Utente:**

>[!BEGINSHADEBOX]

Dove stiamo perdendo la gente sulla strada per l&#39;acquisto?

>[!ENDSHADEBOX]

**Risposta chat collaboratore:**

Tieni presente che Chat con i collaboratori sceglie la visualizzazione corretta, sequenzia i punti di contatto e aggiunge anche i passaggi successivi consigliati.

>[!BEGINSHADEBOX]

![Tabella Funnel che mostra i conteggi delle sessioni, i tassi di conversione e l&#39;abbandono a ogni passaggio dalle sessioni all&#39;acquisto](../../assets/coworker-funnel-response.png)

Questa è una domanda di funnel — lasciate che esegua il funnel di conversione per vedere dove avviene il drop-off sul percorso di acquisto.

Ecco dove stai perdendo delle persone:

| Passaggio funnel | Count | Conversione al successivo | Dispersione |
| --- | --- | --- | --- |
| Sessions | 137,476 | 45,0% visualizza un prodotto | 55% di abbandono senza navigazione dei prodotti |
| Visualizzazioni di prodotti | 61,845 | 55,0% aggiungi al carrello | 45% navigazione ma non aggiunta |
| Aggiunte al carrello | 34,045 | Acquisto del 16,4% | 83,6% carrello di abbandono |
| Acquisti | 5,582 | — | — |

**Il grande risultato: il carrello da acquistare è la tua perdita più grande**

28.463 persone aggiungono articoli al carrello ma non completano mai l’acquisto. Si tratta di un tasso di abbandono dell&#39;83,6% tra carrello e acquisto, di gran lunga il più grande singolo punto di errore.

**Informazioni sulle priorità:**

| Priorità | Problema | Scala delle opportunità |
| --- | --- | --- |
| #1 | Abbandono carrello all’acquisto (calo dell’83,6%) | 28.463 acquirenti persi |
| #2 | Sessione alla visualizzazione prodotto (il 55% non naviga mai) | 75.631 sessioni senza coinvolgimento con il prodotto |
| #3 | Visualizzazione prodotto al carrello (il 45% non viene aggiunto) | 27.800 interessati ma non impegnati |

**Passaggi successivi consigliati:**

1. Suddividere l’abbandono del carrello per canale di marketing: alcuni canali generano traffico a basso intento che si aggiunge al carrello ma non acquista mai?
1. Osservare l&#39;abbandono del carrello per tipo di dispositivo — l&#39;attrito del checkout mobile uccide le conversioni?
1. Individuare i prodotti più abbandonati: problemi di prezzo? Sorpresa sulla spedizione?

**In quali casi vuoi che mi occupi io?** La suddivisione del canale ti direbbe direttamente quali azioni di marketing ti stanno portando &quot;quasi-acquirenti&quot; rispetto agli acquirenti effettivi.

>[!ENDSHADEBOX]

#### &#x200B;2. Eseguire un drill-through nella perdita

**Utente:**

>[!BEGINSHADEBOX]

Ok, suddividiamo per canale di marketing

>[!ENDSHADEBOX]

**Risposta chat collaboratore:**

>[!BEGINSHADEBOX]

![Tabella Funnel con tassi di conversione e abbandono suddivisi per canale di marketing](../../assets/coworker-funnel-response2.png)

È presente una dimensione **Canale di marketing** personalizzata. Lasciate che prenda il funnel in questo modo, poi calcoli i tassi di conversione per canale e identifichi dove ogni canale perde.

**Il verdetto: la perdita non è specifica del canale**

Questo è un risultato davvero rivelatore. Ecco il raggruppamento per canale di funnel:

| Canale | Sessions | Alla vista prodotto | Da aggiungere al carrello | Per acquistare | Conversione globale | Ricavi/sessione |
| --- | --- | --- | --- | --- | --- | --- |
| Ricerca a pagamento | 43,958 | 45.1% | 54.6% | 16.6% | 4.09% | $499.58 |
| Ricerca organica | 31,492 | 44.9% | 54.9% | 16.9% | 4.17% | $494.76 |
| Diretto | 25,245 | 43.6% | 55.4% | 15.8% | 3.82% | $497.29 |
| E-mail | 17,586 | 45.3% | 55.4% | 16.2% | 4.07% | $501.13 |
| Social network a pagamento | 12,684 | 45.4% | 55.7% | 16.0% | 4.03% | $512.17 |
| Visualizzazione | 6,511 | 45.3% | 55.7% | 16.2% | 4.09% | $501.45 |

**Attività principali:**

1. Il tasso di caduta da carrello ad acquisto è uniformemente negativo su tutti i canali (83-84%). Questo significa che il problema non riguarda la qualità del traffico — ogni canale converte le persone nel carrello a tassi simili. La perdita si trova nell’esperienza di pagamento stessa, non nel marketing.
1. Nessun canale è significativamente migliore o peggiore nella conversione. I tassi di conversione complessivi si concentrano strettamente tra il 3,8% e il 4,2% e i ricavi per sessione sono quasi identici (495-512 dollari).
1. Dove l’impatto del volume conta di più: la ricerca a pagamento perde il maggior numero di persone in termini assoluti (9,015 abbandoni del carrello), seguita dalla ricerca organica (6,449 persi). Queste sono le maggiori opportunità di valore in dollari perché guidano più traffico.

**Informazioni strategiche**

I canali di marketing stanno facendo il loro lavoro — tutti fanno sì che la gente si interessi e aggiunga al carrello a ritmi simili. Il problema è a valle del marketing: il vostro pagamento e pagamento è dove il denaro sta perdendo.

**Ricerche successive consigliate:**

1. Suddividere l’abbandono del carrello mobile per categoria di prodotto: è peggio per gli articoli a prezzo elevato (suggerendo problemi di attendibilità per i pagamenti mobili)?
1. Osserva quali canali di marketing sono più determinanti per il traffico mobile: stai spendendo dollari dei media pagati per inviare persone verso un funnel mobile non funzionante?
1. Controlla se c&#39;è un segnale nella pagina o nella sezione del sito: possiamo vedere quali pagine di pagamento sono state visitate per ultime dagli utenti di dispositivi mobili prima di abbandonarle?

**Scegliere l&#39;angolo da esplorare.**

>[!ENDSHADEBOX]

#### &#x200B;3. Continua a indagare

**Utente:**

>[!BEGINSHADEBOX]

Interessante. Proviamo a suddividerci per tipo di dispositivo.

>[!ENDSHADEBOX]

**Risposta chat collaboratore:**

>[!BEGINSHADEBOX]

![Tabella Funnel con tassi di conversione e abbandono suddivisi per tipo di dispositivo](../../assets/coworker-funnel-response3.png)

**Trovato: il checkout mobile è interrotto**

Il funnel è identico tra i dispositivi fino al momento del check-out, quindi il dispositivo mobile cade da un precipizio:

| Dispositivo | Sessions | Alla vista prodotto | Da aggiungere al carrello | Per acquistare | Conversione globale |
| --- | --- | --- | --- | --- | --- |
| Desktop | 70,172 | 44.9% | 54.8% | 23.2% | 5.70% |
| Tablet | 13,855 | 44.7% | 55.6% | 14.3% | 3.56% |
| Dispositivi mobili | 53,449 | 44.9% | 55.3% | 8.1% | 2.02% |

**La pistola fumante**

| Metrica | Desktop | Dispositivi mobili | Intervallo |
| --- | --- | --- | --- |
| Percentuale da carrello ad acquisto | 23.2% | 8.1% | 15 punti percentuali |
| Mobile è | — | 2,8x peggiore | — |
| Carrelli abbandonati | 13,274 | 12,178 | Quasi lo stesso volume assoluto |

L’esperienza di navigazione e di aggiunta al carrello è ottimale per i dispositivi mobili (tasso di navigazione identico al 45%, tasso di aggiunta al carrello pari al 55%). Le persone sono interessate e coinvolte allo stesso modo. Ma qualcosa nel flusso delle casse mobili uccide le conversioni.

**L&#39;opportunità di ricavo**

Se il checkout mobile viene convertito alla stessa velocità del desktop, si otterrebbero circa 1.991 acquisti aggiuntivi, con un aumento del 35% del volume totale degli acquisti dalla correzione di un&#39;esperienza.

**Cosa potrebbe succedere**

Il pattern dei dati (coinvolgimento uguale, calo catastrofico del checkout) è un segnale classico per:

* Limitazione del modulo di pagamento su schermi di piccole dimensioni (problemi di riempimento automatico, layout del modulo)
* Costi imprevisti rilevati al momento del pagamento (spedizione, imposte) che causano shock da adesivo
* Il checkout dell’ospite non è disponibile o una bacheca di accesso su dispositivi mobili
* Problemi di caricamento pagina o timeout durante l’elaborazione del pagamento su dispositivi mobili

**Passaggi successivi consigliati:**

1. Suddividere l’abbandono del carrello mobile per categoria di prodotto: è peggio per gli articoli a prezzo elevato (suggerendo problemi di attendibilità per i pagamenti mobili)?
1. Osserva quali canali di marketing sono più determinanti per il traffico mobile: stai spendendo dollari dei media pagati per inviare persone verso un funnel mobile non funzionante?
1. Controlla se la campagna &quot;Holiday_flash_sale&quot; ha avuto una migliore conversione del pagamento — le campagne basate sull’urgenza potrebbero superare l’attrito del pagamento

**Quali elementi vuoi esplorare o queste prove sono sufficienti per indirizzare l&#39;utente e il team di checkout?**

>[!ENDSHADEBOX]

#### &#x200B;4. Trasformalo in una decisione

**Utente:**

>[!BEGINSHADEBOX]

Quindi cosa dovrei fare?

>[!ENDSHADEBOX]

**Risposta chat collaboratore:**

>[!BEGINSHADEBOX]

In base a ciò che mostrano i dati, ecco dove vorrei concentrarmi:

* **Correggi l&#39;estrazione mobile. Non si tratta di un problema di canale.** Ogni canale converte le persone nel carrello a un ritmo sano e simile, in modo che la spesa pubblicitaria funzioni in modo trasversale. I ricavi vengono persi in modo specifico nel flusso di pagamento mobile, che è il luogo in cui appartiene la correzione.
* **Inizia con il pagamento e con l&#39;attrito del modulo.** Questi sono i motivi più comuni per cui gli acquirenti di dispositivi mobili ad alto intento abbandonano il carrello. L&#39;offerta di opzioni per il portafoglio mobile e la riduzione della forma sono di solito le vincite più veloci.
* **Controlla di nuovo dopo la correzione.** Una volta che il pagamento cambia spedizione, osserva se il tasso di acquisto del carrello mobile si sposta verso il tasso desktop del 23,2%.

Vuoi che salvi questo come progetto in modo da poterlo tenere traccia, o che imposti un avviso se il carrello mobile da acquistare scende al di sotto di una soglia?

>[!ENDSHADEBOX]

### Cos’è successo

In quattro semplici domande, Coworker ci ha aiutato:

* Costruisci un funnel di conversione in più passaggi e contrassegna il carrello da acquistare come la perdita più grande
* Escludi canale di marketing come causa: ogni canale ha registrato perdite quasi equivalenti
* Individua il problema reale al pagamento mobile e quantifica la correzione con un incremento del 35% negli acquisti
* Approfitta di una correzione specifica per definire le priorità: pagamenti mobili e attrito tra moduli. Questo è confrontato con il tasso di conversione del 23,2% del desktop

## Analizzare in Customer Journey Analytics

Dopo aver creato una visualizzazione, puoi aprirla in Analysis Workspace per un’analisi più approfondita e un controllo granulare. La visualizzazione si apre in un nuovo progetto Analysis Workspace in Customer Journey Analytics.

Per aprire una visualizzazione in un nuovo progetto Analysis Workspace:

1. Seleziona [!UICONTROL **Analizza in CJA**] accanto a qualsiasi visualizzazione creata in Coworker.

1. Con la visualizzazione aperta in Customer Journey Analytics, puoi utilizzare l’interfaccia del browser drag-and-drop di Analysis Workspace per apportare modifiche, definire ulteriormente l’analisi, creare un pubblico e molto altro. Puoi anche condividere il tuo progetto Workspace con chi desideri.

   Per ulteriori informazioni su Analysis Workspace, consulta [Panoramica di Analysis Workspace](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-workspace/home).

## Passaggi successivi

Per altri casi d&#39;uso, le abilità utilizzate da Chat con collaboratori per analizzare i dati e le best practice per la scrittura di prompt, vedi [Analizzare i dati con Chat con collaboratori](/help/chat/use-cases/data-insights/analytics-overview-v2.md).
