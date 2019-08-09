---
description: L'integrazione dei Connettori dati per Silverpop utilizza le variabili di Analytics per tenere traccia delle diverse metriche di Silverpop.
seo-description: L'integrazione dei Connettori dati per Silverpop utilizza le variabili di Analytics per tenere traccia delle diverse metriche di Silverpop.
seo-title: Variabili integrazione di Analytics
title: Variabili integrazione di Analytics
uuid: 3 aef 3 caf-e 24 e -4 fe 7-b 4 d 7-50 ca 0 f 6703 b 5
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Analytics Integration Variables{#analytics-integration-variables}

L'integrazione dei Connettori dati per Silverpop utilizza le variabili di Analytics per tenere traccia delle diverse metriche di Silverpop.

Dopo aver identificato l'evento e le evar da usare con l'integrazione di Silverpop, utilizzate Adobe Analytics Admin Console per attivarli (consultate [Suite di rapporti](http://microsite.omniture.com/t2/help/en_US/reference/index.html?f=report_suites_admin)).

Nella tabella seguente sono descritte le variabili di Analytics necessarie per l'integrazione di Silverpop.

## Variabili richieste {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| event (numerico) | Non recapitate | Importato automaticamente da Silverpop. | L'evento Bounce permette di visualizzare il numero di messaggi e-mail che non sono stati consegnati ai destinatari a causa di un problema di consegna. |
| event (numerico) | Clic | Importato automaticamente da Silverpop. | L'evento Clic permette di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| event (numerico) | Aperture | Importato automaticamente da Silverpop. | L'evento Aperto permette di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| event (numerico) | Invia | Importato automaticamente da Silverpop. | L'evento Sends permette di visualizzare il numero di messaggi e-mail inviati. |
| event (numerico) | Annulla sottoscrizione | Importato automaticamente da Silverpop. | L'evento Non iscritto consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail, quindi hanno fatto clic sul collegamento Annulla sottoscrizione per rifiutare i messaggi e-mail futuri dall'organizzazione. |
| eVar | ID silverpop/ID visitatore | Raccolti dai parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzato o un plug-in javascript. | ID visitatore univoco |
| Evar o s. campaign | ID posta | Raccolti dai parametri di query nei collegamenti e-mail tramite il metodo di raccolta automatizzato o un plug-in javascript. | Spesso viene memorizzato nella variabile della campagna. |

## Variabili facoltative {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| evento (contatore) | File scaricato | Raccolta manuale tramite tag Analytics. | Questo evento viene utilizzato per identificare gli utenti che hanno scaricato un file sul sito. |
| evento (contatore) | Modulo avviato | Raccolta manuale tramite tag Analytics. | Modulo avviato viene utilizzato per identificare gli utenti che iniziano un modulo, ma non lo completano. |
| evento (contatore) | Modulo completato | Raccolta manuale tramite tag Analytics. | Il modulo Completato viene utilizzato per identificare i visitatori che iniziano un modulo e non lo completano. |
| eVar | Email Address | Raccolta manuale tramite tag Analytics. | L'indirizzo e-mail consente di raccogliere manualmente l'indirizzo e-mail all'accesso, all'accesso o ad altre pagine su cui viene raccolto l'indirizzo e-mail. Questa variabile viene utilizzata per riproporre gli utenti che hanno acconsentito alla ricezione e-mail, ma non hanno già fatto clic su un messaggio e-mail in passato. |
| eVar | File scaricato | Raccolta manuale tramite tag Analytics. | File scaricato identifica il file scaricato da un visitatore. |
| eVar | Nome modulo | Raccolta manuale tramite tag Analytics. | Nome modulo identifica il modulo abbandonato da un visitatore. |

