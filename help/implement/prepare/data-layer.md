---
title: Creare un livello di dati
description: Scopri cosa è un livello di dati nell’implementazione di Analytics e come può essere utilizzato per mappare le variabili in Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 6a43a24cfe6a2a7f92a9613898660df41daf2c89
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 3%

---

# Creare un livello di dati

Un livello dati è un framework di oggetti JavaScript sul sito che contiene i valori delle variabili utilizzati nell’implementazione di Analytics. Consente un controllo maggiore e una manutenzione più semplice quando si assegnano valori alle variabili di Analytics.

## Prerequisiti

[Creare un documento di progettazione della soluzione](solution-design.md) - È importante che l’organizzazione si allinei ai requisiti di tracciamento. Assicurati di essere preparato con un documento di progettazione della soluzione prima di avvicinarti ai team di sviluppo della tua organizzazione.

## Flusso di lavoro

L’implementazione di Adobe Analytics tramite un livello dati in genere segue questi passaggi:

1. **Collaborare con il team di sviluppo del sito per implementare un livello di dati**: Il team di sviluppo del sito è principalmente responsabile della compilazione dell&#39;oggetto livello dati con valori corretti. Rivedi questa pagina con il tuo team di sviluppo del sito per assicurarti che le aspettative siano allineate tra i team.

   >[!NOTE]
   >
   >Le specifiche dei livelli dati consigliate di Adobe sono facoltative. Se disponi già di un livello di dati, o in altro modo scegli di non seguire le specifiche di Adobe, assicurati che l&#39;organizzazione sia allineata alle specifiche da seguire.
1. **Convalidare il livello dati utilizzando una console del browser**: Una volta creato un livello dati, puoi verificare che funzioni utilizzando qualsiasi console di sviluppo del browser. Puoi aprire la Developer Console nella maggior parte dei browser utilizzando `F12` chiave. Un valore variabile di esempio è `adobeDataLayer.page.title`.
1. **Utilizzare la raccolta dati di Adobe Experience Platform per mappare gli oggetti del livello dati agli elementi dati**: Questo passaggio varia in base al metodo di implementazione della tua organizzazione:
   * **Se utilizzi l’SDK per web**: Mappa gli oggetti livello dati desiderati sui campi XDM desiderati in Adobe Experience Platform Edge. Vedi [Mappatura delle variabili di Analytics](../aep-edge/variable-mapping.md) per determinare la mappatura del livello dati desiderata.
   * **Se utilizzi l’estensione Analytics**: Crea elementi dati in Tag in Raccolta dati di Adobe Experience Platform e assegnali agli oggetti livello dati desiderati. Quindi all’interno dell’estensione Analytics, assegna ogni elemento dati alla variabile Analytics appropriata.

## Specifiche

L&#39;Adobe consiglia di utilizzare [Livello dati client di Adobe](https://github.com/adobe/adobe-client-data-layer/wiki) per implementazioni nuove o ristrutturate.

La tua organizzazione è libera di utilizzare altre specifiche del livello dati, ad esempio [Livello dati digitale esperienza cliente](https://www.w3.org/2013/12/ceddl-201312.pdf)oppure un&#39;altra specifica personalizzata. L’allineamento a un livello di dati coerente che soddisfa le esigenze della tua organizzazione è il più importante.

I livelli dati sono estensibili; se hai dei requisiti specifici per la tua organizzazione, puoi includere oggetti nel livello dati per soddisfare tali esigenze.

## Impostazione dei valori del livello dati

I livelli dati generalmente generano lato server, facendo riferimento agli stessi oggetti utilizzati per creare il contenuto del sito. Stabilisci il livello di dati del sito in base ai requisiti di tracciamento impostati nel [documento di progettazione della soluzione](solution-design.md).

## Passaggi successivi

[Mappatura di oggetti livello dati su elementi dati](../launch/layer-to-elements.md): Utilizza il livello dati del tuo sito in Adobe Experience Platform.
