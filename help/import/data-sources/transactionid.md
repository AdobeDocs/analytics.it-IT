---
title: Origini dati ID transazione
description: Utilizza i valori memorizzati da un hit online per arricchire gli hit offline che condividono un ID transazione.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 8%

---

# Origini dati ID transazione

Le origini dati ID transazione sono una variante delle origini dati di riepilogo che ti consentono di applicare valori salvati da un hit online alle righe offline che condividono lo stesso ID transazione. Questo approccio è utile quando si acquisisce una transazione online ma si ricevono i dettagli in un secondo momento da un altro sistema. Esempi principali includono restituzioni di prodotti, annullamenti di prenotazioni o risultati da interazioni con i call center.

>[!NOTE]
>
>Prima di utilizzare le origini dati ID transazione, devi attivarle in [Impostazioni account generali](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) per la suite di rapporti desiderata.

## Come funziona

Il concetto di ID transazione richiede due parti:

* **Hit online**: qualsiasi hit Analytics completo inviato a una suite di rapporti (AppMeasurement, Web SDK, API, ecc.). In questo hit, si imposta la variabile di implementazione [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **Hit offline**: riga caricata tramite origini dati. Nel file, includi la colonna `transactionID` con un valore corrispondente a un hit online.

Quando invii un hit online contenente la variabile di implementazione `transactionID`, Adobe crea un&#39;istantanea delle seguenti dimensioni impostate o mantenute in quel momento:

* [Categoria](/help/components/dimensions/category.md)
* [Giorni precedenti al primo acquisto](/help/components/dimensions/days-before-first-purchase.md)
* [Giorni dall’ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md)
* [eVar 1-250](/help/components/dimensions/evar.md)
* Dimensioni specifiche della funzionalità abilitate in [Impostazioni della suite di rapporti](/help/admin/tools/manage-rs/report-suites-admin.md) che si comportano in modo simile alle eVar. Le quote specifiche della feature che si comportano in modo simile alle proprietà non sono incluse.
* [Variabili elenco](/help/implement/vars/page-vars/list.md)
* [Canale di marketing](/help/components/dimensions/marketing-channel.md)
* [Dettagli del canale Marketing](/help/components/dimensions/marketing-detail.md)
* [Dimensioni per dispositivi mobili](/help/components/dimensions/mobile-dimensions.md)
* [Dominio di riferimento originale](/help/components/dimensions/original-referring-domain.md)
* [Prodotto](/help/components/dimensions/product.md)
* [Dominio di riferimento](/help/components/dimensions/referring-domain.md)
* [Motore di ricerca](/help/components/dimensions/search-engine.md)
* [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md)
* [Codice di tracking](/help/components/dimensions/tracking-code.md)
* [Numero di visite](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>Le metriche (ad esempio [Ordini](/help/components/metrics/orders.md) o [Eventi personalizzati](/help/components/metrics/custom-events.md)) non sono incluse nello &quot;snapshot&quot;.

Quando carichi un hit offline tramite origini dati che contiene un ID transazione corrispondente, tutte le dimensioni disponibili all’interno dello &quot;snapshot&quot; vengono automaticamente aggiunte alla riga dell’origine dati. Se una determinata dimensione è presente sia nell’hit online che offline, viene utilizzato il valore dell’hit offline.

>[!IMPORTANT]
>
>Il concetto di origini dati ID transazione consente di compilare solo le righe dell’origine dati (hit offline). Non influiscono né modificano l’hit online.

## Considerazioni sull’origine dati per l’ID transazione

Le origini dati ID transazione hanno le seguenti proprietà:

* I dati online devono essere raccolti ed elaborati per primi. Se un’origine dati ID transazione viene caricata prima che una suite di rapporti elabori un hit corrispondente a tale ID transazione, i dati vengono trattati come un’origine dati di riepilogo.
* Gli ID transazione raccolti dagli hit online scadono dopo 25 mesi.
* Le origini dati caricate con un ID transazione scaduto vengono trattate in modo simile ai dati caricati senza un ID transazione.
* Se imposti lo stesso ID transazione su più hit online, viene utilizzata solo la &quot;copia istantanea&quot; della prima occorrenza. I successivi hit online con ID transazione duplicato vengono elaborati come se non avessero un ID transazione.
* Dopo aver popolato un dato valore `transactionID`, lo &quot;snapshot&quot; associato viene considerato immutabile fino alla scadenza dell&#39;ID transazione.
* Se imposti lo stesso ID transazione su più righe di origine dati, tutte le dimensioni disponibili dell’hit online vengono aggiunte a ciascun hit offline. Gli hit offline per lo stesso ID transazione non conoscono nulla l’uno dell’altro; i dati non vengono trasmessi tra gli hit offline.
