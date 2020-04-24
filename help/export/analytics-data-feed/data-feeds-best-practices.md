---
description: 'Di seguito sono riportate alcune best practice per l''elaborazione e la distribuzione dei feed di dati. Dovrebbe '
keywords: Data Feed;best practices;traffic spike;hourly;ftp
title: Procedure consigliate e informazioni generali
uuid: f2d6c13a-5d4e-4fc2-8baa-28c69f0cf5f6
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Best practice

Di seguito sono riportate alcune best practice per l&#39;elaborazione e la distribuzione dei feed di dati.

* Assicurati di comunicare anticipatamente eventuali picchi di traffico previsti. La latenza influisce direttamente sul tempo di elaborazione dei feed di dati. Consultate [Pianificare un picco](/help/admin/c-traffic-management/t-traffic-schedule-spike.md) di traffico nella guida utente di amministrazione.
* I feed di dati non contengono un contratto a livello di servizio, a meno che non sia espressamente indicato nel contratto con Adobe. I feed vengono in genere consegnati entro diverse ore dal passaggio della finestra di rapporto, ma occasionalmente possono richiedere fino a 12 ore o più.
* Assicurati di avere ampio spazio sul tuo sito FTP. Rimuovere regolarmente i file dalla destinazione in modo da non esaurire inavvertitamente lo spazio su disco.
* I feed orari utilizzano il processo di consegna di più file più veloce. Considerate l&#39;utilizzo di feed di file multipli orari se la consegna tempestiva è una priorità elevata per l&#39;organizzazione.
* Se utilizzate sFTP, non leggete o eliminate i file con un `.part` suffisso. Il `.part` suffisso indica che il file è stato parzialmente trasferito. Una volta trasferito il file, il `.part` suffisso scompare.
* Se automatizzate il processo di assimilazione dei feed, prendete in considerazione la possibilità che un file possa essere trasferito più volte. I file duplicati possono essere inviati dall&#39;utente o raramente da Adobe.
