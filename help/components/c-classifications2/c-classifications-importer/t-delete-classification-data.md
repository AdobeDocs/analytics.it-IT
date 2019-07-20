---
description: Procedura che descrive come eliminare o rimuovere i dati di classificazione.
seo-description: Procedura che descrive come eliminare o rimuovere i dati di classificazione.
seo-title: Eliminare i dati di classificazione
solution: Analytics
subtopic: Classificazioni
title: Eliminare i dati di classificazione
topic: Strumenti di amministrazione
uuid: 5 b 1 b 0 ac 7-ee 52-4 fd 8-b 98 e -25283595 cf 0 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Eliminare i dati di classificazione

Procedura che descrive come eliminare o rimuovere i dati di classificazione.

1. Click **[!UICONTROL Admin]** &gt; **[!UICONTROL Classification Importer]**.
1. Fai clic su **[!UICONTROL Browser Export]**.
1. Seleziona la suite di rapporti e il set di dati da cui rimuovere i dati classificazione.
1. Adjust any optional settings to filter specific data you're looking for, then click **[!UICONTROL Export File]**.
1. Once the file has been downloaded, open the file and replace any classification values you wish to delete with [!DNL ~empty~].

   Alternatively, use [!DNL ~deletekey~]. Questo comando considera la classificazione come se non fosse mai avvenuta per la chiave specificata. La tabella viene rimossa completamente e tutti i dati delle colonne vengono rimossi dalle tabelle di ricerca.

   **Controlla**: È necessaria una sola colonna contenente [!DNL ~il valore delta~]. The [!DNL ~empty~] command works at the cell level (key and column combination), so you need [!DNL ~empty~] in the classification column you want to remove. However, [!DNL ~deletekey~] works at the row level (the key and all associated metadata), so it only needs to appear in one of the columns in the row. Questo comando rimuove tutti i metadati dalla riga. Adobe interprets this as though the key was never classified, and displays it in the [None](../../../components/c-classifications2/c-classifications-importer/nonclassified-keys.md#concept_233E51DDF3084FF7B7EA89381C73C5FF) category.

1. Save the file, and upload it using the [!UICONTROL Import File] tab.

   After you upload the file, the system recognizes [!DNL ~empty~] as a command to delete that classification value.

   **Proprietà di questo comando**

* [!DNL ~vuoto deve~] essere minuscola senza spazi. Le seguenti voci non sono valide:

   * [!DNL ~EMPTY~]
   * [!DNL ~ empty ~]
   * [!DNL ~Vuoto~]

* Non è possibile eliminare valori all'interno della colonna della chiave. Questi sono dati passati direttamente al reporting ed è permanente.
* Se stai rimuovendo un valore di classificazione con sottoclassi, vengono rimossi. Le classificazioni non possono esistere senza un valore chiave, e l'elemento principale di una sottoclasse è il suo valore chiave.
* È possibile rimuovere i dati di classificazione lasciando intatto la classificazione principale.

