---
title: Panoramica delle classificazioni
description: Personalizza il raggruppamento di elementi dimensionali.
feature: Classifications
exl-id: 0d2c77ea-610f-48e0-b6a2-6e91794783b1
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 38%

---

# Panoramica delle classificazioni

Una classificazione è un modo per classificare i dati delle variabili di Analytics e visualizzarli in modi diversi quando si generano i rapporti. È possibile stabilire una relazione tra un valore di variabile e i metadati correlati a tale valore. Le classificazioni possono essere utilizzate nella maggior parte delle dimensioni personalizzate, ad esempio [Codice di tracciamento](/help/components/dimensions/tracking-code.md), [prop](/help/components/dimensions/prop.md) e [eVar](/help/components/dimensions/evar.md).

**I set di classificazione** sono il metodo principale per classificare i dati. **Le regole di classificazione** e **Importazione classificazioni** sono metodi legacy per la classificazione dei dati. Tutti i dati di classificazione funzionano allo stesso modo nei rapporti; puoi combinare questi metodi per adattarli al meglio al flusso di lavoro della tua organizzazione.

* **Set di classificazione**: crea e gestisci le classificazioni e le relative regole in un’unica interfaccia semplificata.
* **Regole di classificazione** (legacy): crea regole che assegnano un dato elemento dimensione a un elemento dimensione di classificazione. Questo metodo per classificare i dati è ideale quando una dimensione incontra spesso nuovi valori univoci o quando le classificazioni manuali sarebbero frequenti e onerose.
* **Importazione classificazioni** (legacy): esporta un foglio di calcolo modello con elementi dimensionali in ogni riga. Le colonne rappresentano ogni classificazione per una dimensione. Questo metodo di classificazione dei dati è ideale quando tutti gli elementi dimensionali sono noti e non richiedono aggiornamenti frequenti.

Una singola dimensione può avere più dimensioni di classificazione. Ad esempio, puoi classificare i [!UICONTROL Product IDs] con attributi di prodotto aggiuntivi, quali nome del prodotto, colore, dimensione, descrizione e SKU. Ciascuno di questi attributi sarebbe una dimensione di classificazione separata appartenente alla stessa dimensione principale. L’aumento dei rapporti con questi attributi offre opportunità di reporting più approfondite e complesse. Una volta che una dimensione contiene dati di classificazione, la dimensione di classificazione è disponibile nei rapporti che contengono solo elementi dimensionali di classificazione. Qualsiasi elemento dimensione padre che non contiene un valore di classificazione è raggruppato in [Non specificato](/help/technotes/unspecified.md)
