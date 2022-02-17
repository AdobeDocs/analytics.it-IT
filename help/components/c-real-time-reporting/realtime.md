---
description: Visualizza il traffico della pagina web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati utilizzabili su cui basare le tue decisioni aziendali.
title: Panoramica reportistica in tempo reale
topic-fix: Reports
feature: Real-time
exl-id: 056235bc-42ea-4118-aa54-bc7666044fe3
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 12%

---

# Panoramica reportistica in tempo reale

Il reporting in tempo reale mostra il traffico della pagina web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati utilizzabili su cui basare le tue decisioni aziendali.

>[!NOTE]
>
>Il rapporto in tempo reale non richiede alcuna implementazione o assegnazione di tag aggiuntivi. Utilizza l’implementazione esistente di Adobe Analytics. Per configurare rapporti in tempo reale, vedi [Configurazione rapporti in tempo reale](/help/components/c-real-time-reporting/t-realtime-admin.md).

**[!UICONTROL Site Metrics]** > **[!UICONTROL Real-Time]**

Risposta in tempo reale alle seguenti domande: Cosa è la tendenza sul mio sito e perché? Consente agli addetti al marketing di rispondere rapidamente e di gestire attivamente le prestazioni dei contenuti e delle campagne di marketing. I dati in tempo reale segnalati sono latenti da meno di due minuti e si aggiornano automaticamente su base minuto per minuto.

![](assets/report-realtime.png)

Il dashboard include metriche ad alta frequenza di Adobe Analytics e analisi del sito per segnalare visivamente il traffico e la tendenza della visualizzazione delle pagine di notizie dinamiche e siti web di vendita al dettaglio. In tempo reale è possibile comprendere le tendenze dei dati da minuto a minuto, entro pochi secondi dalla raccolta. Raccoglie e trasferisce i dati in un’interfaccia utente con aggiornamento automatico, utilizzando correlazione e tracciamento in tempo reale dei contenuti e alcune conversioni.

Due degli scenari di utilizzo più diffusi includono editori che desiderano promuovere/moderare le storie quando cambia l’attività dell’utente e addetti al marketing che desiderano tenere traccia del lancio di una nuova linea di prodotti.

In qualità di amministratore, puoi

* Crea fino a 3 rapporti in tempo reale per suite di rapporti, utilizzando dimensioni o classificazioni e metriche esistenti. Utilizza le dimensioni secondarie per correlare (o suddividere) con quella primaria.
* Aggiungi 3 dimensioni (o classificazioni) per report (una primaria e due secondarie), oltre a 1 metrica a livello di sito.
* Utilizza qualsiasi evento personalizzato, evento del carrello acquisti o istanza.
* Visualizza fino a 2 ore di dati storici in tempo reale e modifica questa impostazione:

   * Ultimi 15 minuti: Granularità di 1 minuto
   * Ultimi 30 minuti: Granularità di 1 minuto
   * Ultima 1 ora: Granularità di 2 minuti
   * Ultime 2 ore: Granularità di 4 minuti

* Confronta, ad esempio, i valori della settimana scorsa ai valori dello scorso anno (così come al totale di oggi).

Le eVar (metriche di conversione) non sono supportate, in quanto non esiste alcun concetto di persistenza. Puoi selezionare le metriche di conversione, ma queste funzionano solo se sono impostate sulla stessa pagina delle dimensioni. Per ulteriori informazioni, vedere il messaggio di avviso acquisito in [Impostazione dei rapporti in tempo reale](/help/components/c-real-time-reporting/t-realtime-admin.md).

L&#39;impostazione e la visualizzazione dei rapporti in tempo reale è limitata agli amministratori o a qualsiasi utente nei gruppi di autorizzazioni &quot;Accesso a tutti i rapporti&quot; e &quot;Generazione avanzata di rapporti&quot; . Tuttavia, Real-Time rispetta le autorizzazioni. Se, ad esempio, non disponi dei diritti per visualizzare le entrate, non potrai visualizzare un rapporto in tempo reale che include i dati sulle entrate.

## Latenza dei dati come risultato della configurazione A4T {#section_806CE36354FC4C539A0DED9266A5C704}

Dopo aver abilitato l’integrazione A4T in Adobe [!DNL Target], si verifica una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. Questo aumento della latenza consente l’utilizzo di dati da Analytics e [!DNL Target] da memorizzare sullo stesso hit, per suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

L’aumento della latenza inizia dopo l’implementazione del servizio Identity, anche se questa integrazione non è stata completamente implementata.
