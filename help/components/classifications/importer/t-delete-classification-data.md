---
description: Passaggi che descrivono come eliminare o rimuovere i dati di classificazione.
title: Eliminare i dati di classificazione
feature: Classifications
exl-id: 2b156e66-3090-4048-8192-a412320e3be3
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 5%

---

# Eliminare i dati di classificazione

A volte è necessario rimuovere i dati di classificazione dopo averli caricati. Utilizza uno dei seguenti `~empty~` o `~deletekey~`, a seconda di ciò che si desidera rimuovere.

## Passaggi per rimuovere i dati di classificazione

La rimozione dei dati di classificazione comporta il caricamento di un file di classificazione contenente `~empty~` o `~deletekey~` nelle caselle corrispondenti.

1. Fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Browser Export]**.
1. Seleziona la suite di rapporti e il set di dati da cui desideri rimuovere i dati di classificazione.
1. Regola eventuali impostazioni opzionali per filtrare dati specifici che stai cercando, quindi fai clic su **[!UICONTROL Export File]**.
1. Una volta scaricato il file, aprilo e sostituisci eventuali valori di classificazione con uno dei seguenti `~empty~` o `~deletekey~`.
1. Salvare il file come file di testo delimitato da tabulazioni.
1. Clic **[!UICONTROL Import File]**, e carica di nuovo il file di classificazione salvato in Adobe Analytics.

## Eliminazione di un singolo valore di classificazione

Più classificazioni possono appartenere alla stessa variabile. Ad esempio, puoi avere 2 diverse classificazioni di eVar1. Se desideri rimuovere solo un singolo valore classificato, sostituisci il valore di classificazione con `~empty~`. Ad esempio:

| SKU inventario (eVar8) | Nome inventario | Categoria magazzino |
| --- | --- | --- |
| 857467 | Maglione a V | Abbigliamento da donna |
| 948203 | Bracciale alla caviglia | Gioielli |
| 174391 | Pantaloni corduroy bianchi | `~empty~` |

Utilizzo di `~empty~` nella classificazione Categoria magazzino conserva comunque i dati per la classificazione Nome magazzino. Il `~empty~` Il valore elimina solo i dati di classificazione per quella cella.

## Eliminazione di un’intera riga di classificazione

Utilizzare `~deletekey~` in qualsiasi colonna per eliminare l’intera riga di classificazione. Ad esempio:

| SKU inventario (eVar8) | Nome inventario | Categoria magazzino |
| --- | --- | --- |
| 857467 | Maglione a V | Abbigliamento da donna |
| 948203 | Bracciale alla caviglia | Gioielli |
| 174391 | Pantaloni corduroy bianchi | `~deletekey~` |

Utilizzo di `~deletekey~` nella classificazione Categoria magazzino elimina tutti i dati di classificazione per il valore chiave `174391`. Diventa come se la riga non fosse mai stata classificata.

## Insidie e suggerimenti

* Se si utilizza `~deletekey~`, ne serve solo uno per riga in un file di classificazione.
* `~empty~` e `~deletekey~` deve essere *esatto* corrisponde a. Non sono consentiti spazi o maiuscole.
* Non è possibile eliminare i valori all’interno della colonna chiave; questi valori vengono passati direttamente nella variabile e sono permanenti.
* Se rimuovi un valore di classificazione con sottoclassificazioni, anche queste vengono rimosse. Le classificazioni non possono esistere senza un valore chiave e il valore chiave è l’elemento padre di una sottoclassificazione.
* È possibile rimuovere i dati di sottoclassificazione lasciando intatta la classificazione principale.
