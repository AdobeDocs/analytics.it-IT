---
description: Elenco di messaggi di errore nel  Adobe  Analysis Workspace e relativi componenti
title: Messaggi di errore comuni in Analysis Workspace
translation-type: tm+mt
source-git-commit: 517b62a976cae1e202eccb4486fa5480b3dff08c
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 77%

---


# Messaggi di errore comuni

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che influiscono anche sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

| Messaggio di errore | Perché si verifica? | Ottimizzazione |
| --- | --- | --- |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| [!UICONTROL Error 500: Failed to load page] | I problemi con la rete locale, come le impostazioni [del](https://docs.adobe.com/content/help/it-IT/analytics/technotes/ip-addresses.html)firewall aziendale, contribuiscono a questo errore. Inoltre,  Adobe potrebbe rilevare un problema da risolvere. | Riprovate a eseguire l&#39;accesso dopo alcuni minuti. Se il problema persiste, inviate il codice ID istanza EIM all&#39;Assistenza clienti. |
| [!UICONTROL One of the segments or the search in this visualization contains a text search that returned too many results.] | Il criterio del segmento o il filtro del rapporto è troppo ampio. | Limitate i criteri di ricerca e riprovate. |
| [!UICONTROL The report suite is experiencing unusually heavy reporting. Please try again later.] | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una suite di rapporti specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di generazione di rapporti. | Distribuisci le richieste e le pianificazioni per la suite di rapporti in modo più uniforme durante l’intera giornata. |
| [!UICONTROL The request is too complex.] | La richiesta di generazione rapporti è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla dimensione della richiesta, troppi elementi associati in un segmento o un filtro di ricerca, inclusione di troppe metriche, combinazioni di dimensioni e metriche incompatibili, ecc. | Semplifica la richiesta rimuovendo alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
| [!UICONTROL This dimension does not currently support non-default attribution models.] | L’attribuzione non predefinita non è supportata per la dimensione in uso. | Sostituisci la dimensione nella tabella con una che sia compatibile con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md). |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |

