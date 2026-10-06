---
description: Scopri i miglioramenti e le correzioni di funzioni nelle note sulla versione di Adobe CX Enterprise Coworker Campaigns.
title: Note sulla versione di CX Enterprise Coworker Campaigns
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: ee66c1cc95ef1dd8c5e45c1fcb699547e63b9c8a
workflow-type: tm+mt
source-wordcount: '3590'
ht-degree: 0%
---
# Note sulla versione di Adobe CX Enterprise Coworker Campaigns {#release-notes}

I rilasci delle campagne di collaborazione funzionano su un modello di distribuzione continua che consente un approccio più scalabile e graduale alla distribuzione delle funzioni.

## Settembre 2026 {#sep-2026}

**Data di rilascio: 17 settembre 2026**

* Connettere un’area di lavoro Databricks ospitata su Azure, GCP o un dominio personalizzato
* Non è più possibile avviare le campagne finché il relativo flusso di lavoro non è completamente configurato
* I modelli di campagna sono stati aggiornati con il contenuto aggiornato
* Scegli un connettore direttamente durante il caricamento del file CSV dell’elenco contatti
* È stato corretto un arresto anomalo che poteva verificarsi dopo lo scorrimento di un lungo elenco di iscrizioni di prova
* È stato risolto un problema che poteva causare l’arresto anomalo della pagina durante il caricamento di un file CSV di un pubblico con intestazioni vuote o duplicate
* È stato corretto il testo segnaposto in un prompt della campagna che non veniva compilato dopo la risoluzione
* È stato corretto un arresto anomalo nella pagina Abilità causato da una sfumatura di colore mancante
* È stata corretta la situazione in cui la chat si bloccava ripetendo la stessa domanda dopo aver già risposto
* Le risposte di chat non mostrano più un prefisso dell’ID randagio di fronte alla risposta selezionata
* La chat ora suggerisce risposte rapide al passaggio successivo che puoi toccare per riempire la casella di composizione
* I modelli di campagna ora si aprono in una visualizzazione semplificata all’interno della pagina invece di una finestra di dialogo separata
* La barra di avanzamento della chat espansa ora scorre internamente invece di portare la conversazione fuori dalla vista
* Le impostazioni di Campaign ora riflettono più accuratamente i dettagli più recenti della bacheca
* La finestra di dialogo del piano di aggiornamento ora utilizza un aspetto più coerente
* È stato rimosso un indicatore di stato ridondante dall’intestazione del piano della campagna per un aspetto più pulito
* Le modifiche rapide delle e-mail ora vengono salvate insieme come una singola voce di cronologia delle versioni invece di molte
* Titoli di kit di marchi fissi che occasionalmente scompaiono durante la generazione di una bozza
* Modificare un’immagine con Adobe Express direttamente dalla barra degli strumenti delle immagini
* I dati del pubblico dell’agente di base ora rimangono sincronizzati sulla bacheca della campagna senza un aggiornamento manuale
* I loghi dei marchi sulla bacheca della campagna sono ritagliati in modo più preciso per adattarsi al loro spazio
* Un passaggio di consegne più fluido quando il piano della campagna si sposta sulla bacheca della campagna

**Data di rilascio: 3 settembre 2026**

* Copia qualsiasi messaggio di chat e valuta le risposte AI con un pollice verso l’alto o verso il basso, direttamente dal messaggio stesso
* L’elenco delle attività del piano della campagna ora rimane bloccato sopra l’input della chat mentre la campagna è in esecuzione, quindi puoi tenere traccia dell’avanzamento senza dover scorrere
* Connettere un data warehouse SQL come nuova origine dati per le campagne
* Il precedente editor e-mail basato su chat è stato ritirato a favore del nuovo editor di risorse e-mail
* L’amministratore utenti di prova ora consente di escludere gli utenti Adobe, semplificando la visualizzazione delle iscrizioni di prova reali
* È stato risolto un problema che impediva il caricamento di suggerimenti di campagne simili
* I messaggi di chat ora hanno una spaziatura più stretta e coerente

**Data di rilascio: 1 settembre 2026**

* Le e-mail di grandi dimensioni delle campagne ora vengono visualizzate completamente nell’editor invece di essere tagliate
* Il pulsante di lancio della bacheca della campagna è ora etichettato come &quot;Review and launch&quot; (Revisione e lancio) per chiarezza
* La connessione di un account Salesforce non mostra più un messaggio di errore Marketo errato
* Salesforce ora ha il proprio logo nell’elenco dei connettori
* I connettori disponibili sono ora elencati in anticipo rispetto a quelli in arrivo
* L’onboarding ora mostra un indicatore di avanzamento durante il caricamento del kit del brand
* Il pubblico e le anteprime delle knowledge-source ora dispongono di un pulsante Chiudi e possono aprire lo schermo intero
* Le schede del piano della campagna non si bloccano più mostrando &quot;edificio&quot; dopo che la campagna inizia a essere eseguita
* La chat non mantiene più messaggi di avanzamento temporanei (come &quot;Esplorazione di...&quot;) nella cronologia delle conversazioni
* I controlli della barra degli strumenti ora vengono bloccati in modo appropriato durante l’applicazione di suggerimenti di testo o immagini AI
* È stato risolto un problema a causa del quale la sostituzione di un’immagine nell’editor risorse non funzionava correttamente

## Agosto 2026 {#aug-2026}

**Data di rilascio: 26 agosto 2026**

* Facendo clic in un punto qualsiasi della scheda di un modello della campagna ora si apre l’anteprima, non solo il titolo
* Il segnaposto della barra del prompt della campagna viene nuovamente visualizzato correttamente dopo aver cancellato l’input, con un supporto più chiaro per gli assistenti vocali
* Il suggerimento &quot;Help me prompt&quot; ora sostituisce correttamente il testo esistente nella barra del prompt della campagna
* Il download degli annullamenti dell’abbonamento come CSV ora riflette solo l’esecuzione della campagna che stai visualizzando
* Il confronto del piano di prova ora mostra le campagne di Launch e gli insight di Campaign come funzioni incluse
* I tipi di pubblico creati senza un flusso di lavoro completo ora vengono visualizzati correttamente nella scheda Pubblico della bacheca della campagna
* Le richieste di feedback in stato vuoto vengono lette più naturalmente in tutta l’app

**Data di rilascio: 25 agosto 2026**

* L’accesso a una scheda del browser ora sincronizza automaticamente le altre, correggendo le combinazioni di account tra le schede.
* Facendo clic su Genera ora il piano viene spostato in avanti in modo affidabile, anziché essere rigenerato occasionalmente
* I diagrammi del flusso di lavoro nella chat mostrano più aree di lavoro, pertanto i controlli di zoom non coprono più i passaggi
* Le schede dei dettagli della campagna hanno un aspetto aggiornato e più coerente
* Il salvataggio o la rimozione di un dominio di invio in Domains &amp; Senders è ora più veloce e affidabile

**Data di rilascio: 24 agosto 2026**

* Visualizza la strategia di campagna generata direttamente sulla bacheca della campagna
* Sostituisci il pubblico direttamente dalla finestra di dialogo di convalida della campagna
* Le esportazioni di Campaign PDF e Word ora includono il diagramma del flusso di lavoro reale
* La scheda Approfondimenti rimane visibile con un utile stato vuoto subito dopo il lancio
* Aggiungere o rimuovere punti di contatto durante la revisione dei campi della campagna
* La barra degli strumenti della bacheca di Campaign è più semplice con la rimozione di pulsanti non necessari
* La procedura guidata Domains &amp; Senders esegue lo scrubing dei sottodomini e delle guide la prima volta con un contrassegno
* La procedura guidata Domains &amp; Senders (Domini e mittenti) mostra gli errori di convalida del sottodominio in linea durante la digitazione
* Il call-to-action della campagna di post-bozza è stato rimosso per un flusso più pulito
* I nomi delle lingue cinesi ora vengono visualizzati correttamente nel selettore lingua
* Le miniature delle varianti generate dall’intelligenza artificiale vengono caricate in modo affidabile senza etichette duplicate
* Le nuove campagne create ora vengono visualizzate immediatamente nell’elenco delle campagne recenti nella pagina Home
* Gli approfondimenti di tutte le campagne ora includono un riepilogo generato dall’intelligenza artificiale delle prestazioni della campagna della tua organizzazione
* L’immissione dell’input richiesto in una conversazione del flusso di lavoro non si blocca più
* L’onboarding di prova non lampeggia più con una schermata di caricamento aggiuntiva durante la verifica di un kit del marchio esistente
* Le origini del pubblico di esempio non più valide ora vengono cancellate automaticamente dal flusso di lavoro
* Layout, tema e font ora vengono riprodotti correttamente nella shell unificata di Experience Cloud
* Suggerimenti per campagne simili non mostrano più un campo canale non necessario

**Data di rilascio: 14 agosto 2026**

* Eliminare i domini bozza non più necessari in Domini e mittenti
* Vedi Stato di verifica DNS per ogni record durante la configurazione del dominio
* I dettagli del dominio ora mostrano il mittente dell’e-mail configurato
* I valori dei record DNS vengono troncati in modo chiaro con una descrizione comando per il testo completo
* Formattare più blocchi di testo e-mail contemporaneamente con selezione multipla
* Ottieni suggerimenti di campagne simili durante la creazione di una nuova campagna
* Valutazione degli approfondimenti della campagna in una singola esecuzione di una campagna ricorrente
* Scegli la lingua preferita dal menu del profilo
* Ottieni una spinta quando le descrizioni del modello di campagna richiedono più dettagli
* Le note sulla versione sono più facili da consultare grazie a una migliore navigazione e impaginazione
* Comprimi l’elenco delle campagne recenti della barra laterale per risparmiare spazio
* La vista inventario della campagna ora rimane invariata
* Riordina i filtri di esecuzione e passa a un intervallo di date da un selettore calendario
* Anteprima dei dettagli del pubblico anche su schede di pubblico di sola lettura
* È stato risolto un problema di tempistica dell’accesso e lampeggiamenti nella schermata di flusso di prova dell’onboarding
* L’handle di ridimensionamento della barra di chat non blocca più la barra di scorrimento dell’elenco dei messaggi
* La creazione del kit di branding ora mostra il motivo reale per cui un salvataggio non è riuscito

**Data di rilascio: 6 agosto 2026**

* Campaign Insights ora mostra gli annullamenti dell’abbonamento con un CSV scaricabile di chi ha rinunciato
* Nella scheda Approfondimenti è ora disponibile una tabella di suddivisione delle prestazioni per e-mail
* Visualizza la mappa del percorso della campagna direttamente nella scheda Approfondimenti
* I passaggi di attesa basati sulla durata sono ora visibili nella vista Flusso di lavoro del percorso
* I rami del percorso ponderati vengono visualizzati nella vista di modifica del flusso di lavoro
* Gli elenchi di contatti ora sono connessi ai dati live
* Le campagne ricorrenti mostrano 0 invii immediatamente invece di &quot;approfondimenti in sospeso&quot;
* Modifica il testo del prompt di remix direttamente attorno ai chip segnaposto
* Sono stati migliorati i coachmark e i chip segnaposto più puliti nell’editor di remix
* Le schede del flusso di lavoro di Campaign ora mostrano un utile stato vuoto quando non è in esecuzione nulla
* Il pulsante del piano di aggiornamento non confonde più l’intestazione dei dettagli della campagna
* Le schede del flusso di lavoro hanno un layout più semplice con nome e descrizione del percorso rimossi

## luglio 2026 {#july-2026}

**Data di rilascio: 30 luglio 2026**

* Gli approfondimenti di tutte le campagne ora corrispondono al layout degli approfondimenti di singole campagne, più un nuovo grafico delle prestazioni giornaliere
* Interrompere una campagna in tempo reale direttamente dalla pagina della campagna
* Quando si duplica una campagna ora viene richiesto solo un nuovo nome
* Modifica i modelli e-mail direttamente dall’elenco dei modelli
* Filtrare la visualizzazione ricorrente del percorso di campagne in base all’esecuzione
* Aggiungere un’immagine del brand direttamente dalla bacheca della campagna
* La tabella dell’amministratore della versione di prova ora supporta la ricerca e-mail, l’impaginazione e l’esportazione CSV completa
* Il pulsante &quot;Sorprendi&quot; ora risponde all&#39;istante, senza alcun ritardo nell&#39;animazione
* Sono state rimosse le impostazioni per l’annullamento dell’iscrizione all’e-mail della campagna durante la rielaborazione di questa funzione
* Modificare la pianificazione di una campagna dopo averla già impostata, senza ricominciare
* Aprite l&#39;editor di stili di scrittura dal menu di overflow per un accesso più rapido
* Premendo Invio ora viene inviato in modo coerente su ogni barra dei prompt nell’app

**Data di rilascio: 23 luglio 2026**

* Pianifica le campagne da inviare immediatamente, una volta al momento scelto o su base periodica
* Gestire gli elenchi di annullamento degli abbonamenti dalle liste di contatti e impostare i parametri di annullamento degli abbonamenti nelle impostazioni e-mail delle campagne
* Creare e gestire i moduli con un nuovo inventario ed editor di moduli
* La configurazione del connettore mostra indicazioni più chiare in caso di errore delle credenziali, incluso l’aggiornamento di una connessione esistente
* Le connessioni Marketo ora supportano gli URL di Experience Cloud
* La procedura guidata Domains &amp; Senders rileva altri problemi di record DNS prima che il dominio venga attivato
* Aggiungere connettori direttamente dal menu di aggiunta dell’input della campagna
* Le pagine di inventario mostrano gli stati vuoti illustrati in modo più intuitivo quando non è ancora presente nulla
* Gli insights di Campaign mostrano quale origine dati potenzia ogni metrica
* Gli editor dei marchi sono ora integrati nell’onboarding per una configurazione più semplice
* Visualizzare in anteprima un pubblico di esempio prima di confermare la campagna
* Le campagne per collaboratori ora risiedono nella shell di navigazione unificata di Experience Cloud
* È stata rimossa la barra di suggerimento del feedback mobile per una bacheca campagna più pulita
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 14 luglio 2026**

* Rollout di domini e mittenti, avanzamento del flusso di lavoro in tempo reale e insights reali sulla campagna
* La configurazione di Domini e mittenti è ora completamente disponibile e la scelta del mittente viene salvata automaticamente
* Scegli o aggiorna il mittente dell’e-mail della campagna direttamente dalle impostazioni della campagna
* La scheda Mittenti rimane visualizzabile anche prima della verifica di un dominio
* Le bozze delle e-mail aggiunte durante la conversazione ora vengono visualizzate in modo affidabile sulla bacheca della campagna
* Guida e feedback sono combinati in un popover semplificato
* L&#39;avvio di una nuova conversazione non mostra più i messaggi rimanenti dell&#39;ultima conversazione
* Le conversazioni a più turni non mostrano più i prompt obsoleti nel cassetto delle risposte
* Gli elenchi numerati nei messaggi di chat mantengono l’ordine corretto
* Ora il connettore HubSpot richiede una chiave di servizio corrispondente alla terminologia di HubSpot
* La tabella di amministrazione della versione di prova mostra un numero di utenti e non ritaglia più l’ultima riga
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 9 luglio 2026**

* Un banner di manutenzione e una finestra di dialogo ti avvisano prima del downtime pianificato
* Domains &amp; Senders dispone di una procedura guidata di configurazione per verificare i domini e aggiungere i mittenti
* Le campagne in bozza ora richiedono di completare la configurazione dell’e-mail e del canale prima dell’invio
* La convalida del dominio e del mittente rileva ulteriori problemi, inclusi casi edge di record DNS
* Il menu del profilo è stato spostato nella barra laterale per un accesso più rapido
* I documenti di Source PDF ora vengono visualizzati come una pillola sui dettagli del kit del brand
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 26 giugno 2026**

* Un nuovo dashboard di Insights mostra i KPI relativi alle prestazioni della campagna: invii, aperture, clic, mancati recapiti e altro ancora
* Le campagne mostrano un badge di stato live sulla bacheca in modo da poter visualizzare immediatamente gli invii attivi
* Nella bacheca delle campagne vengono visualizzati suggerimenti contestuali per guidarti nei passaggi successivi
* L’onboarding per i nuovi utenti utilizza i dati reali del brand per personalizzare l’esperienza di configurazione
* Il selettore del colore del marchio gestisce codici esadecimali abbreviati e si apre in una finestra a comparsa ordinata
* I parametri UTM e il limite per i messaggi sono ora configurabili da Impostazioni app
* I collegamenti della Guida consentono ora di aprire il contenuto più recente direttamente su Experience League
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 24 giugno 2026**

* Il lancio di una campagna ora innesca una celebrazione dei coriandoli
* Le campagne mostrano un badge di stato e la bacheca si blocca in sola lettura una volta avviata
* La panoramica del brand si adatta perfettamente allo schermo con prompt a stato vuoto e una migliore visualizzazione del logo
* La convalida mostra una finestra di dialogo chiara anche quando viene restituito un tipo di errore imprevisto
* I contenuti e-mail generati utilizzano l’obiettivo della campagna per ottenere risultati più rilevanti

## Giugno 2026 {#june-2026}

**Data di rilascio: 23 giugno 2026**

* Un passaggio di convalida verifica che la campagna sia pronta prima del lancio
* Scopri perché ogni variante e-mail è stata creata con una nuova logica di variante
* La vista del piano della campagna mostra una barra di avanzamento live milestone nel flusso delle attività in
* L’onboarding per i nuovi utenti utilizza i dati reali del brand per personalizzare l’esperienza di configurazione
* Il selettore del colore del marchio gestisce codici esadecimali abbreviati e si apre in una finestra a comparsa ordinata
* I parametri UTM e il limite per i messaggi sono ora configurabili da Impostazioni app
* I collegamenti della Guida consentono ora di aprire il contenuto più recente direttamente su Experience League
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 19 giugno 2026**

* Verifica la compatibilità del client e-mail per ogni elemento prima dell’invio
* Sfoglia e ripristina le versioni precedenti dell’e-mail con un nuovo pannello per la cronologia delle versioni
* Modifica i colori del brand con un selettore esadecimale e modifica in linea nella pagina del brand
* La libreria dei marchi carica automaticamente più marchi durante lo scorrimento
* Il menu del profilo è stato spostato nella barra laterale per un accesso più rapido
* I documenti di Source PDF ora vengono visualizzati come una pillola sui dettagli del kit del brand
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 12 giugno 2026**

* Sfoglia la guida e le guide del prodotto senza uscire dall’app
* I piani delle campagne vengono visualizzati sezione per sezione quando vengono generati
* Raccogli le conversazioni delle campagne dove hai interrotto in modo più affidabile
* Avvia campagne da una finestra di dialogo dedicata quando il piano è pronto per essere utilizzato
* L’onboarding utilizza una denominazione più chiara del prodotto e indicazioni per i prompt a casa
* La configurazione del connettore mostra i campi corretti per le connessioni API key e sign-in
* Le risposte alle chat fuori ambito suggeriscono cosa chiedere dopo con le richieste di un clic
* Le esportazioni di Campaign PDF mostrano icone, branding del prodotto e un’etichetta del marchio in modo affidabile
* Contatta un esperto e i flussi di aggiornamento caricano i dettagli della versione di prova in modo più affidabile
* I tag di stile per la scrittura si espandono per mostrare il testo completo e il collegamento alla pagina del brand
* Avvia un brand dallo stato della libreria vuota con categorie utili
* Effettua di nuovo l&#39;accesso senza problemi alla scadenza della sessione
* L’app ora risiede in coworker-campaigns.adobe.com con la stessa esperienza
* La registrazione di prova ti indirizza al passaggio successivo dopo aver creato il tuo account
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 11 giugno 2026**

* Le pagine che verranno presto mostreranno un segnaposto pulito senza elementi inutili di sfondo
* Le barre degli strumenti dell’editor e-mail hanno un aspetto simile al tema chiaro
* L’eliminazione di un’immagine e-mail annulla la selezione e la barra degli strumenti scompare
* Le importazioni del pubblico CSV non mostrano più un elenco duplicato nella scheda del pubblico
* L’elemento Chat nella barra laterale viene evidenziato quando si avvia una nuova chat
* L’intestazione dell’app ora mostra solo l’oggetto dell’e-mail (o &quot;Bozza&quot;) durante la modifica di un’e-mail, rimuovendo il prefisso numero &quot;E-mail N:&quot; per il titolo di un livello
* Il menu del profilo è stato spostato nella barra laterale per un accesso più rapido
* I documenti di Source PDF ora vengono visualizzati come una pillola sui dettagli del kit del brand
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 10 giugno 2026**

* L’app ora è Campagne collaboratrici con nomi aggiornati in tutto
* Un primo tour di onboarding ti guida attraverso la creazione di un brand demo
* Avvia campagne da una finestra di dialogo dedicata quando il piano è pronto per essere utilizzato
* Connettere HubSpot con una chiave API dal catalogo delle integrazioni
* Sfogliare le chat con un elenco di conversazioni riprogettato e stati vuoti più chiari
* Annullare e ripristinare le modifiche e-mail con scelte rapide da tastiera comuni
* Riprova a salvare quando l’editor e-mail riscontra un errore temporaneo
* Sostituire le immagini delle e-mail con dimensioni e dimensioni corrette per Adobe Express
* Carica elenchi di pubblico da CSV utilizzando una finestra di dialogo di importazione più chiara in chat
* I tag di stile per la scrittura si espandono per mostrare il testo completo e il collegamento alla pagina del brand
* Avvia un brand dallo stato della libreria vuota con categorie utili
* Effettua di nuovo l&#39;accesso senza problemi alla scadenza della sessione
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 9 giugno 2026**

* Confrontare le opzioni di aggiornamento e utilizzo della versione di valutazione in una finestra di dialogo del piano riprogettata
* Sfogliare e gestire i connettori dati da un catalogo live nell’app
* Compila le impostazioni generali e le preferenze di notifica in Impostazioni
* Al termine della sessione, l&#39;accesso rimane sempre aggiornato con un messaggio chiaro
* L’indirizzo e-mail viene visualizzato automaticamente durante l’invio di un’e-mail di test
* Conferma prima di creare un kit del marchio come predefinito
* I caricamenti di Brand Kit rispettano ora un limite di 100 MB per le dimensioni dei file
* Modifica il nome della campagna direttamente sulla bacheca della campagna
* Anteprima dei modelli e conferma prima di inviare una campagna
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 4 giugno 2026**

* Le chat recenti vengono visualizzate nella barra laterale e puoi rinominarle in linea
* Apri la pagina Chat per cercare e continuare le conversazioni passate
* I flussi di lavoro domestici sono ora modelli di campagna con un flusso di remix più semplice
* I modelli di libreria utilizzano una tabella più chiara con descrizioni e filtri di canale
* I kit marchio mostrano per primi il tuo predefinito e filtrano per pubblicato o bozza
* Dopo aver pubblicato una bozza di marchio, il kit del marchio live viene inviato automaticamente
* I dati di campagne e marchi vengono caricati in modo più affidabile subito dopo l’accesso
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

## Maggio 2026 {#may-2026}

**Data di rilascio: 29 maggio 2026**

* Genera varianti di immagine e scegli le tue immagini direttamente nell’editor e-mail
* Aggiungere immagini dal computer mediante un selettore di file locale nella barra degli strumenti delle immagini
* Descrivi ciò che desideri e lascia che AI generi l’immagine perfetta per la tua e-mail
* Esportare l&#39;e-mail completata come file HTML dal menu Altro
* I suggerimenti di Smart Copy vengono ora visualizzati nella barra degli strumenti e-mail durante la modifica del testo
* Fai clic su un marchio nella bacheca della campagna per visualizzarne immediatamente i dettagli
* Imposta il kit del marchio predefinito direttamente dalla libreria
* Le e-mail nell’editor ora seguono la sequenza del flusso di lavoro per un ordine più chiaro
* Gli allegati della schermata iniziale ora sono limitati ai PDF per un’elaborazione affidabile
* La navigazione da tastiera, il supporto per la lettura dello schermo e le preferenze di movimento sono più coerenti in tutta l’app
* Le etichette in arrivo contrassegnano le pagine che vengono create attivamente
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 21 maggio 2026**

* Modificare le immagini delle e-mail con Adobe Express senza uscire dall’editor
* Creazione di marchi con un chiaro avanzamento durante l’estrazione e la pubblicazione delle risorse
* Gestire domini e mittenti dalla sezione Persone
* Sfogliare e gestire gli elenchi di contatti dalla sezione Persone
* Cambiare modelli di risorse quando si lavora con le risorse di marketing
* Scaricare i piani di Campaign come file Word con diagrammi di flusso di lavoro
* Gli elenchi di campagne, competenze e flussi di lavoro condividono un layout più chiaro
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 14 maggio 2026**

* La libreria riunisce Assets, modelli e marchi in un’unica posizione
* La barra laterale e la navigazione facilitano l’accesso al pubblico e al kit di marchi predefinito
* Scarica il piano della campagna come PDF direttamente dai dettagli della campagna
* La modifica del brand apre pannelli più chiari per la panoramica, lo stile di scrittura e i colori
* Il conto alla rovescia della versione di prova viene visualizzato nell’intestazione in modo che i giorni rimanenti rimangano visibili
* I flussi di lavoro per il marketing sportivo sono pronti quando il tuo breve articolo rientra in quella categoria
* La configurazione di prova manuale gestisce gli indirizzi del sito web dell’azienda in modo più prevedibile
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 8 maggio 2026**

* La chat di Campaign offre un nuovo tentativo chiaro quando un controllo delle attività in background non riesce
* Gli aggiornamenti di stato delle attività e il layout a schermo intero sono più semplici nelle bacheche delle campagne
* L’app inizia più rapidamente caricando percorsi e traduzioni in base alle tue esigenze
* I dati di campagne e marchi rimangono coerenti in tutta l’app
* Le modifiche e-mail di annullamento e ripristino funzionano in modo più prevedibile
* Riprova a salvare quando l’editor e-mail riscontra un errore temporaneo
* Sostituire le immagini delle e-mail con dimensioni e dimensioni corrette per Adobe Express
* Carica elenchi di pubblico da CSV utilizzando una finestra di dialogo di importazione più chiara
* I tag di stile per la scrittura si espandono per mostrare il testo completo e il collegamento alla pagina del brand
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 6 maggio 2026**

* Le bacheche e gli elenchi di Campaign mantengono l’allineamento con i dettagli più recenti mentre lavori
* Nella chat della campagna e in Agent Builder viene visualizzata una dichiarazione generativa di non responsabilità per l’intelligenza artificiale
* I dettagli di contatto del supporto ora utilizzano l’indirizzo e-mail dedicato alle campagne CX Coworker
* La pagina Home di marketing rimuove la sezione della lista d’attesa e mostra più chiaramente il video principale
* Più schermate rispettano automaticamente la lingua e i formati di data locali
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

## Aprile 2026 {#apr-2026}

**Data di rilascio: 28 aprile 2026**

* Gli elenchi e le bacheche di Campaign rimangono sincronizzati e risultano più agili quando apri o aggiorni una campagna
* I flussi di lavoro domestici sono ora modelli di campagna con un flusso di remix più semplice
* I temi scuri e chiari utilizzano uno stile Spectrum aggiornato per ottenere un aspetto più coerente nell’app
* La chat gestisce il contenuto dell’assistente vuoto in modo graduale, con animazioni di stato più fluide e animazioni di stato più chiare
* Le conversazioni ripristinate si aprono senza un flash della barra di chat vuoto e il passaggio tra diverse varianti di e-mail non provoca più lo sfarfallio della barra
* I controlli di caricamento dei file si interrompono dopo l&#39;invio o la continuazione della conversazione
* &quot;Help me write&quot; recupera le idee pronte solo dopo aver aperto il popover
* Gli aggiornamenti di stato mostrano un controllo di espansione solo quando è presente un elenco da visualizzare
* Le schede tra campagne, competenze e flussi di lavoro condividono un layout più coerente
* Gli elenchi delle campagne e i dati del brand vengono caricati in modo più affidabile subito dopo l’accesso
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 19 aprile 2026**

* L’intestazione dell’app ora mostra solo l’oggetto dell’e-mail (o &quot;Bozza&quot;) durante la modifica di un’e-mail, rimuovendo il prefisso numero &quot;E-mail N:&quot; per il titolo di un livello
* Il menu del profilo è stato spostato nella barra laterale per un accesso più rapido
* I documenti di Source PDF ora vengono visualizzati come una pillola sui dettagli del kit del brand
* Il menu del profilo è stato spostato nella barra laterale per un accesso più rapido
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il

**Data di rilascio: 18 aprile 2026**

* L’input della campagna della pagina principale ora dispone di un anello luminoso animato e un gradiente hero più alto e luminoso
* &quot;Surprise me&quot; attiva una sfumatura colorata sul bordo di input
* L’app ora supporta un layout più coerente tra le pagine dei prodotti
* I collegamenti alla documentazione ora aprono il contenuto più recente direttamente in una nuova scheda
* Vari miglioramenti a livello di prestazioni e affidabilità in tutto il
