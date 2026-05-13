---
description: Scopri come creare segmenti da un punto di contatto, aggiungere segmenti come punto di contatto e confrontare flussi di lavoro chiave tra vari segmenti in un’analisi di abbandono in Analysis Workspace.
keywords: abbandono e segmentazione, segmenti nell’analisi dell’abbandono, confronta i segmenti nell’abbandono
title: Applicare I Segmenti Nell’Analisi Dell’Abbandono
feature: Visualizations
role: User, Admin
exl-id: 2177cd09-5a27-4295-8414-580cf53062cb
TQID: https://experienceleague.adobe.com/LZiLhy8ufqzxHyxjqWy1XLv5uU7JgB5eqzPm6wbXF6s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: dcae653e-62c6-4cc8-84e6-ee110b848296
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 442
ht-degree: 39%

---

# Applicare i segmenti nell’analisi dell’abbandono

Puoi creare segmenti da un punto di contatto, aggiungere segmenti come punto di contatto e confrontare flussi di lavoro chiave tra vari segmenti in Analysis Workspace.

>[!IMPORTANT]
>
>I segmenti utilizzati come punti di controllo in Abbandono devono utilizzare un contenitore di livello inferiore rispetto al contesto generale della visualizzazione Abbandono. Con un Abbandono in contesto visitatore, i segmenti utilizzati come punti di controllo devono essere segmenti basati su visite o hit. Con un Abbandono in contesto visita, i segmenti utilizzati come punto di controllo devono essere segmenti basati su hit. Se si usa una combinazione non valida, l’abbandono sarà 100%. Quando aggiungi un segmento incompatibile come punto di contatto, nella visualizzazione Abbandono viene visualizzato un avviso. Alcune combinazioni di contenitori di segmenti non valide genereranno diagrammi di abbandono non validi, ad esempio:
>
>* Utilizzo di un segmento basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono in contesto visitatore.
>* Utilizzo di un segmento basato su visitatore come punto di contatto all’interno di una visualizzazione Abbandono in un contesto visita.
>* Utilizzo di un segmento basato su visite come punto di contatto all’interno di una visualizzazione Abbandono in un contesto visita.
>

## Creare un segmento da un punto di contatto

1. Crea un segmento da un punto di contatto che ti interessa e che potrebbe essere utile da applicare ad altri rapporti. A tale scopo, fai clic con il pulsante destro sul punto di contatto e seleziona **[!UICONTROL Create segment from touchpoint]**.

   ![](assets/fallout-createsegment.png)

   Viene aperto Segment Builder (Generatore segmenti), precompilato con il segmento sequenziale predefinito che corrisponde al punto di contatto selezionato:

   ![](assets/fallout-definesegment.png)

1. Assegna al segmento un titolo e una descrizione e salvalo.

   Ora puoi utilizzare questo segmento in qualsiasi progetto.

## Aggiungere un segmento come punto di contatto

Per vedere, ad esempio, la tendenza degli hit per app mobili e l’effetto dell’abbandono, trascina il segmento Hit nell’abbandono:

![](assets/segment-touchpoint.png)

Oppure puoi creare un punto di contatto AND trascinando il segmento degli hit dell’app mobile su un altro punto di controllo.

## Confrontare i segmenti in Abbandono

Puoi confrontare un numero illimitato di segmenti nella visualizzazione Abbandono. (Il video seguente afferma che è possibile confrontare fino a 3 segmenti, il che è errato.)



1. Selezionare i segmenti da confrontare dal pannello [!UICONTROL Segment] a sinistra. Nell&#39;esempio Nell&#39;esempio sono selezionati due segmenti: **[!UICONTROL iOS]** e **[!UICONTROL Android]**.
1. Trascina i tre segmenti nella zona di rilascio Segmento, nella parte superiore della visualizzazione.

   ![](assets/segment-compare.png)

1. Facoltativo: è possibile mantenere *Tutti gli utenti* come contenitore predefinito o eliminare il contenitore.

1. Ora puoi confrontare l’abbandono tra i tre segmenti, ad esempio quando un segmento ha prestazioni migliori di un altro o altre informazioni.
