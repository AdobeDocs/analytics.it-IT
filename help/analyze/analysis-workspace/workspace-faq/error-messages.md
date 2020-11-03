---
description: Elenco di messaggi di errore nel  Adobe  Analysis Workspace e relativi componenti
title: Messaggi di errore comuni in Analysis Workspace
translation-type: tm+mt
source-git-commit: 1df7eb2b8734a7c260f843494c414a927638ebb4
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 63%

---


# Messaggi di errore comuni

È possibile che, durante l’interazione con Analysis Workspace, si verifichino errori che influiscono anche sulle prestazioni. Di seguito sono elencati i tipi di errore più comuni, il motivo per cui si verificano e le ottimizzazioni possibili.

| Messaggio di errore | Perché si verifica? | Ottimizzazione |
| --- | --- | --- |
| Si è verificato un errore di sistema. Registra una richiesta dell&#39;assistenza clienti in Aiuto > Invia il ticket di assistenza e inserisci il codice di errore. | Adobe sta riscontrando un problema da risolvere. | Invia il codice di errore all’Assistenza clienti. |
| Errore 500: Impossibile caricare la pagina | I problemi con la rete locale, come le impostazioni [del](https://docs.adobe.com/content/help/it-IT/analytics/technotes/ip-addresses.html)firewall aziendale, contribuiscono a questo errore. Inoltre,  Adobe potrebbe rilevare un problema da risolvere. | Riprovate a eseguire l&#39;accesso dopo alcuni minuti. Se il problema persiste, inviate il codice ID istanza EIM all&#39;Assistenza clienti. |
| Uno dei segmenti o la ricerca in questa visualizzazione contiene una ricerca di testo che ha restituito troppi risultati. | Il criterio del segmento o il filtro del rapporto è troppo ampio. | Limita i criteri di testo di ricerca e riprova. |
| La suite di rapporti presenta un reporting insolitamente pesante. Riprovare più tardi. | L’organizzazione sta tentando di eseguire troppe richieste simultanee su una suite di rapporti specifica. Questo errore è causato da richieste API, progetti pianificati, rapporti pianificati, avvisi pianificati e utenti simultanei che eseguono richieste di generazione di rapporti. | Distribuisci le richieste e le pianificazioni per la suite di rapporti in modo più uniforme durante l’intera giornata. |
| La richiesta è troppo complessa. | La richiesta di generazione rapporti è troppo grande e non può essere eseguita. Questo errore è causato da timeout dovuti alla dimensione della richiesta, troppi elementi associati in un segmento o un filtro di ricerca, inclusione di troppe metriche, combinazioni di dimensioni e metriche incompatibili, ecc. | Semplifica la richiesta rimuovendo alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
| Questa dimensione non supporta attualmente modelli di attribuzione non predefiniti. | L’attribuzione non predefinita non è supportata per la dimensione in uso. | Sostituisci la dimensione nella tabella con una che sia compatibile con [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md). |
| La richiesta non è riuscita a causa di troppe colonne o righe preconfigurate. | La tabella contiene troppe celle a forma libera (righe * colonne). | Rimuovi alcune colonne o righe nella tabella oppure prova a suddividere la tabella in più richieste distinte. |
