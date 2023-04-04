---
title: Origini dati ID transazione
description: Scopri il flusso di lavoro generale dell’utilizzo delle origini dati ID transazione.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 54c88a275b48f2b401be450ce35767ab3ea9d40b
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 3%

---

# Origini dati ID transazione

Le origini dati ID transazione sono una variante delle origini dati di riepilogo che ti consente di collegare insieme dati online e offline. Richiede l&#39;utilizzo [`transactionID`](/help/implement/vars/page-vars/transactionid.md) nell’implementazione di Analytics.

* Se una riga in un file origini dati include un ID transazione che corrisponde a un ID transazione già raccolto da AppMeasurement, le dimensioni e le metriche vengono aggiunte all&#39;hit online.
* Se una riga in un file origini dati include un ID transazione che non contiene una corrispondenza, viene trattata in modo simile alle origini dati di riepilogo.

>[!NOTE]
>
>Prima di utilizzare le origini dati ID transazione, devi prima abilitarle in [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) per la suite di rapporti desiderata.

Quando invii un hit online contenente una [`transactionID`](/help/implement/vars/page-vars/transactionid.md) Adobe prende uno &quot;snapshot&quot; di tutte le variabili impostate o persistenti in quel momento. Se viene trovato un ID transazione corrispondente caricato tramite origini dati, i dati offline e online vengono collegati tra loro.

Le origini dati ID transazione hanno le seguenti proprietà:

* I dati online devono essere raccolti ed elaborati per primi. Se un’origine dati ID transazione viene caricata prima che una suite di rapporti elabori un hit corrispondente a tale ID transazione, i dati non sono collegati.
* Gli ID transazione raccolti tramite AppMeasurement scadono dopo circa 90 giorni. Se la tua organizzazione richiede una finestra ID transazione più lunga, contatta l’Assistenza clienti Adobe.
* Le origini dati caricate con un ID transazione scaduto vengono trattate in modo simile ai dati caricati senza un ID transazione.
* Se la stessa variabile è inclusa sia nell&#39;origine dati hit online che nell&#39;ID transazione, viene utilizzato il valore dell&#39;origine dati ID transazione.
* Se una variabile è inclusa in un hit online ma non in un hit di origine dati ID transazione corrispondente, la variabile di hit online viene mantenuta.
* Se imposti lo stesso ID transazione su più hit online, solo la prima occorrenza viene modificata con i dati di un’origine dati ID transazione corrispondente.
* Se imposti lo stesso ID transazione su più righe di origine dati per le stesse dimensioni, viene utilizzato l’ultimo elemento dimensione.

Ad esempio:

1. Puoi inviare una visualizzazione di pagina da AppMeasurement in cui:
   * `eVar1` è uguale a `blue`
   * `eVar2` è uguale a `water`
   * `events` è uguale a `event1`
   * `transactionID` è uguale a `1256`
2. Dopo aver raccolto ed elaborato l&#39;hit, carica un&#39;origine dati ID transazione in cui:
   * `eVar1` è uguale a `yellow`
   * `eVar3` è uguale a `bird`
   * `events` è uguale a `event2`
   * `transactionID` è uguale a `1256`
3. Una volta elaborato l&#39;hit delle origini dati, puoi visualizzare un rapporto in workspace. I dati mostrerebbero quanto segue:
   * `eVar1` è uguale a `yellow`
   * `eVar2` è uguale a `water`
   * `eVar3` è uguale a `bird`
   * `events` è uguale a `event2`

Valore eVar1 `blue` e `event1` Le metriche non sono presenti nel reporting, in quanto il risultato dell&#39;ID transazione ha sovrascritto quei rispettivi valori.
