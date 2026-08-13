---
title: Parola chiave di ricerca
description: Parola chiave di ricerca utilizzata dal visitatore per raggiungere il sito.
feature: Dimensions
exl-id: 5a1236a6-f94b-4679-906a-b539afe36887
TQID: https://experienceleague.adobe.com/4naavrC42ddsxGFJfkOJ0wzHLTa7tdMeI9nKDgVWrBY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 4%

---

# Parola chiave di ricerca

La &#39;parola chiave di ricerca&#39; [dimensione](overview.md) riporta le parole chiave di ricerca utilizzate dai visitatori per raggiungere il sito.

>[!IMPORTANT]
>
>La maggior parte dei motori di ricerca non passa più la parola chiave di ricerca a causa di pratiche di privacy crescenti. Riscontri in cui Adobe riconosce un motore di ricerca ma manca un gruppo di parole chiave sotto l&#39;elemento dimensione `"Keyword unavailable"`.

Un referente deve soddisfare entrambe le condizioni seguenti per essere classificato come parola chiave di ricerca:

* Il dominio di riferimento è riconosciuto da Adobe come [motore di ricerca](search-engine.md) valido;
* Nell&#39;URL di riferimento esiste un parametro di stringa di query per parola chiave. Se la stringa di query della parola chiave esiste ma non contiene un valore, viene raggruppata sotto l&#39;elemento dimensione `"Keyword unavailable"`.

Per distinguere la ricerca a pagamento da quella naturale, è necessario [Rilevamento ricerca a pagamento](/help/admin/tools/manage-rs/edit-settings/general/paid-search-detection/paid-search-detection.md). Sono disponibili più dimensioni per le parole chiave di ricerca:

* **Parola chiave di ricerca**: parola chiave di ricerca utilizzata per raggiungere il sito, indipendentemente dal fatto che sia a pagamento o naturale.
* **Parola chiave di ricerca - a pagamento**: parola chiave di ricerca utilizzata per raggiungere il sito, corrispondente al rilevamento di ricerche a pagamento.
* **Parola chiave di ricerca - naturale**: parola chiave di ricerca utilizzata per raggiungere il sito, che non corrisponde al rilevamento di ricerche a pagamento.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne ad Adobe. Ogni valore è basato sul [referrer](referrer.md) dell&#39;hit, che dipende da [Filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md). Assicurati che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi dimensionali

Gli elementi di Dimension includono parole chiave di ricerca utilizzate per raggiungere il sito. L&#39;elemento dimensione `"Unspecified"` è tutto traffico non di ricerca.
