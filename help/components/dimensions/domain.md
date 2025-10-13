---
title: Dominio
description: L’organizzazione o l’ISP utilizzato dal visitatore per accedere a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 8%

---

# Dominio

La [dimensione](overview.md) del &#39;dominio&#39; riporta i punti di accesso utilizzati dai visitatori per accedere a Internet.

## Popolare questa dimensione con i dati

Adobe collabora con [elemento digitale](https://www.digitalelement.com/) per determinare il dominio del punto di accesso. Per determinare il dominio del punto di accesso vengono utilizzati diversi metodi, tra cui la ricerca DNS inversa. Non richiede alcuna configurazione e non dispone di una variabile da compilare.

* Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito.
* Per le implementazioni di Web SDK, abilita [!UICONTROL Network Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi dimensionali di esempio includono `comcast.net`, `rr.com`, `sbcglobal.net` e `amazonaws.com`. Questi domini sono punti di accesso e non necessariamente il dominio che rappresenta un ISP o un’organizzazione.

I valori Dimension `None` indicano che il proprietario dell&#39;indirizzo IP del punto di accesso non ha fornito un dominio.
