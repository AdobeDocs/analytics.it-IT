---
description: Informazioni sul modello Origini dati, che forniscono un framework di dati idoneo all'invio di un set specifico di dati esterni a Origini dati.
subtopic: Data sources
title: Panoramica modello Origini dati
topic-fix: Developer and implementation
uuid: e768bcff-a996-44c7-a7f2-9a2c651ecad9
exl-id: d3122582-d392-4bd9-af2a-fb3d1292ba66
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 77%

---

# Panoramica modello Origini dati

Informazioni sul modello Origini dati, che forniscono un framework di dati idoneo all&#39;invio di un set specifico di dati esterni a Origini dati.

Il file modello generato da questa procedura guidata è progettato per aiutarti a iniziare l&#39;importazione. Non sei limitato alle colonne definite nel modello. Puoi aggiungere qualsiasi altra colonna che ti serve, a condizione che la metrica o la definizione sia supportata per il tipo di elaborazione dati selezionato.

Puoi visualizzare le metriche e le dimensioni supportate per ogni tipo nelle sezioni seguenti:

* [Registro web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md)
* [Traffico](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) (non più supportato)
* [Conversione](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md)
* [ID transazione](/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md)
* [ID visitatore](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md)
* [Elaborazione completa](/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md)

Ad esempio, per un tipo di dati ID visitatore, puoi aggiungere una colonna per qualsiasi metrica o dimensione elencata in [ID visitatore](/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md).

Una volta creato, puoi scaricare il modello, inserire i dati nel modello, quindi caricare i dati sul sito FTP Origini dati. Una volta elaborati dal server Origini dati, i dati importati sono disponibili per l&#39;uso nei rapporti di marketing.

Il modello Origine dati è un file [!DNL .txt] che puoi aprire con qualsiasi editor di testo. Tuttavia, è più semplice lavorare con il modello utilizzando Microsoft Excel o un&#39;altra applicazione di fogli di calcolo. Il contenuto del modello varia in base alle selezioni effettuate in [!UICONTROL Data Source Activation Wizard].

Per ulteriori informazioni, consulta [Riferimento file di importazione](/help/import/c-data-sources/datasrc-template/datasrc-import-file-reference.md) .
