---
title: Sistema operativo
description: Il sistema operativo del visitatore.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 17c441f8855b8ca0604076763817de8d4d3b8efb
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# Sistema operativo

La dimensione &quot;Sistema operativo&quot; mostra il sistema operativo e la versione utilizzati dal visitatore. Se disponi di funzionalità specifiche per il sistema operativo nella proprietà web, questa dimensione ti aiuta a capire quali sistemi operativi sono più comuni.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna all’Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente.

## Elementi dimensionali

Gli elementi di Dimension includono i sistemi operativi utilizzati dai visitatori. Esempi `"Windows 10"`, `"OS X 10.15"`e `"Android 9"`.

## Modifiche all&#39;etichettatura e alla definizione

Di seguito è riportato un elenco di problemi specifici relativi alla rappresentazione del sistema operativo nell&#39;agente utente e nel reporting di Adobe Analytics.

### Modifica della convenzione di denominazione per il sistema operativo Apple:

A partire dalla versione 11, utilizzeremo MacOS invece di OS X per fare riferimento al sistema operativo Apple.

Esempi:

* &quot;OS X 10.15&quot; (vedi la nota seguente sulla versione 10.15.7 sopra la rappresentazione nelle stringhe UA).
* &quot;MacOS 11.0.0

### La versione del sistema operativo Mac non è corretta nell&#39;agente utente dopo la versione 10.15.7 

L&#39;agente utente sui computer Apple mostra la versione del sistema operativo come 10.15.7 anche se si tratta di versioni più recenti. Ciò è stato fatto perché l&#39;inclusione della versione 11 nell&#39;UA avrebbe causato problemi con alcuni siti web. Questo vale per *tutti i browser* e non è correlato &quot;congelamento&quot; di Google dell&#39;agente utente sui browser Chromium.

I suggerimenti client includono la versione corretta nel suggerimento della versione della piattaforma (&quot;Sec-CH-UA-Platform-Version&quot;). Questo è un suggerimento ad alta entropia quindi non viene raccolto automaticamente dall&#39;Adobe. Consulta la sezione [Domande frequenti sui suggerimenti di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) per informazioni dettagliate su come raccogliere suggerimenti ad alta entropia.

### La versione di Windows non è corretta nell&#39;agente utente che inizia con Windows 11

A partire da gennaio 2023, l&#39;agente utente in tutti i browser mostra rappresenta Windows 11 come Windows 10.

I suggerimenti client includono la versione corretta nel suggerimento della versione della piattaforma (&quot;Sec-CH-UA-Platform-Version&quot;). Questo è un suggerimento ad alta entropia quindi non viene raccolto automaticamente dall&#39;Adobe. Consulta la sezione [Domande frequenti sui suggerimenti di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) per informazioni dettagliate su come raccogliere suggerimenti ad alta entropia.
