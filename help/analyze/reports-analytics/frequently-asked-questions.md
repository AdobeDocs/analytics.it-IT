---
description: Fornisce risposte e suggerimenti per la risoluzione dei problemi ad alcune delle domande più frequenti su Analytics.
keywords: Risoluzione dei problemi di Analytics
title: Domande frequenti su Reports & Analytics
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 99702728-971f-484a-91f5-f3210b89485c
source-git-commit: 4ddc2640aa8b3a22411c86ff8bfe0ecf345a3d63
workflow-type: tm+mt
source-wordcount: '843'
ht-degree: 6%

---

# Domande frequenti

{{ra-eol}}

Fornisce risposte e suggerimenti per la risoluzione dei problemi ad alcune delle domande più frequenti su Analytics per Reports &amp; Analytics. Per domande frequenti sull’implementazione, consulta la sezione [Domande frequenti](/help/implement/faq.md) nella guida utente Implementa .

>[!IMPORTANT]
>A partire dal **31 dicembre 2023**, Adobe intende interrompere Reports &amp; Analytics e i relativi rapporti e funzioni. A quel punto, Reports &amp; Analytics e tutti i suoi rapporti e programmi cesseranno di funzionare. I report, le visualizzazioni e la tecnologia di base che alimentano Reports &amp; Analytics non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di Reports &amp; Analytics sono disponibili in Analysis Workspace. A partire dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di Reports &amp; Analytics sono state spostate in Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. Questo avviso spiega il processo di fine del ciclo di vita.

**Il mio account è stato bloccato; come lo sblocco?**

Per riattivare un account, contatta un amministratore all’interno della tua organizzazione. Vedi anche [Risolvere i problemi di accesso con Adobe Analytics](/help/technotes/troubleshoot-login.md) nella guida utente delle note tecniche.

**Perché viene visualizzato un rapporto vuoto anche se so che i dati vengono raccolti?**

Ci sono diversi elementi da controllare per risolvere i problemi dei dati del report:

* Controlla le metriche utilizzate: Per impostazione predefinita, alcuni rapporti riportano i ricavi in Reports &amp; Analytics. Assicurati che la metrica che stai visualizzando sia rilevante per il rapporto.
* Controlla l’intervallo di date: Gli intervalli di date, in particolare quelli oltre i criteri di conservazione dei dati della tua organizzazione, non possono restituire dati. Verifica che l’intervallo di date sia impostato correttamente.
* Controlla i filtri URL interni: Alcuni rapporti sulle sorgenti di traffico non funzionano fino a quando non definisci correttamente i filtri URL interni.

**Perché mancano alcuni rapporti nel menu di navigazione?**

Tutti i report mancanti da un menu sono solitamente generati da autorizzazioni limitate o personalizzazioni del menu. Contatta un amministratore di prodotto all’interno della tua organizzazione per assicurarti di avere accesso a tutte le dimensioni e metriche necessarie e che la struttura del menu di una suite di rapporti non sia stata personalizzata.

**Perché alcuni valori lunghi vengono tagliati?**

Quasi tutte le variabili in Adobe Analytics hanno un limite di caratteri. Il nome della pagina ha un limite di 100 caratteri, mentre le variabili di conversione personalizzate (eVar) hanno un limite di 255 caratteri. Adobe consiglia di assicurarsi che i valori inviati all’Adobe siano concisi per evitare il troncamento.

**Perché si verifica un ritardo significativo nella generazione dei rapporti?**

Il reporting in tempo reale consente di rendere disponibili alcune metriche del traffico in pochi minuti, mentre la conversione e altri dati ad alta intensità di elaborazione sono solitamente disponibili entro 30-90 minuti. Anche se la piattaforma di Experience Cloud è solida, ci sono alcune situazioni che possono causare ritardi nel reporting. Questo ritardo è definito latenza. Vedi [Latenza](/help/technotes/latency.md) per ulteriori informazioni, consulta la guida utente sulle note tecniche .

**Perché non riesco a vedere la versione del dispositivo su iPhone?**

I dispositivi Apple segnalano la versione del firmware nella stringa dell&#39;agente utente, non la versione del dispositivo. È difficile determinare la versione del dispositivo iPhone utilizzando le informazioni disponibili in Adobe Analytics. Vedi [Confronto delle versioni dei dispositivi iPhone](https://helpx.adobe.com/analytics/kb/comparing-iphone-device-versions.html) nella KB di Analytics per ulteriori informazioni.

**Perché i totali nella parte inferiore del rapporto non corrispondono quando importo i valori?**

Gli elementi Dimension possono essere applicati spesso in più luoghi; ad esempio, visite che si estendono su più prodotti appartenenti a un singolo ordine. L’elemento dimensionale viene riportato su tutte le voci di riga applicabili, ma viene deduplicato nel totale del rapporto. Vedi [Confrontare la somma degli elementi riga con il totale del rapporto](https://helpx.adobe.com/analytics/kb/sum-line-items-different-from-total.html) nella KB di Analytics per ulteriori informazioni.

**Come posso escludere i dati da un particolare indirizzo IP nella mia suite di rapporti?**

È possibile eliminare i dati dalle attività interne del sito web, ad esempio il test del sito e l&#39;utilizzo dei dipendenti, dai rapporti. Questa funzione consente a te e ai tuoi colleghi di visitare il sito senza distorcere i dati sul traffico. Vedi [Escludi per indirizzo IP](/help/admin/admin/exclude-ip.md) nella guida utente di Admin per ulteriori informazioni.

**Posso eliminare una suite di rapporti?**

Impossibile eliminare una suite di rapporti. Tuttavia, una suite di rapporti può essere nascosta da tutte le visualizzazioni in Adobe Analytics. Tieni presente che le chiamate server inviate a una suite di rapporti nascosta vengono comunque conteggiate in base al limite di contratto mensile. Vedi [Nascondere suite di rapporti](/help/admin/company/c-hide-report-suites.md) nella guida utente di Admin per ulteriori informazioni.

**Quando utilizzo la segmentazione, quale contenitore devo utilizzare? Visualizzazione pagina, visita o visitatore?**

Il contenitore di segmenti utilizzato dipende dalla larghezza di acquisizione dei dati. I contenitori di visualizzazione pagina consentono di inserire solo hit che corrispondono a criteri di segmento, utili per filtrare parti irrilevanti delle visite. I contenitori Visita consentono di visualizzare tutti gli hit di una visita in cui uno o più hit corrispondono ai criteri dei segmenti, utili per guardare le sessioni in generale. I contenitori Visitatore consentono di inserire tutte le visite in cui un hit corrisponde a criteri di segmento, utili per guardare le persone. È tua scelta come analista determinare quale contenitore di segmenti è più adatto da utilizzare. Vedi [Panoramica sulla segmentazione](/help/components/segmentation/seg-overview.md) nella guida utente Componenti per ulteriori informazioni.

**Perché il mio segmento non viene visualizzato nella Data Warehouse?**

A causa dell’architettura di elaborazione unica della Data Warehouse, la piattaforma non è ottimizzata per gestire alcuni tipi di dati, ad esempio percorsi. Vedi [Data Warehouse compatibilità segmento](/help/components/segmentation/seg-reference/seg-compatibility.md) nella guida utente Componenti per ulteriori informazioni.
