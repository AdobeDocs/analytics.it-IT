---
title: Supporto dei cookie persistenti
description: Determina se il visitatore può supportare i cookie persistenti.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 6%

---

# Supporto dei cookie persistenti

La dimensione [dimension](overview.md) del supporto dei cookie persistenti mostra se l&#39;hit ha utilizzato un identificatore visitatore proveniente da un&#39;origine persistente. La sorgente persistente più comune proviene da un cookie, ma può anche utilizzare intestazioni mobili e altre sorgenti.

## Popolare questa dimensione con i dati

Adobe determina il valore di questa dimensione lato server in base all’origine dell’identificatore dell’hit. Non esiste un modo per impostarlo direttamente. Funziona automaticamente per tutte le implementazioni.

## Elementi dimensionali

* **`Enabled`**: l&#39;identificatore del visitatore dell&#39;hit proviene da un&#39;origine che in genere persiste. Gli esempi più comuni includono `aid`, `fid` o `mid` parametri della stringa di query, in quanto derivano i loro valori da un cookie.
* **`Disabled`**: l&#39;identificatore visitatore dell&#39;hit proviene da un&#39;origine che Adobe non riconosce come persistente, ad esempio IP + stringa dell&#39;agente utente. Questo elemento dimensione include anche gli ID visitatore personalizzati che utilizzano la variabile [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Differenza tra &quot;Supporto cookie&quot; e &quot;Supporto cookie persistente&quot;

* **Supporto cookie**: AppMeasurement tenta di impostare un cookie generico. L’elemento dimensione si basa sulla verifica se il cookie è stato impostato correttamente.
* **Supporto cookie persistenti**: l&#39;elemento dimensione si basa sul fatto che l&#39;identificatore dell&#39;hit provenga da un&#39;origine persistente, ad esempio un cookie.
