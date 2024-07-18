---
title: Supporto per cookie
description: Determina se il browser supporta i cookie.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 7%

---

# Supporto per cookie

Il rapporto &quot;Supporto cookie&quot; [dimension](overview.md) indica se il browser supporta i cookie per un determinato hit. È utile determinare la proporzione di visitatori che utilizzano browser che supportano i cookie e di quelli che li disabilitano intenzionalmente.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalla stringa di query [`k`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. L&#39;AppMeasurement tenta di impostare un cookie denominato `s_cc`, quindi rileva se il cookie esiste. Il risultato è il valore del parametro della stringa di query `Y` (se il browser supporta e ha i cookie abilitati) o `N` (se il browser ha i cookie disabilitati). Se utilizzi AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno a AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `k` in ogni hit con il valore `Y` o `N`.

## Elementi dimensionali

Gli elementi della dimensione includono `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: il browser supporta i cookie e li ha abilitati.
* **`Disabled`**: il browser non supporta i cookie o il visitatore li ha disabilitati.
* **`Unknown`**: l&#39;AppMeasurement non è in grado di determinare il supporto dei cookie. La stringa di query `k` non è presente nella richiesta di immagine.
