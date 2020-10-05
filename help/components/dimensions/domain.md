---
title: Dominio
description: L'organizzazione o l'ISP che il visitatore utilizza per accedere a Internet.
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 1%

---


# Dominio

La dimensione &quot;Dominio&quot; indica i punti di accesso che i visitatori utilizzano per accedere a Internet.

## Compilare questa dimensione con i dati

 Adobe collabora con [Digital Element](https://www.digitalelement.com/) per determinare il dominio del punto di accesso. Per determinare il dominio del punto di accesso vengono utilizzati diversi metodi, inclusa la ricerca DNS inversa. Non richiede alcuna configurazione e non ha una variabile da compilare. Funziona automaticamente con tutte le implementazioni AppMeasurement.

## Elementi Dimension

Gli elementi di dimensione di esempio includono `comcast.net`, `rr.com`, `sbcglobal.net`e `amazonaws.com`. Questi domini sono punti di accesso e non necessariamente il dominio che rappresenta un ISP o un&#39;organizzazione.

I valori Dimension `None` indicano che il proprietario dell&#39;indirizzo IP del punto di accesso non ha fornito un dominio.
