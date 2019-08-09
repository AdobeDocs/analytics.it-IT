---
description: L'integrazione dei Connettori dati per DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.
keywords: DFA
seo-description: L'integrazione dei Connettori dati per DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.
seo-title: Variabili ed eventi di Analytics
solution: Analytics
title: Variabili ed eventi di Analytics
topic: Connettori dati
uuid: 8996 cb 58-c 793-4600-99 ef-af 3064642 b 29
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Variabili ed eventi di Analytics{#analytics-variables-and-events}

L'integrazione dei Connettori dati per DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.

Oltre alla variabile della campagna, puoi utilizzare eventi Analytics ed evar che hanno un senso. Dopo aver identificato l'evento e le evar da utilizzare con l'integrazione DFA, utilizzate Admin Console di Analytics per attivarli. Prima di attivare l'integrazione DFA, le variabili di integrazione devono essere abilitate. La tabella seguente descrive le variabili di Analytics necessarie per l'integrazione DFA.

| Variabile | Nome descrittivo | Metodo di compilazione | Descrizione |
|---|---|---|---|
| s. campaign o evar | Codice di tracciamento annunci | Compilazione automatica dal Connettore dati per le campagne DFA. | Tiene traccia delle conversioni di click-through per tutte le campagne. |
| eVar* | View-Through | Compilazione automatica tramite VISTA e DFA per campagne DFA. | Tiene traccia dei dati-through per gli ID DFA. Questa evar deve avere la stessa scadenza della *`s.campaign`* variabile. Deve essere la stessa variabile di conversione indicata nell'ID del provider variabile (vedi [Aggiornare il codice di raccolta dati del sito Web](../dfa-data-connector-analytics/dfa-integration/dfa-web-site-updates/dfa-update-data-collection-code.md#concept-8c108723ea0b4cc9a8c5cdc2d05894e3)). Assicuratevi che l'evar disponga di tutte le sottorelazioni complete abilitate. Il costo per l'abilitazione di questa funzione è parte della tariffa di integrazione dei connettori dati |
| eVar* | Errori query DFA | (Facoltativo) Compilata tramite codice di raccolta javascript. | Contiene uno dei diversi codici di errore restituiti da DFA (consultate la tabella in [Configurazione dell'integrazione](../dfa-data-connector-analytics/dfa-integration/dfa-integration.md#concept-cf33e1051c73452cbd26e950d0293858) per un elenco di questi codici di errore) |
| prodView* | Conteggio-through | Compilazione automatica dal Connettore dati per le campagne DFA. | Acquisisce il numero di volte in cui gli utenti hanno visualizzato un annuncio, non hanno click-through, ma hanno avuto accesso al sito. |
| prodView* | Impressioni | Compilazione automatica tramite un feed di dati da DFA. | Monitora il numero di volte in cui è stato distribuito un annuncio DFA specifico. |
| prodView* | Clic | Compilazione automatica tramite un feed di dati da DFA. | Tiene traccia del numero di volte in cui gli utenti hanno fatto clic su un banner banner DFA specifico. Questa metrica può fornire numeri diversi rispetto alla metrica click-through Analytics nativa per uno dei vari motivi. Consultate [Riconciliazione delle discrepanze metriche](../dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies/dfa-reconciling-metric-discrepancies.md#concept-8c31ebe761ca4b3fab1e3a18ef5d098f) per ulteriori informazioni. |
| prodView* | Timeout DFA | (Facoltativo) Compilata tramite codice di raccolta javascript. | Conta il numero di volte in cui il DFA non risponde prima dell' *`s.maxDelay`* uscita. Questo può aiutarti a determinare se è presente un problema di implementazione DFA. |
| prodView* | Prezzo media DFA | Compilazione automatica tramite un feed di dati da DFA. | Contiene le metriche costi multimediali inserite nell'interfaccia DFA. Affinché queste metriche possano essere visualizzate, questa funzione deve essere attivata sul lato DFA. |

* Seleziona un evento evar o personalizzato non utilizzato.
