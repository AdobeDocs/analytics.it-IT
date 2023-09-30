---
title: Dominio
description: L’organizzazione o l’ISP utilizzato dal visitatore per accedere a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 2%

---

# Dominio

Il &#39;Dominio&#39; [dimensione](overview.md) segnala i punti di accesso utilizzati dai visitatori per accedere a internet.

## Popola questa dimensione con i dati

Adobe di partner con [Elemento digitale](https://www.digitalelement.com/) per determinare il dominio del punto di accesso. Per determinare il dominio del punto di accesso vengono utilizzati diversi metodi, tra cui la ricerca DNS inversa. Non richiede alcuna configurazione e non dispone di una variabile da compilare.

* Ad AppMeasurement, le implementazioni di questa dimensione sono pronte all’uso.
* Per le implementazioni dell’SDK web, abilita [!UICONTROL Network Lookup] quando [configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Elementi dimensionali

Esempi di elementi dimensionali includono `comcast.net`, `rr.com`, `sbcglobal.net`, e `amazonaws.com`. Questi domini sono punti di accesso e non necessariamente il dominio che rappresenta un ISP o un’organizzazione.

Valori Dimension di `None` significa che il proprietario dell&#39;indirizzo IP del punto di accesso non ha fornito un dominio.
