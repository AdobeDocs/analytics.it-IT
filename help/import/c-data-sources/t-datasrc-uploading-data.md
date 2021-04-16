---
description: Procedura che descrive come caricare un file origini dati.
subtopic: Data sources
title: Caricare un file origini dati
topic-fix: Developer and implementation
uuid: 5a9dde91-1297-47e5-9393-611b40413c17
exl-id: 8b7fa32c-01f2-452b-bf8e-8a81da266926
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 61%

---

# Caricare un file origini dati

Dopo aver preparato un file di dati Origini dati, invialo a Origini dati per l&#39;elaborazione. Adobe mantiene diversi server FTP Origini dati su cui puoi caricare i file Origini dati. Ricorda quanto segue sui server FTP Origini dati:

* Seleziona Informazioni FTP accanto alla voce Origine dati nella scheda [!UICONTROL Data Sources Manage] per visualizzare le informazioni relative a host FTP, login e password per l&#39;account FTP dell&#39;origine dati. Chiunque abbia accesso a queste informazioni può caricare i dati nella tua suite di rapporti.
* Per motivi di sicurezza, gli account FTP vengono chiusi dopo 30 giorni di inattività.
* Gli account FTP sono specifici per l&#39;origine di dati. Non è possibile utilizzare un account FTP per caricare i file Origini di dati su più origini dati.

**Per caricare un file origini dati**

1. Utilizza un client FTP per inviare i dati al tuo sito FTP Origini di dati.

   (Disponibile nel collegamento Info FTP in Origini dati Manager).

1. Carica un file [!DNL .fin] per notificare ad Adobe il completamento del caricamento del file Origini dati.

   Il file [!DNL .fin] deve avere esattamente lo stesso nome del file Origini dati, ad eccezione dell&#39;estensione del file. Adobe non mette in coda il file Origini dati per l&#39;elaborazione finché non carichi il file [!DNL .fin] .

   Non caricare il file finché non è terminato il caricamento di tutti i file Origini dati. In caso contrario, Origini dati potrebbe tentare di elaborare un file incompleto.
1. Dopo il caricamento del file .fin , è importante disconnettersi dal sito FTP Origini dati. Il motivo è che Analytics utilizza gli eventi di logout come attivatore per indicare che i file sono pronti per l’elaborazione.
1. Controlla la presenza di eventuali messaggi durante l&#39;elaborazione del file Origini dati.

   Origini dati Manager visualizza eventuali errori che si verificano durante l&#39;elaborazione del file.
