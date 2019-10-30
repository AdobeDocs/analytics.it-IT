---
description: Puoi implementare un metodo personalizzato per identificare i visitatori impostando la variabile s.visitorID.
keywords: Implementazione di Analytics
seo-description: Puoi implementare un metodo personalizzato per identificare i visitatori impostando la variabile s.visitorID.
seo-title: ID visitatore personalizzato
solution: Analytics
title: ID visitatore personalizzato
topic: Sviluppatore e implementazione
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# ID visitatore personalizzato

Puoi implementare un metodo personalizzato per identificare i visitatori impostando la variabile s.visitorID.

Un ID visitatore personalizzato può essere utilizzato sui siti in cui hai un modo univoco per identificare i visitatori. Un esempio è costituito da un ID generato quando un utente accede al sito Web utilizzando un nome utente e una password.

Se hai la capacità di derivare e gestire i [!UICONTROL visitor IDs] tuoi utenti, puoi usare i seguenti metodi per impostare l’ID:

| Metodo | Descrizione |
|---|---|
| [s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) , variabile | Se JavaScript è utilizzato nel browser, o se utilizzi un'altra libreria AppMeasurement, puoi impostare l'ID visitatore in una variabile di raccolta dati. |
| Parametro della stringa di query sulla richiesta di immagine | Questo consente di trasmettere il file [!UICONTROL visitor ID] ad Adobe tramite il [!UICONTROL vid query string] parametro su una richiesta di immagine hardcoded. |
| API di inserimento dati | Sui dispositivi che utilizzano protocolli wireless che non accettano JavaScript, potete inviare un post XML contenente l'elemento `<visitorid/>` XML ai server di raccolta Adobe dai vostri server. |
| Riscrittura URL e VISTA | Alcune architetture di distribuzione supportano l'utilizzo della riscrittura URL per mantenere lo stato di sessione quando non è possibile impostare un cookie. In tali casi, i servizi tecnici Adobe possono implementare una [!DNL VISTA] regola che cerca il valore della sessione nell’URL della pagina, quindi formattarlo e inserirlo nei [!UICONTROL visid] valori. |
>[!CAUTION]
>**Gli ID visitatore personalizzati devono essere sufficientemente granulari/univoci**: Un'implementazione non valida degli ID visitatore personalizzati può portare a dati errati e a prestazioni di reporting scadenti. Se l’ID visitatore personalizzato non è univoco o granulare abbastanza, o se non è impostato in modo corretto su un valore predefinito comune come la stringa "NULL" o "0", gli hit di molti visitatori diversi saranno visualizzati da Adobe Analytics come un singolo visitatore. Questa situazione genera dati errati, con i conteggi dei visitatori troppo bassi e i segmenti che non funzionano correttamente per quel visitatore. Un ID visitatore personalizzato non sufficientemente granulare impedisce inoltre la corretta diffusione dei dati tra i nodi del cluster di reporting di Analytics. In questa situazione, un nodo diventa sovraccarico e non può elaborare le richieste di report in modo tempestivo. Alla fine tutti i report per la suite per report avranno esito negativo. <br>Gli ID visitatore personalizzati implementati male potrebbero non influenzare immediatamente le prestazioni di reporting, perché Analytics spesso può gestire diversi mesi di dati non bilanciati; tuttavia, nel tempo un ID visitatore personalizzato implementato in modo non corretto può diventare problematico al punto da richiedere ad Analytics di disabilitare l'elaborazione per le suite di rapporti interessate.</br><br>Gli implementatori devono seguire le linee guida secondo cui un singolo valore ID visitatore personalizzato non deve mai essere accreditato per più dell'1% del traffico della suite di rapporti. Anche se la linea guida dell'1% è sufficiente per la maggior parte delle suite di rapporti, il limite effettivo che potrebbe causare l'impatto delle prestazioni di reporting potrebbe essere inferiore all'1% per le suite di rapporti molto grandi.</br>
