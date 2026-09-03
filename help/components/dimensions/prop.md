---
title: Prop
description: Una dimensione personalizzata che puoi utilizzare nel reporting.
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
TQID: https://experienceleague.adobe.com/2WMG5X3GNmogf-9Bbapq78pjVg5ibQQw7Bgb0qNpF1E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 475
ht-degree: 8%

---

# Prop

*Questa pagina della guida descrive il funzionamento di prop come [dimensione](overview.md). Per informazioni su come implementare prop, vedi [prop](/help/implement/vars/page-vars/prop.md) nella guida utente Implementa.*

Le proprietà sono variabili personalizzate che puoi utilizzare come desideri. Non persistono oltre l’hit impostato.

>[!TIP]
>
>Adobe consiglia di utilizzare [eVar](evar.md) nella maggior parte dei casi. Nelle versioni precedenti di Adobe Analytics, prop e eVar presentavano vantaggi e svantaggi l’uno per l’altro. Tuttavia, Adobe ha migliorato le eVar per soddisfare quasi tutti i casi d’uso per prop.

Se hai un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), puoi allocare queste dimensioni personalizzate a valori specifici della tua organizzazione. Il numero di prop disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 75 proprietà.

## Popolare prop con i dati

Ogni prop raccoglie dati dalla stringa di query [`c1` - `c75`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il parametro della stringa di query `c1` raccoglie dati per prop1, mentre il parametro della stringa di query `c68` raccoglie dati per prop68.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dati, utilizza le variabili `prop1` - `prop75`. Per le linee guida per l&#39;implementazione, consulta [prop](/help/implement/vars/page-vars/prop.md) nella Guida utente di implementazione.

## Elementi dimensionali

Poiché le proprietà contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali di ciascuna proprietà. Assicurati di registrare lo scopo di ogni proprietà e degli elementi dimensionali tipici in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

## Distinzione tra maiuscole e minuscole

Per impostazione predefinita, le proprietà non distinguono tra maiuscole e minuscole. Se invii lo stesso valore in casi diversi (ad esempio, `"DOG"` e `"Dog"`), Analysis Workspace li raggruppa nello stesso elemento dimensione. Viene utilizzato il caso del primo valore visualizzato all’inizio del mese di riferimento. Data Warehouse mostra il primo valore rilevato durante il periodo della richiesta.

Puoi fare distinzione tra maiuscole e minuscole in qualsiasi proprietà. Puoi anche disattivare la distinzione tra maiuscole e minuscole per qualsiasi proprietà una volta abilitata. Contatta l’Assistenza clienti di Adobe con l’ID suite di rapporti e le variabili desiderate per attivare o disattivare la distinzione tra maiuscole e minuscole.

>[!WARNING]
>
>L’attivazione della distinzione tra maiuscole e minuscole può causare il cliff di elementi dimensionali, risultati imprevisti con i segmenti e problemi con i filtri. Adobe consiglia vivamente di impostare due periodi di tempo principali, ad esempio l’inizio di un mese o di un anno.

## Valore delle proprietà rispetto alle eVar

Nella maggior parte dei casi, Adobe consiglia di utilizzare le eVar. Le eccezioni a questa istruzione sono le seguenti:

* Puoi utilizzare prop nei rapporti in tempo reale. Le eVar richiedono almeno 30 minuti per essere visualizzate nel reporting.
* Le proprietà possono diventare prop elenco, che accettano più valori nello stesso hit. Le variabili elenco sono una variabile separata e sono disponibili solo tre variabili elenco.
* Quando abiliti il percorso in un prop, le dimensioni [Entry](entry-dimensions.md) e [Exit](exit-dimensions.md) diventano immediatamente disponibili. Se desideri dimensioni di entrata e di uscita per le eVar, puoi creare manualmente un segmento.

Consulta [eVar](evar.md) per ulteriori confronti tra prop ed eVar.
