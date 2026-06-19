---
title: Altezza browser - con bucket
description: Altezza della finestra del browser in pixel.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 292
ht-degree: 3%

---

# Altezza browser

In &#39;Altezza browser - bucket&#39; [dimensione](overview.md) è visualizzata l&#39;altezza della finestra del browser, classificata in gruppi predefiniti. Questa dimensione è utile quando desideri capire dove si trova la &quot;piega&quot; sul sito per i visitatori. Sapere dove si trova la piega può consentirti di ottimizzare il contenuto da visualizzare.

Questa dimensione è diversa dall’altezza dello schermo. L&#39;altezza del browser è il numero di pixel all&#39;interno dello spazio visualizzabile del browser, mentre l&#39;altezza dello schermo è l&#39;altezza dell&#39;intero monitor in pixel. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

L&#39;altezza del browser è sempre inferiore o uguale all&#39;altezza dello schermo, poiché non include la navigazione o i bordi del browser.

>[!NOTE]
>
>Data Warehouse fornisce anche una dimensione &#39;[!UICONTROL Browser height - granular]&#39; che riporta l&#39;altezza esatta dei pixel invece di raggruppare i valori in bucket predefiniti.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa di query [`bh`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `window.innerHeight` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `bh` nel primo hit di ogni visita.

Adobe mantiene l’altezza del browser per una visita. Se l’altezza del browser è regolata a metà visita, la regolazione non viene registrata.

## Elementi dimensionali

Gli elementi Dimension includono tutte le altezze del browser raccolte, classificate in gruppi predefiniti. Ad esempio, se l&#39;altezza del browser di un hit è `720`, viene raggruppato nell&#39;elemento dimensione `700 to 799`.
