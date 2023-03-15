---
title: Supporto per cookie
description: Determina se il browser supporta i cookie.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 3%

---

# Supporto per cookie

La dimensione &quot;Supporto cookie&quot; segnala se il browser supporta i cookie per un dato hit. È utile determinare la proporzione di visitatori che utilizzano browser che supportano i cookie e di quelli che li disabilitano intenzionalmente.

## Popola questa dimensione con i dati

Questa dimensione raccoglie dati da [`k` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement tenta di impostare un cookie denominato `s_cc`, quindi rileva se il cookie esiste. Il risultato è il valore del parametro della stringa query `Y` (se il browser supporta e dispone di cookie abilitati) oppure `N` (se i cookie del browser sono disabilitati). Se utilizzi AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), assicurati di includere i `k` parametro della stringa di query su ogni hit con il valore `Y` o `N`.

## Elementi dimensionali

Gli elementi del Dimension includono `Enabled`, `Disabled`, e `Unknown`.

* **`Enabled`**: il browser supporta i cookie e li ha abilitati.
* **`Disabled`**: il browser non supporta i cookie o il visitatore li ha disabilitati.
* **`Unknown`**: AppMeasurement non è riuscito a determinare il supporto dei cookie. Il `k` stringa di query non presente nella richiesta di immagine.
