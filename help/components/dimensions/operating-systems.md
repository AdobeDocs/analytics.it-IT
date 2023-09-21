---
title: Sistema operativo
description: Il sistema operativo del visitatore.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 1%

---

# Sistema operativo

Il &#39;sistema operativo&#39; [dimensione](overview.md) mostra il sistema operativo e la versione utilizzati dal visitatore. Se nella proprietà web sono presenti funzioni specifiche per il sistema operativo, questa dimensione ti aiuta a capire quali sistemi operativi sono più comuni.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento a una tabella di ricerca interna a Adobe. Il valore di ricerca si basa sul `User-Agent` Intestazione HTTP nelle richieste di immagini. Se utilizzi una libreria di AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito.

## Elementi dimensionali

Gli elementi di Dimension includono i sistemi operativi utilizzati dai visitatori. Alcuni esempi includono `"Windows 10"`, `"OS X 10.15"`, e `"Android 9"`.

## Modifiche dell&#39;etichettatura e della definizione

Di seguito è riportato un elenco di problemi specifici relativi al modo in cui il sistema operativo è stato rappresentato nell’agente utente e nei rapporti di Adobe Analytics.

### Modifica della granularità del sistema operativo

Il 2 marzo 2023 è stato aggiornato il reporting per includere maggiori dettagli nel sistema operativo. Dopo questa data includiamo la versione patch del sistema operativo. Ad esempio, un utente con OS X 10.15.7 sarebbe apparso come &quot;OS X 10.15&quot; prima del 2 marzo. Dopo il 2 marzo appariranno come &quot;OS X 10.15.7&quot;.

### Modifica della convenzione di denominazione per il sistema operativo Apple:

A partire dalla versione 11 utilizzeremo MacOS invece di OS X per fare riferimento al sistema operativo Apple.

Esempi:

* &quot;OS X 10.15&quot; (vedere la nota seguente sulla versione 10.15.7 sopra la rappresentazione nelle stringhe UA).
* &quot;MacOS 11.0.0

### La versione del sistema operativo Mac non è corretta nell’agente utente dopo la versione 10.15.7 

L’agente utente sui computer Apple mostra la versione del sistema operativo 10.15.7 anche per le versioni più recenti. Ciò è stato fatto perché l’inclusione della versione 11 negli Stati Uniti avrebbe causato problemi con alcuni siti web. Questo è vero per *tutti i browser* e non è correlato al &quot;congelamento&quot; dell’agente utente da parte di Google sui browser basati su Chromium.

Tieni presente che gli hint client includono la versione corretta nell’hint di versione della piattaforma (&quot;Sec-CH-UA-Platform-Version&quot;). Questo è un hint ad alta entropia quindi non viene raccolto automaticamente dall&#39;Adobe. Consulta la [Domande frequenti sui suggerimenti di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) per informazioni dettagliate su come raccogliere hint ad alta entropia.

### La versione di Windows non è corretta nell’agente utente che inizia con Windows 11

A partire da gennaio 2023, l’agente utente in tutti i browser mostra Windows 11 come Windows 10.

Tieni presente che gli hint client includono la versione corretta nell’hint di versione della piattaforma (&quot;Sec-CH-UA-Platform-Version&quot;). Questo è un hint ad alta entropia quindi non viene raccolto automaticamente dall&#39;Adobe. Consulta la [Domande frequenti sui suggerimenti di Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) per informazioni dettagliate su come raccogliere hint ad alta entropia.
