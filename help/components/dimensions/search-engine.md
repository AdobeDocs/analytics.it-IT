---
title: Motore di ricerca
description: Il motore di ricerca utilizzato dal visitatore per raggiungere il sito.
feature: Dimensions
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
TQID: https://experienceleague.adobe.com/fOk6ypu24XzT6aypOHUAE-RYSW39wyrzkyt-lvOKy7Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 225
ht-degree: 6%

---

# Motore di ricerca

La [dimensione](overview.md) del &#39;motore di ricerca&#39; segnala i motori di ricerca utilizzati dai visitatori per raggiungere il sito. Un referente deve soddisfare entrambe le seguenti condizioni per essere classificato come motore di ricerca:

* Il dominio di riferimento è riconosciuto da Adobe come un motore di ricerca valido;
* Nell&#39;URL di riferimento esiste un parametro di stringa di query per parola chiave. Il parametro della stringa di query può essere vuoto (come nel caso di diversi motori di ricerca a causa di pratiche di privacy).

Per distinguere la ricerca a pagamento da quella naturale, è necessario [Rilevamento ricerca a pagamento](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md). Sono disponibili più dimensioni per i motori di ricerca:

* **Motore di ricerca**: il motore di ricerca utilizzato per raggiungere il sito, indipendentemente dal fatto che sia a pagamento o naturale.
* **Motore di ricerca - a pagamento**: motore di ricerca utilizzato per raggiungere il sito, che corrisponde al rilevamento di ricerche a pagamento.
* **Motore di ricerca - naturale**: motore di ricerca utilizzato per raggiungere il sito, che non corrisponde al rilevamento di ricerche a pagamento.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne ad Adobe. Ogni valore è basato sul [referrer](referrer.md) dell&#39;hit, che dipende da [Filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Assicurati che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi dimensionali

Gli elementi di Dimension includono i motori di ricerca utilizzati per raggiungere il sito. Valori di esempio includono `"Google"`, `"Microsoft Bing"`, e `"DuckDuckGo"`. L&#39;elemento dimensione `"Unspecified"` è tutto traffico non di ricerca.
