---
description: Procedura che descrive come caricare un file origini dati.
subtopic: Data sources
title: Caricare un file origini dati
topic: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
translation-type: tm+mt
source-git-commit: fb2a63432275c4ab621df263035400051ff6bb32
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 61%

---


# Caricare un file origini dati

Dopo aver preparato un file di dati Origini dati, invialo a Origini dati per l&#39;elaborazione. Adobe mantiene diversi server FTP Origini dati su cui puoi caricare i file Origini dati. Ricorda quanto segue sui server FTP Origini dati:

* Select FTP Info next to the Data Source entry in the [!UICONTROL Data Sources Manage] tab to see the FTP Host, Login, and Password information for the data source&#39;s FTP account. Chiunque abbia accesso a queste informazioni può caricare i dati nella tua suite di rapporti.
* Per motivi di sicurezza, gli account FTP vengono chiusi dopo 30 giorni di inattività.
* Gli account FTP sono specifici per l&#39;origine di dati. Non è possibile utilizzare un account FTP per caricare i file Origini di dati su più origini dati.

**Per caricare un file origini dati**

1. Utilizza un client FTP per inviare i dati al tuo sito FTP Origini di dati.

   (Disponibile nel collegamento Info FTP in Origini dati Manager).

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   The [!DNL .fin] file must have the exact same name as the Data Sources file, except for the file extension. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   Non caricare il file finché non è terminato il caricamento di tutti i file Origini dati. In caso contrario, Origini dati potrebbe tentare di elaborare un file incompleto.
1. Dopo il caricamento del file .fin, è importante uscire dal sito FTP Origini dati. Il motivo è che Analytics utilizza gli eventi di logout come trigger per indicare che i file sono pronti per l&#39;elaborazione.
1. Controlla la presenza di eventuali messaggi durante l&#39;elaborazione del file Origini dati.

   Origini dati Manager visualizza eventuali errori che si verificano durante l&#39;elaborazione del file.

