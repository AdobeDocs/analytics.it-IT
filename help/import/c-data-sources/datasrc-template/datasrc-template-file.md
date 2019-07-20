---
description: Informazioni sul modello Origini dati, che forniscono un framework di dati idoneo all'invio di un set specifico di dati esterni a Origini dati.
seo-description: Informazioni sul modello Origini dati, che forniscono un framework di dati idoneo all'invio di un set specifico di dati esterni a Origini dati.
seo-title: Panoramica del modello Origini dati
solution: Analytics
subtopic: Origini dati
title: Panoramica del modello Origini dati
topic: Sviluppatore e implementazione
uuid: e 768 bcff-a 996-44 c 7-a 7 f 2-9 a 2 c 651 ecad 9
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica del modello Origini dati

Informazioni sul modello Origini dati, che forniscono un framework di dati idoneo all'invio di un set specifico di dati esterni a Origini dati.

Il file modello generato da questa procedura guidata è progettato per aiutarti a iniziare l'importazione. Non sei limitato alle colonne definite nel modello. Puoi aggiungere qualsiasi altra colonna che ti serve, a condizione che la metrica o la definizione sia supportata per il tipo di elaborazione dati selezionato.

Puoi visualizzare le metriche e le dimensioni supportate per ogni tipo nelle sezioni seguenti:

* [Registro web](../../../import/c-data-sources/c-datasrc-types/datasrc-web-log.md#concept_E25D89C8B90A41FEB7DF4E936CACEE2B)
* [Traffico](../../../import/c-data-sources/c-datasrc-types/datasrc-traffic.md#concept_F50D3AC6A5544D06BB81EF1E279576BC) (non più supportato)
* [Conversione  ](../../../import/c-data-sources/c-datasrc-types/datasrc-conversion.md#concept_FA3B6557128649C0B662E95C6B617FA0)
* [ID transazione](../../../import/c-data-sources/c-datasrc-types/datasrc-transactionid.md#concept_A97302E9EC45468A8F30285FACE8C776)
* [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5)
* [Elaborazione completa](../../../import/c-data-sources/c-datasrc-types/datasrc-full-processing.md#concept_975B1BB9981D49139B4EE09C78CDE6ED)

For example, for a Visitor ID data type, you can add a column for any metric or dimensions listed in [Visitor ID](../../../import/c-data-sources/c-datasrc-types/datasrc-visitorid.md#concept_1CFAA61D57A84B22A41F7A8E0DFCAAB5).

Una volta creato, puoi scaricare il modello, inserire i dati nel modello, quindi caricare i dati sul sito FTP Origini dati. Una volta elaborati dal server Origini dati, i dati importati sono disponibili per l'uso nei rapporti di marketing.

The Data Source template is a [!DNL .txt] file that you can open with any text editor. Tuttavia, è più semplice lavorare con il modello utilizzando Microsoft Excel o un'altra applicazione di fogli di calcolo. The template content varies based on your selections in the [!UICONTROL Data Source Activation Wizard].

See [Import File Reference](../../../import/c-data-sources/datasrc-template/datasrc-import-file-reference.md#concept_472095E1D011434D98A21C101A4618BD) for additional details.
