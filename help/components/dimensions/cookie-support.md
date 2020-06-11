---
title: Supporto per cookie
description: Determina se il browser supporta i cookie.
translation-type: tm+mt
source-git-commit: a8dc233e962a49674a30ff3c9f0b5d0d45b09f24
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---


# Supporto per cookie

La dimensione &#39;Cookie support&#39; segnala se il browser supporta i cookie per un determinato hit. È utile determinare il rapporto tra i visitatori che utilizzano browser che supportano i cookie e quelli che li disattivano intenzionalmente.

## Compilare questa dimensione con i dati

Questa dimensione raccoglie i dati dalla stringa [`k` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement tenta di impostare un cookie denominato `s_cc`, quindi rileva se il cookie esiste già. Il risultato è il valore del parametro della stringa di query `Y` (se il browser supporta e dispone di cookie abilitati) o `N` (se il browser ha cookie disattivati). Se usi AppMeasurement (ad esempio tramite Adobe Experience Platform Launch), questa dimensione non è disponibile. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertati di includere il parametro della stringa di `k` query in ogni hit con il valore `Y` o `N`.

## Valori dimensione

I valori delle dimensioni includono `Enabled`, `Disabled`e `Unknown`.

* **`Enabled`**: Il browser supporta i cookie e li attiva.
* **`Disabled`**: Il browser non supporta i cookie, o il visitatore li ha disattivati.
* **`Unknown`**: AppMeasurement: impossibile determinare il supporto dei cookie. La stringa di `k` query non era presente nella richiesta immagine.
