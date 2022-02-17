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

A volte è necessario rimuovere i dati di classificazione dopo il caricamento. Utilizza `~empty~` o `~deletekey~`, a seconda di cosa si desidera rimuovere.

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

Utilizzo `~empty~` nella classificazione Categoria inventario vengono mantenuti i dati per la classificazione Nome inventario. La `~empty~` elimina solo i dati di classificazione per quella cella.

## Eliminazione di un’intera riga di classificazione

Utilizzo `~deletekey~` in qualsiasi colonna per eliminare l’intera riga di classificazione. Ad esempio:

| SKU inventario (eVar8) | Nome magazzino | Categoria magazzino |
| --- | --- | --- |
| 857467 | Maglione a V | Abbigliamento da donna |
| 948203 | Bracciale a caviglia | Gioielli |
| 174391 | Pantaloni cordua bianchi | `~deletekey~` |

Utilizzo `~deletekey~` nella classificazione Categoria inventario vengono eliminati tutti i dati di classificazione per il valore chiave `174391`. Diventa come se la riga non fosse mai stata classificata.

## Insidie e suggerimenti

* Se utilizzi `~deletekey~`, basta una riga per riga in un file di classificazione.
* `~empty~` e `~deletekey~` devono *esatto* corrisponde. Non sono consentiti spazi o maiuscole.
* Non è possibile eliminare i valori all’interno della colonna chiave. Questi valori vengono passati direttamente nella variabile ed è permanente.
* Se rimuovi un valore di classificazione con sottoclassificazioni, anche queste sottoclassificazioni vengono rimosse. Le classificazioni non possono esistere senza un valore chiave e l’elemento padre di una sottoclassificazione è il suo valore chiave.
* È possibile rimuovere i dati di sottoclassificazione lasciando intatta la classificazione padre.
