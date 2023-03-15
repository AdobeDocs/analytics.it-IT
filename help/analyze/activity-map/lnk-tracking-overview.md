---
description: Activity Map tiene traccia dei collegamenti con un algoritmo più affidabile che
title: Tracciamento solido dei collegamenti
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
feature: Activity Map
role: User, Admin
exl-id: 1f077234-ff88-46ce-a931-2d21d68042b0
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 2%

---

# Tracciamento solido dei collegamenti

Activity Map tiene traccia dei collegamenti con un algoritmo più affidabile che:

* Include il tracciamento delle aree della pagina per evitare che lo stesso collegamento venga confuso tra dispositivi diversi, perché viene visualizzato in posizioni diverse sulla pagina;
* Assicura l’univocità dei collegamenti, il che significa che i collegamenti distinti non possono essere scambiati per uno a causa di problemi con LinkID o con browser diversi.

Per ulteriori informazioni sul tracciamento dei collegamenti in Activity Map, consulta [qui](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## In che modo il tracciamento dei collegamenti Activity Map può raccogliere i dati PII {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION]
>
>Attivando il tracciamento Activity Map, potresti raccogliere dati personali (PII, personally identifiable information). Questi dati possono essere utilizzati da soli o con altre informazioni per identificare, contattare o individuare una singola persona o per identificare un individuo nel contesto.

Di seguito sono riportati alcuni casi noti in cui i dati PII potrebbero essere raccolti utilizzando il tracciamento Activity Map:

* `Mailto` collegamenti. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta predefinito nel computer per l&#39;invio di un messaggio di posta elettronica.
* `User ID` collegamenti che possono essere visualizzati nell’intestazione/piè di pagina di un sito web dopo l’accesso dell’utente.
* Per gli istituti finanziari, il numero di conto può essere indicato come collegamento. Facendo clic su di esso verrà raccolto il testo del collegamento.
* I siti web dedicati al settore sanitario possono anche presentare dati PII sotto forma di collegamenti. Facendo clic su questi collegamenti verrà raccolto il testo del collegamento, con conseguente raccolta di dati PII.
