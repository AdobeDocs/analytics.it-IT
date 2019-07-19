---
description: 'Seguono alcune best practice per l''elaborazione e la consegna dei feed di dati. Dovresti '
keywords: Feed dati; best practice; picco di traffico; orario; ftp
seo-description: 'Seguono alcune best practice per l''elaborazione e la consegna dei feed di dati. Dovresti '
seo-title: Best practice e informazioni generali
solution: Analytics
title: Best practice e informazioni generali
uuid: f 2 d 6 c 13 a -5 d 4 e -4 fc 2-8 baa -28 c 69 f 0 cf 5 f 6
translation-type: tm+mt
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566

---


# Best practice e informazioni generali

Seguono alcune best practice per l'elaborazione e la consegna dei feed di dati. Dovreste:

* Si prevede che i feed di dati vengano consegnati entro 12 ore dalla fine di un determinato periodo di tempo del 95%.

   Ad esempio, se disponete di un feed orario, la richiesta di feed di dati delle 3 a. m. ora deve essere distribuita entro le dell'ora. I feed di dati per suite di rapporti con volume di traffico elevato possono richiedere più tempo per essere elaborati e consegnati, in particolare se sono configurati come feed giornalieri piuttosto che come feed orari.
* Ensure that you [communicate any anticipated traffic spikes](https://marketing.adobe.com/resources/help/en_US/reference/t_traffic_schedule_spike.html) ahead of time. Qualsiasi latenza upstream ha un impatto diretto sulla rapidità con cui il processo di feed di dati può iniziare.
* Accertatevi di disporre di ampie stanze sul vostro sito FTP. Ripulirla periodicamente per evitare inavvertitamente lo spazio su disco.
* Quando si modificano le credenziali FTP, assicurati che le credenziali siano attuali nel sistema di feed dati di Adobe.
* Se possibile, utilizzate la distribuzione oraria. Rende i file più piccoli e rapidi da produrre/trasmettere.
* Prendete in considerazione la possibilità di utilizzare la distribuzione di più file (in genere effettuata con feed giornalieri di grandi dimensioni). La distribuzione più file suddivide il singolo file monolitico in file più piccoli e li distribuisce tutti allo stesso tempo. Anche in questo caso, i file più piccoli consentono di creare, comprimere e trasmettere i dati in modo più rapido.
* Se utilizzi un sftp come metodo di consegna, non leggi e non elimini i file con suffisso «. part». Il suffisso «. part» indica che il file è parzialmente trasferito, non è completo. Una volta trasferito il file, il file verrà rinominato senza il suffisso «. part».
* Create il processo ETL presupponendo che, a volte, un file possa essere trasferito più di una volta. In caso contrario, si possono utilizzare dati duplicati.
