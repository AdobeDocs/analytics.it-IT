---
description: Per verificare che l'inoltro lato server sia abilitato correttamente, è necessario controllare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l'inoltro lato server sia abilitato correttamente.
solution: Analytics
title: Verificare l'implementazione lato server
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 6%

---

# Verificare l&#39;implementazione lato server

Per verificare che l&#39;inoltro lato server sia abilitato correttamente, è necessario controllare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o utilizzando uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l&#39;inoltro lato server sia abilitato correttamente.

Per controllare lo stato dell&#39;inoltro lato server:

1. Carica una pagina di prova contenente il codice AppMeasurement aggiornato.
1. Negli strumenti di debug del browser o utilizzando il software proxy, controlla la risposta HTTP dalla richiesta di tracciamento di Analytics (puoi facilmente filtrare questo passaggio selezionando qualsiasi percorso contenente &quot;b/ss&quot;).
1. Inspect la risposta HTTP. Se la risposta contiene dati di Audience Manager (come illustrato di seguito), l&#39;inoltro lato server funziona.

![](assets/ssf-succeed.png)

>[!CAUTION]
>
>Se la risposta contiene la coppia chiave valore `"status":"SUCCESS"` per un&#39;immagine 2 x 2, l&#39;inoltro lato server * non è configurato correttamente. Assicurati che il servizio Identity sia correttamente distribuito, che il modulo App Measurement sia stato implementato, che la suite di rapporti applicabile sia stata mappata nell’organizzazione IMS corretta e che l’inoltro lato server sia stato abilitato nella console di amministrazione di Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

