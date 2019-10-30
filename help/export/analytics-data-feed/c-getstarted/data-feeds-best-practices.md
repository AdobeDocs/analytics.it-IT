---
description: 'Di seguito sono riportate alcune best practice per l''elaborazione e la distribuzione dei feed di dati. Dovrebbe '
keywords: Feed dati;best practice;impennata del traffico;ora;ftp
seo-description: 'Di seguito sono riportate alcune best practice per l''elaborazione e la distribuzione dei feed di dati. Dovrebbe '
seo-title: Procedure consigliate e informazioni generali
solution: Analytics
title: Procedure consigliate e informazioni generali
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Procedure consigliate e informazioni generali

Di seguito sono riportate alcune best practice per l'elaborazione e la distribuzione dei feed di dati. È necessario:

* Si prevede che i feed di dati vengano consegnati entro 12 ore dalla fine di un determinato periodo di tempo, il 95% del tempo.

   Ad esempio, se disponete di un feed orario, la richiesta di feed dati per le 3-4 del mattino dovrebbe essere consegnata entro le 16.00 del 95% del tempo. I feed di dati per le suite di rapporti con un volume di traffico elevato possono richiedere più tempo per l’elaborazione e la distribuzione, in particolare se sono configurati come feed giornalieri anziché come feed orari.
* Assicurati di [comunicare anticipatamente eventuali picchi](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) di traffico previsti. Qualsiasi latenza upstream ha un impatto diretto sulla velocità di avvio del processo di feed di dati.
* Assicurati di avere ampio spazio sul tuo sito FTP. Pulirlo regolarmente in modo da non esaurire inavvertitamente lo spazio su disco.
* Quando cambi le credenziali FTP, accertati che siano aggiornate nel sistema di feed dati di Adobe.
* Se possibile, utilizzare la consegna oraria. Consente di ridurre e velocizzare la produzione e la trasmissione dei file.
* Considerate l’utilizzo della distribuzione "su più file" (in genere con i feed giornalieri di grandi dimensioni). La distribuzione di più file interrompe il singolo file monolitico in file più piccoli e li distribuisce tutti allo stesso tempo. Anche in questo caso, file più piccoli rendono più veloce la creazione, la decompressione e la trasmissione dei dati.
* Se utilizzate sFTP come metodo di consegna, non leggete e non eliminate i file con suffisso ".part". Il suffisso ".part" indica che il file è stato parzialmente trasferito, ma non è completo. Una volta trasferito il file, il nome verrà rinominato senza il suffisso ".part".
* Create il processo ETL partendo dal presupposto che, a volte, un file possa essere trasferito più volte. In caso contrario, potresti ritrovarti con dati duplicati.
