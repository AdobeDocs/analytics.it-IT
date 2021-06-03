---
description: L’integrazione dei Data Connectors per Silverpop utilizza le variabili di Analytics per tenere traccia di varie metriche Silverpop.
title: Variabili dell'integrazione di Analytics
uuid: 3aef3caf-e24e-4fe7-b4d7-50ca0f6703b5
exl-id: 0b8b31f5-65a8-41e0-97d1-d75fb1b91f62
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 5%

---

# Variabili dell&#39;integrazione di Analytics{#analytics-integration-variables}

L’integrazione dei Data Connectors per Silverpop utilizza le variabili di Analytics per tenere traccia di varie metriche Silverpop.

Dopo aver identificato gli eventi e le eVar da utilizzare con l’integrazione Silverpop, utilizza l’Admin Console Adobe Analytics per abilitarli (consulta [Suite di rapporti](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html)).

La tabella seguente descrive le variabili di Analytics necessarie per l’integrazione Silverpop.

## Variabili richieste {#section-3ca8dc46bab0436cba0c9ef827c8356a}

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| evento (numerico) | Rimbalzi | Importa automaticamente da Silverpop. | L’evento Bounces ti consente di visualizzare il numero di messaggi e-mail che non sono stati recapitati ai destinatari a causa di un problema di consegna. |
| evento (numerico) | Clic | Importa automaticamente da Silverpop. | L’evento Clic consente di visualizzare il numero di visitatori che hanno fatto clic sul messaggio e-mail. |
| evento (numerico) | Aperture | Importa automaticamente da Silverpop. | L’evento Open (Apertura) consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail. |
| evento (numerico) | Invio | Importa automaticamente da Silverpop. | L’evento Invio ti consente di visualizzare il numero di messaggi e-mail inviati. |
| evento (numerico) | Annulla sottoscrizione | Importa automaticamente da Silverpop. | L’evento Annulla sottoscrizione ti consente di visualizzare il numero di visitatori che hanno aperto il messaggio e-mail e poi hanno fatto clic sul collegamento Annulla sottoscrizione per rinunciare ai messaggi e-mail futuri della tua organizzazione. |
| eVar | ID Silverpop/ID visitatore | Raccolti da parametri di query in collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. | ID visitatore univoco |
| eVar o s.campaign | ID postale | Raccolti da parametri di query in collegamenti e-mail tramite il metodo di raccolta automatizzata o un plug-in JavaScript. | Questa viene spesso memorizzata nella variabile della campagna. |

## Variabili facoltative {#section-5f0a32b0a2084c87a64b5f90c0d0fb53}

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| evento (contatore) | File scaricato | Raccolta manuale tramite i tag di Analytics. | Questo evento viene utilizzato per identificare gli utenti che hanno scaricato un file sul sito. |
| evento (contatore) | Modulo avviato | Raccolta manuale tramite i tag di Analytics. | Viene utilizzato per identificare gli utenti che iniziano un modulo, ma che non lo completano. |
| evento (contatore) | Modulo completato | Raccolta manuale tramite i tag di Analytics. | Il modulo Completato viene utilizzato per identificare i visitatori che iniziano un modulo e non lo completano. |
| eVar | Email Address | Raccolta manuale tramite i tag di Analytics. | Indirizzo e-mail consente di raccogliere manualmente l’indirizzo e-mail all’accesso, all’accesso o ad altre pagine su cui viene raccolto l’indirizzo e-mail. Questa variabile viene utilizzata per eseguire il remarketing degli utenti che hanno acconsentito alla ricezione di e-mail, ma che potrebbero non aver già fatto clic su di essa in passato. |
| eVar | File scaricato | Raccolta manuale tramite i tag di Analytics. | Il file scaricato identifica il file scaricato da un visitatore. |
| eVar | Nome modulo | Raccolta manuale tramite i tag di Analytics. | Nome modulo identifica il modulo abbandonato da un visitatore. |
