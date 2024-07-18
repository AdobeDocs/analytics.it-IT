---
description: Di seguito sono riportate alcune best practice per l’elaborazione e la distribuzione di feed di dati.
keywords: Feed dati;best practice;picco di traffico;ogni ora;ftp
title: Best practice e informazioni generali
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 6b42fc4a383b05a3630cbba7c5bce6b4561a9419
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 0%

---

# Best practice per i feed dati

Di seguito sono riportate alcune best practice per l’elaborazione e la distribuzione di feed di dati.

* Assicurati di comunicare in anticipo eventuali picchi di traffico previsti. La latenza influisce direttamente sul tempo di elaborazione dei feed di dati. Vedi [Pianificare un picco di traffico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md) nella guida utente dell&#39;amministratore.

* I feed di dati non contengono un accordo sui livelli di servizio, a meno che non sia esplicitamente indicato nel contratto con Adobe. I feed vengono generalmente consegnati entro diverse ore dal termine del periodo definito per la generazione del rapporto, tuttavia possono occasionalmente richiedere fino a 12 ore o più.

* I feed orari che utilizzano più file elaborano il processo più veloce. Valuta l’utilizzo di feed di file multipli orari se una consegna tempestiva è una priorità elevata per la tua organizzazione.

* Se automatizzi il processo di acquisizione dei feed, considera la possibilità che hit e file possano essere trasferiti più di una volta. Il processo di acquisizione dei feed deve gestire gli hit duplicati e i file duplicati senza generare errori o duplicare i dati. È consigliabile utilizzare la combinazione delle colonne `hitid_high` e `hitid_low` per identificare in modo univoco un hit.

  In rari casi, è possibile che vengano visualizzati valori duplicati di `hitid_high` e `hitid_low`. In questo caso, verifica che il file non sia stato inviato ed elaborato in precedenza. Se solo alcune righe di un file sono duplicate, provare ad aggiungere `visit_num` e `visit_page_num` per determinare l&#39;univocità.

* Se utilizzi l’FTP (scelta non consigliata), assicurati di avere spazio sufficiente sul sito FTP. Rimuovere regolarmente i file dalla destinazione in modo da non esaurire inavvertitamente lo spazio su disco.

* Se si utilizza sFTP (scelta non consigliata), non leggere o eliminare i file con suffisso `.part`. Il suffisso `.part` indica che il file è stato trasferito parzialmente. Una volta trasferito il file, il suffisso `.part` scompare.