---
description: Puoi implementare un metodo personalizzato per identificare i visitatori impostando la variabile s. visitorid.
keywords: Implementazione di Analytics
seo-description: Puoi implementare un metodo personalizzato per identificare i visitatori impostando la variabile s. visitorid.
seo-title: ID visitatore personalizzato
solution: Analytics
title: ID visitatore personalizzato
topic: Sviluppatore e implementazione
uuid: 49881 e 27-0418-4 ecf-a 092-dcc 3 db 923 f 40
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID visitatore personalizzato

Puoi implementare un metodo personalizzato per identificare i visitatori impostando la variabile s. visitorid.

Un ID visitatore personalizzato può essere utilizzato in siti in cui hai modo univoco per identificare i visitatori. Un esempio è rappresentato da un ID generato quando un utente accede al sito Web utilizzando un nome utente e una password.

Should you have the ability to derive and manage the [!UICONTROL visitor IDs] of your users, you can use the following methods to set the ID:

| Metodo | Descrizione |
|---|---|
| [variabile s. visitorid](/help/implement/js-implementation/c-variables/page-variables.md) | Se javascript viene utilizzato nel browser o se utilizzi un'altra libreria appmeasurement, puoi impostare l'ID visitatore in una variabile di raccolta dati. |
| Parametro stringa query nella richiesta immagine | This lets you pass the [!UICONTROL visitor ID] to Adobe via the [!UICONTROL vid query string] parameter on a hard-coded image request. |
| API di inserimento dati | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers. |
| Riscrittura URL e VISTA | Alcune architetture di distribuzione forniscono supporto per l'utilizzo di riscrittura URL per mantenere lo stato della sessione quando non è possibile impostare un cookie. In such cases, Adobe engineering services can implement a [!DNL VISTA] rule that would look for the session value in the URL of the page, then format and place into the [!UICONTROL visid] values. |
>[!CAUTION]
>**Gli ID visitatore personalizzati devono essere sufficientemente granulari/univoci**: Un'implementazione non valida degli ID visitatore personalizzati può portare a dati non corretti e a prestazioni di reporting scadenti. Se l'ID visitatore personalizzato non è univoco o granulare, oppure è impostato in modo errato su un valore predefinito comune, come la stringa "NULL" o "0", gli hit provenienti da molti visitatori diversi verranno visti da Adobe Analytics come singolo visitatore. Questa situazione genera dati non corretti, con i conteggi dei visitatori troppo bassi e i segmenti non funzionano correttamente per quel visitatore. Un ID visitatore personalizzato non sufficientemente dettagliato impedisce anche che i dati vengano distribuiti correttamente tra i nodi del cluster di report Analytics. In questa situazione, un nodo viene sovraccaricato e non è in grado di elaborare i rapporti in modo tempestivo. Alla fine, tutti i rapporti relativi alla suite di rapporti non vanno a buon fine. <br>Gli ID visitatore personalizzati implementati in modo errato potrebbero non influenzare immediatamente le prestazioni di reporting perché Analytics spesso può gestire più mesi di dati non bilanciati; Tuttavia, nel corso del tempo, un valore di ID visitatore personalizzato non implementato in modo scadente può diventare problematico per il momento in cui Analytics disabilita l'elaborazione per le suite di rapporti interessate.</br><br>Gli addetti all'implementazione devono seguire la linea guida per non ricevere mai un valore di ID visitatore personalizzato per più del 1% del traffico della suite di rapporti. Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
