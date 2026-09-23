---
title: Dominio di riferimento
description: Il dominio generale su cui si trovava un visitatore prima di fare clic per accedere al sito.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 4%
---
# Dominio di riferimento

La [dimensione](overview.md) del &#39;dominio di riferimento&#39; segnala i domini su cui i visitatori fanno clic per raggiungere il sito. Questa dimensione è utile per capire quali siti di terze parti generano più traffico verso la tua. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sul sito esterno e un visitatore deve fare clic su di esso.

>[!IMPORTANT]
>
>Devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

Lo stesso rapporto può mostrare risultati diversi tra Analysis Workspace e Data Warehouse. Analysis Workspace segnala il dominio di riferimento per ogni singola pagina, esclusi i valori che corrispondono ai filtri URL interni. Data Warehouse segnala solo il primo dominio di riferimento della visita e ignora i filtri URL interni.

## Popolare questa dimensione con i dati

Adobe deriva questa dimensione dal [referrer](referrer.md) di ogni hit, utilizzando la porzione di dominio dell&#39;URL del referente. Nessuna variabile da impostare. Devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti; in caso contrario, potrai includere domini interni o impedire la visualizzazione di domini esterni.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal referrer) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal referrer) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Visita |

Adobe persiste nel dominio di riferimento per una visita. Se un visitatore abbandona e fa clic su un collegamento su un dominio diverso all’interno di una singola visita, il nuovo valore viene aggiornato e persiste per il resto della visita. Se desideri visualizzare solo il valore originale, consulta [Dominio di riferimento originale](original-referring-domain.md).

## Elementi dimensionali

Gli elementi di Dimension includono i domini su cui i visitatori fanno clic per accedere al sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l&#39;elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione significa che non era presente alcun valore di riferimento, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro. L&#39;elemento dimensione `"Typed/Bookmarked"` viene visualizzato anche per i reindirizzamenti che non supportano Analytics. Vedi [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente delle note tecniche.

### Elementi Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine memorizzate nella cache**: i ragni di Google scansionano costantemente il Web e memorizzano le copie delle pagine nel caso in cui vengano portate offline. Queste pagine memorizzate in cache sono disponibili accanto alla maggior parte dei risultati di ricerca facendo clic sul collegamento &quot;Memorizzate in cache&quot;. Quando un utente fa clic su questo collegamento e visualizza il contenuto memorizzato nella cache di Google, `googleusercontent.com` è l&#39;elemento dimensione.
* **Pagine tradotte**: Google offre un servizio di traduzione solido e comodo. Quando si visualizza un sito che utilizza questo servizio, il sito ha origine da `googleusercontent.com`. Questo elemento dimensione viene visualizzato se l’utente fa clic su un collegamento per tornare al contenuto originale.
