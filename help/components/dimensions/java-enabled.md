---
title: Java abilitato
description: Determina se Java è abilitato nel browser.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 1%

---

# Java abilitato

La dimensione &quot;Java abilitato&quot; determina se il browser al momento dispone di Java abilitato. È utile nei casi in cui desideri introdurre funzionalità basate su Java sul tuo sito e vuoi sapere quanti visitatori hanno già abilitato Java. Per coloro che hanno disabilitato Java, puoi fornire un&#39;alternativa o istruzioni su come abilitarlo.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dal [`v` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati rilevando se Java è abilitato nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il `v` parametro della stringa query contenente &quot;Y&quot; o &quot;N&quot; se desideri utilizzare questa dimensione.

## Elementi Dimension

Gli elementi di Dimension includono &quot;Abilitato&quot;, &quot;Disabilitato&quot; e &quot;Sconosciuto&quot;.

* **Abilitato**: Java è abilitato nel browser. La `v` la stringa di interrogazione conteneva il valore &quot;Y&quot;.
* **Disabilitato**: Java è disabilitato nel browser, o in caso contrario non supporta Java. La `v` la stringa di interrogazione conteneva il valore &quot;N&quot;.
* **Sconosciuto**: AppMeasurement non è riuscito a determinare il supporto Java. La `v` stringa di query non presente nella richiesta di immagine.
