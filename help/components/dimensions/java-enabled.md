---
title: Java abilitato
description: Determina se Java è abilitato nel browser.
translation-type: tm+mt
source-git-commit: 226c54b782651ea8c6f4b7bb8030a1513c440a1d
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---


# Java abilitato

La dimensione &quot;Java enabled&quot; determina se il browser al momento dispone di Java abilitato. È utile nei casi in cui si desidera introdurre funzionalità basate su Java sul sito e si desidera sapere quanti visitatori dispongono già di Java abilitato. Per coloro che hanno Java disattivato, puoi fornire un&#39;alternativa o istruzioni su come attivarlo.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`v` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati rilevando se Java è abilitato nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite Adobe Experience Platform Launch), questa dimensione non è disponibile. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertati di includere il parametro della stringa di `v` query contenente &quot;Y&quot; o &quot;N&quot; per utilizzare questa dimensione.

## Valori dimensione

I valori delle dimensioni includono &quot;Enabled&quot;, &quot;Disabled&quot; e &quot;Unknown&quot;.

* **Abilitato**: Java è abilitato nel browser. La stringa di `v` query conteneva il valore &quot;Y&quot;.
* **Disattivato**: Java è disattivato nel browser, altrimenti non supporta Java. La stringa di `v` query conteneva il valore &quot;N&quot;.
* **Sconosciuto**: AppMeasurement non è stato in grado di determinare il supporto Java. La stringa di `v` query non era presente nella richiesta immagine.
