---
title: Dominio
description: L’organizzazione o l’ISP utilizzato dal visitatore per accedere a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 3%

---

# Dominio

La dimensione &quot;Dominio&quot; riporta i punti di accesso utilizzati dai visitatori per accedere a Internet.

## Popola questa dimensione con i dati

Adobe di partner con [Elemento digitale](https://www.digitalelement.com/) per determinare il dominio del punto di accesso. Per determinare il dominio del punto di accesso vengono utilizzati diversi metodi, tra cui la ricerca DNS inversa. Non richiede alcuna configurazione e non dispone di una variabile da compilare. Funziona con tutte le implementazioni AppMeasurement pronte all’uso.

## Elementi dimensionali

Esempi di elementi dimensionali includono `comcast.net`, `rr.com`, `sbcglobal.net`, e `amazonaws.com`. Tieni presente che questi domini sono punti di accesso e non necessariamente il dominio che rappresenta un ISP o un’organizzazione.

Valori Dimension di `None` significa che il proprietario dell&#39;indirizzo IP del punto di accesso non ha fornito un dominio.
