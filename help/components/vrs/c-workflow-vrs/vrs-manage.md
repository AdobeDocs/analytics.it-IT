---
description: Gestione suite di rapporti virtuale consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le suite di rapporti virtuali. Non è visibile agli utenti non amministratori.
keywords: Suite di rapporti virtuali
title: Gestione delle suite di rapporti virtuali
feature: VRS
exl-id: b6d58456-bd07-4d97-aff8-216e8440fdc0
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 15%

---

# Gestione delle suite di rapporti virtuali

Gestione suite di rapporti virtuale consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le suite di rapporti virtuali. Non è visibile agli utenti non amministratori.

**[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Virtual Report Suites]**

![](assets/vrs-manage.png)

>[!NOTE]
>
>In Gestione suite di rapporti virtuale è possibile visualizzare solo le suite di rapporti virtuali personalizzate. Devi fare clic **[!UICONTROL Show All]** per vedere di tutti gli altri.

| Attività | Descrizione |
| --- | --- |
| Add | Consente di accedere al generatore di suite di rapporti virtuali per creare nuove suite di rapporti virtuali. |
| Tag | Tutti gli utenti possono creare tag per le suite di rapporti virtuali e applicare uno o più tag a una suite di rapporti virtuale. Tuttavia, puoi visualizzare solo i tag per le suite di rapporti virtuali di tua proprietà. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing</li><li>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso</li><li>Tag di categorie: maschile; geografia</li><li>Tag del flusso di lavoro: Curato per (una specifica unità operativa); Approvato</li></ul> |
| Elimina | Se elimini una suite di rapporti virtuale, i rapporti e le dashboard pianificati con questa suite di rapporti virtuale continuano a funzionare normalmente. Il report o il dashboard continua a utilizzare la suite di rapporti virtuali eliminati fino a quando non si salva nuovamente il report pianificato.  I rapporti pianificati non vengono aggiornati quando si modifica una suite di rapporti virtuale con lo stesso nome.<br>Ad esempio: Supponiamo di avere due suite di rapporti virtuali con lo stesso nome e suite di rapporti principali diverse:<br>È presente un segnalibro che fa riferimento alla suite di rapporti virtuali per la suite di rapporti principale. Quindi elimini la suite di rapporti virtuali perché è un duplicato. Il segnalibro continua a essere eseguito, facendo riferimento alla definizione della VRS eliminata. Se modifichi la definizione della VRS rimanente, la VRS applicata al segnalibro non subirà modifiche. Usa la vecchia definizione. Per risolvere il problema, aggiorna il segnalibro in modo che faccia riferimento alla nuova definizione. Se non sei sicuro se un segnalibro, un dashboard o un rapporto pianificato utilizzano una VRS eliminata, puoi modificare il nome della VRS rimanente in modo che sia più chiaro se il segnalibro utilizza la VRS rimanente. |
| Rinomina | Ovunque venga visualizzata la suite di rapporti virtuali, come nel selettore delle suite di rapporti, viene visualizzato il nuovo nome. |
| Approva/Annulla approvazione | Approva le suite di rapporti virtuali per renderle &quot;ufficiali&quot; o &quot;canoniche&quot;. È possibile annullare il processo annullando l’approvazione. |
| Copia | Crea una copia distinta con il proprio nuovo ID suite di rapporti, ma con lo stesso nome e la stessa definizione. |
| Export to CSV (Esporta in CSV) | Esporta la definizione della suite di rapporti virtuale in un file .csv . |
| Filtro | Filtrare per tag, suite di rapporti principale, proprietari e altri filtri (Mostra tutto, Personali, Preferiti e Approvati). |
