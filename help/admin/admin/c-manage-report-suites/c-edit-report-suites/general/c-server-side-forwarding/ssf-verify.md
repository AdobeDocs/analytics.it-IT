---
description: Per verificare che l’inoltro lato server sia abilitato correttamente, è necessario controllare la risposta HTTP dalla richiesta di tracciamento di Analytics. Queste istruzioni illustrano gli indicatori che devono essere presenti per garantire che l’inoltro lato server sia abilitato correttamente.
solution: Analytics
title: Verificare l’implementazione dell’inoltro lato server
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 70%

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
>Se la risposta contiene la coppia chiave-valore `"status":"SUCCESS"` o un’immagine 2 x 2, l’inoltro lato server *non* è configurato correttamente. Assicurati che il servizio Identity sia correttamente implementato, che il modulo App Measurement sia stato implementato, che la suite di rapporti applicabile sia stata mappata sull’ID organizzazione corretto e che l’inoltro lato server sia stato abilitato negli Strumenti di amministrazione di Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
