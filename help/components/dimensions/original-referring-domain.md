---
title: Dominio di riferimento originale
description: Il primo dominio di riferimento in cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 409
ht-degree: 3%

---

# Dominio di riferimento originale

La [dimensione](overview.md) del &#39;dominio di riferimento originale&#39; riporta il primo dominio di riferimento attraverso il quale un visitatore ha fatto clic per raggiungere il sito. Una volta impostato, contiene lo stesso valore per l’intera durata di vita dell’ID visitatore. Questa dimensione è utile per capire quali siti di terze parti originariamente indirizzano il traffico verso il sito.

>[!IMPORTANT]
>
>Devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione sia nell’interfaccia di Analytics che nell’implementazione.

* All&#39;interno dell&#39;implementazione, questa dimensione recupera i dati dalla stringa di query [`r`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `r` nelle richieste di immagini.
* Nell&#39;interfaccia di Analytics devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

Adobe mantiene il dominio di riferimento originale per tutta la vita di un visitatore. Se un visitatore abbandona e fa clic su un collegamento in un dominio diverso in qualsiasi momento, il nuovo valore non viene registrato. Se desideri visualizzare nuovi valori, consulta [Dominio di riferimento](referring-domain.md).

## Elementi dimensionali

Gli elementi di Dimension includono i domini su cui i visitatori fanno clic per accedere al sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l&#39;elemento dimensione `"None"`. Questo elemento dimensione significa che non era presente alcun valore di riferimento, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro.

## Confronta dominio di riferimento con dominio di riferimento originale

Il dominio di riferimento può cambiare tra le visite. Ad esempio, un visitatore arriva al tuo sito tramite `google.com`, quindi una settimana dopo arriva al tuo sito tramite `twitter.com`. Alla fine effettuano un acquisto sul tuo sito. Se si utilizza Dominio di riferimento come dimensione con attribuzione ultimo contatto, `twitter.com` ottiene il merito per l&#39;acquisto. Se utilizzi il dominio di riferimento Originale come dimensione, `google.com` ottiene il merito per l&#39;acquisto indipendentemente dal modello di attribuzione.

Il dominio di riferimento originale non cambia mai per l’intera durata di un determinato ID visitatore.
