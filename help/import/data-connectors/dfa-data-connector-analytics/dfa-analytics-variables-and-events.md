---
description: L’integrazione dei Data Connectors per DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.
keywords: DFA
title: Variabili ed eventi di Analytics
feature: Data Connectors
uuid: 8996cb58-c793-4600-99ef-af3064642b29
exl-id: 8c3df2e8-84cd-4a14-b15b-42233d874c19
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 5%

---

# Variabili ed eventi di Analytics{#analytics-variables-and-events}

L’integrazione dei Data Connectors per DFA utilizza le variabili di Analytics per tenere traccia dei risultati delle campagne DFA.

A parte la variabile campagna, puoi utilizzare gli eventi di Analytics e le eVar che hanno senso per te. Una volta identificati gli eventi e le eVar da utilizzare con questa integrazione DFA, utilizza l’Admin Console Analytics per abilitarli. Le variabili di integrazione devono essere abilitate prima di attivare l’integrazione DFA. La tabella seguente descrive le variabili di Analytics necessarie per l’integrazione DFA.

| Variabile | Nome descrittivo | Metodo di compilazione | Descrizione |
|---|---|---|---|
| s.campaign o eVar | Codice di tracciamento degli annunci | Compilazione automatica tramite Connettore dati per campagne DFA. | Tiene traccia delle conversioni click-through per tutte le campagne. |
| eVar* | View-Through | Viene compilato automaticamente tramite VISTA e DFA per le campagne DFA. | Tiene traccia dei dati di visualizzazione per gli ID DFA. Questo eVar deve avere la stessa scadenza della variabile *`s.campaign`*. Deve essere la stessa variabile di conversione identificata nel Variable Provider ID. Assicurati che l’eVar disponga di sottorelazioni complete abilitate. Il costo per l&#39;abilitazione di questa funzione fa parte del costo di integrazione dei Data Connectors |
| eVar* | Errori di query DFA | (Facoltativo) Viene compilata tramite il codice di raccolta JavaScript. | Contiene uno dei diversi codici di errore restituiti da DFA. |
| prodView* | Conteggio view-through | Compilazione automatica tramite Connettore dati per campagne DFA. | Acquisisce il numero di volte in cui gli utenti hanno visualizzato un annuncio, non hanno fatto click-through, ma sono arrivati sul tuo sito. |
| prodView* | Impression | Compilato automaticamente tramite un feed di dati da DFA. | Tiene traccia del numero di volte in cui è stato servito un annuncio DFA specifico. |
| prodView* | Clic | Compilato automaticamente tramite un feed di dati da DFA. | Tiene traccia del numero di volte in cui gli utenti hanno fatto clic su un banner pubblicitario DFA specifico. Questa metrica può fornire numeri diversi rispetto alla metrica di click-through nativa di Analytics per uno dei vari motivi. Per ulteriori informazioni, consulta [Riconciliazione delle discrepanze metriche](/help/import/data-connectors/dfa-data-connector-analytics/dfa-reconciling-metric-discrepancies.md) . |
| prodView* | Timeout DFA | (Facoltativo) Viene compilata tramite il codice di raccolta JavaScript. | Conta il numero di volte in cui DFA non riesce a rispondere prima del timeout di *`s.maxDelay`*. Questo può aiutarti a determinare se c’è un problema di implementazione DFA. |
| prodView* | Costo del supporto DFA | Compilato automaticamente tramite un feed di dati da DFA. | Contiene le metriche dei costi dei contenuti multimediali che sono state inserite nell’interfaccia DFA. Affinché queste metriche vengano visualizzate, è necessario abilitare questa funzione sul lato DFA. |

*Selezionare un evento eVar o personalizzato non utilizzato.
