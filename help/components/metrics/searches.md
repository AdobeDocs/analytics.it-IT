---
title: Ricerche
description: Il numero di volte in cui un hit corrisponde a criteri di ricerca esterni.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 1%

---


# Ricerche

La metrica &quot;Searches&quot; (Ricerche) mostra il numero di hit che corrispondono al rilevamento di ricerche esterne di Adobe. Questa metrica è utile quando si desidera esaminare gli elementi di dimensione non di ricerca e vedere in che modo hanno contribuito al traffico dei motori di ricerca.

## Modalità di calcolo di questa metrica

Questa metrica indica il numero di hit che corrispondono al rilevamento di ricerca esterno di Adobe. Deve corrispondere a entrambi i seguenti parametri:

* Il valore referrer dell&#39;hit è un dominio di ricerca riconosciuto da Adobe
* L&#39;URL di provenienza dell&#39;hit contiene un parametro di stringa di query per parole chiave. A causa di pratiche di privacy moderne, questo valore della stringa di query è in genere vuoto. Adobe riconosce le stringhe di query vuote per parole chiave come parte del rilevamento di ricerche.
