---
description: Di seguito sono riportate alcune best practice per l’elaborazione e la distribuzione dei feed di dati.
keywords: Feed di dati;best practice;picco di traffico;ogni ora;ftp
title: Procedure consigliate e informazioni generali
feature: Data Feeds
exl-id: 5f6fbc13-b176-4f69-8f2d-7accc6e6ac2d
source-git-commit: 6f7f46b0fee46e572a65f639ea511478c0118f4e
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# Best practice

Di seguito sono riportate alcune best practice per l’elaborazione e la distribuzione dei feed di dati.

* Assicurati di comunicare anticipatamente eventuali picchi di traffico previsti. La latenza influisce direttamente sul tempo di elaborazione dei feed di dati. Vedi [Pianificare un picco di traffico](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-management/t-traffic-schedule-spike.md) nella guida utente Admin.

* I feed di dati non contengono un accordo a livello di servizio, a meno che non sia esplicitamente indicato nel contratto con l’Adobe. In genere i feed vengono consegnati entro diverse ore dal passaggio dell’intervallo di reporting, ma occasionalmente possono richiedere fino a 12 ore o più.

* Assicurati di avere ampio spazio sul tuo sito FTP. Rimuovi regolarmente i file dalla destinazione in modo da non esaurire inavvertitamente lo spazio su disco.

* I feed orari utilizzano il processo di consegna di più file più veloce. Considera l’utilizzo di più feed di file orari se una consegna tempestiva è una priorità elevata per la tua organizzazione.

* Se utilizzi sFTP, non leggere o eliminare i file con un `.part` suffisso La `.part` suffisso indica che il file è parzialmente trasferito. Una volta trasferito il file, il `.part` il suffisso scompare.

* Se automatizza il processo di inserimento dei feed, considera la possibilità che gli hit e i file possano essere trasferiti più di una volta. Il processo di acquisizione dei feed deve gestire hit duplicati e file duplicati senza errori o duplicazioni dei dati. Si consiglia di utilizzare la combinazione di `hitid_high` e `hitid_low` per identificare in modo univoco un hit.

   In rari casi, potresti vedere duplicati `hitid_high` e `hitid_low` valori. In questo caso, conferma che il file non è stato inviato ed elaborato in precedenza. Se solo alcune delle righe di un file sono duplicate, è consigliabile aggiungere `visit_num` e `visit_page_num` per determinare l&#39;univocità.
