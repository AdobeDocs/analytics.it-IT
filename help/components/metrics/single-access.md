---
title: Accesso singolo
description: Il numero di volte in cui un elemento dimensione non è cambiato in una visita.
feature: Metrics
exl-id: 973ce835-9d6f-4ead-90c9-0b80aac82cc0
TQID: https://experienceleague.adobe.com/9rDXvGopDNEhkh6cA-JmkwazYWagbMDo1g7yZ2n-gLI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 441
ht-degree: 2%

---

# Accesso singolo

La **[!UICONTROL Single access]** [metrica](overview.md) mostra il numero di visite in cui la dimensione di reporting applicabile conteneva un solo valore per un&#39;intera visita. Si tratta della versione più ampia di [[!UICONTROL Single page visits]](single-page-visits.md) specifica per la dimensione. Questa metrica è utile nel contesto di qualsiasi dimensione in cui desideri visualizzare il valore di una dimensione quando è stata impostata una sola volta durante una visita.

## Come è calcolata questa metrica

La definizione di questa metrica dipende dall&#39;impostazione del progetto di [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **Conta istanze ripetute abilitate**: conta le visite in cui la dimensione contiene esattamente un valore in una visita. Se la dimensione persiste, non può più essere considerata un singolo accesso.
* **Numero istanze ripetute disabilitate**: conta le visite in cui la dimensione contiene un singolo valore univoco. Puoi impostare più volte lo stesso valore per l’elemento dimensionale, oppure impostarlo in modo che persista e venga comunque conteggiato come un singolo accesso.

Indipendentemente da &#39;[!UICONTROL Count repeat instances]&#39;, la visita non è più considerata un singolo accesso se la dimensione cambia in un secondo valore univoco. Le chiamate di tracciamento dei collegamenti sono incluse in questo calcolo se in esse è impostata la dimensione.

## Differenza tra &#39;[!UICONTROL Single access]&#39; e &#39;[!UICONTROL Single page visit]&#39;

Nel contesto della dimensione [[!UICONTROL Page]](../dimensions/page.md), &#39;[!UICONTROL Single access]&#39; e &#39;[!UICONTROL Single page visits]&#39; sono sempre identici indipendentemente dall&#39;impostazione del progetto &#39;[!UICONTROL Count repeat instances]&#39;. Le loro differenze emergono quando utilizzate altre quote.

* **[!UICONTROL Single access]**: mostra il numero di visite in cui era presente l&#39;elemento dimensione specificato per un singolo hit. È contestuale alla dimensione utilizzata nel progetto.
* **[!UICONTROL Single page visit]**: mostra il numero di visite in cui la dimensione &#39;[!UICONTROL Page]&#39; era presente per un singolo hit. Anche se si utilizza un&#39;altra dimensione nel report, vengono comunque conteggiate le visite che contengono un singolo elemento di dimensione univoco &#39;[!UICONTROL Page]&#39;.

Se [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings) è disabilitato, le definizioni delle metriche cambiano leggermente:

* **Accesso singolo**: mostra il numero di visite in cui l&#39;elemento dimensione specificato non è stato modificato per l&#39;intera visita.
* **Visita a pagina singola**: mostra il numero di visite in cui la dimensione &#39;[!UICONTROL Page]&#39; non è stata modificata per l&#39;intera visita.

Ad esempio, considera il seguente esempio di visite con due hit. La dimensione nel report è [[!UICONTROL Site section]](../dimensions/site-section.md) e &#39;[!UICONTROL Count repeat instances]&#39; è disabilitato.

* Un visitatore visita due pagine, ma si trovano entrambe nella stessa sezione del sito. Poiché la sezione del sito è rimasta la stessa durante la visita, conta come un singolo accesso. Non viene conteggiata come visita di una singola pagina perché la visita contiene più di un elemento dimensione [!UICONTROL Page] univoco.
* Un visitatore visita due pagine in diverse sezioni del sito, ma entrambe le pagine hanno lo stesso nome. La visita non viene conteggiata come un singolo accesso perché sono presenti due valori univoci della sezione del sito. Conta come una visita a pagina singola perché è presente un singolo elemento dimensione [!UICONTROL Page] univoco.
