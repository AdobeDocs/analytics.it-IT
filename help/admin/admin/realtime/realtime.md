---
description: Visualizza il traffico delle pagine Web e classifica le visualizzazioni delle pagine in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.
title: Rapporti in tempo reale
topic: Reports
uuid: c09cc605-0b3b-41ab-9b46-8c2a26f579a3
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 16%

---


# Rapporti in tempo reale

Visualizza il traffico delle pagine Web e classifica le visualizzazioni delle pagine in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.

>[!NOTE]
>
>Il rapporto in tempo reale non richiede alcuna implementazione o tag aggiuntivi. Utilizza l’implementazione esistente di Adobe  Analytics. Per configurare i rapporti in tempo reale, consulta Configurazione [dei rapporti in tempo](/help/admin/admin/realtime/t-realtime-admin.md)reale.

**[!UICONTROL Site Metrics]** > **[!UICONTROL Real-Time]**

Risposta in tempo reale alle seguenti domande: Che cosa è tendenza sul mio sito, e perché? Consente agli esperti di marketing di rispondere e gestire attivamente le prestazioni dei contenuti e delle campagne di marketing in modo rapido. I dati in tempo reale segnalati sono latenti di meno di due minuti e si aggiornano automaticamente di minuto per minuto.

![](assets/report-realtime.png)

Il dashboard include metriche ad alta frequenza di Adobe  Analytics e analisi del sito per segnalare visivamente il traffico e la tendenza della visualizzazione delle pagine delle notizie dinamiche e dei siti Web per la vendita al dettaglio. In tempo reale è possibile comprendere le tendenze dei dati da minuto a minuto, entro pochi secondi dalla raccolta. Raccoglie e trasferisce i dati in un’interfaccia con aggiornamento automatico, utilizzando la correlazione in tempo reale e il tracciamento del contenuto e alcune conversioni.

Due degli scenari di utilizzo più comuni sono gli editori che desiderano promuovere o ridurre le storie in base ai cambiamenti dell&#39;attività dell&#39;utente e gli addetti al marketing che desiderano monitorare il lancio di una nuova linea di prodotti.

In qualità di amministratore potete

* Crea fino a 3 report in tempo reale per suite di rapporti, utilizzando dimensioni o classificazioni e metriche esistenti. Utilizzate le dimensioni secondarie per correlare (o suddividere) quella principale.
* Aggiungi 3 dimensioni (o classificazioni) per report (uno principale e due secondario), oltre a 1 metrica per l&#39;intero sito.
* Utilizzate qualsiasi evento personalizzato, evento del carrello acquisti o istanza.
* Visualizzare fino a 2 ore di dati storici in tempo reale e modificare questa impostazione:

   * Ultimi 15 minuti: Granularità di 1 minuto
   * Ultimi 30 minuti: Granularità di 1 minuto
   * Ultima 1 ora: Granularità di 2 minuti
   * Ultime 2 ore: Granularità di 4 minuti

* Confronta, ad esempio, i valori della settimana scorsa con i valori dello scorso anno (oltre al totale odierno).

Tenere presente che le eVar (metriche di conversione) non sono supportate, poiché non esiste un concetto di persistenza. Sebbene sia possibile selezionare le metriche di conversione, queste funzionano solo se sono impostate sulla stessa pagina delle dimensioni. Per ulteriori informazioni, vedere il messaggio di avviso acquisito in [Impostazione dei rapporti](/help/admin/admin/realtime/t-realtime-admin.md)in tempo reale.

L&#39;impostazione e la visualizzazione dei rapporti in tempo reale è limitata agli amministratori o a qualsiasi utente nei gruppi di autorizzazioni &quot;Accesso a tutti i rapporti&quot; e &quot;Rapporti avanzati&quot;. Tuttavia, in tempo reale le autorizzazioni vengono rispettate. Se, ad esempio, non disponete dei diritti per visualizzare le entrate, non sarete in grado di visualizzare un rapporto in tempo reale che include i dati sulle entrate.

## Latenza dei dati come risultato della configurazione A4T {#section_806CE36354FC4C539A0DED9266A5C704}

Dopo che l&#39;integrazione A4T è abilitata nel  Adobe Target, si verificherà una latenza aggiuntiva di 5-10 minuti in Adobe  Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

L&#39;aumento della latenza inizia dopo l&#39;implementazione del servizio identità, anche se l&#39;integrazione non è stata implementata completamente.
