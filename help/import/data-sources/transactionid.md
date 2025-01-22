---
title: Origini dati ID transazione
description: Scopri il flusso di lavoro generale dell’utilizzo delle origini dati ID transazione.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: e281d43204e1c5b10508661f04b880125fe8671c
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 2%

---

# Origini dati ID transazione

Le origini dati ID transazione sono una variante delle origini dati di riepilogo che consente di collegare dati online e offline. Richiede l&#39;utilizzo della variabile [`transactionID`](/help/implement/vars/page-vars/transactionid.md) nell&#39;implementazione di Analytics.

* Se una riga in un file di origini dati include un ID transazione che corrisponde a un ID transazione già raccolto da AppMeasurement, le dimensioni e le metriche vengono aggiunte all&#39;hit online.
* Se una riga in un file di origini dati include un ID transazione che non contiene una corrispondenza, la riga viene trattata in modo simile alle origini dati di riepilogo.

>[!NOTE]
>
>Prima di utilizzare le origini dati ID transazione, devi attivarle in [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) per la suite di rapporti desiderata.

Quando invii un hit online contenente un valore [`transactionID`](/help/implement/vars/page-vars/transactionid.md), Adobe crea un&#39;&quot;istantanea&quot; di tutte le variabili impostate o mantenute in quel momento. Se viene trovato un ID transazione corrispondente caricato tramite origini dati, i dati offline e online vengono legati tra loro.

Le origini dati ID transazione hanno le seguenti proprietà:

* I dati online devono essere raccolti ed elaborati per primi. Se un’origine dati ID transazione viene caricata prima che una suite di rapporti elabori un hit corrispondente a tale ID transazione, i dati non vengono collegati.
* L&#39;ID transazione raccolto tramite AppMeasurement scade dopo 25 mesi.
* Le origini dati caricate con un ID transazione scaduto vengono trattate in modo simile ai dati caricati senza un ID transazione.
* Se la stessa variabile è inclusa sia nell’hit online che nell’origine dati ID transazione, viene utilizzato il valore dell’origine dati ID transazione.
* Se una variabile è inclusa in un hit online ma non in un hit origine dati ID transazione corrispondente, la variabile hit online viene mantenuta.
* Se imposti lo stesso ID transazione su più hit online, solo la prima occorrenza viene modificata con i dati di un’origine dati ID transazione corrispondente.
* Se imposti lo stesso ID transazione su più righe di origine dati per le stesse dimensioni, viene utilizzato l’elemento dimensione più recente.

Ad esempio:

1. Si invia una visualizzazione di pagina da un AppMeasurement in cui:
   * `eVar1` è uguale a `blue`
   * `eVar2` è uguale a `water`
   * `events` è uguale a `event1`
   * `transactionID` è uguale a `1256`
2. Dopo la raccolta e l’elaborazione dell’hit, carichi un’origine dati ID transazione in cui:
   * `eVar1` è uguale a `yellow`
   * `eVar3` è uguale a `bird`
   * `events` è uguale a `event2`
   * `transactionID` è uguale a `1256`
3. Una volta elaborato l’hit delle origini dati, puoi visualizzare un rapporto in Workspace. I dati mostravano quanto segue:
   * `eVar1` è uguale a `yellow`
   * `eVar2` è uguale a `water`
   * `eVar3` è uguale a `bird`
   * `events` è uguale a `event2`

Il valore `blue` di eVar1 e la metrica `event1` non sono presenti nel reporting, poiché l&#39;hit della transazione ha sovrascritto i rispettivi valori.
