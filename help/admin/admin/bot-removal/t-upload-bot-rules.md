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
source-git-commit: d0bd48684764a60b488d1e39c968ad70c743f1db

---


# Caricare regole bot

Per importare regole bot di importazione in massa, potete caricare un file CSV che definisca le regole.

Create un file CSV con le seguenti colonne, nell'ordine seguente:

| Colonna 1 | Colonna 2 | Colonna 3 | Colonna 4 | Colonna 5 |
|--- |--- |---|---|---|
| Nome bot | Inizio IP | Fine IP | Regola corrispondenza agente<br>(contiene o inizia con)</br> | Escludi agente<br>(limite di 255 caratteri)</br> |

Puoi definire tre tipi di regole bot:

* L'agente utente contiene o inizia con
* Indirizzo IP singolo o corrispondenza con caratteri jolly
* Corrispondenza intervallo IP

Ogni riga nel file di importazione può contenere solo una delle seguenti definizioni bot:

* **L'agente utente contiene o inizia con**: Fornite una stringa agente utente da far corrispondere nella colonna Agente. Specificate il tipo di corrispondenza da eseguire con il posizionamento *o* *con il* campo Corrispondenza agente. Un valore facoltativo può essere incluso nella colonna Agente esclusivo che definisce una o più stringhe delimitate dal vettore ( `|` ) che l'agente non contiene. Le corrispondenze stringa non sono sensibili alle maiuscole/minuscole. Entrambe le colonne Inizio IP e Fine IP devono essere vuote.

* **Indirizzo IP singolo o corrispondenza caratteri jolly**: Per associare un singolo indirizzo IP ( `10.10.10.1`) o un indirizzo IP jolly ( `10.10.*.*`), inserite lo stesso valore sia nelle colonne Inizio IP che Fine IP. Corrispondenza regola, Agente Include e Agente Escludi devono essere vuoti.

* **Corrispondenza intervallo IP**: Definite una serie di indirizzi IP utilizzando le colonne Inizio IP e Fine IP. I caratteri jolly possono essere utilizzati per associare ad esempio `10.10.10.*` intervalli IP `10.10.20.*`. Corrispondenza regola, Agente Include e Agente Escludi devono essere vuoti.

## Regole multiple combinate con OR

Per far corrispondere un bot utilizzando una combinazione di regole unite a un operatore OR (ad esempio, agente utente o indirizzo IP), fornite un nome identico per tutte le regole che desiderate combinare nel campo del nome bot. Le corrispondenze AND non sono supportate.

## Sovrascrivi tutte le regole con un file di caricamento

Selezionate la **[!UICONTROL Overwrite existing rules]** casella di controllo per eliminare tutte le regole esistenti e sostituirle con quelle definite nel file di caricamento.

## Regole di esportazione

**[!UICONTROL Export Uploaded Bot File]** Il pulsante esporta tutte le regole definite nell'interfaccia utente in formato CSV.
