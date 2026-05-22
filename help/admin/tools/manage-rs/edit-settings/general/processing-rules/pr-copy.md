---
title: Copiare le regole di elaborazione
description: Scopri come copiare le regole di elaborazione da una suite di rapporti a un’altra.
feature: Processing Rules
role: Admin
exl-id: bb34ecac-0512-4cff-9ef0-72db2dcabc03
TQID: 'https://experienceleague.adobe.com/x7mG1fjpNiPn0x6No0RtEz4aJLcN2t7wpUkJ-0LQxII'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: fbaf7f9a-8341-44f6-aa57-6c8d50741804
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 241
ht-degree: 0%

---

# Copiare le regole di elaborazione tra le suite di rapporti

La copia delle regole di elaborazione evita di ricreare manualmente la stessa logica in più suite di rapporti. Puoi utilizzare la funzione di copia per condividere facilmente la funzionalità delle regole di elaborazione tra più suite di rapporti o per copiare la funzionalità testata da una suite di rapporti di sviluppo a una suite di rapporti di produzione.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing rules]** > **[!UICONTROL Copy processing rules]**

Questa interfaccia consente due opzioni:

* **Sostituisci tutte le regole di elaborazione**: questa opzione elimina tutte le regole di elaborazione dalla suite di rapporti di destinazione, quindi aggiunge tutte le regole di elaborazione alla suite di rapporti di destinazione nello stesso ordine. Non è possibile selezionare un numero limitato di regole di elaborazione da sostituire.
* **Aggiungi regole di elaborazione specifiche**: questa opzione consente di selezionare una o più regole di elaborazione. Le regole aggiunte vengono aggiunte alla fine dell’elenco delle regole di elaborazione in ogni suite di rapporti di destinazione. Considera l’ordine e le regole di elaborazione già esistenti quando aggiungi le regole a ciascuna suite di rapporti di destinazione.

Quando si selezionano le regole di elaborazione da aggiungere o le suite di rapporti in cui copiare, è possibile utilizzare `Ctrl`/`Cmd` + `Click` per selezionare più regole di elaborazione o suite di rapporti. Dopo aver selezionato le suite di rapporti desiderate in cui copiare, seleziona **[!UICONTROL Copy]** e conferma la finestra modale visualizzata.

>[!WARNING]
>
>Le regole di elaborazione influiscono direttamente sulla raccolta dei dati e, se utilizzate in modo errato, possono causare la perdita di dati. Prima di copiarle in una suite di rapporti di produzione, testa sempre le regole di elaborazione in una suite di rapporti di sviluppo per attenuare i problemi di qualità dei dati.
