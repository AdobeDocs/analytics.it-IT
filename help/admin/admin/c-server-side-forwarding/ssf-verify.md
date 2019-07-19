---
description: Per verificare che l'inoltro lato server sia abilitato correttamente, dovrai ispezionare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento di proxying come Charles Web Debugger. Le istruzioni seguenti illustrano quali indicatori devono essere presenti per garantire che l'inoltro lato server sia abilitato correttamente.
seo-description: Per verificare che l'inoltro lato server sia abilitato correttamente, dovrai ispezionare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento di proxying come Charles Web Debugger. Le istruzioni seguenti illustrano quali indicatori devono essere presenti per garantire che l'inoltro lato server sia abilitato correttamente.
seo-title: Come verificare l'implementazione lato server
solution: Audience Manager
title: Come verificare l'implementazione lato server
uuid: e 37296 cc -0120-486 a-a 4 ca -78 d 648 cf 6 a 11
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Come verificare l'implementazione lato server

Per verificare che l'inoltro lato server sia abilitato correttamente, dovrai ispezionare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento di proxying come Charles Web Debugger. Le istruzioni seguenti illustrano quali indicatori devono essere presenti per garantire che l'inoltro lato server sia abilitato correttamente.

Per verificare lo stato dell'inoltro lato server:

1. Carica una pagina di prova contenente il codice appmeasurement aggiornato.
1. Negli strumenti di debug del browser o utilizzando il software proxy, ispezionate la risposta HTTP dalla richiesta di tracciamento di Analytics (potete filtrare facilmente selezionando un percorso contenente «b/ss».
1. Ispezionare la risposta HTTP. Se la risposta contiene i dati di Audience Manager (come illustrato di seguito), l'inoltro lato server funziona.

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>If the response contains the key value pair `"status":"SUCCESS"` or a 2 x 2 image, then server-side forwarding * is not* configured correctly. Assicurati che il servizio Identità sia correttamente distribuito, che tu abbia implementato il modulo Misurazione app, che la suite di rapporti applicabile sia stata mappata sull'organizzazione IMS corretta e che l'inoltro lato server sia stato attivato nella console di amministrazione di Analytics.

>[!MORE_ LIKE_ THIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

