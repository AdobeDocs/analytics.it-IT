---
title: Unione basata sui campi
description: Comprendi i prerequisiti e le limitazioni dell’unione di dati utilizzando l’unione basata sui campi.
exl-id: 81f2768c-53c2-40b4-8d3b-8d3b94cd7318
feature: CDA
role: Admin
source-git-commit: 5faf1631a52594591a74a93868198da8bc0f9cff
workflow-type: tm+mt
source-wordcount: '562'
ht-degree: 1%

---

# Unione basata sui campi

{{available-existing-customers}}

Analytics tra dispositivi fornisce due metodi distinti per unire i dati. Questo metodo si basa su una variabile di Analytics, ad esempio [prop](/help/implement/vars/page-vars/prop.md) o [eVar](/help/implement/vars/page-vars/evar.md), per contenere un identificatore persona. Utilizza tale variabile come base per collegare i dispositivi. Adobe consiglia questa opzione di unione per maggiore trasparenza e prevedibilità nel tracciamento dei visitatori.

## Prerequisiti specifici per l’unione basata sui campi

Se intendi implementare Cross-Device Analytics utilizzando l’unione basata sui campi, è necessario quanto segue. Collabora con i team della tua organizzazione e con il tuo account team Adobe per assicurarti di soddisfare tutte le seguenti esigenze.

>[!WARNING]
>
>Il mancato rispetto di tutti i prerequisiti può comportare l’impossibilità di abilitare Cross-Device Analytics o risultati errati durante l’unione dei dati.

* Tutti i prerequisiti elencati nella [pagina della panoramica](overview.md).
* L’implementazione deve impostare una prop o eVar che identifichi un individuo in modo univoco ogni volta che possibile, ad esempio quando un utente accede o apre un’e-mail. Questo requisito si applica a tutte le piattaforme, incluse le app mobili se utilizzate.<br/>Evita di assegnare un valore predefinito a questa proprietà o eVar. Quando a 2.000 o più dispositivi diversi viene assegnato lo stesso valore predefinito, la persona viene aggiunta a un elenco di persone non valide e questi eventi vengono eliminati dalla suite di rapporti virtuali abilitata per CDA, generando analisi errate.
* Comunica la variabile di identificazione desiderata al tuo account team di Adobe quando viene eseguito il provisioning per l’unione basata sui campi.

## Limitazioni specifiche dell’unione basata sui campi

* L’unione basata sui campi funziona meglio nelle suite di rapporti che hanno un elevato tasso di identificazione/autenticazione degli utenti.
* Anche se le proprietà e le eVar hanno regole sulla gestione dei caratteri maiuscoli e minuscoli a scopo di reporting, l’unione basata sui campi non trasforma in alcun modo la proprietà o l’eVar utilizzata per l’unione. L’unione basata sui campi utilizza il valore nel campo specificato così come esiste dopo le regole VISTA e di post-elaborazione. Il processo di unione distingue tra maiuscole e minuscole. Ad esempio, se a volte la parola &quot;Bob&quot; viene visualizzata nella prop/eVar e a volte viene visualizzata la parola &quot;BOB&quot;, queste verranno trattate come due persone separate dal processo di unione.
* Poiché l’unione basata sui campi distingue tra maiuscole e minuscole, Adobe consiglia di rivedere eventuali regole VISTA o regole di elaborazione applicabili alla proprietà o all’eVar utilizzata per l’unione basata sui campi. Devono essere riviste per garantire che nessuna di queste regole introduca nuove forme dello stesso ID. Ad esempio, assicurati che le regole VISTA o di elaborazione non introducano lettere minuscole nella proprietà o eVar solo per una parte degli hit.
* L’unione basata sui campi non supporta l’utilizzo di più di una proprietà o eVar a scopo di unione. Ad esempio, se eVar12 contiene l’ID di accesso e eVar20 contiene l’ID e-mail, devi sceglierne uno.
* L’unione basata sui campi non combina o concatena i campi (ad esempio, eVar10 + prop5).
* La proprietà o eVar deve contenere un singolo tipo di ID. Ad esempio, la proprietà o eVar non deve contenere una combinazione di ID di accesso e ID e-mail.
* Se si verificano più hit con la stessa marca temporale per lo stesso visitatore, ma con valori diversi nella prop di unione o in eVar, CDA sceglierà in base all’ordine alfabetico. Pertanto, se il visitatore A ha due hit con la stessa marca temporale e uno degli hit specifica Bob e l’altro specifica Ann, CDA sceglierà Ann.


## Passaggi successivi

Una volta che la tua organizzazione soddisfa tutti i requisiti e comprende le limitazioni, puoi avviare [Configurazione di Cross-Device Analytics](setup.md).

