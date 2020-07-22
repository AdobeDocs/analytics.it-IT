---
description: Fornisce risposte e suggerimenti per la risoluzione dei problemi ad alcune delle domande  Analytics più frequenti.
keywords: Troubleshooting Analytics
title: Domande frequenti
uuid: 285b0ea4-aa07-4d39-a74f-37b1d02d19f1
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 0%

---


# Domande frequenti

Fornisce risposte e suggerimenti per la risoluzione dei problemi ad alcune delle domande  Analytics più frequenti per Reporting e  Analytics. Per le domande di implementazione più frequenti, consulta le [Domande frequenti](/help/implement/faq.md) nella guida Implementa.

**Il mio account è stato bloccato; come lo sblocco?**

Per riattivare un account, contattate un amministratore all&#39;interno dell&#39;organizzazione. Consultate anche [Risoluzione dei problemi di accesso con Adobe  Analytics](/help/technotes/troubleshoot-login.md) nella guida utente di Technotes.

**Perché viene visualizzato un rapporto vuoto anche se so che i dati vengono raccolti?**

Per risolvere i problemi relativi ai dati del rapporto, è necessario controllare diversi elementi:

* Controlla le metriche utilizzate: Per impostazione predefinita, alcuni rapporti sono su Entrate in Reporting e  Analytics. Assicurati che la metrica visualizzata sia rilevante per il rapporto.
* Controlla l’intervallo di date: Gli intervalli di date, in particolare quelli oltre i criteri di conservazione dei dati aziendali, non possono restituire alcun dato. Verificare che l&#39;intervallo di date sia impostato correttamente.
* Controlla filtri URL interni: Alcuni rapporti sulle origini di traffico non funzionano fino a quando non si definiscono correttamente i filtri URL interni.

**Perché alcuni rapporti mancano nel menu di navigazione?**

Qualsiasi rapporto mancante in un menu proviene in genere da autorizzazioni limitate o personalizzazione del menu. Contatta un amministratore di prodotto all&#39;interno dell&#39;organizzazione per assicurarti di avere accesso a tutte le dimensioni e metriche necessarie e che la struttura del menu di una suite di rapporti non sia stata personalizzata.

**Perché alcuni valori lunghi vengono tagliati?**

Quasi tutte le variabili in Adobe  Analytics hanno un limite di caratteri. Il limite per il nome della pagina è di 100 caratteri, mentre per le variabili di conversione personalizzate (eVar) è previsto un limite di 255 caratteri. Adobe consiglia di assicurarsi che i valori inviati ad Adobe siano concisi per evitare il troncamento.

**Perché si verifica un ritardo notevole nella generazione dei rapporti?**

Il reporting in tempo reale consente di rendere disponibili alcune metriche del traffico in pochi minuti, mentre la conversione e altri dati che richiedono molta elaborazione sono in genere disponibili entro 30-90 minuti. Anche se la piattaforma Experience Cloud  è solida, ci sono alcune situazioni che possono causare ritardi nella generazione dei report. Tale ritardo è definito latenza. Per ulteriori informazioni, consulta [Latenza](/help/technotes/latency.md) nella guida utente di Technotes.

**Perché non è possibile visualizzare la versione del dispositivo su iPhone?**

I dispositivi Apple segnalano la versione del firmware nella stringa agente utente, non nella versione del dispositivo. È difficile determinare la versione del dispositivo iPhone utilizzando le informazioni disponibili per Adobe  Analytics. Per ulteriori informazioni, consulta [Confronto delle versioni](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) dei dispositivi iPhone nella  Analytics KB.

**Perché i totali nella parte inferiore del rapporto non corrispondono quando si calcolano i valori?**

Gli elementi dimensionali possono essere spesso applicati in più posizioni; ad esempio, visite che si estendono su mezzanotte o su più prodotti appartenenti a un singolo ordine. L&#39;elemento dimensione è segnalato tra tutte le voci applicabili, ma è deduplicato nel totale del rapporto. Per ulteriori informazioni, consulta [Confrontare la somma degli elementi di riga con il totale](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) del report nel  Analytics KB.

**Come si escludono i dati da un particolare indirizzo IP nella suite di rapporti?**

Puoi eliminare dai rapporti i dati dalle attività interne del sito Web, ad esempio i test del sito e l&#39;utilizzo dei dipendenti. Questa funzione consente a voi e ai vostri colleghi di visitare il sito senza distorcere i dati del traffico. Per ulteriori informazioni, consulta [Escludi per indirizzo](/help/admin/admin/exclude-ip.md) IP nella guida utente per l&#39;amministratore.

**Posso eliminare una suite di rapporti?**

Non è possibile eliminare una suite di rapporti. Tuttavia, una suite di rapporti può essere nascosta da tutte le visualizzazioni in Adobe  Analytics. Le chiamate server inviate a una suite di rapporti nascosta continuano a essere conteggiate per il limite del contratto mensile. Per ulteriori informazioni, consulta [Nascondere le suite](/help/admin/company/c-hide-report-suites.md) di rapporti nella guida utente per l&#39;amministratore.

**Quando si utilizza la segmentazione, quale contenitore è necessario utilizzare? Visualizzazione pagina, visita o visitatore?**

Il contenitore del segmento utilizzato dipende dalla larghezza di acquisizione dei dati. I contenitori di visualizzazione pagina consentono di inserire solo hit che corrispondono ai criteri dei segmenti, utili per filtrare parti irrilevanti delle visite. I contenitori delle visite consentono di visualizzare tutti gli hit di una visita in cui uno o più hit corrispondono ai criteri del segmento, utili per osservare le sessioni in generale. I contenitori dei visitatori consentono di effettuare tutte le visite in cui un hit corrisponde ai criteri dei segmenti, utili per osservare le persone. È la scelta da parte dell&#39;utente come analista determinare quale contenitore di segmenti è più adatto da utilizzare. See [Segmentation overview](/help/components/c-segmentation/seg-overview.md) in the Components user guide for more information.

**Perché il mio segmento non viene visualizzato nella Data warehouse?**

A causa &#39;architettura di elaborazione univoca, la piattaforma non è ottimizzata per gestire alcuni tipi di dati, come i percorsi. Per ulteriori informazioni, consulta [Data warehouse della compatibilità](/help/components/c-segmentation/seg-reference/seg-compatibility.md) dei segmenti nella guida utente Componenti.
