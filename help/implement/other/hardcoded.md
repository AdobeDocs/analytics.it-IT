---
title: Implementazione con richieste di immagini hardcoded
description: Implementazione  Adobe Analytics tramite un tag immagine HTML (richiesta immagine hardcoded)
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---


# Implementazione con richieste di immagini hardcoded

Le librerie AppMeasurement fornite da  Adobe compilano le variabili presenti sulla pagina, quindi le inviano come richiesta di immagine a  Adobe. Potete ignorare completamente le librerie AppMeasurement e inviare manualmente una richiesta di immagine al Adobe . Questo metodo richiede la formulazione manuale della richiesta di immagini e della stringa di query.

Questo metodo di implementazione può essere utilizzato su qualsiasi piattaforma in cui siano visualizzate immagini provenienti da origini esterne. Non si basa affatto su JavaScript.

>[!NOTE]
>
>Sebbene le richieste di immagini hardcoded siano facili da configurare, è difficile eseguire il debug, la manutenzione e la modifica in scala per progetti più grandi. Prima di continuare, assicuratevi che le richieste di immagini hardcoded siano l’opzione migliore.

## Sintassi richiesta immagine

Esempio di richiesta di immagine con hardcoded tramite HTML:

```html
<img src="https://example.sc.omtrdc.net/b/ss/examplersid/1?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` specifica il protocollo. Fate corrispondere il protocollo utilizzato nella richiesta di immagine con il protocollo utilizzato dal resto del sito.
* `example.sc.omtrdc.net` è il valore contenuto nella [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variabile.
* `/b/ss/` è incluso in tutte le richieste di immagini. Fa parte della struttura di file per le immagini memorizzate  server di raccolta dati di Adobe.
* `examplersid` è l&#39;ID suite di rapporti a cui vuoi inviare i dati.
* `/1/` è la fonte di hit. Consultate `hit_source` in Riferimento [colonna](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) Dati nella guida per l’utente relativa all’esportazione. Controlla l&#39;ordine utilizzato dai cookie e da altri metodi per identificare i visitatori.
* Tutto ciò che segue il delimitatore di stringa di query (`?`) è dato che si desidera includere nei rapporti. Consulta Parametri [query di raccolta](../validate/query-parameters.md) dati per l’elenco completo dei parametri che puoi includere in una richiesta di immagine.

## Richieste di immagini hardcoded in Microsoft Outlook

Poiché la maggior parte delle e-mail è basata su HTML, è possibile tenere traccia delle e-mail aperte e inviare tali dati a  Adobe Analytics. Se l’organizzazione sceglie di utilizzare questo metodo, tenere presente quanto segue:

* Ogni rendering e-mail può incrementare una chiamata server fatturabile.
* Vengono tracciati solo i client e-mail che supportano HTML e consentono l’utilizzo di immagini. Per impostazione predefinita, alcuni client e-mail, come Microsoft Outlook, bloccano le immagini esterne. Questi messaggi e-mail non vengono tracciati finché il destinatario non sceglie di scaricare immagini esterne.

Per comporre un messaggio e-mail di Outlook contenente una richiesta di immagine:

1. Aprite un editor HTML. Se non è disponibile un editor HTML, funziona anche un editor di testo normale.
2. In un nuovo file HTML, inserite un `<img>` tag di richiesta immagine hardcoded racchiuso in un `<body>` tag.
3. Salvate il file HTML.
4. Aprite Microsoft Outlook e componete un messaggio e-mail.
5. Fare clic sulla scheda Inserisci e quindi su **Allega file**. Selezionate il file HTML per la richiesta di immagini.
6. Fate clic sul menu a comparsa accanto a Inserisci e selezionate **Inserisci come testo**. Se si fa clic sul pulsante Inserisci senza il menu a comparsa, il file HTML diventa un allegato e non funziona.

L’e-mail non sembra cambiare, poiché la richiesta dell’immagine è un pixel trasparente 1x1. Se desiderate visualizzare la richiesta di immagine a scopo di test, modificate il file HTML in modo da includere un bordo, testo aggiuntivo o altro contenuto.

## Domande frequenti

Scoprite le domande più frequenti utilizzando richieste di immagini hardcoded.

### I parametri delle stringhe di query sono sensibili alle maiuscole/minuscole?

Sì. Verificate che i parametri della stringa di query corrispondano esattamente, altrimenti non verranno registrati. Ad esempio, `pagename` non è un parametro di stringa di query valido, mentre `pageName` è.

### È possibile includere spazi nella stringa di query?

I valori per ciascuno dei parametri della stringa di query sono codificati nell’URL. La codifica URL converte in caratteri legali i caratteri che normalmente non sono consentiti negli URL. Ad esempio, un carattere spazio viene convertito in `%20`. Accertatevi che i caratteri non alfanumerici siano codificati nell’URL.  Adobe codifica automaticamente i valori quando le richieste di immagini raggiungono i server di raccolta dati.

Per ulteriori informazioni sul funzionamento della codifica URL, consultate Riferimento [codifica URL](https://www.w3schools.com/tags/ref_urlencode.asp) HTML in W3Schools.

### Qual è il numero massimo di caratteri consentiti per un singolo valore?

Ogni variabile ha una lunghezza massima diversa. La maggior parte delle variabili di traffico contiene fino a 100 byte, mentre la maggior parte delle variabili di conversione contiene fino a 255 byte. Quando una richiesta di immagine raggiunge i server di raccolta dei dati,  Adobe tronca automaticamente questi valori alla lunghezza massima consentita.
