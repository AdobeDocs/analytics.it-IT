---
title: URL della pagina
description: URL della pagina.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 6%
---
# URL della pagina

La &#39;dimensione URL pagina&#39; [dimensione](overview.md) elenca gli URL sul sito.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo in Data Warehouse. Se desideri utilizzare una dimensione URL in altre soluzioni Analytics, prova a copiare il valore in un [eVar](evar.md) per ogni hit.

## Popolare questa dimensione con i dati

AppMeasurement raccoglie automaticamente l&#39;URL della pagina in ogni [chiamata di visualizzazione della pagina (`t()`)](/help/implement/vars/functions/t-method.md). È possibile sovrascrivere il valore raccolto utilizzando la variabile [`pageURL`](/help/implement/vars/page-vars/pageurl.md). Se un URL è più lungo di 255 byte, l&#39;overflow viene memorizzato nel parametro della stringa di query `-g`. Nell’URL sono incluse le stringhe di protocollo e di query. [Le chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) eliminano sempre questa dimensione, anche se il valore URL esiste.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`pageURL`](/help/implement/vars/page-vars/pageurl.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.URL`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parametro query** | [`g`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<pageUrl>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 255 byte (nessun limite fisso con overflow) |
| **Persistenza** | Hit |

## Compilare un’eVar con l’URL

Adobe consiglia di impostare un eVar per la stringa concatenata `window.location.hostname + window.location.pathname`. Questa stringa funziona in genere meglio di `window.location.href` perché omette i tag di protocollo, le stringhe di query e di ancoraggio.

Se desideri che eVar corrisponda esattamente alla dimensione &quot;URL pagina&quot; in Data Warehouse, puoi utilizzare [variabili dinamiche](/help/implement/vars/page-vars/dynamic-variables.md) e impostare eVar su `D=g` per ogni hit.

## Elementi dimensionali

Gli elementi di Dimension includono gli URL delle pagine del sito.
