---
description: Passaggi che descrivono come eliminare o rimuovere i dati di classificazione.
subtopic: Classifications
title: Eliminare i dati di classificazione
feature: Admin Tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 5%

---

# Eliminare i dati di classificazione

A volte è necessario rimuovere i dati di classificazione dopo il caricamento. Utilizzare `~empty~` o `~deletekey~`, a seconda di ciò che si desidera rimuovere.

## Passaggi per rimuovere i dati di classificazione

La rimozione dei dati di classificazione comporta il caricamento di un file di classificazione contenente `~empty~` o `~deletekey~` nelle celle appropriate.

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Browser Export]**.
1. Seleziona la suite di rapporti e il set di dati da cui desideri rimuovere i dati di classificazione.
1. Regola le impostazioni facoltative per filtrare i dati specifici che stai cercando, quindi fai clic su **[!UICONTROL Export File]**.
1. Una volta scaricato il file, apri il file e sostituisci eventuali valori di classificazione con `~empty~` o `~deletekey~`.
1. Salvare il file come file di testo delimitato da tabulazioni.
1. Fai clic su **[!UICONTROL Import File]** e carica di nuovo il file di classificazione salvato in Adobe Analytics.

## Eliminazione di un singolo valore di classificazione

Più classificazioni possono appartenere alla stessa variabile. Ad esempio, puoi avere 2 diverse classificazioni di eVar1. Se desideri rimuovere un solo valore classificato, sostituisci il valore di classificazione con `~empty~`. Ad esempio:

| SKU inventario (eVar8) | Nome magazzino | Categoria magazzino |
| --- | --- | --- |
| 857467 | Maglione a V | Abbigliamento da donna |
| 948203 | Bracciale a caviglia | Gioielli |
| 174391 | Pantaloni cordua bianchi | `~empty~` |

Se si utilizza `~empty~` nella classificazione Categoria inventario, i dati vengono mantenuti per la classificazione Nome inventario. Il valore `~empty~` elimina solo i dati di classificazione per quella cella.

## Eliminazione di un’intera riga di classificazione

Utilizza `~deletekey~` in qualsiasi colonna per eliminare l’intera riga di classificazione. Ad esempio:

| SKU inventario (eVar8) | Nome magazzino | Categoria magazzino |
| --- | --- | --- |
| 857467 | Maglione a V | Abbigliamento da donna |
| 948203 | Bracciale a caviglia | Gioielli |
| 174391 | Pantaloni cordua bianchi | `~deletekey~` |

Utilizzando `~deletekey~` nella classificazione Categoria inventario vengono eliminati tutti i dati di classificazione per il valore chiave `174391`. Diventa come se la riga non fosse mai stata classificata.

## Insidie e suggerimenti

* Se utilizzi `~deletekey~`, ne serve solo uno per riga in un file di classificazione.
* `~empty~` e  `~deletekey~` devono essere  ** exactmatch. Non sono consentiti spazi o maiuscole.
* Non è possibile eliminare i valori all’interno della colonna chiave. Questi valori vengono passati direttamente nella variabile ed è permanente.
* Se rimuovi un valore di classificazione con sottoclassificazioni, anche queste sottoclassificazioni vengono rimosse. Le classificazioni non possono esistere senza un valore chiave e l’elemento padre di una sottoclassificazione è il suo valore chiave.
* È possibile rimuovere i dati di sottoclassificazione lasciando intatta la classificazione padre.
