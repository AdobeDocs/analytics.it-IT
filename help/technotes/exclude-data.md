---
title: Escludere i dati in  Adobe Analytics
description: Scopri diversi metodi per escludere i dati sia prima che dopo la raccolta dati.
translation-type: tm+mt
source-git-commit: 47b14bde1bb1217bcb172c6d4f01d68f917d44db
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Escludere i dati in  Adobe Analytics

L&#39;esclusione dei dati è comunemente utilizzata per impedire che le attività di test dell&#39;organizzazione popolino i dati di produzione o per evitare che i dati indesiderati vengano gonfiati erroneamente nei rapporti. Utilizzate uno dei seguenti metodi per escludere i dati da  Adobe Analytics a seconda del caso d&#39;uso.

## Escludi raccolta dati post-raccolta dati

I seguenti metodi sono metodi per escludere i dati nel reporting di Analytics dopo  server di raccolta dei dati di Adobe ricevono le richieste di immagini. I dati esclusi con questi metodi vengono ancora conteggiati per le chiamate server fatturabili.

* **Escludi per IP**:  Adobe Analytics fornisce funzionalità di base per escludere i dati per indirizzi IP o intervalli in una suite di rapporti. Consultate [Escludi per IP](/help/admin/admin/exclude-ip.md) nella guida utente per l&#39;amministratore.
* **Regole** bot: Le regole bot recuperano il traffico dalle stringhe note dell&#39;agente utente bot e le escludono dai report di Analytics. I dati esclusi tramite le regole bot sono inseriti nel rapporto Bots. È possibile creare regole bot personalizzate per escludere dati aggiuntivi. Consultate Regole [bot (](/help/admin/admin/bot-removal/bot-rules.md) bot Rules) nella guida utente per l&#39;amministratore.
* **Regole** VISTA: A seconda delle esigenze della tua organizzazione, gli hit che soddisfano i tuoi requisiti vengono inviati a un&#39;altra suite di rapporti dedicata alla ricezione dei dati esclusi. Le regole VISTA vengono comunemente utilizzate rispetto agli indirizzi IP, ma non solo. Puoi utilizzare qualsiasi dimensione per includere o escludere dati nelle suite di rapporti. le norme VISTA sono soggette a costi aggiuntivi; per informazioni, contattate il responsabile commerciale di riferimento della vostra organizzazione.
* **Cookie** di rifiuto: Tutti i visitatori del sito possono scegliere volontariamente di non essere tracciati in  Adobe Analytics visitando una pagina specifica del server di tracciamento. Consultate [Implementare i collegamenti](/help/implement/js/opt-out.md) di rifiuto nella guida utente Implementa.

>[!TIP]
>
>Le regole di elaborazione non possono escludere dati o inviare dati a un&#39;altra suite di rapporti. Tuttavia, alcune variabili possono essere impostate in modo condizionale e un segmento può essere utilizzato per escludere tali dati dai rapporti.

## Escludi raccolta dati pre-raccolta dati

Per evitare che determinati hit raggiungano i server di raccolta dati di Analytics, utilizza la [`abort`](/help/implement/vars/config-vars/abort.md) variabile. Questo flag impedisce l’invio della richiesta immagine. Le chiamate server fatturabili non vengono incrementate per le richieste di immagini interrotte, in quanto non raggiungono  server di raccolta dati di Adobe.
