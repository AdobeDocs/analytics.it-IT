---
title: Implementazione con richieste di immagini codificate
description: Implementare Adobe Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded)
feature: Implementation Basics
exl-id: 84247daf-c94b-456c-9824-6d4a0b3e6065
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 0%

---

# Implementazione con richieste di immagini codificate

Le librerie AppMeasurement fornite da Adobe compilano le variabili presenti nella pagina, quindi le inviano come una richiesta di immagine ad Adobe. Puoi ignorare completamente le librerie AppMeasurement e inviare manualmente una richiesta di immagine ad Adobe. Questo metodo richiede la formulazione manuale della richiesta di immagine e della stringa di interrogazione.

Questo metodo di implementazione può essere utilizzato su qualsiasi piattaforma che visualizza immagini provenienti da sorgenti esterne. Non si basa affatto su JavaScript.

>[!NOTE]
>
>Sebbene le richieste di immagini codificate siano facili da configurare, è difficile eseguire il debug, la manutenzione e la scalabilità per progetti di grandi dimensioni. Assicurati che le richieste di immagini codificate siano l’opzione migliore prima di procedere.

## Sintassi della richiesta immagine

Di seguito è riportato un esempio di richiesta di immagine hardcoded che utilizza HTML:

```html
<img src="https://example.data.adobedc.net/b/ss/examplersid/1/s234234238479?AQB=1&g=http%3A%2F%2Fexample.com&pageName=Example%20hardcoded%20hit&v1=Example%20value&AQE=1"/>
```

* `https://` designa il protocollo. Usa il protocollo utilizzato nella richiesta di immagine con il protocollo utilizzato dal resto del sito.
* `example.data.adobedc.net` è il valore contenuto nel [`trackingServer`](/help/implement/vars/config-vars/trackingserver.md) variabile.
* `/b/ss/` è incluso in tutte le richieste di immagini. Fa parte della struttura dei file per le immagini archiviate sui server di raccolta dati di Adobe.
* `examplersid` è l&#39;ID suite di rapporti a cui desideri inviare i dati. Per più suite di rapporti, separa gli ID con virgole e senza spazi (ad esempio `examplersid1,examplersid2` e così via).
* `/1/` è la sorgente hit. Vedi `hit_source` sotto [Riferimento colonna dati](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md) nella guida utente Export. Controlla l’ordine utilizzato dai cookie e da altri metodi per identificare i visitatori.
* `/s234234238479` (`"s"` + un numero casuale) impedisce al browser di memorizzare in cache la richiesta di immagine.
* Tutto ciò che segue il delimitatore della stringa di query (`?`) sono dati che desideri includere nei rapporti. Vedi [Parametri query di raccolta dati](../validate/query-parameters.md) per l’elenco completo dei parametri che puoi includere in una richiesta di immagine.

## Richieste di immagini codificate in Microsoft Outlook

Poiché la maggior parte delle e-mail sono basate su HTML, è possibile tenere traccia delle e-mail aperte e inviare tali dati ad Adobe Analytics. Se l&#39;organizzazione sceglie di utilizzare questo metodo, tieni presente quanto segue:

* Ogni rendering di e-mail può incrementare una chiamata al server fatturabile.
* Vengono tracciati solo i client e-mail che supportano HTML e consentono il tracciamento delle immagini. Alcuni client di posta elettronica, come Microsoft Outlook, bloccano per impostazione predefinita le immagini esterne. Queste e-mail non vengono tracciate finché il destinatario non sceglie di scaricare immagini esterne.

Per comporre un&#39;e-mail di Outlook che include una richiesta di immagine:

1. Apri un editor di HTML. Se un editor di HTML non è disponibile, funziona anche un editor di testo normale.
2. In un nuovo file HTML, inserisci una richiesta di immagine hardcoded `<img>` tag racchiusi in un `<body>` tag .
3. Salva il file HTML.
4. Apri Microsoft Outlook e crea un messaggio e-mail.
5. Passa alla scheda Inserisci e fai clic su **Allega file**. Seleziona il file HTML della richiesta di immagine.
6. Fare clic sul menu a comparsa accanto a Inserisci e selezionare **Inserisci come testo**. Se si fa clic sul pulsante Inserisci senza il menu a comparsa, il file HTML diventa un allegato che non funziona.

L’e-mail non sembra cambiare, in quanto la richiesta di immagine è un pixel trasparente 1x1. Se desideri visualizzare la richiesta di immagine a scopo di test, modifica il file HTML in modo da includere un bordo, un testo aggiuntivo o altro contenuto.

## Domande frequenti

Scopri le domande comuni che utilizzano richieste di immagini codificate.

### I parametri delle stringhe query sono sensibili a maiuscole e minuscole?

Sì. Assicurati che i parametri della stringa di query corrispondano esattamente, altrimenti non vengono registrati. Ad esempio: `pagename` non è un parametro di stringa di query valido, mentre `pageName` ).

### Posso includere spazi nella stringa query?

I valori per ciascuno dei parametri della stringa di query sono codificati nell’URL. La codifica URL converte in caratteri legali i caratteri normalmente non validi negli URL. Ad esempio, un carattere spazio viene convertito in `%20`. Assicurati che qualsiasi carattere non alfanumerico sia codificato in URL. L’URL di Adobe decodifica automaticamente i valori quando le richieste di immagini raggiungono i server di raccolta dati.

Vedi [Riferimento per la codifica URL di HTML](https://www.w3schools.com/tags/ref_urlencode.asp) su W3Schools per ulteriori informazioni sul funzionamento della codifica URL.

### Qual è il numero massimo di caratteri che un singolo valore può avere?

Ogni variabile ha una lunghezza massima diversa. La maggior parte delle variabili di traffico contiene fino a 100 byte, mentre la maggior parte delle variabili di conversione può contenere fino a 255 byte. Quando una richiesta di immagine raggiunge i server di raccolta dati, Adobe tronca automaticamente questi valori alla loro lunghezza massima.
