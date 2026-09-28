---
description: Per verificare che l’inoltro lato server sia abilitato correttamente, è necessario controllare la risposta HTTP dalla richiesta di tracciamento di Analytics. Queste istruzioni illustrano gli indicatori che devono essere presenti per garantire che l’inoltro lato server sia abilitato correttamente.
solution: Analytics
title: Verificare l’implementazione dell’inoltro lato server
feature: Report Suite Settings
exl-id: 21db4572-da3c-43aa-a774-86a089656695
role: Admin
TQID: 'https://experienceleague.adobe.com/FpB4dk9D87gc24t5KG6WRJ-r8GFOvOEUlRTTjc6XFYI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 70%
---
# Verificare l’implementazione dell’inoltro lato server

Per verificare che l’inoltro lato server sia abilitato correttamente, è necessario controllare la risposta HTTP dalla richiesta di tracciamento di Analytics. Questo può essere fatto utilizzando gli strumenti di sviluppo di un browser o uno strumento proxy come Charles Web Debugger. Le istruzioni seguenti illustrano gli indicatori che devono essere presenti per garantire che l’inoltro lato server sia abilitato correttamente.

Per controllare lo stato dell’inoltro lato server:

1. Carica una pagina di prova contenente il codice AppMeasurement aggiornato.
1. Negli strumenti di debug del browser o utilizzando il software proxy, controlla la risposta HTTP dalla richiesta di tracciamento di Analytics (puoi facilmente filtrarla selezionando qualsiasi percorso contenente “b/ss”).
1. Verifica la risposta HTTP. Se la risposta contiene dati di Audience Manager (come illustrato di seguito), l’inoltro lato server funziona.

![](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/assets/ssf-succeed.png)

>[!CAUTION]
>
>Se la risposta contiene la coppia chiave-valore `"status":"SUCCESS"` o un’immagine 2 x 2, l’inoltro lato server *non* è configurato correttamente. Assicurati che il servizio Identity sia correttamente implementato, che il modulo App Measurement sia stato implementato, che la suite di rapporti applicabile sia stata mappata sull’ID organizzazione corretto e che l’inoltro lato server sia stato abilitato negli Strumenti di amministrazione di Analytics.

>[!MORELIKETHIS]
>
>* [Charles Web Debugger](https://www.charlesproxy.com/)
