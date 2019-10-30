---
description: Per verificare che l'inoltro lato server sia abilitato correttamente, è necessario esaminare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l'inoltro lato server sia correttamente abilitato.
seo-description: Per verificare che l'inoltro lato server sia abilitato correttamente, è necessario esaminare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l'inoltro lato server sia correttamente abilitato.
seo-title: Verificare l'implementazione lato server
solution: Audience Manager
title: Verificare l'implementazione lato server
uuid: e37296cc-0120-486a-a4ca-78d648cf6a11
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Verificare l'implementazione lato server

Per verificare che l'inoltro lato server sia abilitato correttamente, è necessario esaminare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l'inoltro lato server sia correttamente abilitato.

Per verificare lo stato dell'inoltro lato server:

1. Carica una pagina di prova contenente il codice AppMeasurement aggiornato.
1. Negli strumenti di debug del browser in uso o con il software proxy, controllate la risposta HTTP dalla richiesta di tracciamento di Analytics (potete facilmente filtrarla selezionando qualsiasi percorso contenente "b/s").
1. Esaminate la risposta HTTP. Se la risposta contiene dati di Audience Manager (come illustrato di seguito), l'inoltro lato server funziona.

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>Se la risposta contiene la coppia di valori chiave `"status":"SUCCESS"` o un'immagine 2 x 2, l'inoltro lato server * non è configurato correttamente. Verificate che il servizio identità sia stato distribuito correttamente, che il modulo App Measurement sia stato distribuito, che la suite di rapporti applicabile sia stata mappata sull'organizzazione IMS corretta e che l'inoltro lato server sia stato abilitato nella console di amministrazione di Analytics.

>[!MORE_LIKE_THIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

