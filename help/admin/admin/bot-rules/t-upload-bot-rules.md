---
description: Per importare regole bot di importazione in massa, potete caricare un file CSV che definisca le regole.
seo-description: Per importare regole bot di importazione in massa, potete caricare un file CSV che definisca le regole.
seo-title: Caricare regole bot
solution: Analytics
subtopic: Regole bot
title: Caricare regole bot
topic: Strumenti di amministrazione
uuid: bd 70 c 199-5817-437 e -980 d -6 d 8 f 95 d 82 f 2 c
translation-type: tm+mt
source-git-commit: 93d6c7698216b3064f5417dbcfb33184efc2c132

---


# Caricare regole bot

Per importare regole bot di importazione in massa, potete caricare un file CSV che definisca le regole.

Create un file CSV con le seguenti colonne nell'ordine visualizzato:

<table id="table_770891EF9E4A49F695977BB6446736B5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Nome bot</code> </p> </td> 
   <td colname="col2"> <p> <code> Inizio IP </code> </p> </td> 
   <td colname="col3"> <p> <code> Fine IP </code> </p> </td> 
   <td colname="col4"> <p> <code> Regola corrispondenza agente (contiene o inizia con)</code> </p> </td> 
   <td colname="col5"> <p> <code> Agente include (limite char 100)</code> </p> </td> 
   <td colname="col6"> <p> <code> Escludi agente (limite char 255)</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Puoi definire tre tipi di regole bot:

* L'agente utente contiene o inizia con
* Indirizzo IP singolo o corrispondenza con caratteri jolly
* Corrispondenza intervallo IP

Ogni riga nel file di importazione può contenere solo una delle seguenti definizioni bot:

* **L'agente utente contiene o inizia con**: Fornite una stringa agente utente da far corrispondere nella colonna Agente. Specify the type of match you want performed by placing *contains* or *starts with* in the Agent Match Rule field. An optional value can be included in the Agent Exclude column that defines one or more pipe-delimited ( `|` ) strings that the Agent does not contain. Le corrispondenze stringa non sono sensibili alle maiuscole/minuscole. Entrambe le colonne Inizio IP e Fine IP devono essere vuote.

* **Indirizzo IP singolo o corrispondenza caratteri jolly**: Per associare un singolo indirizzo IP ( `10.10.10.1`) o un indirizzo IP jolly ( `10.10.*.*`), inserite lo stesso valore sia nelle colonne Inizio IP che Fine IP. Corrispondenza regola, Agente Include e Agente Escludi devono essere vuoti.

* **Corrispondenza intervallo IP**: Definite una serie di indirizzi IP utilizzando le colonne Inizio IP e Fine IP. Wildcards can be used to match IP ranges, for example `10.10.10.*` to `10.10.20.*`. Corrispondenza regola, Agente Include e Agente Escludi devono essere vuoti.

## Regole multiple combinate con OR

Per far corrispondere un bot utilizzando una combinazione di regole unite a un operatore OR (ad esempio, agente utente o indirizzo IP), fornite un nome identico per tutte le regole che desiderate combinare nel campo del nome bot. Le corrispondenze AND non sono supportate.

## Sovrascrivi tutte le regole con un file di caricamento

Select the **[!UICONTROL Overwrite existing rules]** checkbox to delete all existing rules and replace them with the rules defined in the upload file.

## Regole di esportazione

**[!UICONTROL Export Uploaded Bot File]** Il pulsante esporta tutte le regole definite nell'interfaccia utente in formato CSV.
