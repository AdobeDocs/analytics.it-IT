---
title: Area geografica di Activity Map
description: L’area del sito su cui hai fatto clic.
feature: Dimensions
role: User, Admin
exl-id: e262e537-ce73-492a-8ab3-b88cd77cb8c5
TQID: https://experienceleague.adobe.com/mmLp5-dgKGeovIOMPZxliyhfbpUSMLXca-3Qs6QA0SA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 5%

---

# Area geografica di Activity Map

Nella &#39;Area geografica Activity Map&#39; [dimensione](overview.md) sono visualizzate le aree del sito in cui è stato fatto più clic. Questa dimensione è utile quando desideri confrontare i clic tra aree generali del sito anziché tra singoli collegamenti. È utile anche per le aree del sito che forniscono contenuti dinamici. Ad esempio, se hai una pagina iniziale con articoli di notizie rotanti, usare la dimensione [Activity Map Link](activity-map-link.md) sarebbe difficile perché il testo del collegamento cambia costantemente. Tuttavia, poiché tali collegamenti utilizzano la stessa area, è possibile analizzarne le prestazioni anche se i singoli collegamenti potrebbero cambiare ogni giorno.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [variabile di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. Se l&#39;implementazione utilizza [Activity Map](/help/analyze/activity-map/overview.md), questa variabile di dati di contesto raccoglie automaticamente i dati quando si fa clic sui collegamenti.

Per un determinato collegamento su cui è stato fatto clic, controlla l’elemento DOM principale in base all’ordine:

* Valore nell&#39;attributo impostato da [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - impostato sull&#39;attributo `id` per impostazione predefinita
* Un valore nell&#39;attributo `aria-label` quando l&#39;attributo `role="region"`
* Elementi semantici `<header>`, `<main>`, `<footer>` o `<nav>` (solo Web SDK)

Se l&#39;elemento DOM padre non soddisfa nessuno dei criteri di cui sopra, la ricerca continua in modo ricorsivo fino alla gerarchia DOM. Se non vengono trovati elementi corrispondenti, viene restituito il valore `BODY`.

## Elementi dimensionali

Gli elementi di Dimension includono le aree etichettate sul sito. I valori di regione specifici dipendono dagli attributi utilizzati e dalla presenza di elementi HTML semantici.
