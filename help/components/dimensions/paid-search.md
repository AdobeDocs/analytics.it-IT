---
title: Ricerca a pagamento
description: Distingue le metriche da ricerca a pagamento e naturale.
feature: Dimensions
exl-id: b12665a3-e92f-4fc1-acd3-ea17a316e5e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# Ricerca a pagamento

La &quot;Ricerca a pagamento&quot; [dimensione](overview.md) consente di esaminare qualsiasi metrica e confrontarla tra ricerca a pagamento e ricerca naturale. Tutti gli altri risultati al di fuori dei motori di ricerca vengono omessi. Questa dimensione è utile per comprendere in che modo le attività di ricerca a pagamento si confrontano con la ricerca organica.

## Popola questa dimensione con i dati

L’unico requisito per il corretto funzionamento di questa dimensione è disporre di [Rilevamento di ricerca a pagamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/paid-search-detection/paid-search-detection.md) configurato correttamente nelle impostazioni della suite di rapporti. Se il rilevamento di ricerche a pagamento è configurato correttamente e una suite di rapporti contiene dati, questa dimensione funziona sempre.

## Elementi dimensionali

Gli elementi Dimension includono due valori statici: `"Natural"` e `"Paid"`. Se una visita soddisfa i criteri di un motore di ricerca e corrisponde anche al rilevamento di ricerche a pagamento, appartiene al `"Paid"` elemento dimensione. Se una visita soddisfa i criteri di un motore di ricerca e *non* corrisponde al rilevamento di ricerche a pagamento, appartiene al `"Natural"` elemento dimensione.
