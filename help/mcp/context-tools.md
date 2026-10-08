---
title: Strumenti contestuali di sessione in CX Coworker Gateway
description: Scopri gli strumenti di base che consentono di impostare il contesto dell’organizzazione, della sandbox e della visualizzazione dati per tutte le chiamate allo strumento CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%
---
# Strumenti contestuali di sessione in Adobe CX Coworker Gateway {#mcp-core}

Adobe CX Coworker Gateway include un set di strumenti contestuali di sessione che stabiliscono l’organizzazione Adobe, la sandbox di Adobe Experience Platform e la visualizzazione dati di Customer Journey Analytics in cui operano tutti gli altri strumenti di prodotto. Non è richiesta alcuna licenza o abilitazione aggiuntiva. Questi strumenti sono disponibili per ogni utente autenticato dopo la connessione al [server gateway di CX Coworker](overview.md).

## Funzionamento del contesto {#mcp-core-how}

CX Coworker Gateway effettua ogni chiamata allo strumento in un’organizzazione Adobe attiva. Inoltre, i requisiti di contesto dipendono dal prodotto:

- **I prodotti basati su Experience Platform** — [Gli strumenti Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) e [Journey Optimizer](ajo-mcp.md) funzionano all&#39;interno di una sandbox Experience Platform. Imposta la sandbox una volta per sessione con `core-set_sandbox`; tutte e tre le condividono.
- **Altri prodotti** — I prodotti non generati su Experience Platform non utilizzano il contesto sandbox. Ad esempio, gli strumenti [Customer Journey Analytics](cja-mcp.md) vengono risolti in una visualizzazione dati e gli strumenti [Adobe Analytics](analytics-mcp.md) in suite di rapporti.

Imposta il contesto una sola volta all’inizio di una sessione: i singoli strumenti di prodotto non cambiano organizzazioni, sandbox o visualizzazioni dati a metà sessione.

## Strumenti disponibili {#mcp-core-tools}

| Strumento | Descrizione |
| --- | --- |
| `core-list_orgs` | Elenca le organizzazioni Adobe accessibili all’utente autenticato. Restituisce il nome visualizzato e l&#39;identificatore `@AdobeOrg` di ogni organizzazione. Usare questa opzione per cercare l&#39;ID organizzazione prima di chiamare `core-switch_org`. |
| `core-switch_org` | Imposta l’organizzazione Adobe attiva per la sessione. Tutte le successive chiamate dello strumento vengono indirizzate a questa organizzazione fino al termine della sessione o al cambio di organizzazione. |
| `core-list_sandboxes` | Elenca le sandbox di Experience Platform disponibili nell’organizzazione attiva. Restituisce il nome, il titolo, il tipo (produzione o sviluppo) e lo stato di ogni sandbox. Utilizzare questa opzione per cercare il nome di una sandbox prima di chiamare `core-set_sandbox`. |
| `core-set_sandbox` | Imposta la sandbox di Experience Platform attiva per la sessione. Gli strumenti Real-Time CDP, Experience Platform e Journey Optimizer applicano la valutazione dei propri dati a questa sandbox. |
| `core-list_dataviews` | Elenca le visualizzazioni dati di Customer Journey Analytics disponibili per l’utente autenticato nel contesto corrente. Restituisce gli ID delle visualizzazioni dati e i nomi visualizzati. Utilizzare questa opzione per cercare una visualizzazione dati prima di chiamare `core-set_dataview`. |
| `core-set_dataview` | Imposta la visualizzazione dati predefinita di Customer Journey Analytics per la sessione. Con questa impostazione, gli strumenti di CJA che richiedono una visualizzazione dati, ad esempio `findDimensions`, `findMetrics` e `runReport`, utilizzano questo valore automaticamente a meno che non venga specificata una visualizzazione dati diversa nella singola chiamata dello strumento. |

## Configurazione di sessione tipica {#mcp-core-setup}

Imposta il contesto all’inizio di una sessione prima di richiamare gli strumenti del prodotto:

1. **Organizzazione** — Chiama `core-list_orgs` per elencare le organizzazioni accessibili, quindi `core-switch_org` con l&#39;ID organizzazione di destinazione.
2. **Sandbox**: se prevedi di utilizzare gli strumenti Real-Time CDP, Experience Platform o Journey Optimizer, chiama `core-list_sandboxes` per elencare le sandbox disponibili, quindi `core-set_sandbox` con il nome della sandbox di destinazione.
3. **Visualizzazione dati** (solo CJA) - Se prevedi di utilizzare gli strumenti di Customer Journey Analytics, chiama `core-list_dataviews` per elencare le visualizzazioni dati disponibili, quindi `core-set_dataview` con la visualizzazione dati scelta.

Puoi chiedere al tuo client MCP di completare questa configurazione in un’unica richiesta in lingua naturale:

> &quot;Utilizzare l&#39;organizzazione `1234ABCD@AdobeOrg`, la sandbox `prod` e la visualizzazione dati `My Company — Global` per questa sessione.&quot;

Il client chiamerà gli strumenti appropriati e confermerà una volta impostato il contesto.

>[!TIP]
>
>Se le credenziali Adobe appartengono a una sola organizzazione, `core-list_orgs` e `core-switch_org` funzionano ancora, ma l&#39;organizzazione effettiva sarà la stessa indipendentemente. È comunque necessario chiamare `core-set_sandbox` se si intende utilizzare gli strumenti Real-Time CDP, Experience Platform o Journey Optimizer e `core-set_dataview` se si intende utilizzare gli strumenti Customer Journey Analytics.

## Esempi di prompt {#mcp-core-examples}

| Obiettivo | Esempio di prompt |
| --- | --- |
| Scopri le organizzazioni disponibili | &quot;A quali organizzazioni Adobe ho accesso?&quot; |
| Imposta contesto organizzazione | &quot;Passare all&#39;organizzazione `My Org (1234ABCD@AdobeOrg)`.&quot; |
| Scopri le sandbox disponibili | &quot;Elencare le sandbox disponibili nella mia organizzazione corrente.&quot; |
| Imposta contesto sandbox | &quot;Usa la sandbox `prod` per questa sessione.&quot; |
| Scopri le visualizzazioni dati disponibili | &quot;A quali visualizzazioni dati di Customer Journey Analytics posso accedere?&quot; |
| Impostare il contesto della visualizzazione dati | &quot;Imposta `My Company — Global` come visualizzazione dati predefinita.&quot; |
| Configurazione completa della sessione | &quot;Configurare una sessione utilizzando l&#39;organizzazione `1234ABCD@AdobeOrg`, la sandbox `prod` e la visualizzazione dati `My Company — Global`.&quot; |

## Pagine correlate {#mcp-core-related}

- [Installare Adobe CX Coworker Gateway](install.md): come collegare il client MCP, inclusa la sezione di installazione del contesto di prodotto.
- [Accedere agli strumenti di CX Coworker Gateway](access.md) — requisiti di accesso per prodotto.