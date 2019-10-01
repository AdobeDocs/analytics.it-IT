---
description: L'integrazione dei Connettori dati per Silverpop utilizza le variabili di Analytics per tenere traccia di varie metriche Silverpop.
seo-description: L'integrazione dei Connettori dati per Silverpop utilizza le variabili di Analytics per tenere traccia di varie metriche Silverpop.
seo-title: Variabili di integrazione di Analytics
title: Variabili di integrazione di Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Analytics Integration Variables{#analytics-integration-variables}

L'integrazione dei Connettori dati per Silverpop utilizza le variabili di Analytics per tenere traccia di varie metriche Silverpop.

Dopo aver identificato gli eventi e le eVar da utilizzare con l'integrazione Silverpop, utilizzate Adobe Analytics Admin Console per abilitarli (consultate [Suite](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html)di rapporti).

La tabella seguente descrive le variabili di Analytics necessarie per l'integrazione di Silverpop.

## Variabili richieste {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| event (numerico) | Bounce | Importa automaticamente da Silverpop. | L'evento Bounces consente di visualizzare il numero di messaggi e-mail che non sono stati inviati ai destinatari a causa di un problema di consegna. |
| event (numerico) | Clic | Importa automaticamente da Silverpop. | L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| event (numerico) | Apre | Importa automaticamente da Silverpop. | L’evento Opened (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| event (numerico) | Invio | Importa automaticamente da Silverpop. | L'evento Sending consente di visualizzare il numero di messaggi e-mail inviati. |
| event (numerico) | Annulla sottoscrizione | Importa automaticamente da Silverpop. | L’evento Annulla sottoscrizione consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e hanno quindi fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri della vostra organizzazione. |
| eVar | ID Silverpop/ID visitatore | Raccolti da parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. | ID visitatore univoco |
| eVar o s.campaign | ID postale | Raccolti da parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. | Questo viene spesso memorizzato nella variabile della campagna. |

## Variabili facoltative {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| event (contatore) | File scaricato | Raccolta manuale tramite i tag di Analytics. | Questo evento viene utilizzato per identificare gli utenti che hanno scaricato un file sul sito. |
| event (contatore) | Modulo avviato | Raccolta manuale tramite i tag di Analytics. | Il modulo avviato viene utilizzato per identificare gli utenti che iniziano un modulo, ma non lo completano. |
| event (contatore) | Modulo completato | Raccolta manuale tramite i tag di Analytics. | Modulo completato viene utilizzato per identificare i visitatori che iniziano un modulo e che non lo completano. |
| eVar | Email Address | Raccolta manuale tramite i tag di Analytics. | Indirizzo e-mail è destinato alla raccolta manuale dell’indirizzo e-mail all’accesso, all’accesso o ad altre pagine in cui l’indirizzo e-mail viene raccolto. Questa variabile viene utilizzata per reimmettere in commercio gli utenti che hanno acconsentito alla ricezione di e-mail, ma che non hanno già fatto clic su di essa in passato. |
| eVar | File scaricato | Raccolta manuale tramite i tag di Analytics. | Il file scaricato identifica il file scaricato da un visitatore. |
| eVar | Nome modulo | Raccolta manuale tramite i tag di Analytics. | Nome modulo identifica il modulo abbandonato da un visitatore. |

