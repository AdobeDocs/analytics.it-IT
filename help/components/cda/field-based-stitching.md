---
title: Unione basata sui campi
description: Comprendi i prerequisiti e le limitazioni dell’unione di dati utilizzando l’unione basata sui campi.
translation-type: tm+mt
source-git-commit: 7b43c4ebbf9446507ab90a90e26c51635303dcc6
workflow-type: tm+mt
source-wordcount: '303'
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

* L’unione basata sui campi funziona meglio sulle suite di rapporti che hanno un tasso di identificazione elevato dell’utente. Se la suite di rapporti ha una bassa identificazione o tasso di accesso, considera l&#39;utilizzo del [grafico Co-op](device-graph.md).
* Sebbene prop ed eVar dispongano di regole per la gestione dei caratteri maiuscoli e minuscoli a scopo di reporting, l’unione basata sui campi non trasforma la proprietà o l’eVar utilizzati per l’unione in alcun modo. L’unione basata sui campi utilizza il valore nel campo specificato in quanto esiste dopo le regole VISTA e le regole di post-elaborazione. Ad esempio, se a volte la parola &quot;Bob&quot; compare nel prop/eVar e a volte compare la parola &quot;BOB&quot;, questi verranno trattati come due persone separate.

## Passaggi successivi

Una volta che l&#39;organizzazione soddisfa tutti i requisiti e comprende i limiti, puoi iniziare a [Configurare Cross-Device Analytics](setup.md).
