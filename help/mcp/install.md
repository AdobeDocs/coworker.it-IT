---
title: Installare Adobe CX Coworker Gateway
description: Scopri come collegare i client compatibili con MCP a Adobe CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%
---
# Installare Adobe CX Coworker Gateway {#mcp-install}

Leggere questa guida per scoprire come collegare un client compatibile con MCP a Adobe CX Coworker Gateway.  CX Coworker Gateway utilizza un endpoint per tutti gli strumenti di prodotto documentati:

```
https://cx-coworker-gateway.adobe.io/mcp
```

Prima di eseguire l’installazione, verifica che l’organizzazione e l’account utente possano accedere agli strumenti di prodotto necessari. Consulta [Accedere agli strumenti di CX Coworker Gateway](access.md).

## Come funziona l’installazione {#mcp-install-how}

CX Coworker Gateway utilizza un trasporto HTTP remoto con un flusso di accesso Adobe basato su browser. In ogni client supportato, il modello di configurazione è lo stesso:

1. Aggiungere l&#39;URL dell&#39;endpoint: `https://cx-coworker-gateway.adobe.io/mcp`.
2. Salva o abilita la connessione.
3. Completa l’accesso Adobe basato su browser la prima volta che il client richiama uno strumento.
4. Se necessario, imposta il contesto del prodotto per la sessione: organizzazione per tutti i prodotti, sandbox per gli strumenti basati su Experience Platform e visualizzazione dati per Customer Journey Analytics. Vedi [Contesto del prodotto per le chiamate allo strumento](#mcp-connect-params).

>[!NOTE]
>
>Nella configurazione del client MCP non sono necessari chiavi API, token bearer, segreti client o intestazioni aggiuntive. L’autenticazione viene gestita tramite il flusso di accesso di Adobe al primo utilizzo.

## Installazione Enterprise (gestita dall&#39;amministratore) {#mcp-install-enterprise}

La maggior parte dei piani client MCP del team e dell&#39;organizzazione richiede che un amministratore aggiunga connettori personalizzati per l&#39;organizzazione. In questi ambienti, l’installazione prevede due passaggi:

1. Un amministratore aggiunge l&#39;endpoint del gateway di CX Coworker una volta per l&#39;organizzazione.
2. Ogni utente abilita il connettore e accede con le proprie credenziali Adobe.

### Passaggio 1: un amministratore aggiunge l’endpoint {#mcp-install-enterprise-admin}

L&#39;amministratore aggiunge `https://cx-coworker-gateway.adobe.io/mcp` come connettore personalizzato o server MCP remoto nelle impostazioni dell&#39;organizzazione del client. La posizione esatta dipende dal client.

#### Claude Team ed Enterprise {#mcp-install-enterprise-claude}

Nei piani Team ed Enterprise di [!DNL Claude], i connettori a livello di organizzazione sono gestiti da un&#39;area di lavoro **Proprietario** o **Proprietario principale**.

1. Accedi a [!DNL Claude] come **Proprietario** o **Proprietario primario**.
2. Vai a **Impostazioni** > **Amministrazione** > **Connettori**. In alcuni piani, viene visualizzato come **Impostazioni organizzazione** > **Connettori**.
3. Selezionare **Aggiungi connettore personalizzato**.
4. Immettere `https://cx-coworker-gateway.adobe.io/mcp` come URL del server e utilizzare un nome riconoscibile, ad esempio &quot;Adobe for CX Coworker Gateway&quot;.
5. Salva il connettore.

#### Team e organizzazione ChatGPT {#mcp-install-enterprise-chatgpt}

Nelle aree di lavoro Team ed Enterprise di [!DNL ChatGPT], i connettori vengono aggiunti da un amministratore dell&#39;area di lavoro.

1. Accedere a [!DNL ChatGPT] come amministratore dell&#39;area di lavoro.
2. Vai a **Impostazioni** > **Connettori**. In alcuni piani, viene visualizzato come **Impostazioni** > **App e connettori**.
3. Seleziona **Aggiungi connettore**.
4. Immetti `https://cx-coworker-gateway.adobe.io/mcp` come URL del server.
5. Salva il connettore. A seconda della configurazione dell’area di lavoro, questo passaggio potrebbe richiedere l’abilitazione della modalità sviluppatore o la concessione dell’approvazione a livello di area di lavoro.

#### Altri client gestiti dall&#39;organizzazione {#mcp-install-enterprise-other}

Per altri client che supportano connettori remoti gestiti dall&#39;organizzazione, aggiungere CX Coworker Gateway come server MCP HTTP remoto utilizzando `https://cx-coworker-gateway.adobe.io/mcp`. Lascia vuote le intestazioni facoltative, i campi del token Bearer, i campi dell’ID client e i campi del segreto client, a meno che il client non richieda un valore segnaposto.

### Passaggio 2: gli utenti abilitano il connettore {#mcp-install-enterprise-user}

Dopo che un amministratore ha aggiunto CX Coworker Gateway, ogni utente lo abilita per il proprio account:

1. Apri le impostazioni del connettore personale, dell’app o MCP nel client.
2. Individuare il connettore CX Coworker Gateway e abilitarlo.
3. Avvia una conversazione, richiama uno degli strumenti Adobe e, quando richiesto, completa l’accesso Adobe basato su browser.
4. Se necessario, imposta il contesto del prodotto per la sessione: organizzazione per tutti i prodotti, sandbox per gli strumenti basati su Experience Platform e visualizzazione dati per Customer Journey Analytics. Vedi [Contesto del prodotto per le chiamate allo strumento](#mcp-connect-params).

Gli utenti non devono immettere l’URL personalmente quando un amministratore ha già aggiunto il connettore per l’organizzazione.

## Installazione singola (self-service) {#mcp-install-individual}

Se utilizzi un piano individuale, un client sviluppatore configurato localmente o un’organizzazione che consente ai membri di aggiungere i propri connettori, aggiungi l’endpoint direttamente nelle impostazioni client.

### Claude individual {#mcp-install-individual-claude}

Per il desktop `claude.ai` e [!DNL Claude] su un piano individuale:

1. Apri **Impostazioni** > **Connettori**.
2. Selezionare **Aggiungi connettore personalizzato**.
3. Immetti `https://cx-coworker-gateway.adobe.io/mcp` come URL del server.
4. Salva e abilita il connettore, quindi completa il flusso di accesso di Adobe al primo utilizzo.

### Individuo ChatGPT {#mcp-install-individual-chatgpt}

1. Apri **Impostazioni** > **Connettori**. In alcuni piani, viene visualizzato come **Impostazioni** > **App e connettori**.
2. Seleziona **Aggiungi connettore**.
3. Immetti `https://cx-coworker-gateway.adobe.io/mcp` come URL del server.
4. Salva e abilita il connettore, quindi completa il flusso di accesso di Adobe al primo utilizzo.

### Cursore {#mcp-install-individual-cursor}

1. Apri **Impostazioni** > **MCP**.
2. Selezionare **Aggiungi nuovo server**.
3. Immetti `https://cx-coworker-gateway.adobe.io/mcp` come URL del server.
4. Seleziona **Connetti** e completa il flusso di accesso di Adobe.

Dopo la connessione, gli strumenti Adobe per gateway CX Coworker sono disponibili nelle modalità Compositore cursore e Agente.

### Claude Code {#mcp-install-individual-claude-code}

Aggiungi l’endpoint dal terminale:

```bash
claude mcp add --transport http cx-enterprise https://cx-coworker-gateway.adobe.io/mcp
```

Quindi avviare [!DNL Claude Code] ed eseguire:

```text
/mcp
```

Seleziona il server `cx-enterprise` e completa il flusso di accesso di Adobe nel browser.

### Codice {#mcp-install-individual-codex}

Aggiungi l’endpoint dal terminale:

```bash
codex mcp add cx-enterprise --url https://cx-coworker-gateway.adobe.io/mcp
```

Autentica:

```bash
codex mcp login cx-enterprise
```

Verifica la configurazione:

```bash
codex mcp list
```

È inoltre possibile aggiungere l&#39;endpoint direttamente a `~/.codex/config.toml`:

```toml
[mcp_servers.cx-enterprise]
url = "https://cx-coworker-gateway.adobe.io/mcp"
```

### Configurazione JSON generale {#mcp-install-individual-json}

Per i client che accettano una configurazione del server MCP basata su JSON, utilizza uno dei seguenti formati a seconda che il client supporti HTTP remoto nativo o richieda un bridge locale.

**Tramite `mcp-remote` ponte**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://cx-coworker-gateway.adobe.io/mcp"
      ]
    }
  }
}
```

**HTTP remoto nativo**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "url": "https://cx-coworker-gateway.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

### Altri clienti {#mcp-install-individual-other}

Per altri client desktop o Web con supporto MCP remoto, aggiungere Adobe for CX Coworker Gateway come server HTTP remoto utilizzando `https://cx-coworker-gateway.adobe.io/mcp`. Lascia vuote le intestazioni facoltative, i campi del token Bearer, i campi dell’ID client e i campi del segreto client, a meno che il client non richieda un valore segnaposto.

## Contesto del prodotto per le chiamate allo strumento {#mcp-connect-params}

MCP rivolge ogni chiamata allo strumento a un’organizzazione Adobe attiva. Inoltre, i requisiti di contesto dipendono dal prodotto:

- **Prodotti basati su Experience Platform**: gli strumenti Real-Time CDP, Experience Platform e Journey Optimizer funzionano all&#39;interno di una sandbox Experience Platform. Imposta la sandbox una volta per sessione; tutte e tre le condividono.
- **Altri prodotti** — I prodotti non generati su Experience Platform non utilizzano il contesto sandbox. Gli strumenti di Adobe Analytics, Customer Journey Analytics, Workfront, Marketo e Target vengono risolti in base alle proprie risorse di prodotto, ad esempio le visualizzazioni dati per Customer Journey Analytics e le suite di rapporti per Adobe Analytics.

Imposta il contesto una sola volta all’inizio di una sessione: i singoli strumenti di prodotto non cambiano organizzazioni, sandbox o visualizzazioni dati a metà sessione. Consulta [Strumenti di contesto sessione](context-tools.md) per gli strumenti che impostano il contesto dell&#39;organizzazione, della sandbox e della visualizzazione dati.

Esempio:

> &quot;Utilizzare l&#39;organizzazione `1234ABCD@AdobeOrg`, la sandbox `prod` e la visualizzazione dati `My Company — Global` per questa sessione.&quot;

Se non conosci i valori richiesti, chiedi al client MCP di elencare le organizzazioni, le sandbox o le visualizzazioni dati disponibili per le tue credenziali Adobe.