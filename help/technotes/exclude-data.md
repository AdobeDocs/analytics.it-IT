---
title: Escludere i dati in Adobe Analytics
description: Scopri vari metodi per escludere i dati sia prima che dopo la raccolta.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---

# Escludere i dati in Adobe Analytics

L’esclusione dei dati viene comunemente utilizzata per impedire che le attività di test della tua organizzazione compilino i dati di produzione o per evitare che i dati indesiderati gonfiino i rapporti in modo errato. Utilizza uno dei seguenti metodi per escludere i dati da Adobe Analytics a seconda del caso d’uso.

## Escludere la raccolta dati post-raccolta dati

I seguenti metodi sono modi per escludere i dati nel reporting di Analytics dopo che i server di raccolta dati di Adobe ricevono le richieste di immagini. I dati esclusi utilizzando questi metodi vengono comunque conteggiati per le chiamate server fatturabili.

* **Escludi per IP**: Adobe Analytics fornisce funzionalità di base per escludere i dati per indirizzi IP o intervalli in una suite di rapporti. Vedi [Escludi per IP](/help/admin/admin/exclude-ip.md) nella guida utente Admin.
* **Regole bot**: Le regole dei bot acquisiscono il traffico dalle stringhe note dell’agente utente bot e le escludono dai rapporti di Analytics. I dati esclusi tramite regole bot vengono inseriti nel rapporto Bots. È possibile creare regole bot personalizzate per escludere dati aggiuntivi. Vedi [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) nella guida utente Admin.
* **Regole VISTA**: A seconda delle esigenze dell’organizzazione, gli hit che soddisfano le tue esigenze vengono inviati a un’altra suite di rapporti dedicata alla ricezione dei dati esclusi. Le regole VISTA vengono comunemente utilizzate per gli indirizzi IP, ma non sono limitate ad essi. Puoi utilizzare qualsiasi dimensione per includere o escludere dati nelle suite di rapporti. Le norme VISTA sono soggette a costi aggiuntivi; per ulteriori informazioni, contatta l’account manager della tua organizzazione.
* **Cookie di rinuncia**: Tutti i visitatori del sito possono volontariamente rinunciare al tracciamento in Adobe Analytics visitando una pagina specifica del server di tracciamento. Vedi [Implementare i collegamenti di rinuncia](/help/implement/js/opt-out.md) nella guida utente Implementa .

>[!TIP]
>
>Le regole di elaborazione non possono escludere dati o inviare dati a un&#39;altra suite di rapporti. Tuttavia, alcune variabili possono essere impostate in modo condizionale e un segmento può essere utilizzato per escludere tali dati dal reporting.

## Escludere i dati pre-raccolta dati

Per evitare che determinati hit raggiungano i server di raccolta dati di Analytics, utilizza la variabile [`abort`](/help/implement/vars/config-vars/abort.md) variabile. Questo flag impedisce l’invio della richiesta di immagine. Le chiamate server fatturabili non vengono incrementate per le richieste di immagini interrotte, poiché non raggiungono i server di raccolta dati di Adobe.
