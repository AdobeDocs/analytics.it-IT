---
description: I tasti non classificati sono raggruppati nei rapporti di classificazione come una singola riga etichettata None. Può essere utile rinominarla in modo più descrittivo.
title: Tasti non classificati
feature: Classifications
exl-id: 37288c2d-f6f6-4343-87a1-3c3a7b56fe32
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 68%

---

# Tasti non classificati

I tasti non classificati sono raggruppati nei rapporti di classificazione come una singola riga etichettata None. Può essere utile rinominarla in modo più descrittivo.

## Tasti non classificati {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Tasti non classificati sono raggruppati nei rapporti di classificazione come una singola riga etichettata *`None`*. Può essere utile rinominare *`None`* in modo più descrittivo.

Ad esempio, supponiamo che i codici di tracciamento contengano informazioni che delineano il tipo di campagna mobile a cui è associato il codice di tracciamento. Stai utilizzando una classificazione (Tipo di campagna mobile) per raggruppare questi codici di tracciamento in categorie quali mobile, web, applicazione iOS, applicazione Android e così via. Alcune campagne potrebbero non essere campagne mobile e pertanto non essere classificate con un tipo di campagna mobile. Tutti i codici di tracciamento non classificati saranno raggruppati in *`None`* nel rapporto [!UICONTROL Mobile Campaign Type].

## Rinomina il tasto di classificazione None {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Per rinominare un tasto non classificato visualizzato come *`none`* nel reporting:

1. Utilizzando l’importazione, esporta le classificazioni in un file locale.
1. Aggiungi una riga al file e digita `~none~` nella colonna Tasto.
1. Nella riga aggiunta, digita il nome più descrittivo nella colonna o nelle colonne di classificazione appropriate.

   Per seguire l’esempio riportato in questa documentazione, potresti digitare “non-mobile campaign” (campagna non mobile) in una colonna denominata [!UICONTROL Mobile Campaign Type].

   Questa voce rinomina *`None`* in *`non-mobile campaign`* nel rapporto [!UICONTROL Mobile Campaign Type].

   ![Esempio di chiave non classificata](/help/components/classifications/importer/assets/non-classified-key.png)

1. [Importa di nuovo i dati](/help/components/classifications/importer/import-file.md) nel sistema.
