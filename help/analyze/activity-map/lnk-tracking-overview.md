---
description: 'Activity Map tiene traccia dei collegamenti con un algoritmo più affidabile '
title: Tracciamento solido dei collegamenti
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
feature: Activity Map
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 3%

---


# Tracciamento solido dei collegamenti

Activity Map tiene traccia dei collegamenti con un algoritmo più affidabile che:

* Include il tracciamento delle aree della pagina per evitare che i casi dello stesso collegamento vengano confusi tra dispositivi diversi, perché il collegamento viene visualizzato in posizioni diverse sulla pagina;
* Assicura l&#39;univocità del collegamento, il che significa che non è possibile sbagliare i collegamenti distinti per uno a causa di problemi con LinkID o tra browser diversi.

Per ulteriori informazioni sul tracciamento dei collegamenti in Activity Map, visita [qui](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Come il tracciamento dei collegamenti Activity Map può raccogliere dati PII {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION]
>
>Attivando il tracciamento di Activity Map, è possibile che si raccolgano dati di informazioni personali identificabili (PII). Questi dati possono essere utilizzati da soli o con altre informazioni per identificare, contattare o individuare una singola persona o per identificare un individuo nel contesto.

Di seguito sono riportati alcuni casi noti in cui i dati PII potrebbero essere raccolti utilizzando il tracciamento di Activity Map:

* `Mailto` link. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta elettronica predefinito sul computer per l’invio di un messaggio di posta elettronica.
* `User ID` collegamenti che possono essere visualizzati nell’intestazione/piè di pagina di un sito web dopo l’accesso dell’utente.
* Per gli istituti finanziari, il numero del conto può essere indicato come collegamento. Facendo clic su di esso verrà raccolto il testo del collegamento.
* I siti web sanitari possono anche avere dati PII mostrati come link. Facendo clic su questi collegamenti si raccoglierà il testo del collegamento, raccogliendo quindi dati PII.
