---
title: Domande frequenti relative all'implementazione
description: Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 68%

---


# Domande frequenti sull’implementazione di Analytics

Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.

## Qual è la differenza tra l’ID visitatore Experience Cloud e l’ID visitatore Analytics?

Identity Service assegna un identificatore univoco e permanente che può essere condiviso tra le altre soluzioni Experience Cloud. L’ID visitatore di Analytics è utilizzato solo da Analytics. Adobe consiglia di utilizzare il servizio ID visitatori di Experience Cloud per la tua implementazione.

## Come si implementa il Tracciamento video Heartbeat?

Vedi la sezione [Misurazione di audio e video in Adobe Analytics](https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html).

## Un’interruzione del servizio Adobe può influire sulle prestazioni?

No. Il file JavaScript non è ospitato sui server Adobe, pertanto un’interruzione da parte di Adobe non influirà sulla libreria AppMeasurement. Se utilizzi Adobe Experience Platform Launch, il file JavaScript è ospitato da Akamai o in una posizione server determinata dalla tua organizzazione.

## L’invio di dati dal browser ai servizi Adobe riduce le prestazioni?

AppMeasurement crea un oggetto immagine all’interno della pagina HTML e il browser quindi richiede l’oggetto immagine ai server di raccolta dati Adobe. Se i server di raccolta dati dovessero essere lenti o non rispondere, la gestione del thread della richiesta verrebbe ritardata fino al ritorno dell’immagine o al verificarsi di un timeout. Poiché i browser gestiscono immagini con più thread, un’interruzione di Adobe avrebbe un impatto minimo sul tempo di caricamento della pagina, bloccando un thread mentre gli altri continuano a funzionare.

## Come posso annullare o rimuovere un&#39;implementazione di Analytics?

A volte un&#39;organizzazione vorrebbe rimuovere un&#39;implementazione a causa della scadenza del contratto o per ridurre il numero di chiamate server.

* **Implementazioni tramite Launch**: Disattivate o disinstallate l&#39;estensione  Adobe Analytics nella [!UICONTROL Extensions] scheda, quindi pubblicate.
* **Implementazioni** AppMeasurement precedenti: Sostituite l’intero contenuto del `s_code.js` file con la seguente riga di codice:

```js
var s = new Object();
```

>[!WARNING]
>
>Non eseguire:
>
>* Modificate la suite di rapporti impostando un valore non valido, in quanto crea un carico non necessario  server  Adobi.
>* Rimuovere il `s_code.js` file, a meno che non vengano rimossi anche tutti i riferimenti al file in ogni pagina.
>* Modificate la `trackingServer` variabile in modo che punti lontano dal Adobe . AppMeasurement invia comunque le richieste di immagini, che restituiscono 404 errori.

