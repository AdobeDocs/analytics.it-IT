---
title: Uscite
description: Un’istanza dell’ultimo valore in una visita.
feature: Metrics
exl-id: 0997ed1f-29b0-403d-9ed2-644a5ff19aef
TQID: https://experienceleague.adobe.com/KTpLeq4YjWgaFR-xcq1PBENAO5mb-wV-71BODlRGGlM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 184
ht-degree: 3%

---

# Uscite

*Questa pagina della guida descrive il funzionamento delle uscite come una metrica. Per informazioni sul funzionamento delle uscite come dimensione, vedere [Dimensioni di uscita](../dimensions/exit-dimensions.md).*

La [metrica](overview.md) &quot;Uscite&quot; mostra il numero di volte in cui un dato elemento dimensione viene acquisito come ultimo valore in una visita. Questa metrica è utile quando vuoi saperne di più sull’ultima cosa che i visitatori vedono prima di lasciare il sito. Vedere gli ultimi valori di una dimensione può aiutarti a comprendere e ottimizzare l’esperienza che un visitatore ottiene prima di partire.

## Come è calcolata questa metrica

Al termine di una [visita](visits.md), registra l&#39;elemento dimensione più recente come uscita. Esiste una sola uscita per dimensione per visita. Non è necessariamente l’ultimo hit della visita se la dimensione è stata impostata negli hit precedenti. È una metrica basata sulle visite; si applica retroattivamente a tutti gli hit nella visita.

>[!TIP]
>
>Se visualizzi questa metrica rispetto a una dimensione non sempre impostata in ogni visita, puoi nascondere l’elemento dimensione &quot;Non specificato&quot; in Analysis Workspace. Fare clic sull&#39;icona del filtro, quindi deselezionare [!UICONTROL Include unspecified (None)].
