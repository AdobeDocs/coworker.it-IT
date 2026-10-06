---
description: descrizione.
title: Comprendere l’editor e-mail
product_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
source-git-commit: 94cf399a48d13ee83c702804b50fdccd4baa9d71
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%
---
# Comprendere l’editor e-mail {#email-editor}

L’editor e-mail consente di perfezionare un’e-mail generata dall’intelligenza artificiale direttamente sulla bacheca della campagna. Modifica l’oggetto e il preheader, formatta il testo e le immagini in linea o sostituiscili in un altro modello.

Selezionando una scheda e-mail nella bacheca della campagna, si apre l’editor e-mail come pannello laterale. Da lì, l’utente può modificare l’oggetto e il preheader (con alternative suggerite dall’intelligenza artificiale), fare clic nel corpo dell’e-mail per selezionare e formattare testo o immagini, passare da una variante generata dall’intelligenza artificiale a un’altra, scambiare il modello HTML, verificare la compatibilità e-mail con il client e inviare un messaggio e-mail di test alla propria casella in entrata. Le modifiche vengono salvate automaticamente e le versioni precedenti possono essere riviste e ripristinate.

## Come accedere

1. Apri la campagna desiderata e fai clic su Apri editor nella scheda e-mail.

SCHERMATA

1. Modifica direttamente i campi **Oggetto** e **Preintestazione** oppure fai clic su **Suggerimenti avanzati** accanto a per le alternative generate da IA.
1. Fai clic sul corpo dell’e-mail per selezionare un blocco di testo o un’immagine, quindi utilizza la barra degli strumenti mobile che viene visualizzata per formattare il testo o gestire l’immagine.
1. Utilizza **Cambia modello HTML** per sostituire il corpo dell&#39;e-mail con un altro modello.
1. Utilizza **Invia e-mail di test**, immetti un indirizzo del destinatario e fai clic su **Invia** per inviare un&#39;anteprima live a tale indirizzo tramite e-mail.
1. Utilizza l’icona della cronologia delle versioni per visualizzare in anteprima e ripristinare una versione salvata in precedenza.
1. Le modifiche vengono salvate automaticamente: non è richiesto alcun passaggio di salvataggio manuale.

### Comportamenti chiave

- I caricamenti di immagini sono limitati a 10 MB; le immagini superiori a circa 3 MB vengono compresse automaticamente, con una nota sulla qualità che consiglia immagini inferiori a 3 MB.
- I campi Oggetto e Preheader hanno l’opzione per un’alternativa generata dall’intelligenza artificiale tramite questa ICONA.
- Usa Ctrl+z (CMD+z per Mac) per annullare e annullare l’ultima azione. Utilizzare CTRL+Y (CMD+y per Mac) per &quot;Ripetere&quot; e invertire l&#39;ultima operazione di annullamento. KEITH CHECK STANDARD
- Le versioni salvate in precedenza possono essere visualizzate in anteprima e ripristinate da un pannello della cronologia delle versioni tramite questa ICONA.
- Per impostazione predefinita, vengono generate due varianti per e-mail; puoi selezionare la variante desiderata tramite le relative miniature a destra.

## Funzionalità non disponibili in questa funzionalità

- Non si tratta di un generatore di blocchi drag-and-drop, non esiste una libreria di blocchi e i blocchi di contenuto non possono essere aggiunti, rimossi o riordinati; la modifica avviene direttamente sul HTML e-mail esistente.
- Attualmente non supporta l’inserimento di tag di personalizzazione/unione.
- Non fornisce un campo di testo alternativo per le immagini.
- Non applica un oggetto, un preheader o altri controlli a livello di contenuto prima che un’e-mail venga considerata &quot;pronta&quot;; gli unici controlli pre-lancio sono a livello di campagna (configurazione dell’invio, e-mail di test inviata, un pubblico reale), non i controlli sul contenuto dell’e-mail stesso.
- L’attivazione dell’anteprima desktop/mobile non è disponibile nella visualizzazione standard di modifica delle e-mail per campagne. [È NECESSARIO INPUT per confermare l&#39;ambito]
- [INPUT NECESSARIO — per confermare con il tecnico: se l&#39;editor diventa di sola lettura (non solo il campo del mittente) dopo l&#39;attivazione/l&#39;avvio di una campagna.]
