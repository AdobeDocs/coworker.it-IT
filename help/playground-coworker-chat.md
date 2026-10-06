---
title: Introduzione Alla Chat Con I Colleghi In Playground
description: Scopri come utilizzare Chat con collaboratori in Playground per scoprire come i prompt in linguaggio naturale possono aiutarti a imparare, indagare e perfezionare il tuo lavoro.
hide: true
autotag-review: '2026-09-02T16:21:52.199Z'
TQID: 'https://experienceleague.adobe.com/a-9nJwwe4TFdi0ljwyyHfVfz-VqHL5lQbtmkU5P1Axw'
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
    internal-label: CX Enterprise
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
  - id: edbd1a0e-46c8-49da-8c10-dba9ec80bba9
    internal-label: Experience Platform
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fdddec33-c9cb-4459-b8b6-2664395a6f10
    internal-label: Real-Time Customer Data Platform
  - id: fdae8433-07cd-42e7-acce-738afe63f6bb
    internal-label: CX Enterprise Coworker
feature_v2:
  - id: 9c3a4e5f-6d7b-4c8a-8e9f-1b2c3d4e5f6a
    internal-label: Datasets
  - id: a4a9911c-3a92-4f17-a7f9-fe2eb3235fef
    internal-label: Monitoring
  - id: a50ad69b-1331-40e9-b634-531a085a6a54
    internal-label: Identities
  - id: a9eb38d5-9d89-492f-af4e-b968a07f2d91
    internal-label: Permissions
  - id: abc02dd6-664f-446a-9aaa-675bc0f2fe4a
    internal-label: Sources
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: ba929a52-9339-4154-9487-317dc875a3c7
    internal-label: Use cases
  - id: d21bd11d-08df-4cd6-ad8f-cb59a09de5c0
    internal-label: Sandboxes
  - id: d2a6cbf4-df32-480f-909e-b42f66dcb9f0
    internal-label: Places
  - id: de9975b2-c43a-4287-9698-4f4cad92b83f
    internal-label: Schemas
  - id: ebefeaba-efa6-45e2-ae01-f6171cdb8d1e
    internal-label: Tier
  - id: eec185bd-7d60-4193-ba3f-da427569936a
    internal-label: Destinations
  - id: f5a6b7c8-5003-4003-9003-500000000003
    internal-label: Services
topic_v2:
  - id: b4dd41a7-ccf8-4e9d-918e-acaab534a307
    internal-label: Data quality
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
source-git-commit: dbee38135a5491fd21b65fdbb70ba60d949d7560
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%
---
# Guida introduttiva alla chat per collaboratori in Playground

Utilizza Chat con collaboratori in Playground per scoprire in che modo i prompt in linguaggio naturale possono aiutarti a imparare, indagare e perfezionare il tuo lavoro. Playground offre alcuni esempi di modi per avviare una conversazione in modo da poter capire rapidamente cosa può fare una chat di Coworker.

>[!IMPORTANT]
>
>Per completare l&#39;esercizio, attenersi alla procedura descritta di seguito.
>
>- Collegamento: [ao.adobe.io](https://ao.adobe.io/)
>- Istanza: AEP GenAI - VA7
>- Sandbox: `fsi-box`

## Demo collaboratore AI: [!DNL weBank] campagna di aggiornamento carta di credito

Questo esercizio tratta Real-Time CDP e Adobe Journey Optimizer.

Sei uno stratega di CX Enterprise presso **[!DNL weBank]**, una società di servizi finanziari leader nel settore digitale. Utilizza AI Coworker per passare dai dati non elaborati a una campagna live, interamente tramite conversazione.

## Parte 1: Comprendere la tua attività

### 1.1 — Procurarsi la terra

**Chiedi conferma**

> Panoramica della sandbox: quanti tipi di pubblico, set di dati e destinazioni ho?

**Risultato previsto**

Il collaboratore restituisce un inventario sandbox completo in secondi:

| Risorsa | Count |
| --- | --- |
| Tipi di pubblico | 21 |
| Set di dati | 30 |
| Schemi | 28 |
| Origini | 3 |
| Destinazioni | 1 (Amazon S3) |
| Percorsi | 0 |

### 1.2 — Quale pubblico esiste già?

**Chiedi conferma**

> Elenca tutti i tipi di pubblico in base alle dimensioni

**Risultato previsto**

Coworker elenca 21 tipi di pubblico ordinati per dimensione, da 8.012 profili a 0:

| Categoria | Pubblico | Profili |
| --- | --- | --- |
| Punteggi tendenza | Upgrade carta di credito elevato | 1,195 |
| Punteggi tendenza | Canale | 4,113 |
| Punteggi tendenza | Basso | 8,012 |
| Propensione ipotecaria | Alto | 1,233 |
| Propensione ipotecaria | Canale | 4,141 |
| Propensione ipotecaria | Basso | 7,946 |
| Livelli valore account | +500 K | 4,377 |
| Livelli valore account | 250-500 K | 4,537 |
| Livelli valore account | 100-250 K | 2,666 |
| Livelli valore account | 50-100 K | 894 |
| Livelli valore account | &lt;50.000 | 846 |
| Demografia | Femmina | 6,719 |
| Demografia | Maschio | 6,601 |
| Informazioni geografiche | Costa orientale | 2,260 |
| Informazioni geografiche | West Coast | 1,740 |
| Consenso canale | E-mail | 6,597 |
| Consenso canale | SMS | 6,675 |
| Compleanno | Compleanno questo mese | 0 |
| Compleanno | Entro 7 giorni | 0 |
| Compleanno | Oggi | 0 |
| Compleanno | Prossimi 30 giorni | 0 |

Tutti i tipi di pubblico per il compleanno mostrano attualmente 0 perché dipendono dal tempo.

### 1.3 — Quali dati alimentano questi tipi di pubblico?

**Chiedi conferma**

> Quali set di dati sono disponibili che contengono i dati dei clienti?

**Risultato previsto**

Cooker identifica due set di dati aziendali chiave e i relativi set di dati di sistema:

| Set di dati | Descrizione |
| --- | --- |
| **weBank: CRM** | Dati profilo cliente/account (profilo + identità abilitati) |
| **weBank: azioni del cliente** | Dati evento comportamentale (profilo + identità abilitati) |

I set di dati Journey Optimizer di sistema per i segnali di coinvolgimento includono il tracciamento e-mail, il tracciamento push, il consenso e il feedback sui messaggi.

## Parte 2: Scoprire i campi giusti

### 2.1 — Trovare i campi del valore conto

**Chiedi conferma**

> Quali campi sono disponibili in relazione al valore o al saldo del conto?

**Risultato previsto**

Coworker fa emergere il campo primario e i campi correlati nel set di dati **weBank: CRM**:

| Campo | Note |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.totalAccountValue` | Campo primario; utilizzato in tutti e 5 i tipi di pubblico di livello Valore account |
| `numberOfAccounts` | Campo correlato |
| `accountType` | Campo correlato |
| `currentStatement` | Campo correlato |
| `actionAmount` | Campo correlato |

### 2.2 — Trova campi carta di credito

**Chiedi conferma**

> Trova campi relativi al tipo di carta di credito o carta di credito

**Risultato previsto**

Il collaboratore identifica questi campi nello schema **weBank: CRM**:

| Campo | Descrizione |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardType` | Memorizza il tipo di carta (Visa, Mastercard, Amex) |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardHolder` | Nome del titolare della carta |

### 2.3 — Campi geografici

**Chiedi conferma**

> Esiste un campo per lo stato o l’area geografica?

**Risultato previsto**

Il collaboratore identifica i campi geografici nel set di dati **weBank: CRM**:

| Campo | Note |
| --- | --- |
| `homeAddress.state` | Abbreviazione di stato USA; utilizzata in Lives on East Coast e Lives on West Coast |
| `homeAddress.stateProvince` | Trovato anche |
| `homeAddress.region` | Trovato anche |
| `placeContext.geo.stateProvince` | Trovato anche |

## Parte 3: Trovare il pubblico giusto per una campagna di riattivazione

### 3.1 — Chiedi all’intelligenza artificiale di aiutarti a trovare il pubblico giusto

**Chiedi conferma**

> Aiutami a trovare o creare il pubblico giusto per una campagna di riattivazione della carta di credito: voglio indirizzare l’attività ai clienti con una propensione elevata o media per l’aggiornamento di una carta di credito, ma che non hanno ancora agito

**Risultato previsto**

Coworker trova due tipi di pubblico candidati che non sono mai stati oggetto di targeting in un percorso o in una destinazione:

| Pubblico | Profili |
| --- | --- |
| Upgrade carta di credito elevato | 1,195 |
| Medium per l&#39;aggiornamento della carta di credito | 4,113 |

Opzioni consigliate:

| Opzione | Approccio |
| --- | --- |
| **A** | Utilizzate entrambi direttamente con ramificazioni di percorso: offerta aggressiva per Alta, crescita per Medium |
| **B** | Creare un segmento di segmenti derivato con logica di esclusione e aggiornamento per una gestione più pulita |

Dimensione combinata: circa 5.308 profili

### 3.2 — Creare un pubblico di precisione

**Chiedi conferma**

> Crea un pubblico di clienti che rientrano nel pubblico &quot;Propensities: Credit Card Upgrade High&quot; (Propensione: aggiornamento carta di credito elevato) E il cui valore di account è superiore a 250.000 $ E che hanno acconsentito all’invio di e-mail

Assegna a questo nome **Aggiornamento Platinum - Idoneo per e-mail di alto valore** → Seleziona batch → Approva piano

**Risultato previsto**

I collaboratori definiscono la propensione ML, il valore finanziario e l’idoneità del canale in un segmento di precisione — lavoro che normalmente richiederebbe un ticket del team di dati.

### 3.3 — Stima dimensioni e cascata

**Chiedi conferma**

> Quanto è grande il pubblico? Mostrami il guasto della cascata.

**Risultato previsto**

Collaboratore restituisce una stima del conteggio dei profili in tempo reale e un grafico a cascata visivo:

| Passaggio filtro | Risultato |
| --- | --- |
| Elevata propensione all&#39;upgrade della carta di credito | Circa 1,195 profili |
| + Valore dell’account superiore a 250.000 dollari | Si riduce ulteriormente |
| + Consenso e-mail | Conteggio finale indirizzabile |

Questo mostra esattamente quale condizione è il filtro più grande e se allentare i criteri.

### 3.4 — Verificare la presenza di tipi di pubblico simili

**Chiedi conferma**

> Esistono tipi di pubblico esistenti simili a quello appena creato?

**Risultato previsto**

Collaboratore conferma che non esiste un singolo pubblico combinato, ma che sono già presenti tutti i blocchi predefiniti:

| Blocco predefinito | Dettagli |
| --- | --- |
| Propensione: Upgrade carta di credito elevato | Punteggio ≥ 90 |
| Valore account: 250-500K | Pubblico esistente |
| Valore account: +500K | Pubblico esistente |
| Consenso e-mail | `consents.marketing.email.val = "y"` |

Il collaboratore conferma che non esiste alcun rischio di duplicazione e consiglia di procedere.

## Parte 4: Creare il Percorso

### 4.1 — Le idee di percorso si fondano sui dati

**Chiedi conferma**

> In base ai casi d’uso più comuni nei servizi finanziari, suggerisci alcuni percorsi vincenti che posso creare con il pubblico che ho

**Risultato previsto**

Coworker suggerisce cinque idee concrete di percorso fondate sul pubblico reale:

| idea percorso | Tipi di pubblico |
| --- | --- |
| Tocco fedeltà compleanno | Compleanno entro 7 giorni + Livelli valore account |
| Aggiornamento carta di credito | Upgrade CC High + consenso e-mail |
| Ipoteca portata regionale | Ipoteca alta + costa est/ovest |
| Upgrade di Wealth Tier Advisory | Valore account: +500K |
| Attivazione cross-channel consenso | Consenso e-mail meno consenso SMS |

### 4.2 — Creazione del percorso di aggiornamento della carta di credito

**Chiedi conferma**

> Crea un percorso utilizzando il pubblico &quot;Aggiornamento Platinum - Idoneo per e-mail di valore elevato&quot;. Invia una notifica push con i vantaggi di WeBank Platinum Card. Aspettate 3 giorni. Se il cliente non ha richiesto, invia un SMS con un’offerta limitata di 0% APR per 12 mesi sui trasferimenti a saldo. Attendere altri 5 giorni. Se ancora non viene presentata alcuna candidatura, invia una notifica push finale con un invito personale al banchiere.

Esamina piano → Approva piano → Concedi autorizzazioni

**Risultato previsto**

Coworker crea un percorso completo a 3 contatti e 2 canali da una singola descrizione del linguaggio naturale, inclusi timer di attesa, controlli di condizione e offerte in aumento.

### 4.3 — Bonus: Creazione di un percorso da un&#39;immagine

**Chiedi conferma**

> Crea il percorso dall&#39;immagine caricata

**Risultato previsto**

Coworker legge l’immagine caricata, inclusi nodi, canali, tempi di attesa e condizioni, e genera l’intero percorso in Journey Optimizer. Questo trasforma un artefatto di pianificazione direttamente in un percorso distribuibile.

### 4.4 — Verifica dei conflitti

**Chiedi conferma**

> Esistono percorsi attivi che potrebbero entrare in conflitto con il percorso appena creato?

**Risultato previsto**

Collaboratore controlla automaticamente tutti i percorsi attivi per verificare la sovrapposizione del pubblico, le collisioni tra pianificazioni e la saturazione del canale.

## Parte 5: trasformare i rilasci di Percorso in un nuovo pubblico

### 5.1 — Identificare il punto di caduta

**Chiedi conferma**

> Mostrami il percorso appena creato e individua quale passaggio presenta il maggior calo

**Risultato previsto**

Collaboratore analizza gli eventi delle fasi di percorso e fa emergere il nodo con la frequenza di uscita più elevata. Ad esempio:

> Il 68% dei profili che hanno ricevuto la prima e-mail non l’ha mai aperta ed è uscito prima del passaggio SMS.

### 5.2 — Creare un pubblico di riferimento

**Chiedi conferma**

> Trasforma questi abbandoni di percorso in un nuovo pubblico: persone che sono entrate nel percorso di aggiornamento Platinum ma che non hanno mai raggiunto il passaggio SMS

Denomina **Aggiornamento Platino - E-Mail Non-Responders** → Seleziona Batch → Approva Piano

**Risultato previsto**

Coworker crea un nuovo pubblico basato sui dati comportamentali del percorso, profili che sono entrati nel percorso ma che non sono progrediti al passaggio SMS. Questo pubblico è immediatamente utilizzabile per una campagna di follow-up.

### 5.3 — Riattivare i rilasci

**Chiedi conferma**

> Crea un percorso di riattivazione per il pubblico &quot;Aggiornamento Platinum - E-mail dei non-responder&quot;. Prova un approccio diverso: inizia con una notifica push che evidenzia un’offerta limitata di 75.000 punti bonus, attendi 2 giorni, quindi invia un invito direct mailing per visitare la filiale locale.

Esamina piano → Approva piano → Concedi autorizzazioni

**Risultato previsto**

Coworker crea un percorso di ripristino dedicato utilizzando canali e messaggi diversi per i non-responder. Ora hai chiuso il ciclo su una perdita di conversione — interamente attraverso la conversazione.

## Parte 6: Controllo qualità e convalida automatizzati

### 6.1 — Verifica dello stato di freschezza e di ingestione dei dati

**Chiedi conferma**

> Ci sono problemi di qualità dei dati con i set di dati che alimentano i miei tipi di pubblico? Verifica lo stato di acquisizione per weBank: CRM e weBank: Azioni dei clienti

**Risultato previsto**

Il collaboratore segnala l’integrità dell’acquisizione per ogni set di dati:

| Set di dati | Stato | Dettagli |
| --- | --- | --- |
| **weBank: CRM** | Integro | 39 record acquisiti, 32 al profilo, zero errori |
| **weBank: azioni del cliente** | Flag secondario | 441 record acquisiti; 35 avevano timestamp scaduti; circa l’8% esclusi a causa della finestra TTL |

Consiglio: rivedi le impostazioni TTL o controlla il sistema di origine per i record non aggiornati.

### 6.2 — Convalidare il percorso prima della pubblicazione

**Chiedi conferma**

> Esamina il percorso di aggiornamento Platinum per individuare eventuali errori o problemi di qualità: verifica la presenza di timer di attesa mancanti, percorsi senza uscita, configurazioni di canale mancanti e divari di idoneità del pubblico

**Risultato previsto**

Il collaboratore esamina la struttura del percorso e segnala problemi quali:

| Tipo di problema | Esempio |
| --- | --- |
| Percorsi inattivi | Percorsi che non terminano con un nodo finale |
| Configurazione dei canali | Azioni senza configurazioni della superficie di canale |
| Timer di attesa | Timer che potrebbero causare problemi con SLA |
| Contenuto | Nodi con contenuto mancante |

## Parte 7: Monitoraggio e governance

### 7.1 — Monitorare lo stato del pubblico nel tempo

**Chiedi conferma**

> Mostratemi come è cambiato il pubblico &quot;Propensione: aggiornamento carta di credito elevato&quot; negli ultimi 30 giorni

**Risultato previsto**

Collaboratore restituisce una visualizzazione per serie temporali della crescita o del declino del pubblico con l’analisi delle tendenze, che consente di identificare se il punteggio del modello ML è in evoluzione o se le modifiche dei dati a monte influiscono sulla qualifica.

### 7.2 — Diagnosticare una modifica

**Chiedi conferma**

> Perché il pubblico &quot;Account Value: +500K&quot; è sceso di recente?

**Risultato previsto**

Collaboratore esegue l’analisi causale decomponendo la variazione in:

| Fattore | Domanda |
| --- | --- |
| Aggiornamento dei dati | C&#39;è stato un gap di acquisizione? |
| Modifiche ai criteri di unione | L’unione dei profili è stata modificata? |
| Modifiche all’origine a monte | I dati CRM hanno smesso di scorrere? |
| Comportamento effettivo del cliente | I valori dell&#39;account sono stati effettivamente rifiutati? |

Questo sostituisce 1-2 giorni di valutazione dell’analista.

