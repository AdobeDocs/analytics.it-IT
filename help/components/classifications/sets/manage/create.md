---
title: Creare un set di classificazione
description: Campi e descrizioni disponibili durante la creazione di un set di classificazione.
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 7%

---

# Creare un set di classificazione

Puoi utilizzare Gestione set di classificazione per creare un set di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > **[!UICONTROL Add]**

Quando crei un set di classificazione, sono disponibili i seguenti campi.

* **[!UICONTROL Name]**: campo di testo utilizzato per identificare il set di classificazione. Questo campo non può essere modificato al momento della creazione, ma può essere rinominato in un secondo momento.
* **[!UICONTROL Column Name]**: nome della prima dimensione di classificazione da creare. Questo campo è il nome della dimensione utilizzato in Analysis Workspace e il nome della colonna quando si esportano i dati di classificazione. Puoi aggiungere altri nomi di colonna dopo la creazione del set di classificazione.
* **[!UICONTROL Type]**: pulsanti di scelta che indicano il tipo di classificazione.
   * **[!UICONTROL Primary]**: applica alle dimensioni raccolte in Analytics. Sono un modo per raggruppare (classificare) i valori delle dimensioni granulari in livelli di dati più significativi. Ad esempio, potrebbe essere utile raggruppare le parole chiave di ricerca interna in categorie di ricerca interna per comprendere meglio i temi nei dati di ricerca.
   * **[!UICONTROL Lookup]**: comunemente definita figlio o sottoclassificazioni, una tabella di ricerca è una classificazione di una classificazione primaria. Si tratta di metadati relativi a un valore di classificazione, anziché alla dimensione originale. Ad esempio, la variabile di prodotto potrebbe avere una classificazione primaria di &quot;Codice colore&quot;. Una tabella di ricerca di &quot;Nome colore&quot; può quindi essere allegata a &quot;Codice colore&quot; per spiegare ulteriormente il significato di ciascun codice.
* **[!UICONTROL Subscriptions]** Le suite di rapporti e le dimensioni a cui si applica questo set di classificazione. Puoi aggiungere più combinazioni di suite di rapporti e dimensioni a un set di classificazione.

![Creare un set di classificazione](../../assets/classification-set-create.png)

Se esiste un set di classificazione per una determinata suite di rapporti + variabile, la classificazione viene aggiunta allo schema. Una determinata combinazione di suite di rapporti e variabile non può appartenere a più set di classificazione.
