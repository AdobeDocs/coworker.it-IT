---
source-git-commit: e5bf2a0a2ee55513b32442f70d01dc5825ac9d6a
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 5%
---
# Documentazione di CX Enterprise Coworker

Source per il set di documentazione di Adobe CX Enterprise Coworker.

## Configurazione di pubblicazione

Utilizzare i flussi di lavoro di convalida e mirroring dell&#39;articolo condiviso in `.github/workflows/`.
Il flusso di lavoro di convalida viene eseguito per le richieste pull e invia messaggi push a `main`.
Il flusso di lavoro di mirroring viene eseguito quando si esegue il push a `main`.

Utilizza `markdownlint_custom.json` per le sostituzioni della regola Markdown e `linkcheckexclude.json`, ad esempio le esclusioni URL.
Il file `pipeline.opts` segue la configurazione di verifica dei collegamenti in `cx-enterprise-ai.en`.
Aggiungi reindirizzamenti URL a `redirects.csv` utilizzando le colonne `source,dest`.
