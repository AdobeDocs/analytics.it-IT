---
description: Il gestore delle suite di rapporti virtuali consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le suite di rapporti virtuali. questa funzione non è visibile agli utenti non amministratori.
keywords: Suite di rapporti virtuali
title: Gestione delle suite di rapporti virtuali
feature: VRS
exl-id: b6d58456-bd07-4d97-aff8-216e8440fdc0
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 19%

---

# Gestione delle suite di rapporti virtuali

Il gestore delle suite di rapporti virtuali consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le suite di rapporti virtuali. questa funzione non è visibile agli utenti non amministratori.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual report suites]**

![](assets/vrs-manage.png)

>[!NOTE]
>
>In Gestione suite di rapporti virtuali, puoi visualizzare solo le tue suite di rapporti virtuali. Devi fare clic su **[!UICONTROL Show All]** per visualizzare i di tutti gli altri.

| Attività | Descrizione |
| --- | --- |
| Add | Consente di accedere al generatore di suite di rapporti virtuali e creare nuove suite di rapporti virtuali. |
| Tag | Tutti gli utenti possono creare tag per suite di rapporti virtuali e applicarne uno o più a una suite di rapporti virtuale. Tuttavia, puoi visualizzare solo i tag per le suite di rapporti virtuali di tua proprietà. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing</li><li>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso</li><li>Tag di categorie: uomo; geografia</li><li>Tag del flusso di lavoro: Curato per (una specifica unità operativa); Approvato</li></ul> |
| Delete (Elimina) | Se elimini una suite di rapporti virtuale, i rapporti e le dashboard pianificati a cui è applicata questa suite di rapporti virtuale continuano a funzionare normalmente. Il rapporto o la dashboard continua a utilizzare la suite di rapporti virtuale eliminata fino a quando non salvi nuovamente il rapporto pianificato.  I rapporti pianificati non vengono aggiornati quando si modifica una suite di rapporti virtuali con lo stesso nome.<br>Ad esempio: si supponga di disporre di due suite di rapporti virtuali con lo stesso nome e suite di rapporti padre diverse:<br>Si dispone di un segnalibro che fa riferimento alla suite di rapporti virtuale per la suite di rapporti principale. Quindi elimini la suite di rapporti virtuale perché è un duplicato. Il segnalibro continua a essere eseguito, facendo riferimento alla definizione delle suite di rapporti virtuali eliminate. Se modifichi la definizione delle restanti suite di rapporti virtuali, la suite di rapporti virtuale applicata al segnalibro non cambia. Utilizza la vecchia definizione. Per risolvere il problema, aggiorna il segnalibro in modo che faccia riferimento alla nuova definizione. Se non sei sicuro se un segnalibro, una dashboard o un rapporto pianificato utilizzi una suite di rapporti virtuale eliminata, puoi modificare il nome delle suite di rapporti virtuali rimanenti in modo che sia più chiaro se il segnalibro utilizza le suite di rapporti virtuali rimanenti. |
| Rinomina | Ovunque venga visualizzata la suite di rapporti virtuale, come nel selettore della suite di rapporti, viene visualizzato il nuovo nome. |
| Approva/Annulla approvazione | Approva le suite di rapporti virtuali per renderle &quot;ufficiali&quot; o &quot;canoniche&quot;. È possibile annullare il processo annullando l&#39;approvazione. |
| Copy | Crea una copia distinta con il proprio nuovo ID suite di rapporti, ma con lo stesso nome e la stessa definizione. |
| Export to CSV (Esporta in CSV) | Esporta la definizione della suite di rapporti virtuale in un file .csv. |
| Filtro | Puoi filtrare per tag, suite di rapporti principale, proprietari e altri filtri (Mostra tutto, Personali, Preferiti e Approvati). |
