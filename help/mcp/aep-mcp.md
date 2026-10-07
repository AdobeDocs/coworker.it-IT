---
title: Strumenti Experience Platform in CX Coworker Gateway
description: Scopri quali strumenti Adobe Experience Platform sono disponibili tramite CX Coworker Gateway.
hide: true
source-git-commit: 6c126810936bea3e883d74e6ff685991cb40cd4a
workflow-type: tm+mt
source-wordcount: '1947'
ht-degree: 6%
---

# Strumenti Adobe Experience Platform in Adobe CX Coworker Gateway {#aep-mcp}

È possibile utilizzare gli strumenti del prodotto Adobe Experience Platform per verificare schemi, set di dati, configurazioni di governance dei dati, risorse del servizio query ed eventi di audit da un client compatibile con MCP. Questi strumenti sono disponibili tramite [Adobe CX Coworker Gateway](overview.md) quando l&#39;organizzazione è abilitata e l&#39;account utente dispone delle autorizzazioni Experience Platform necessarie.

>[!AVAILABILITY]
>
>Lo strumento del prodotto Experience Platform si trova in Beta. L’accesso avviene solo su invito e richiede l’abilitazione dell’organizzazione Adobe. Consulta [Accedere agli strumenti di CX Coworker Gateway](access.md).

## Riepilogo

| Strumento | Descrizione | Risorsa | Funzionalità | Stato |
| --- | --- | --- | --- | --- |
| `search_allowed_ip_ranges` | Recuperare le restrizioni di accesso IP di Query Service | Autenticazione Data Distiller · Intervalli IP | list | Attivo |
| `search_audit` | Elencare gli eventi di controllo delle attività degli utenti in Experience Platform | Query di audit · eventi di audit | elenco, filtro per tipo di risorsa, azione, stato, intervallo di tempo | Attivo |
| `search_datasets` | Query di metadati di acquisizione batch e set di dati | API catalogo · set di dati, batch | list, get, filter, list last, list files (elenco, ottieni, filtro, ultimo elenco, file elenco) | Attivo |
| `search_class_relations` | Cerca relazioni di classe aziendale in Experience Platform | Relazioni di classe · Indice YAML statico | ricerca per token, multi-termine, corrispondenza parziale | Attivo |
| `search_data_access` | Elenca i file dai batch di acquisizione non riusciti | API di accesso ai dati · batch non riusciti | elencare i file non riusciti | Attivo |
| `search_data_lake` | Ispezionare i metadati del set di dati e lo stato del batch | API Data Lake · set di dati, batch | get, get size, list failed batch | Attivo |
| `search_dule` | Etichette, criteri e azioni di governance dei dati delle query | Governance dei dati · etichette, criteri, azioni_marketing | list, get, list enabled, evaluate | Attivo |
| `search_query_service` | Query di query SQL, modelli, pianificazioni e avvisi | Query Service · query, modelli, pianificazioni, avvisi | list, get, filter, get connection params | Attivo |
| `search_sandbox_health_assessment` | Recuperare i risultati più recenti della valutazione dello stato di esecuzione e funzionamento per la sandbox corrente | Esecuzione e funzionamento · valutazioni di verifica stato | list, ottieni per nome assegno | Attivo |
| `search_schema_registry` | Query di schemi, gruppi di campi, classi e tipi XDM | Registro schema · schemi, gruppi di campi, classi, data_types, descrittori | list, get, filter by container | Attivo |
| `execute_observability_metrics_query` | Query delle metriche [!DNL Observability Insights] per la sandbox corrente o per tutte le sandbox | Observability Insights · metriche | query di serie temporali e di aggregazione, richieste con più metriche, filtri di tag, groupBy/exclude, per-metric downsampling | Attivo |
| `inspect_observability_breaches` | Rileva [!DNL Observability Insights] intervalli di violazione quando una metrica supera la linea di base configurata | Informazioni sull’osservabilità · violazioni | elenco degli intervalli di violazione per serie, organizzazione e ambito sandbox | Attivo |

## Riferimento dello strumento

### search_allowed_ip_ranges

**Risorsa:** Autenticazione Distiller dati · Intervalli IP
**Stato:** Attivo

Recupera tutte le restrizioni di accesso IP configurate per Query Service nella sandbox corrente. Restituisce l’ID organizzazione e l’elenco degli intervalli IP consentiti. Disponibile solo per i clienti con il componente aggiuntivo Data Distiller.

**Funzionalità:** elenca gli intervalli IP consentiti per Query Service

Nessun parametro.

### search_audit

**Risorsa:** query di controllo · eventi di controllo
**Stato:** Attivo

Elenca i record con marca temporale delle attività degli utenti nei servizi Experience Platform. Restituisce il tipo di azione, l’e-mail utente, le informazioni sulla risorsa e lo stato dell’evento. Utilizzare `asset_type` e `action` per limitare i risultati. Viene impostato automaticamente sugli ultimi 7 giorni in cui non è specificato alcun intervallo di tempo. Limitato agli ultimi 1000 record ed eventi degli ultimi 90 giorni.

**Funzionalità:** elenca eventi di controllo, filtra per tipo di risorsa, azione, stato, intervallo di tempo, impagina

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `action` | No | Filtra per tipo di azione. Valori comuni (separati da virgola per OR): `Create`, `Delete`, `Update`, `Enable`, `Disable` |
| `asset_type` | No | Filtra per tipo di risorsa. Deve essere uno dei seguenti valori: `Dataset`, `Schema`, `Segment`, `Destination`, `Source Data Flow`, `Merge Policy`, `Identity Namespace`, `Identity Graph`, `Sandbox`, `Role`, `Query`, `Scheduled Query`, `Datastream`, `Computed Attribute`, `Field Group`, `Class`, `Data Types`, `Account`, `Product Profile`, `Query Template`, `Work Order`, `Audit Logs`, `Access Control Policy` |
| `status` | No | Filtra per stato evento. Valori: `Success`, `Failure`, `Allow`, `Deny`. Separa da virgole per OR |
| `start_time` | No | Primo timestamp. ISO 8601 UTC con ms, esempio: `2024-01-15T00:00:00.000Z` |
| `end_time` | No | Timestamp più recente. ISO 8601 UTC con ms |
| `property_filter` | No | Espressione filtro non elaborato, ad esempio `action==create`. Preferisci i parametri dedicati qui sopra |
| `orderby` | No | Ordinamento: `timestamp` (asc) o `-timestamp` (desc) |
| `limit` | No | Numero massimo di risultati (3-1000, valore predefinito 50) |
| `start` | No | Offset paginazione. Incrementa per valore limite per ogni pagina |
| `query_id` | No | ID query da una risposta precedente per ripetere la stessa query |

### search_datasets

**Risorsa:** API catalogo · set di dati, batch
**Stato:** Attivo

Strumento di invio unificato per Experience Platform Catalog Service. Eseguire query sui metadati del set di dati (riferimenti schema, tag, informazioni sulla creazione) o sui record di acquisizione batch (stato, metriche, elenchi di file). Utilizzare `dataset/list` per individuare i set di dati, `batch/list` per verificare l&#39;integrità dell&#39;acquisizione e `batch/list_files` o `batch/get_meta_files` per controllare specifici contenuti batch. Tutte le operazioni sono di sola lettura.

**Funzionalità:** elencare set di dati, ottenere set di dati, elencare batch, ottenere batch, elencare ultimo batch per set di dati, elencare file batch, ottenere file metadati batch (errori di riga, file di input)

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `entity_type` | Sì | `dataset` o `batch` |
| `operation` | Sì | `list`, `get`, `list_last`, `list_files`, `get_meta_files`. Combo validi: dataset → list, get; batch → tutti e cinque |
| `resource_id` | No | ID set di dati o batch. Richiesto per `dataset/get`, `batch/get`, `batch/list_files`, `batch/get_meta_files` |
| `query_params.limit` | No | Risultati massimi per pagina (massimo 100). Si applica a tutte le operazioni di elenco |
| `query_params.start` | No | Offset paginazione. Si applica a tutte le operazioni di elenco |
| `query_params.order_by` | No | Direzione di ordinamento, ad esempio `asc:created,updated`. Si applica a tutte le operazioni di elenco |
| `query_params.properties` | No | Inserisce nell&#39;elenco Consentiti la proprietà separata da virgole. Si applica a set di dati/elenco, set di dati/get, batch/elenco, batch/elenco_last |
| `query_params.name` | No | Filtrare i set di dati per nome (solo set di dati/elenco) |
| `query_params.tags` | No | Filtra i set di dati per tag, ad esempio `unifiedProfile:enabled:true` (solo set di dati/elenco) |
| `query_params.property_filter` | No | Filtro Regex per oggetti di risposta (set di dati/elenco e batch/elenco) |
| `query_params.status` | No | Filtra batch per stato: `success`, `failed`, `loading`, `active` (solo batch/elenco) |
| `query_params.dataset_id` | No | Definire l’ambito dei batch per un set di dati specifico (batch/elenco e batch/elenco_ultimo) |
| `query_params.created_after` | No | Filtra i batch creati dopo la marca temporale Unix in ms (solo batch/elenco) |
| `query_params.created_before` | No | Filtra i batch creati prima della marca temporale Unix in ms (solo batch/elenco) |
| `query_params.last_batch_status` | No | Filtra per ultimo stato batch (solo batch/list_last) |
| `query_params.aggregate` | No | Restituire le metriche aggregate a livello principale (solo batch/get) |
| `query_params.path` | No | File Meta da scaricare: `row_errors`, `input_files`, `row_errors_sample.json` (solo batch/get_meta_files) |

### search_class_relations

**Risorsa:** relazioni di classe · indice YAML statico
**Stato:** Attivo

Cercare le relazioni della classe aziendale Experience Platform per nome utilizzando l&#39;indice statico `class_relations_v1.yaml`. Non viene effettuata alcuna chiamata API di Experience Platform. Accetta un singolo termine o termini separati da virgole; ogni termine viene confrontato con i nomi delle classi utilizzando la corrispondenza parziale dei token. Restituisce classi corrispondenti con relazioni di inoltro (a cosa punta ciascuna classe) e relazioni inverse (a cui punta la classe). Utilizza questa funzione per comprendere le relazioni tra le entità prima di creare query, flussi di dati o composizioni di schema.

**Funzionalità:** ricerca per token, ricerca con più termini separati da virgole, corrispondenza parziale dei token, espansione del sinonimo bidirezionale

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `query` | Sì | Nome della classe aziendale o tipo di oggetto da cercare. Supporta le corrispondenze token parziali (`dat` corrispondenze `dataset`, `data_type`, ecc.). Passa più termini separati da virgole per cercare più classi contemporaneamente (esempio: `dataset, schema`) |
| `n` | No | Numero massimo di risultati corrispondenti da restituire (valore predefinito: 5, min 1) |

### search_data_access

**Risorsa:** API di accesso ai dati · batch non riusciti
**Stato:** Attivo

Accedi ai file dai batch di acquisizione dati di Experience Platform non riusciti. Utilizzare `failed_batch/list_failed` per elencare i file appartenenti a un batch non riuscito per la diagnosi degli errori. Richiede un ID batch per tutte le operazioni. Nota: `file/get` e `dataset/preview` sono disabilitati perché espongono i dati del record effettivo. Tutte le operazioni sono di sola lettura.

**Funzionalità:** elenca i file da un batch di acquisizione non riuscito

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `entity_type` | Sì | `failed_batch` — elenca i file da un batch di acquisizione non riuscito |
| `operation` | Sì | `list_failed` — l&#39;unica operazione supportata |
| `resource_id` | Sì | ID batch del batch non riuscito |
| `query_params.start` | No | Indice di inizio paging, ad esempio `1` |
| `query_params.limit` | No | Numero di risultati per pagina, ad esempio `10` |
| `query_params.path` | No | Filtro nome file completo, ad esempio `profiles.csv` |


### search_data_lake

**Risorsa:** API Data Lake · set di dati, batch
**Stato:** Attivo

Ispeziona il set di dati e i metadati batch dal livello del Data Lake. Utilizza `get` per i metadati completi, `get_size` per le metriche delle dimensioni di archiviazione e acquisizione e `list_failed` per monitorare gli errori di acquisizione in un intervallo di tempo. Viene impostato automaticamente sugli ultimi 7 giorni per i quali non è stato fornito alcun intervallo di tempo per `list_failed`. Tutte le operazioni sono di sola lettura e richiedono un ID risorsa.

**Funzionalità:** ottenere il set di dati/i metadati del batch, ottenere le metriche delle dimensioni di archiviazione, elencare i batch con errori in un intervallo di tempo

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `entity_type` | Sì | `dataset` o `batch` |
| `operation` | Sì | `get`, `get_size`, `list_failed`. `list_failed` supporta solo il tipo di entità `batch` |
| `resource_id` | Sì | ID set di dati o ID batch. Per `list_failed`: l&#39;ID del set di dati per l&#39;ambito non riesce a |
| `query_params.created_after` | No | Inizio della finestra temporale. Timestamp Unix in ms |
| `query_params.created_before` | No | Fine della finestra temporale. Timestamp Unix in ms |
| `query_params.limit` | No | Risultati max per pagina (massimo 100) |
| `query_params.order_by` | No | Direzione di ordinamento, ad esempio `desc:created` |

### search_dule

**Risorsa:** Governance dei dati · etichette, criteri, azioni_marketing
**Stato:** Attivo

Esegui una query sull’API del servizio criteri per etichette di utilizzo dei dati, criteri e azioni di marketing. Utilizza `marketing_action/evaluate` per verificare se un&#39;azione di marketing su dati con etichette specifiche violerebbe i criteri di governance. Tutte le operazioni sono di sola lettura.

**Funzionalità:** etichette di utilizzo dei dati per l&#39;elenco/recupero, criteri per l&#39;elenco/recupero, criteri abilitati per l&#39;elenco, azioni di marketing per l&#39;elenco/recupero, valutazione delle azioni di marketing rispetto alle etichette

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `entity_type` | Sì | `label`, `policy` o `marketing_action` |
| `operation` | Sì | `list`, `get`, `list_enabled` (solo criterio), `evaluate` (solo marketing_action). `list_enabled` non richiede l&#39;ambito |
| `scope` | No | `core` (definito da Adobe) o `custom` (definito dall&#39;organizzazione). Richiesto per `list`, `get`, `evaluate`; non utilizzato per `list_enabled` |
| `resource_id` | No | Nome etichetta, ID criterio o nome dell’azione di marketing. Richiesto per `get` e `evaluate` |
| `query_params.dule_labels` | No | Etichette separate da virgole (ad esempio `C1,C3`). Richiesto per `marketing_action/evaluate`; filtro facoltativo per `policy/list` |
| `query_params.limit` | No | Numero massimo di risultati |
| `query_params.start` | No | Cursore di impaginazione dal valore `_page.next` di una risposta precedente |
| `query_params.orderby` | No | Campi di ordinamento separati da virgole |
| `query_params.property_filter` | No | Espressione filtro, ad esempio `name==C1` |
| `query_params.marketing_action` | No | Limita l’elenco dei criteri ai criteri che fanno riferimento a questa azione di marketing (solo criterio/elenco) |
| `query_params.include_draft` | No | Includi criteri BOZZA in `marketing_action/evaluate` (impostazione predefinita: solo criteri ABILITATI) |

### search_query_service

**Risorsa:** Query Service · query, modelli, pianificazioni, esecuzioni pianificate, connessioni, sottoscrizioni di avvisi
**Stato:** Attivo

Strumento unificato per le risorse di Query Service. Elenca e recupera query ad hoc, modelli SQL salvati, query pianificate e relative esecuzioni, parametri di connessione interattivi (per client PSql/JDBC) e sottoscrizioni di avvisi. Per gli elenchi di query, il valore predefinito è `isService==false,isParentLevel==true` per filtrare il traffico interno. Tutte le operazioni sono di sola lettura.

**Funzionalità:** query di tipo list/get, modelli di tipo list/get, pianificazioni di tipo list/get, esecuzioni di tipo list/get schedule, parametri di connessione, sottoscrizioni di avvisi di tipo list

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `entity_type` | Sì | `query`, `query_template`, `schedule`, `schedule_run`, `connection`, `alert_subscription` |
| `operation` | Sì | `list`, `get`, `get_connection_params`, `list_by_u...` |

### execute_observability_metrics_query

**Risorsa:** Informazioni di osservabilità · Metriche
**Stato:** Attivo

Eseguire una query sulle metriche [!DNL Observability Insights] per la sandbox corrente o per tutte le sandbox dell&#39;organizzazione. Supporta più metriche in una singola richiesta, filtri basati su tag e downsampling per metrica. Per `scope=org`, includere almeno un filtro `groupBy` per ogni metrica. Tutte le operazioni sono di sola lettura.

**Funzionalità:** punti di dati della metrica query, serie temporali o aggregati, richieste con più metriche, filtri tag, groupBy/exclude, per-metric downsampling

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `metrics` | Sì | Matrice di specifiche metriche. Ciascuno include `name` (nome metrica completo), `aggregator` (`sum`, `avg`, `min`, `max`, `count`, `last`, `p50`, `p95`, `p99`, varianti di istogramma o `absent`), `filters` facoltativo e `downsample` facoltativo |
| `start` | Sì | Inizio finestra, ISO 8601, esempio: `2026-01-15T00:00:00.000Z`. Deve essere precedente a `end`. Finestra massima: 31 giorni |
| `end` | Sì | Fine finestra, ISO 8601. Deve essere successivo a `start` |
| `granularity` | No | Dimensione intervallo di tempo: `MINUTE`, `FIVE_MINUTE`, `TEN_MINUTE`, `FIFTEEN_MINUTE`, `THIRTY_MINUTE`, `HOUR`, `FOUR_HOUR`, `TWELVE_HOUR`, `DAY`, `TWO_DAY`, `WEEK`, `MONTH` o `ALL` (comprime la finestra in un singolo aggregato). Ometti per consentire al server di scegliere |
| `scope` | No | `sandbox` (impostazione predefinita) esegue query sulla sandbox corrente. `org` esegue una query su tutte le sandbox dell&#39;organizzazione e consiglia un filtro `groupBy` per ogni metrica |

Ogni filtro in `metrics[].filters` include `name` (nome tag), `value` (corrispondenza esatta, con caratteri jolly o regex) e `groupBy` e `exclude` booleani facoltativi.

### inspect_observability_breaches

**Risorsa:** Informazioni di osservabilità · violazioni
**Stato:** Attivo

Rileva intervalli di violazione di [!DNL Observability Insights], gli intervalli di tempo in cui una metrica ha superato la linea di base configurata, per la sandbox corrente o in tutte le sandbox dell’organizzazione. Restituisce gli intervalli pre-corrispondenti per serie. Le violazioni aperte ancora in corso alla fine della finestra vengono restituite con `end: null`. Tutte le operazioni sono di sola lettura.

**Funzionalità:** elencare gli intervalli di violazione per serie, organizzazione e ambito sandbox

**Parametri:**

| Parametro | Obbligatorio | Descrizione |
| --- | --- | --- |
| `metrics` | Sì | Matrice di specifiche di violazione. Ciascuno include `name` (nome metrica completo) e `filters` facoltativo |
| `start` | Sì | Inizio finestra, ISO 8601. Deve essere precedente a `end`. Finestra massima: 31 giorni |
| `end` | Sì | Fine finestra, ISO 8601 |
| `granularity` | No | Dimensione bucket di tempo, stessi valori di `execute_observability_metrics_query` eccetto `ALL`. Ogni bucket viene valutato in modo indipendente rispetto alla linea di base |
| `scope` | No | `sandbox` (impostazione predefinita) o `org`. Su `org` senza un filtro sandbox, includi almeno un filtro con `groupBy: true` per metrica in modo che i risultati vengano suddivisi per tale dimensione invece che compressi nell&#39;organizzazione |

`inspect_observability_breaches` non accetta `aggregator` o `downsample` su `metrics[]`. Lo strumento imposta questi parametri internamente per valutare la condizione di violazione.

>[!NOTE]
>
>Entrambi gli strumenti Observability Insights sono inoltre limitati a una stima di 10.000 punti dati per richiesta. Restringi l&#39;intervallo di tempo, aggiungi filtri o utilizza un `granularity` meno recente se una richiesta viene rifiutata per il superamento di questo limite.

### search_sandbox_health_assessment

**Risorsa:** Eseguire e utilizzare · Valutazioni di verifica stato
**Stato:** Attivo

Recuperare i risultati più recenti della valutazione del controllo di integrità di esecuzione e funzionamento per la sandbox corrente. Restituisce i risultati per ogni categoria supportata, inclusi schemi e identità, segmentazione, acquisizione e profilo. Per identificare la causa principale senza una ricerca separata, ogni risultato include le risorse interessate dietro un controllo non riuscito. Vengono restituiti solo gli assegni con un nome leggibile pubblicato. Tutte le operazioni sono di sola lettura.

>[!NOTE]
>
>Questo strumento recupera solo i risultati della valutazione. Per risolvere un problema segnalato, utilizzare il pannello dei dettagli del controllo di integrità nell&#39;interfaccia utente [!DNL Experience Platform]. Consulta [Verifiche stato](https://experienceleague.adobe.com/en/docs/experience-platform/run-and-operate/health-checks). Le indicazioni di correzione automatica per i controlli di integrità supportati sono disponibili come abilità in [CX Coworker Chat](../chat/overview.md).

**Funzionalità:** elenca tutti i risultati del controllo di integrità per la sandbox corrente, ottiene i risultati per un controllo denominato

Nessun parametro.
