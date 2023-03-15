---
title: Java abilitato
description: Determina se Java è abilitato nel browser.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 2%

---

# Java abilitato

La dimensione &quot;Java abilitato&quot; determina se nel browser è abilitato Java. È utile nei casi in cui desideri introdurre funzionalità basate su Java sul sito e vuoi sapere quanti visitatori hanno già Java abilitato. Per coloro che hanno Java disabilitato, puoi fornire un’alternativa o istruzioni su come abilitarlo.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`v` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati rilevando se Java è abilitato nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), assicurati di includere i `v` parametro della stringa di query contenente &quot;Y&quot; o &quot;N&quot; se desideri utilizzare questa dimensione.

## Elementi dimensionali

Gli elementi di Dimension includono &quot;Enabled&quot; (Abilitato), &quot;Disabled&quot; (Disabilitato) e &quot;Unknown&quot; (Sconosciuto).

* **Abilitato**: Java è abilitato nel browser. Il `v` la stringa di query conteneva il valore &quot;Y&quot;.
* **Disabilitato**: Java è disabilitato nel browser o non supporta in altro modo Java. Il `v` la stringa di query conteneva il valore &quot;N&quot;.
* **Sconosciuto**: AppMeasurement non è stato in grado di determinare il supporto Java. Il `v` stringa di query non presente nella richiesta di immagine.
