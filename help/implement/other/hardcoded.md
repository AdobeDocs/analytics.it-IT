---
title: Implementazione con richieste di immagini hardcoded
description: Implementare Adobe  Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded)
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 0%

---


# Implementazione con richieste di immagini hardcoded

Librerie AppMeasurement fornite da variabili di compilazione Adobe presenti sulla pagina, quindi inviatele come richiesta di immagine ad Adobe. Puoi ignorare completamente le librerie AppMeasurement e inviare manualmente una richiesta di immagine ad Adobe. Questo metodo richiede la formulazione manuale della richiesta di immagini e della stringa di query.

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
* `example.sc.omtrdc.net` è il valore contenuto nella `trackingServer` variabile.
* `/b/ss/` è incluso in tutte le richieste di immagini. Fa parte della struttura di file per le immagini memorizzate nei server di raccolta dati Adobe.
* `examplersid` è l&#39;ID suite di rapporti a cui vuoi inviare i dati.
* `/1/` è la fonte di hit. Consultate `hit_source` in Riferimento [colonna](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) Dati nella guida per l’utente relativa all’esportazione. Controlla l&#39;ordine utilizzato dai cookie e da altri metodi per identificare i visitatori.
* Tutto ciò che segue il delimitatore di stringa di query (`?`) è dato che si desidera includere nei rapporti. Consulta Parametri [query di raccolta](../validate/query-parameters.md) dati per l’elenco completo dei parametri che puoi includere in una richiesta di immagine.

## Domande frequenti

Scoprite le domande più frequenti utilizzando richieste di immagini hardcoded.

**I parametri delle stringhe di query sono sensibili alle maiuscole/minuscole?**

Sì. Verificate che i parametri della stringa di query corrispondano esattamente, altrimenti non verranno registrati. Ad esempio, `pagename` non è un parametro di stringa di query valido, mentre `pageName` è.

**È possibile includere spazi nella stringa di query?**

I valori per ciascuno dei parametri della stringa di query sono codificati nell’URL. La codifica URL converte in caratteri legali i caratteri che normalmente non sono consentiti negli URL. Ad esempio, un carattere spazio viene convertito in `%20`. Accertatevi che i caratteri non alfanumerici siano codificati nell’URL. Adobe decodifica automaticamente i valori quando le richieste di immagini raggiungono i server di raccolta dati.

Per ulteriori informazioni sul funzionamento della codifica URL, consultate Riferimento [codifica URL](https://www.w3schools.com/tags/ref_urlencode.asp) HTML in W3Schools.

**Qual è il numero massimo di caratteri consentiti per un singolo valore?**

Ogni variabile ha una lunghezza massima diversa. La maggior parte delle variabili di traffico contiene fino a 100 byte, mentre la maggior parte delle variabili di conversione contiene fino a 255 byte. Quando una richiesta di immagine raggiunge i server di raccolta dei dati, Adobe tronca automaticamente questi valori alla lunghezza massima consentita.
