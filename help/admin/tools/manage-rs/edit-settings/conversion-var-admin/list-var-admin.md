---
title: Variabili elenco
description: Crea e configura variabili elenco da utilizzare nei rapporti.
feature: Admin Tools
role: Admin
exl-id: 6d9a52d4-e7f3-4bbc-bad4-55c79f30b9f7
TQID: https://experienceleague.adobe.com/22yU-AEfp08-BPNwwC6LrJO7iX7n44mZzP9799l6fmQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 471
ht-degree: 21%

---

# Variabili elenco

Crea e configura variabili elenco da utilizzare nei rapporti. Imposta il delimitatore, la scadenza, l’allocazione e i valori massimi. Raccogliere dati per le variabili elenco utilizzando [`list1` - `list3`](/help/implement/vars/page-vars/list.md).

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL List Variables]**

* **[!UICONTROL Name]**: nome della variabile elenco. Questo nome è l’etichetta della dimensione in Analysis Workspace.

* **[!UICONTROL Status]**: abilitare o disabilitare la raccolta dei dati per questa variabile. Se una variabile è disabilitata, non vengono raccolti dati, anche se l’implementazione invia dati a tale variabile.

* **[!UICONTROL Value Delimiter]**: carattere utilizzato per separare i valori all&#39;interno della variabile elenco. Nella maggior parte dei casi si tratta di caratteri come virgole, due punti, pipe o altri caratteri simili. I caratteri multibyte non sono supportati come delimitatori nelle variabili elenco.

* **[!UICONTROL Expire After]**: simile alla scadenza di eVar, questo campo determina il tempo che può trascorrere tra la variabile elenco e l&#39;evento di conversione per effettuare la correlazione.
   * **A livello di visualizzazione pagina o di visita**: gli eventi di successo oltre la visualizzazione pagina o la visita non verranno collegati ai valori all&#39;interno della variabile elenco.
   * **In base a un periodo di tempo, ad esempio giorno, settimana, mese e così via**: gli eventi di successo oltre il periodo di tempo specificato non verranno collegati a nessun valore all&#39;interno della variabile elenco. È anche possibile definire un numero personalizzato di giorni.
   * **Eventi di conversione specifici**: qualsiasi altro evento di successo attivato dopo l&#39;evento specifico designato non verrà collegato ad alcun valore all&#39;interno della variabile elenco.
   * **Mai**: qualsiasi quantità di tempo può passare tra la variabile elenco e l&#39;evento di successo.

* **[!UICONTROL Allocation]**: questa impostazione determina il modo in cui gli eventi di successo dividono il credito tra i valori:
   * **Completo**: tutti i valori delle variabili definiti prima della scadenza della variabile ricevono il pieno credito per gli eventi di successo.
   * **Lineare**: tutti i valori delle variabili definiti prima della scadenza della variabile ricevono credito diviso per gli eventi di conversione.
   * I valori delle variabili non vengono mai sovrascritti, ma vengono aggiunti ai valori che ricevono credito per gli eventi di successo.

* **[!UICONTROL Description]**: descrizione del modo in cui l&#39;organizzazione utilizza la variabile elenco.

* **[!UICONTROL Max Values]**: specifica il numero di valori attivi consentiti per questa variabile elenco. Ad esempio, se è impostato su 3, vengono salvati solo gli ultimi 3 valori acquisiti e tutti i valori precedenti acquisiti vengono scartati. Tieni presente che se più valori per la stessa variabile elenco vengono inviati per lo stesso hit ed è stato impostato un limite utilizzando i valori massimi, ogni valore avrà la stessa marca temporale e non è garantito quale valore viene salvato. Se un visitatore persiste più valori del massimo consentito, vengono utilizzati i valori più recenti. Sono consentiti fino a 250 valori massimi.

  Questa impostazione è utile per limitare l’attribuzione a un numero specifico di valori. Ad esempio, se una variabile elenco è impostata su `"A,B,C"` nella prima pagina di una visita e poi su `"X,Y,Z"` nella pagina successiva, l’attribuzione viene distribuita a questi sei valori in base alla sua allocazione. Se desideri limitare l&#39;attribuzione solo a `"X,Y,Z"`, puoi impostare i valori massimi su tre.
