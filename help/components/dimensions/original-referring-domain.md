---
title: Dominio di riferimento originale
description: Il primo dominio di riferimento in cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 6%
---
# Dominio di riferimento originale

La [dimensione](overview.md) del &#39;dominio di riferimento originale&#39; riporta il primo dominio di riferimento attraverso il quale un visitatore ha fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata di vita dell’ID visitatore. Questa dimensione è utile per capire quali siti di terze parti originariamente indirizzano il traffico verso il sito.

>[!IMPORTANT]
>
>Devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

## Popolare questa dimensione con i dati

Adobe deriva questa dimensione dal primo [referrer](referrer.md) del visitatore, utilizzando la porzione di dominio dell&#39;URL del referente. Nessuna variabile da impostare. Devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti; in caso contrario, potrai includere domini interni o impedire la visualizzazione di domini esterni.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal primo referente del visitatore) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal primo referente del visitatore) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Visitatore |

Se un visitatore abbandona e fa clic su un collegamento in un dominio diverso in qualsiasi momento, il nuovo valore non viene registrato. Per visualizzare i nuovi valori, vedere [Dominio di riferimento](referring-domain.md).

## Elementi dimensionali

Gli elementi di Dimension includono i domini su cui i visitatori fanno clic per accedere al sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l&#39;elemento dimensione `"None"`. Questo elemento dimensione significa che non era presente alcun valore di riferimento, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro.

## Confronta dominio di riferimento con dominio di riferimento originale

Il dominio di riferimento può cambiare tra le visite. Ad esempio, un visitatore arriva al tuo sito tramite `google.com`, quindi una settimana dopo arriva al tuo sito tramite `twitter.com`. Alla fine effettuano un acquisto sul tuo sito. Se si utilizza Dominio di riferimento come dimensione con attribuzione ultimo contatto, `twitter.com` ottiene il merito per l&#39;acquisto. Se utilizzi il dominio di riferimento Originale come dimensione, `google.com` ottiene il merito per l&#39;acquisto indipendentemente dal modello di attribuzione.

Il dominio di riferimento originale non cambia mai per l’intera durata di un determinato ID visitatore.
