---
title: Supporto per cookie
description: Determina se il browser supporta i cookie.
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 2%

---

# Supporto per cookie

La dimensione &#39;Supporto cookie&#39; indica se il browser supporta i cookie per un determinato hit. È utile determinare il rapporto tra i visitatori che utilizzano i browser che supportano i cookie e quelli che li disattivano intenzionalmente.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i dati dalla [`k` stringa query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement cerca di impostare un cookie denominato `s_cc`, quindi rileva se il cookie esiste. Il risultato è il valore del parametro della stringa query `Y` (se il browser supporta e dispone di cookie abilitati) o `N` (se il browser ha i cookie disabilitati). Se utilizzi AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona come se fosse preconfigurata. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il parametro della stringa di query `k` su ogni hit con il valore `Y` o `N`.

## Elementi Dimension

Gli elementi del Dimension includono `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: Il browser supporta i cookie e li attiva.
* **`Disabled`**: Il browser non supporta i cookie o il visitatore li ha disattivati.
* **`Unknown`**: AppMeasurement non è riuscito a determinare il supporto dei cookie. La stringa di query `k` non era presente nella richiesta di immagine.
