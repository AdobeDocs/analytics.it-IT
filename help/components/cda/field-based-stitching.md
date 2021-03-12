---
title: Unione basata sui campi
description: Comprendi i prerequisiti e le limitazioni dell’unione di dati utilizzando l’unione basata sui campi.
translation-type: tm+mt
source-git-commit: beed7ffcc39b9b2628b1487b5e2eac42fa3a94d0
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 1%

---


# Unione basata sui campi

Analisi multidispositivo fornisce due metodi distinti per unire i dati. Questo metodo si basa su una variabile di Analytics, ad esempio [prop](/help/implement/vars/page-vars/prop.md) o [eVar](/help/implement/vars/page-vars/evar.md), per contenere un identificatore di persona. Usa quella variabile come base per collegare i dispositivi.

## Prerequisiti specifici per l’unione basata sui campi

Se intendi implementare Cross-Device Analytics utilizzando l’unione basata sui campi, sono necessari i seguenti elementi. Collabora con i team all’interno della tua organizzazione e con il tuo Adobe Account Manager per assicurarti di soddisfare tutte le seguenti esigenze.

>[!IMPORTANT]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di abilitare Cross-Device Analytics o risultati errati durante l’unione dei dati.

* Tutti i prerequisiti elencati nella [pagina di panoramica](overview.md).
* L’implementazione deve impostare una proprietà o un eVar che identifichi in modo univoco un individuo ogni volta che è possibile, ad esempio quando un utente accede o apre un’e-mail. Questo requisito si applica a tutte le piattaforme, incluse le app mobili se utilizzate. Comunica la variabile di identificazione desiderata al tuo Account Manager quando è stato eseguito il provisioning per l&#39;unione basata su campi.

## Limitazioni specifiche per l’unione basata sui campi

* L’unione basata sui campi funziona meglio sulle suite di rapporti che hanno un elevato tasso di identificazione/autenticazione dell’utente.
* Sebbene prop ed eVar dispongano di regole per la gestione dei caratteri maiuscoli e minuscoli a scopo di reporting, l’unione basata sui campi non trasforma la proprietà o l’eVar utilizzati per l’unione in alcun modo. L’unione basata sui campi utilizza il valore nel campo specificato in quanto esiste dopo le regole VISTA e le regole di post-elaborazione. Il processo di unione fa distinzione tra maiuscole e minuscole. Ad esempio, se a volte la parola &quot;Bob&quot; compare nel prop/eVar e a volte compare la parola &quot;BOB&quot;, questi verranno trattati come due persone separate dal processo di unione.
* Dato che l’unione basata sui campi fa distinzione tra maiuscole e minuscole, l’Adobe consiglia di rivedere eventuali regole VISTA o regole di elaborazione applicabili al prop o all’eVar utilizzato per l’unione basata sui campi. Devono essere esaminati per assicurarsi che nessuna di queste regole stia introducendo nuovi moduli con lo stesso ID. Ad esempio, è necessario assicurarsi che nessun VISTA o regole di elaborazione introduca valori minimi nella proprietà o nell’eVar solo in una parte degli hit.
* Le cuciture basate sul campo non supportano l&#39;uso di più proprietà o eVar a scopo di unione. Ad esempio, se eVar12 contiene l’ID di accesso e eVar20 contiene l’ID e-mail, devi sceglierne uno.
* L’unione basata sui campi non combina o concatena i campi (ad esempio eVar10 + prop5).
* La proprietà o l&#39;eVar deve contenere un singolo tipo di ID. Ad esempio, il prop o eVar non deve contenere una combinazione di ID di accesso e ID e-mail.
* Se si verificano più hit con la stessa marca temporale per lo stesso visitatore, ma con valori diversi nella proprietà di unione o in eVar, CDA sceglierà in base all’ordine alfabetico. Quindi, se il visitatore A ha due hit con la stessa marca temporale e uno degli hit specifica Bob e l’altro specifica Ann, CDA sceglierà Ann.


## Passaggi successivi

Una volta che l&#39;organizzazione soddisfa tutti i requisiti e comprende i limiti, puoi iniziare a [Configurare Cross-Device Analytics](setup.md).
