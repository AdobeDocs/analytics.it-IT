---
description: Visualizza il traffico delle pagine Web e classifica le visualizzazioni delle pagine in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.
seo-description: Visualizza il traffico delle pagine Web e classifica le visualizzazioni delle pagine in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.
seo-title: Panoramica reportistica in tempo reale
solution: Analytics
title: Panoramica reportistica in tempo reale
topic: Rapporti
uuid: ff832952-c507-4c63-9437-25d9c44c44d1
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Panoramica reportistica in tempo reale

Il reporting in tempo reale mostra il traffico delle pagine Web e classifica le visualizzazioni delle pagine in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.

>[!NOTE]
>
>Il rapporto in tempo reale non richiede alcuna implementazione o tag aggiuntivi. Utilizza l’implementazione esistente di Adobe Analytics. Per configurare i rapporti in tempo reale, consulta Configurazione [dei rapporti in tempo](/help/components/c-real-time-reporting/t-realtime-admin.md)reale.

**[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Real-Time]**

Risposta in tempo reale alle seguenti domande: Che cosa è tendenza sul mio sito, e perché? Consente agli esperti di marketing di rispondere e gestire attivamente le prestazioni dei contenuti e delle campagne di marketing in modo rapido. I dati in tempo reale segnalati sono latenti di meno di due minuti e si aggiornano automaticamente di minuto per minuto.

![](assets/report-realtime.png)

Il dashboard include le metriche ad alta frequenza di Adobe Analytics e l'analisi del sito per segnalare visivamente il traffico e la tendenza della visualizzazione delle pagine delle notizie dinamiche e dei siti Web per la vendita al dettaglio. In tempo reale è possibile comprendere le tendenze dei dati da minuto a minuto, entro pochi secondi dalla raccolta. Raccoglie e trasferisce i dati in un’interfaccia con aggiornamento automatico, utilizzando la correlazione in tempo reale e il tracciamento del contenuto e alcune conversioni.

Due degli scenari di utilizzo più comuni sono gli editori che desiderano promuovere/ridurre le storie in base ai cambiamenti dell'attività utente e gli addetti al marketing che desiderano monitorare il lancio di una nuova linea di prodotti.

In qualità di amministratore potete

* Crea fino a 3 report in tempo reale per suite di rapporti, utilizzando dimensioni o classificazioni e metriche esistenti. Utilizzate le dimensioni secondarie per correlare (o suddividere) quella principale.
* Aggiungi 3 dimensioni (o classificazioni) per report (uno principale e due secondario), oltre a 1 metrica a livello di sito.
* Utilizzate qualsiasi evento personalizzato, evento del carrello acquisti o istanza.
* Visualizzare fino a 2 ore di dati storici in tempo reale e modificare questa impostazione:

   * Ultimi 15 minuti: Granularità di 1 minuto
   * Ultimi 30 minuti: Granularità di 1 minuto
   * Ultima 1 ora: Granularità di 2 minuti
   * Ultime 2 ore: Granularità di 4 minuti

* Confronta, ad esempio, i valori della settimana scorsa con i valori dello scorso anno (oltre al totale odierno).

Tenere presente che le eVar (metriche di conversione) non sono supportate, poiché non esiste un concetto di persistenza. Sebbene sia possibile selezionare le metriche di conversione, queste funzionano solo se sono impostate sulla stessa pagina delle dimensioni. Per ulteriori informazioni, vedere il messaggio di avviso acquisito in [Impostazione dei rapporti](/help/components/c-real-time-reporting/t-realtime-admin.md)in tempo reale.

L'impostazione e la visualizzazione dei rapporti in tempo reale è limitata agli amministratori o a qualsiasi utente nei gruppi di autorizzazioni "Accesso a tutti i rapporti" e "Rapporti avanzati". Tuttavia, in tempo reale le autorizzazioni vengono rispettate. Se, ad esempio, non disponete dei diritti per visualizzare le entrate, non sarete in grado di visualizzare un rapporto in tempo reale che include i dati sulle entrate.

## Latenza dei dati come risultato della configurazione A4T {#section_806CE36354FC4C539A0DED9266A5C704}

Dopo l'abilitazione dell'integrazione A4T in Adobe [!DNL Target], si verificherà una latenza aggiuntiva di 5-10 minuti in Adobe Analytics. This latency increase allows data from Analytics and [!DNL Target] to be stored on the same hit, allowing you to break down tests by page and site section.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

L'aumento della latenza inizia dopo l'implementazione del servizio identità, anche se l'integrazione non è stata implementata completamente.
