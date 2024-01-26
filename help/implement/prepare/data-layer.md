---
title: Creare un livello di dati
description: Scopri cosa è un livello dati nell’implementazione di Analytics e come può essere utilizzato per mappare le variabili in Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 100%

---

# Creare un livello di dati

Un livello dati è un framework di oggetti JavaScript presenti sul sito che contiene i valori delle variabili utilizzati nell’implementazione di Analytics. Consente un controllo maggiore e una manutenzione più semplice quando si assegnano valori alle variabili di Analytics.

## Prerequisiti

[Creazione di un documento di progettazione della soluzione](solution-design.md): è importante che la tua organizzazione si allinei ai requisiti di tracciamento. Assicurati di aver preparato un documento di progettazione della soluzione prima di rivolgerti ai team di sviluppo della tua organizzazione.

## Flusso di lavoro

Generalmente, l’implementazione di Adobe Analytics utilizzando un livello dati segue questi passaggi:

1. **Collaborare con il team di sviluppo del sito per implementare un livello di dati**: il team di sviluppo del sito è principalmente responsabile della compilazione dell’oggetto di livello dati con valori corretti. Esamina questa pagina con il tuo team di sviluppo del sito per assicurarti che le aspettative siano allineate tra i team.

   >[!NOTE]
   >
   >Il rispetto delle specifiche dei livelli dati consigliate da Adobe è facoltativo. Se disponi già di un livello dati, oppure scegli di non seguire le specifiche di Adobe, assicurati che la tua organizzazione sia allineata sulle specifiche da seguire.

1. **Convalidare il livello dati utilizzando una console del browser**: una volta creato un livello dati, puoi convalidarne il funzionamento utilizzando la console per sviluppatori di qualsiasi browser. Puoi aprire la console per gli sviluppatori nella maggior parte dei browser utilizzando il tasto `F12`. Un esempio di valore della variabile è `adobeDataLayer.page.title`.
1. **Utilizzare la raccolta dati di Adobe Experience Platform per mappare gli oggetti del livello dati agli elementi di dati**: questo passaggio varia in base al metodo di implementazione della tua organizzazione:
   * **Se utilizzi l’estensione Web SDK**: mappa gli oggetti di livello dati sui campi XDM desiderati in Adobe Experience Platform Edge. Consulta [Mappatura delle variabili di Analytics](../aep-edge/variable-mapping.md) per determinare la mappatura del livello dati desiderata.
   * **Se utilizzi l’estensione Analytics**: crea elementi dati nei Tag della Raccolta dati di Adobe Experience Platform e assegnali agli oggetti livello dati desiderati. Quindi all’interno dell’estensione Analytics, assegna ogni elemento dati alla variabile di Analytics appropriata.

## Specifiche

Adobe consiglia di utilizzare il [Livello dati client di Adobe](https://github.com/adobe/adobe-client-data-layer/wiki) per implementazioni nuove o ristrutturate.

La tua organizzazione è libera di utilizzare altre specifiche del livello dati, ad esempio il [Livello dati digitale dell’esperienza del cliente](https://www.w3.org/2013/12/ceddl-201312.pdf), oppure un’altra specifica completamente personalizzata. L’allineamento a un livello dati coerente che soddisfi le esigenze della tua organizzazione è la cosa più importante.

I livelli dati sono estensibili; se hai dei requisiti specifici per la tua organizzazione, puoi includere oggetti nel tuo livello dati per soddisfare tali esigenze.

## Impostazione dei valori del livello dati

Generalmente i livelli dati generano lato server, facendo riferimento agli stessi oggetti utilizzati per creare il contenuto del sito. Stabilisci il livello dati del sito in base ai requisiti di tracciamento impostati nel [documento di progettazione della soluzione](solution-design.md) della tua organizzazione.

## Passaggi successivi

[Mappatura di oggetti livello dati su elementi dei dati](../launch/layer-to-elements.md): utilizza il livello dati del tuo sito in Adobe Experience Platform.
