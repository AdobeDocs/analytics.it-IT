---
description: Procedura che descrive come caricare un file origini dati.
seo-description: Procedura che descrive come caricare un file origini dati.
seo-title: Caricare un file Origini dati
solution: Analytics
subtopic: Origini dati
title: Caricare un file Origini dati
topic: Sviluppatore e implementazione
uuid: 5 a 9 dde 91-1297-47 e 5-9393-611 b 40413 c 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caricare un file Origini dati

Procedura che descrive come caricare un file origini dati.

Dopo aver preparato un file di dati Origini dati, invialo a Origini dati per l'elaborazione. Adobe mantiene diversi server FTP Origini dati su cui puoi caricare i file Origini dati. Ricorda quanto segue sui server FTP Origini dati:

* Select FTP Info next to the Data Source entry in the [!UICONTROL Data Sources Manage] tab to see the FTP Host, Login, and Password information for the data source’s FTP account. Chiunque abbia accesso a queste informazioni può caricare i dati nella tua suite di rapporti.
* Per motivi di sicurezza, gli account FTP vengono chiusi dopo 30 giorni di inattività.
* Gli account FTP sono specifici per l'origine di dati. Non è possibile utilizzare un account FTP per caricare i file Origini di dati su più origini dati.

**Per caricare un file origini dati**

1. Utilizza un client FTP per inviare i dati al tuo sito FTP Origini di dati.

   (Disponibile nel collegamento Info FTP in Origini dati Manager).

1. Upload a [!DNL .fin] file to notify Adobe that the Data Sources file upload is complete.

   The [!DNL .fin] file must have the exact same name as the Data Sources file, except for the file extension. Adobe does not queue the Data Sources file for processing until you upload the [!DNL .fin] file.

   Non caricare il file finché non è terminato il caricamento di tutti i file Origini dati. In caso contrario, Origini dati potrebbe tentare di elaborare un file incompleto.
1. Controlla la presenza di eventuali messaggi durante l'elaborazione del file Origini dati.

   Origini dati Manager visualizza eventuali errori che si verificano durante l'elaborazione del file.

