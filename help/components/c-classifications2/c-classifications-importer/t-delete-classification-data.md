---
description: Procedura che descrive come eliminare o rimuovere i dati di classificazione.
solution: Analytics
subtopic: Classifications
title: Eliminare i dati di classificazione
topic: Admin tools
uuid: 5b1b0ac7-ee52-4fd8-b98e-25283595cf0c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Eliminare i dati di classificazione

Procedura che descrive come eliminare o rimuovere i dati di classificazione.

1. Fai clic su **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Browser Export]**.
1. Seleziona la suite di rapporti e il set di dati da cui desideri rimuovere i dati di classificazione.
1. Regolate le impostazioni facoltative per filtrare i dati specifici che state cercando, quindi fate clic **[!UICONTROL Export File]**.
1. Una volta scaricato il file, aprite il file e sostituite i valori di classificazione che desiderate eliminare con [!DNL ~vuoti~].

   In alternativa, utilizzate [!DNL ~deletekey~]. Questo comando considera la classificazione come se non si fosse mai verificata per la chiave specificata. La rimozione completa e tutti i dati delle colonne dalle tabelle di ricerca.

   **Caveat**: È sufficiente una colonna contenente [!DNL ~deleteKey~]. Il comando [!DNL ~vuoto~] funziona a livello di cella (combinazione di tasti e colonne), pertanto è necessario [!DNL ~vuoto~] nella colonna classificazione che si desidera rimuovere. Tuttavia, [!DNL ~deleteKey~] funziona a livello di riga (la chiave e tutti i metadati associati), pertanto deve essere visualizzato solo in una delle colonne della riga. Questo comando rimuove tutti i metadati dalla riga. Adobe interpreta questo concetto come se la chiave non fosse mai stata classificata e la visualizzi nella categoria [Nessuno](/help/components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF) .

1. Salvate il file e caricatelo utilizzando la [!UICONTROL Import File] scheda.

   Dopo aver caricato il file, il sistema riconosce [!DNL ~vuoto~] come comando per eliminare il valore di classificazione.

   **Proprietà di questo comando**

* [!DNL ~vuoto~] deve essere minuscolo senza spazi. Le seguenti voci non sono valide:

   * [!DNL ~VUOTO~]
   * [!DNL ~ empty ~]
   * [!DNL ~Vuoto~]

* Non è possibile eliminare i valori nella colonna chiave. Si tratta di dati passati direttamente nel reporting ed è permanente.
* Se si rimuove un valore di classificazione con sottoclassificazioni, vengono anche rimossi. Le classificazioni non possono esistere senza un valore chiave, e l'elemento padre di una sottoclassificazione è il relativo valore chiave.
* È possibile rimuovere i dati di sottoclassificazione lasciando intatta la classificazione padre.

