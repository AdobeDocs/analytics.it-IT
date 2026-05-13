---
title: Escludere i dati in Adobe Analytics
description: Scopri diversi metodi per escludere i dati sia prima che dopo la raccolta.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
role: Admin
TQID: https://experienceleague.adobe.com/EVXvZGgeAPTcUUd035DgBAyU38hKNh8xU7nX3g7aY7o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 356
ht-degree: 0%

---

# Escludere i dati in Adobe Analytics

L’esclusione dei dati viene comunemente utilizzata per impedire che le attività di test dell’organizzazione popolino i dati di produzione o che dati indesiderati possano gonfiare erroneamente i rapporti. Utilizza uno dei seguenti metodi per escludere dati da Adobe Analytics a seconda del caso d’uso.

## Escludere la raccolta di dati successivi ai dati

I metodi seguenti consentono di escludere i dati dal reporting di Analytics dopo che i server di raccolta dati di Adobe hanno ricevuto le richieste di immagini. I dati esclusi utilizzando questi metodi vengono comunque conteggiati per le chiamate al server fatturabili.

* **Escludi per IP**: Adobe Analytics fornisce funzionalità di base per escludere i dati per gli indirizzi IP o gli intervalli in una suite di rapporti. Vedi [Escludi per IP](/help/admin/tools/exclude-ip.md) nella guida utente dell&#39;amministratore.
* **Regole bot**: le regole bot prelevano traffico dalle stringhe note dell&#39;agente utente bot e le escludono dai rapporti di Analytics. I dati esclusi tramite le regole bot vengono inseriti nel rapporto Bots. È possibile creare regole bot personalizzate per escludere dati aggiuntivi. Vedi [Regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) nella guida utente Admin.
* **Regole VISTA**: a seconda delle esigenze della tua organizzazione, gli hit che corrispondono ai tuoi requisiti vengono inviati a un&#39;altra suite di rapporti dedicata alla ricezione di dati esclusi. Le regole VISTA vengono comunemente utilizzate per gli indirizzi IP, ma non sono limitate a essi. Puoi utilizzare qualsiasi dimensione per includere o escludere dati nelle suite di rapporti. Le regole VISTA sono soggette a costi aggiuntivi; contatta il team del tuo account Adobe per dettagli.
* **Cookie di rinuncia**: tutti i visitatori del sito possono rinunciare volontariamente al tracciamento in Adobe Analytics visitando una pagina specifica del server di tracciamento. Consulta [Implementare collegamenti di rinuncia](/help/implement/js/opt-out.md) nella guida utente di implementazione.

>[!TIP]
>
>Le regole di elaborazione non possono escludere dati o inviarli a un’altra suite di rapporti. Tuttavia, alcune variabili possono essere impostate in modo condizionale e un segmento può essere utilizzato per escludere tali dati dal reporting.

## Escludere la raccolta di dati preliminari

Se vuoi impedire che alcuni hit raggiungano i server di raccolta dati di Analytics, utilizza la variabile [`abort`](/help/implement/vars/config-vars/abort.md). Questo flag impedisce l’invio della richiesta di immagine. Le chiamate al server fatturabili non vengono incrementate per le richieste di immagini interrotte, in quanto non raggiungono i server di raccolta dati di Adobe.
