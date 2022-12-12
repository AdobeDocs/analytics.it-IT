---
description: Per verificare che l’inoltro lato server sia abilitato correttamente, è necessario controllare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l’inoltro lato server sia abilitato correttamente.
solution: Analytics
title: Verificare l’implementazione dell’inoltro lato server
feature: Server-Side Forwarding
exl-id: 21db4572-da3c-43aa-a774-86a089656695
source-git-commit: beef45403f3c3eb7ac423ca8e0b6db0143ff1b9b
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 84%

---

# Verificare l’implementazione dell’inoltro lato server

Per verificare che l’inoltro lato server sia abilitato correttamente, è necessario controllare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l’inoltro lato server sia abilitato correttamente.

Per controllare lo stato dell’inoltro lato server:

1. Carica una pagina di prova contenente il codice AppMeasurement aggiornato.
1. Negli strumenti di debug del browser o utilizzando il software proxy, controlla la risposta HTTP dalla richiesta di tracciamento di Analytics (puoi facilmente filtrarla selezionando qualsiasi percorso contenente “b/ss”).
1. Verifica la risposta HTTP. Se la risposta contiene dati di Audience Manager (come illustrato di seguito), l’inoltro lato server funziona.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Se la risposta contiene la coppia chiave-valore `"status":"SUCCESS"` o un’immagine 2 x 2, l’inoltro lato server *non* è configurato correttamente. Assicurati che il servizio Identity sia correttamente distribuito, hai implementato il modulo App Measurement , che la suite di rapporti applicabile sia stata mappata sull’ID organizzazione corretto e che l’inoltro lato server sia stato abilitato in Strumenti di amministrazione di Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)

