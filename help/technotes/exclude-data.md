---
title: Escludere i dati in Adobe Analytics
description: Scopri diversi metodi per escludere i dati sia prima che dopo la raccolta.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Escludere i dati in Adobe Analytics

L’esclusione dei dati viene comunemente utilizzata per impedire che le attività di test dell’organizzazione popolino i dati di produzione o che dati indesiderati possano gonfiare erroneamente i rapporti. Utilizza uno dei seguenti metodi per escludere dati da Adobe Analytics a seconda del caso d’uso.

## Escludere la raccolta di dati successivi ai dati

I metodi seguenti consentono di escludere i dati nei rapporti di Analytics dopo che i server di raccolta dati di Adobe hanno ricevuto le richieste di immagini. I dati esclusi utilizzando questi metodi vengono comunque conteggiati per le chiamate al server fatturabili.

* **Escludi per IP**: Adobe Analytics fornisce funzionalità di base per escludere i dati per gli indirizzi IP o gli intervalli in una suite di rapporti. Consulta [Escludi per IP](/help/admin/admin/exclude-ip.md) nella guida utente Admin.
* **Regole bot**: le regole bot prelevano traffico dalle stringhe note dell’agente utente bot e le escludono dai rapporti di Analytics. I dati esclusi tramite le regole bot vengono inseriti nel rapporto Bots. È possibile creare regole bot personalizzate per escludere dati aggiuntivi. Consulta [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) nella guida utente Admin.
* **Regole VISTA**: a seconda delle esigenze della tua organizzazione, gli hit che corrispondono alle tue esigenze vengono inviati a un’altra suite di rapporti dedicata alla ricezione dei dati esclusi. Le regole VISTA vengono comunemente utilizzate per gli indirizzi IP, ma non sono limitate a essi. Puoi utilizzare qualsiasi dimensione per includere o escludere dati nelle suite di rapporti. Le regole VISTA sono soggette a costi aggiuntivi; contatta l’account manager della tua organizzazione per ulteriori dettagli.
* **Cookie di rinuncia**: tutti i visitatori del sito possono rinunciare volontariamente al tracciamento in Adobe Analytics visitando una pagina specifica del server di tracciamento. Consulta [Implementare collegamenti di rinuncia](/help/implement/js/opt-out.md) nella guida utente Implementa.

>[!TIP]
>
>Le regole di elaborazione non possono escludere dati o inviarli a un’altra suite di rapporti. Tuttavia, alcune variabili possono essere impostate in modo condizionale e un segmento può essere utilizzato per escludere tali dati dal reporting.

## Escludere la raccolta di dati preliminari

Se desideri impedire che determinati hit raggiungano i server di raccolta dati di Analytics, utilizza [`abort`](/help/implement/vars/config-vars/abort.md) variabile. Questo flag impedisce l’invio della richiesta di immagine. Le chiamate al server fatturabili non vengono incrementate per le richieste di immagini interrotte, in quanto non raggiungono i server di raccolta dati Adobe.
