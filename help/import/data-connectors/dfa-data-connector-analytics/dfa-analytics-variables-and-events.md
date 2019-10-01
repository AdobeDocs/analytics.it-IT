---
description: L’integrazione dei connettori dati per il DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.
keywords: DFAE
seo-description: L’integrazione dei connettori dati per il DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.
seo-title: Variabili ed eventi di Analytics
solution: Analytics
title: Variabili ed eventi di Analytics
topic: Connettori dati
uuid: 8996cb58-c793-4600-99ef-af3064642b29
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Variabili ed eventi di Analytics{#analytics-variables-and-events}

L’integrazione dei connettori dati per il DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.

A parte la variabile della campagna, puoi utilizzare gli eventi di Analytics e le eVar che ti interessano. Una volta identificati gli eventi e le eVar da utilizzare con questa integrazione DFA, utilizzate l'Admin Console di Analytics per abilitarli. Le variabili di integrazione devono essere abilitate prima di attivare l’integrazione DFAE. Nella tabella seguente sono descritte le variabili di Analytics necessarie per l’integrazione DFA.

| Variabile | Nome descrittivo | Metodo di compilazione | Descrizione |
|---|---|---|---|
| s.campaign o eVar | Codice di tracciamento annunci | Compilato automaticamente dal connettore dati per le campagne DFA. | Monitora le conversioni click-through per tutte le campagne. |
| eVar* | Visualizzazione | Compilazione automatica tramite VISTA e DFA per campagne DFA. | Monitora i dati di visualizzazione degli ID DFA. Questa eVar deve avere la stessa scadenza della *`s.campaign`* variabile. Deve essere la stessa variabile di conversione identificata nell'ID provider variabile. Accertatevi che l'eVar disponga di sottorelazioni complete abilitate. Il costo per l'abilitazione di questa funzione è parte della tariffa di integrazione dei connettori dati |
| eVar* | Errori query DFA | (Facoltativo) Compilato tramite codice di raccolta JavaScript. | Contiene uno dei diversi codici di errore restituiti dal DFA. |
| prodView* | Conteggio visualizzazione-through | Compilato automaticamente dal connettore dati per le campagne DFA. | Acquisisce il numero di volte in cui gli utenti hanno visualizzato un annuncio, non hanno fatto clic su di esso, ma sono arrivati sul sito. |
| prodView* | Impressioni | Compilazione automatica tramite un feed di dati da DFA. | Tiene traccia del numero di volte in cui è stato servito un annuncio DFAE specifico. |
| prodView* | Clic | Compilazione automatica tramite un feed di dati da DFA. | Tiene traccia del numero di volte in cui gli utenti hanno fatto clic su un banner pubblicitario DFA specifico. Questa metrica può fornire numeri diversi rispetto alla metrica di click-through nativa di Analytics per uno dei diversi motivi. Per ulteriori informazioni, consulta [Riconciliazione delle](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) differenze tra metriche. |
| prodView* | Timeout DFA | (Facoltativo) Compilato tramite codice di raccolta JavaScript. | Conta il numero di volte in cui il DFAE non risponde prima del *`s.maxDelay`* timeout. Questo può aiutarti a determinare se esiste un problema di implementazione DFA. |
| prodView* | Costo del supporto DFA | Compilazione automatica tramite un feed di dati da DFA. | Contiene le metriche del costo dei supporti che sono state inserite nell’interfaccia DFAE. Affinché queste metriche vengano visualizzate, questa funzione deve essere abilitata sul lato DFAE. |

*Selezionare un'eVar o un evento personalizzato non utilizzato.
