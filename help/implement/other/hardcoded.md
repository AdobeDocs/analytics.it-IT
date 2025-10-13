---
title: Implementazione con richieste di immagini codificate
description: Implementare Adobe Analytics utilizzando un tag immagine HTML (richiesta immagine codificata)
feature: Implementation Basics
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 0%

---

# Implementazione con richieste di immagini codificate

Le librerie AppMeasurement fornite da Adobe compilano le variabili presenti nella pagina, quindi le inviano come richiesta di immagine ad Adobe. Puoi ignorare completamente le librerie AppMeasurement e inviare manualmente una richiesta di immagine ad Adobe. Questo metodo richiede la formulazione manuale della richiesta di immagine e della stringa di query.

Questo metodo di implementazione può essere utilizzato su qualsiasi piattaforma che visualizza immagini da sorgenti esterne. Non si basa affatto su JavaScript.

>[!NOTE]
>
>Anche se le richieste di immagini codificate sono facili da configurare, è difficile eseguirne il debug, mantenerle e ridimensionarle per progetti più grandi. Prima di procedere, assicurati che le richieste di immagini codificate siano l’opzione migliore.

## Sintassi della richiesta di immagine

Di seguito è riportato un esempio di richiesta di immagine hardcoded tramite HTML:

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1/s234234238479?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` indica il protocollo. Abbina il protocollo utilizzato nella richiesta di immagine a quello utilizzato dal resto del sito.
* `example.data.adobedc.net` è il valore contenuto nella variabile [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md).
* `/b/ss/` è incluso in tutte le richieste di immagini. Fa parte della struttura dei file per le immagini memorizzate sui server di raccolta dati di Adobe.
* `examplersid` è l&#39;ID suite di rapporti a cui desideri inviare i dati. Per più suite di rapporti, separa gli ID con virgole e senza spazi (ad esempio `examplersid1,examplersid2` e così via).
* `/1/` è l&#39;origine dell&#39;hit. Vedi `hit_source` in [Riferimento colonna dati](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) nella guida utente di esportazione. Controlla l&#39;ordine utilizzato dai cookie e da altri metodi per identificare i visitatori.
* `/s234234238479` (`"s"` + un numero casuale) impedisce al browser di memorizzare nella cache la richiesta di immagine.
* Tutto ciò che segue il delimitatore di stringa di query (`?`) sono dati che si desidera includere nei report. Per l&#39;elenco completo dei parametri che è possibile includere in una richiesta di immagine, vedere [Parametri query raccolta dati](../validate/query-parameters.md).

## Richieste di immagini codificate in Microsoft Outlook

Poiché la maggior parte delle e-mail è basata su HTML, è possibile tracciare le e-mail aperte e inviare tali dati ad Adobe Analytics. Se la tua organizzazione sceglie di utilizzare questo metodo, tieni presente quanto segue:

* Ogni rendering di e-mail può incrementare una chiamata al server fatturabile.
* Vengono tracciati solo i client e-mail che supportano HTML e consentono l’utilizzo di immagini. Per impostazione predefinita, alcuni client di posta elettronica, come Microsoft Outlook, bloccano le immagini esterne. Queste e-mail vengono tracciate solo dopo che il destinatario avrà scelto di scaricare immagini esterne.

Per comporre un messaggio e-mail di Outlook che include una richiesta di immagine:

1. Apri un editor di HTML. Se non è disponibile un editor di HTML, funziona anche un editor di testo normale.
2. In un nuovo file HTML, inserire un tag di richiesta immagine hardcoded `<img>` racchiuso in un tag `<body>`.
3. Salva il file HTML.
4. Apri Microsoft Outlook e componi un messaggio e-mail.
5. Passare alla scheda Inserisci e fare clic su **Allega file**. Seleziona il file HTML della richiesta di immagine.
6. Fare clic sul menu a comparsa accanto a Inserisci e selezionare **Inserisci come testo**. Se si fa clic sul pulsante Inserisci senza il menu a comparsa, il file HTML diventa un allegato e non funziona.

L’e-mail non sembra cambiare, poiché la richiesta di immagine è un pixel trasparente 1x1. Se desideri visualizzare la richiesta di immagine a scopo di test, modifica il file HTML per includere un bordo, testo aggiuntivo o altro contenuto.

## Domande frequenti

Scopri le domande comuni utilizzando richieste di immagini codificate.

### I parametri delle stringhe di query fanno distinzione tra maiuscole e minuscole?

Sì. Assicurati che i parametri della stringa di query corrispondano esattamente, altrimenti non vengono registrati. `pagename` ad esempio non è un parametro di stringa di query valido, mentre `pageName` lo è.

### È possibile includere spazi nella stringa di query?

I valori per ciascuno dei parametri della stringa di query sono codificati in URL. La codifica URL converte in caratteri validi i caratteri che normalmente non sono validi negli URL. Ad esempio, un carattere spazio viene convertito in `%20`. Assicurati che qualsiasi carattere non alfanumerico sia codificato in URL. L’URL di Adobe decodifica automaticamente i valori quando le richieste di immagini raggiungono i server di raccolta dati.

Per ulteriori informazioni sul funzionamento della codifica URL, vedere [Riferimento per la codifica URL di HTML](https://www.w3schools.com/tags/ref_urlencode.asp) in W3Schools.

### Qual è il numero massimo di caratteri che un singolo valore può avere?

Ogni variabile ha una lunghezza massima diversa. La maggior parte delle variabili di traffico contiene fino a 100 byte, mentre la maggior parte delle variabili di conversione contiene fino a 255 byte. Quando una richiesta di immagine raggiunge i server di raccolta dati, Adobe tronca automaticamente questi valori alla lunghezza massima consentita.
