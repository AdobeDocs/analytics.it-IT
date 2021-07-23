---
title: Java abilitato
description: Determina se Java è abilitato nel browser.
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 1%

---

# Java abilitato

La dimensione &quot;Java abilitato&quot; determina se il browser al momento dispone di Java abilitato. È utile nei casi in cui desideri introdurre funzionalità basate su Java sul tuo sito e vuoi sapere quanti visitatori hanno già abilitato Java. Per coloro che hanno disabilitato Java, puoi fornire un&#39;alternativa o istruzioni su come abilitarlo.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [`v` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati rilevando se Java è abilitato nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), assicurati di includere il parametro della stringa di query `v` contenente &quot;Y&quot; o &quot;N&quot; se desideri utilizzare questa dimensione.

## Elementi Dimension

Gli elementi di Dimension includono &quot;Abilitato&quot;, &quot;Disabilitato&quot; e &quot;Sconosciuto&quot;.

* **Abilitato**: Java è abilitato nel browser. La stringa di query `v` conteneva il valore &quot;Y&quot;.
* **Disabilitato**: Java è disabilitato nel browser, o in caso contrario non supporta Java. La stringa di query `v` conteneva il valore &quot;N&quot;.
* **Sconosciuto**: AppMeasurement non è riuscito a determinare il supporto Java. La stringa di query `v` non era presente nella richiesta di immagine.
