---
description: Procedura che descrive come eliminare o rimuovere i dati di classificazione.
subtopic: Classifications
title: Eliminare i dati di classificazione
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 5%

---


# Eliminare i dati di classificazione

A volte è necessario rimuovere i dati di classificazione dopo il caricamento. Utilizzate `~empty~` o `~deletekey~`, a seconda di cosa desiderate rimuovere.

## Passaggi per rimuovere i dati di classificazione

La rimozione dei dati di classificazione comporta il caricamento di un file di classificazione contenente `~empty~` o `~deletekey~` nelle celle appropriate.

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Browser Export]**.
1. Seleziona la suite di rapporti e il set di dati da cui desideri rimuovere i dati di classificazione.
1. Regolate le impostazioni facoltative per filtrare i dati specifici che state cercando, quindi fate clic **[!UICONTROL Export File]**.
1. Una volta scaricato il file, aprite il file e sostituite eventuali valori di classificazione con `~empty~` o `~deletekey~`.
1. Salvate il file come file di testo delimitato da tabulazioni.
1. Fate clic **[!UICONTROL Import File]** e caricate nuovamente il file di classificazione salvato in  Adobe Analytics.

## Eliminazione di un singolo valore di classificazione

Più classificazioni possono appartenere alla stessa variabile. Ad esempio, potete avere 2 diverse classificazioni di  eVar1. Se si desidera rimuovere un solo valore classificato, sostituire il valore di classificazione con `~empty~`. Ad esempio:

| SKU magazzino ( eVar8) | Nome magazzino | Categoria magazzino |
| --- | --- | --- |
| 857467 | Maglione con collo a V | Vestiti da donna |
| 948203 | braccialetto per caviglia | Gioielli |
| 174391 | Pantaloni cordili bianchi | `~empty~` |

L&#39;utilizzo `~empty~` nella classificazione Categoria magazzino conserva i dati per la classificazione Nome magazzino. Il `~empty~` valore elimina solo i dati di classificazione per quella cella.

## Eliminazione di un&#39;intera riga di classificazione

Utilizzare `~deletekey~` in qualsiasi colonna per eliminare l&#39;intera riga di classificazione. Ad esempio:

| SKU magazzino ( eVar8) | Nome magazzino | Categoria magazzino |
| --- | --- | --- |
| 857467 | Maglione con collo a V | Vestiti da donna |
| 948203 | braccialetto per caviglia | Gioielli |
| 174391 | Pantaloni cordili bianchi | `~deletekey~` |

Utilizzando `~deletekey~` nella classificazione Categoria magazzino vengono eliminati tutti i dati di classificazione per il valore chiave `174391`. Diventa come se la riga non fosse mai stata classificata.

## Cascate e suggerimenti

* Se si utilizza `~deletekey~`, è necessario solo uno per riga in un file di classificazione.
* `~empty~` e `~deletekey~` devono essere corrispondenze *esatte* . Non sono consentiti spazi o maiuscole.
* Non è possibile eliminare i valori nella colonna chiave. Questi valori vengono passati direttamente nella variabile ed è permanente.
* Se si rimuove un valore di classificazione con sottoclassificazioni, anche queste sottocategorie vengono rimosse. Le classificazioni non possono esistere senza un valore chiave, e l&#39;elemento padre di una sottoclassificazione è il relativo valore chiave.
* È possibile rimuovere i dati di sottoclassificazione lasciando intatta la classificazione padre.
