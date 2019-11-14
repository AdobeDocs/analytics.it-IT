---
description: Virtual Report Suite Manager (Gestione suite di rapporti virtuali) consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le suite di rapporti virtuali. Non è visibile agli utenti non amministratori.
keywords: Virtual Report Suite
solution: Analytics
title: Gestione delle suite di rapporti virtuali
topic: Reports and analytics
uuid: ce683c01-2d7d-4f2a-98db-946f68eda99b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Gestione delle suite di rapporti virtuali

Virtual Report Suite Manager (Gestione suite di rapporti virtuali) consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le suite di rapporti virtuali. Non è visibile agli utenti non amministratori.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Components]** &gt; **[!UICONTROL Virtual Report Suites]**

![](assets/vrs-manage.png)

> [!NOTE] In Virtual Report Suite Manager (Gestione suite di rapporti virtuali) puoi visualizzare solo le suite di rapporti virtuali. Devi cliccare **[!UICONTROL Show All]** per vedere quello di tutti gli altri.

| Attività | Descrizione |
|--- |--- |
| Aggiungi | Consente di accedere al generatore di suite di rapporti virtuali, dove è possibile creare nuove suite di rapporti virtuali. |
| Tag | Tutti gli utenti possono creare tag per segmenti e applicare uno o più tag a un segmento. Tuttavia, potete visualizzare i tag solo per i segmenti di proprietà. Che tipo di tag creare? Di seguito sono riportati alcuni suggerimenti per tag utili:<ul><li>Tag basati sui nomi dei team, come Social Marketing e Mobile Marketing</li><li>Tag del progetto (tag di analisi), ad esempio Analisi della pagina di partecipazione</li><li>Tag categoria: Uomo; geografia</li><li>Tag flusso di lavoro: Cura per (una specifica unità operativa); Approvato</li></ul> |
| Elimina | Se elimini una suite di rapporti virtuale, i rapporti pianificati e le dashboard con questa suite di rapporti virtuali continuano a funzionare normalmente. Il rapporto o il dashboard continua a utilizzare la suite di rapporti virtuali eliminata fino a quando non si salva nuovamente il rapporto pianificato.  I rapporti pianificati non vengono aggiornati quando si modifica una suite di rapporti virtuale con lo stesso nome.<br>Ad esempio: Supponiamo di avere due suite di rapporti virtuali con lo stesso nome e diverse suite di rapporti padre:<br>si dispone di un segnalibro che fa riferimento alla suite di rapporti virtuale per la suite di rapporti principale. Quindi si elimina la suite di rapporti virtuali perché è un duplicato. Il segnalibro continua a essere eseguito, facendo riferimento alla definizione della VRS eliminata. Se si modifica la definizione della VRS rimanente, la VRS applicata al segnalibro non viene modificata. Usa la vecchia definizione. Per risolvere il problema, aggiornare il segnalibro in modo che faccia riferimento alla nuova definizione. Se non si è certi che un segnalibro, una dashboard o un rapporto pianificato utilizzi una VRS eliminata, è possibile modificare il nome della VRS rimanente in modo che sia più chiaro se il segnalibro utilizza la VRS rimanente. |
| Rinomina | Ovunque venga visualizzata la suite di rapporti virtuale, come nel selettore della suite di rapporti, viene visualizzato il nuovo nome. |
| Approva/Annulla approvazione | Approvare le suite di rapporti virtuali per renderle "ufficiali" o "canoniche". È possibile annullare il processo annullando l'approvazione. |
| Copia | Crea una copia distinta con il proprio nuovo ID suite di rapporti, ma con lo stesso nome e definizione. |
| Export to CSV (Esporta in CSV) | Esporta la definizione della suite di rapporti virtuale in un file .csv. |
| Filtro | Filtrare per tag, suite di rapporti principale, proprietari e altri filtri (Mostra tutto, Personale, Preferiti e Approvato). |
