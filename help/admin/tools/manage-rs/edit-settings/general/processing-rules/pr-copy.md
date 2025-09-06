---
title: Copiare le regole di elaborazione
description: Scopri come copiare le regole di elaborazione da una suite di rapporti a un’altra.
feature: Processing Rules
role: Admin
exl-id: bb34ecac-0512-4cff-9ef0-72db2dcabc03
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '241'
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
