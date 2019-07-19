---
description: Le chiavi non classificate sono raggruppate nei rapporti di classificazione come una singola voce con etichetta Nessuno. Può essere utile rinominare Nessuno in un modo più descrittivo.
seo-description: Le chiavi non classificate sono raggruppate nei rapporti di classificazione come una singola voce con etichetta Nessuno. Può essere utile rinominare Nessuno in un modo più descrittivo.
seo-title: Tasti non classificati
solution: Analytics
subtopic: Classificazioni
title: Tasti non classificati
topic: Strumenti di amministrazione
uuid: b 73 a 9161-0 c 6 f -4 c 8 d -900 b -54 ab 2 c 36147 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tasti non classificati

Le chiavi non classificate sono raggruppate nei rapporti di classificazione come una singola voce con etichetta Nessuno. Può essere utile rinominare Nessuno in un modo più descrittivo.

## Non-classified keys {#concept_233E51DDF3084FF7B7EA89381C73C5FF}

Non-classified keys are grouped together in classification reports as a single line item labeled *`None`*. It can be useful to rename *`None`* to something more descriptive.

Ad esempio, supponiamo che i codici di monitoraggio contengano informazioni che delineano il tipo di campagna mobile con cui è associato il codice di tracciamento. State utilizzando classificazione (Tipo di campagna mobile) per raggruppare questi codici di tracciamento in categorie come Web per dispositivi mobili, applicazione iOS, Applicazione Android e così via. Alcune campagne potrebbero non essere campagne mobili e non sono quindi classificate con un tipo di campagna mobile. All non-classified tracking codes would be grouped under *`None`* in the [!UICONTROL Mobile Campaign Type] report.

## Rename the None classification key {#task_8CD595DA82AA44D08CEF002B588C3C30}

<!-- 

t_rename_classification_none.xml

 -->

Steps that describe how to rename a non-classified key that displays as *`none`* in reporting.

1. Mediante Importazione, esportate le classificazioni in un file locale.
1. Add a row to the file, and type [!DNL ~none~] in the Key column.
1. Nella riga che hai aggiunto, digita il nome più descrittivo nelle colonne di classificazione appropriate.

   To follow the example in this documentation, you might type "non-mobile campaign" in a column named [!UICONTROL Mobile Campaign Name].

   This entry renames *`None`* to *`non-mobile campaign`* in the [!UICONTROL Mobile Campaign Type] report.
1. [Reimportate i dati](../../../components/c-classifications2/c-classifications-importer/import-file.md#concept_F88785E2BDFD448CB5D1DA3491466B0D) nel sistema.
