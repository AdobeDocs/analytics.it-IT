---
description: Visualizza il traffico delle pagine Web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.
seo-description: Visualizza il traffico delle pagine Web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.
seo-title: Rapporti in tempo reale
solution: Analytics
title: Rapporti in tempo reale
topic: Rapporti
uuid: c 09 cc 605-0 b 3 b -41 ab -9 b 46-8 c 2 a 26 f 579 a 3
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Rapporti in tempo reale

Visualizza il traffico delle pagine Web e classifica le visualizzazioni di pagina in tempo reale. Fornisce dati fruibili su cui basare le decisioni aziendali.

>[!NOTE]
>
>Il report in tempo reale non richiede un'implementazione o un tag aggiuntivo. sfrutta la tua implementazione esistente di Adobe Analytics. To configure real-time reports, see [Real-Time Reports Configuration](../../../admin/admin/realtime/t-realtime-admin.md#task_1CD03E9B6BDB48B08E9E612183557F40).

**[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Real-Time]**

In tempo reale sono riportate le seguenti domande: Cosa succede al sito e perché? Consente di rispondere rapidamente e di gestire attivamente le prestazioni dei contenuti e delle campagne di marketing. I dati in tempo reale segnalati sono inferiori a due minuti e vengono aggiornati automaticamente a cadenza minuto.

![](assets/report-realtime.png)

Il dashboard include metriche ad alta frequenza e analisi del sito ad alta frequenza di Adobe Analytics per il traffico visivo e la visualizzazione delle pagine di siti Web di notizie dinamiche e vendita al dettaglio. In tempo reale le tendenze nei dati sono riconoscibili da minuti a minuto, entro i secondi della raccolta. Raccoglie e trasmette i dati in un'interfaccia utente che aggiorna automaticamente, utilizzando la correlazione in tempo reale e il tracciamento dei contenuti e alcune conversioni.

Due scenari di utilizzo più comuni includono editori che desiderano promuovere/declassare storie in seguito a modifiche dell'attività utente, e agli addetti al marketing che desiderano tenere traccia del lancio di una nuova linea di prodotti.

In qualità di amministratore, potete

* Crea fino a 3 report in tempo reale per suite di rapporti, utilizzando dimensioni o classificazioni esistenti e metriche. Utilizzate le dimensioni secondarie per correlare (o suddividere) quella principale.
* Aggiungi 3 dimensioni (o classificazioni) per report (una primaria e due secondaria), oltre alla metrica 1 al sito.
* Utilizzate un evento personalizzato, un evento carrello acquisti o un'istanza.
* Visualizzare fino a 2 ore di dati storici in tempo reale e modificare questa impostazione:

   * Ultimi 15 minuti: Granularità di 1 minuti
   * Ultimi 30 minuti: Granularità di 1 minuti
   * Ultima 1 ora: Granularità di 2 minuti
   * Ultime 2 ore: Granularità di 4 minuti

* Confronta, ad esempio, i valori della settimana scorsa con i valori dello scorso anno (oltre al valore complessivo di oggi).

Tenere presente che le evar (metriche di conversione) non sono supportate, in quanto non esiste alcun concetto di persistenza. Anche se puoi selezionare le metriche di conversione, funzionano solo se sono impostate sulla stessa pagina delle dimensioni. For more information, see the warning message captured in [Setting up Real-Time Reports](../../../admin/admin/realtime/t-realtime-admin.md#task_1CD03E9B6BDB48B08E9E612183557F40).

La configurazione e la visualizzazione dei report in tempo reale è limitata agli amministratori o a qualsiasi utente nei gruppi di autorizzazione «Accesso ai report» e «Rapporti avanzati». Tuttavia, in Tempo reale le autorizzazioni sono rispettate. Se, ad esempio, non disponi dei diritti per visualizzare i ricavi, non potrai visualizzare un report in tempo reale che include dati sui ricavi.

## Data Latency as a Result of A4T Configuration {#section_806CE36354FC4C539A0DED9266A5C704}

Dopo che l'integrazione con T 4 T è abilitata in Adobe Target, si possono verificare ulteriori 5-10 minuti di latenza in Adobe Analytics. Questo aumento della latenza consente la memorizzazione dei dati da Analytics e Target nello stesso hit, con conseguente possibilità di suddividere i test per pagina e sezione del sito.

Questo aumento si riflette in tutti i servizi e gli strumenti di Adobe Analytics, compresi lo streaming live e il reporting in tempo reale e si applica nei seguenti scenari:

* Per lo streaming live, i rapporti in tempo reale e le richieste API e per i dati correnti per le variabili di traffico, vengono ritardati solo gli insiemi con ID di dati supplementari.
* Per i dati correnti sulle metriche di conversione, i dati finalizzati e i feed di dati, tutti gli hit sono ritardati di altri 5-7 minuti.

L'incremento della latenza inizia dopo l'implementazione del servizio identità, anche se l'integrazione non è stata implementata completamente.
