---
title: Java abilitato
description: Determina se Java è abilitato nel browser.
feature: Dimensions
exl-id: 2d4b4ea2-65ba-4d39-a040-f989b5eddc6e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 5%

---

# Java abilitato

La [dimensione](overview.md) &quot;Java abilitato&quot; determina se nel browser è abilitato Java. È utile nei casi in cui desideri introdurre funzionalità basate su Java sul sito e vuoi sapere quanti visitatori hanno già Java abilitato. Per coloro che hanno Java disabilitato, puoi fornire un’alternativa o istruzioni su come abilitarlo.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa di query [`v`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati rilevando se Java è abilitato nel browser. Se utilizzi una libreria di AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno a AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `v` contenente &quot;Y&quot; o &quot;N&quot; se desideri utilizzare questa dimensione.

## Elementi dimensionali

Gli elementi di Dimension includono &quot;Enabled&quot; (Abilitato), &quot;Disabled&quot; (Disabilitato) e &quot;Unknown&quot; (Sconosciuto).

* **Abilitato**: Java è abilitato nel browser. La stringa di query `v` contiene il valore &quot;Y&quot;.
* **Disabilitato**: Java è disabilitato nel browser o non supporta Java. La stringa di query `v` contiene il valore &quot;N&quot;.
* **Sconosciuto**: l&#39;AppMeasurement non è stato in grado di determinare il supporto Java. La stringa di query `v` non è presente nella richiesta di immagine.
