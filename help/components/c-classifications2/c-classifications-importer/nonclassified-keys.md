---
description: Le chiavi non classificate sono raggruppate nei rapporti sulla classificazione come un singolo elemento con etichetta Nessuno. Può essere utile rinominare None in modo più descrittivo.
seo-description: Le chiavi non classificate sono raggruppate nei rapporti sulla classificazione come un singolo elemento con etichetta Nessuno. Può essere utile rinominare None in modo più descrittivo.
seo-title: Tasti non classificati
solution: Analytics
subtopic: Classifications
title: Tasti non classificati
topic: Strumenti di amministrazione
uuid: b73a9161-0c6f-4c8d-900b-54ab2c36147c
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Tasti non classificati

Le chiavi non classificate sono raggruppate nei rapporti sulla classificazione come un singolo elemento con etichetta Nessuno. Può essere utile rinominare None in modo più descrittivo.

## Tasti non classificati {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Le chiavi non classificate sono raggruppate nei rapporti sulla classificazione come un singolo elemento etichettato *`None`*. Può essere utile rinominare *`None`* un elemento più descrittivo.

Ad esempio, se i codici di tracciamento contengono informazioni che delineano il tipo di campagna mobile a cui è associato il codice di tracciamento, Stai utilizzando la classificazione (Tipo campagna mobile) per raggruppare questi codici di monitoraggio in categorie come Mobile Web, iOS Application, Android Application e così via. Alcune campagne potrebbero non essere campagne mobili e pertanto non essere classificate con un tipo di campagna mobile. Tutti i codici di monitoraggio non classificati saranno raggruppati *`None`* nel [!UICONTROL Mobile Campaign Type] rapporto.

## Rinominare la chiave di classificazione None {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Procedura che descrive come rinominare una chiave non classificata visualizzata come *`none`* nel reporting.

1. Utilizzando il modulo di importazione, esportate le classificazioni in un file locale.
1. Aggiungere una riga al file e digitare [!DNL ~none~] nella colonna Chiave.
1. Nella riga aggiunta, digitate il nome più descrittivo nelle colonne di classificazione appropriate.

   Per seguire l'esempio riportato in questa documentazione, potresti digitare "campagna non mobile" in una colonna denominata [!UICONTROL Mobile Campaign Name].

   Questa voce rinomina *`None`* in *`non-mobile campaign`* nel [!UICONTROL Mobile Campaign Type] report.
1. [Importare nuovamente i dati](/help/components/c-classifications2/c-classifications-importer/import-file.md) nel sistema.
