---
description: ' Activity Map tiene traccia dei collegamenti con un algoritmo più affidabile '
title: Tracciamento solido dei collegamenti
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 2%

---


# Tracciamento solido dei collegamenti

 Activity Map tiene traccia dei collegamenti con un algoritmo più affidabile che:

* Include il tracciamento delle aree della pagina per evitare che i casi dello stesso collegamento vengano confusi tra dispositivi diversi, perché il collegamento viene visualizzato in diverse posizioni sulla pagina;
* Assicura l’univocità del collegamento, il che significa che non è possibile erroneamente creare collegamenti distinti per uno di essi a causa di problemi riscontrati con LinkID o da browser diversi.

Per maggiori informazioni sul tracciamento dei collegamenti in  Activity Map, visita [qui](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

##  tracciamento dei collegamenti Activity Map può raccogliere dati PII {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION]
>
>Attivando il tracciamento  Activity Map, potresti raccogliere dati personali (PII). Questi dati possono essere utilizzati in modo indipendente o con altre informazioni per identificare, contattare o individuare una singola persona, o per identificare un individuo nel contesto.

Di seguito sono riportati alcuni casi noti in cui i dati PII potrebbero essere raccolti utilizzando  Activity Map Tracking:

* `Mailto` collegamenti. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta elettronica predefinito sul computer per l&#39;invio di un messaggio e-mail.
* `User ID` collegamenti che possono essere visualizzati nell’intestazione o piè di pagina di un sito Web dopo che l’utente ha eseguito l’accesso.
* Per gli istituti finanziari, il numero del conto può essere indicato come collegamento. Facendo clic su di esso verrà raccolto il testo del collegamento.
* I siti Web per il settore sanitario possono anche avere dati PII visualizzati come collegamenti. Facendo clic su questi collegamenti si raccoglierà il testo del collegamento, raccogliendo quindi i dati PII.
