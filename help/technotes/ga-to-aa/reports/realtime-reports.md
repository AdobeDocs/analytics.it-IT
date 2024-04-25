---
title: Rapporti in tempo reale in Adobe Analytics
description: Scopri come creare rapporti in tempo reale in Adobe Analytics rivolti agli utenti che hanno più familiarità con la Google Analytics.
feature: Third-party Integration
exl-id: 0ca27992-fff8-4bb4-8582-31fd401b23f6
source-git-commit: 8f08ff46d33d050d0bdb4e0555611ba37ccc8474
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---

# Rapporti in tempo reale

I rapporti in tempo reale mostrano cosa sta succedendo sul tuo sito in questo momento. Questi tipi di report sono particolarmente utili per visualizzare i risultati immediati degli aggiornamenti apportati al sito. Ad esempio, un’azienda che esegue una vendita il Black Friday può misurare il traffico verso pagine specifiche e determinare quali vendite dare priorità in base alle prestazioni in quel momento.

![Rapporto in tempo reale](/help/technotes/ga-to-aa/assets/realtime.png)

I rapporti in tempo reale sono una delle poche funzioni non ancora introdotte in Analysis Workspace. Utilizza i rapporti per ottenere questi dati. Richiedono una configurazione semplice per iniziare a raccogliere i dati.

Per accedere alla pagina di configurazione del rapporto in tempo reale (sono necessarie le autorizzazioni di amministratore):

1. Clic **[!UICONTROL Workspace]** nella barra di navigazione superiore di Adobe Analytics.
1. Seleziona **[!UICONTROL Reports]** dalla barra di navigazione a sinistra.
1. Seleziona **[!UICONTROL Enagement]** ![Freccia](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ChevronRight_18_N.svg) **[!UICONTROL Real-Time]**. È inoltre possibile ![Ricerca](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) cerca in tempo reale.
1. Se per la suite di rapporti non è ancora abilitato il tempo reale, viene visualizzato un messaggio con un collegamento per configurare la suite di rapporti.

Adobe consente di raccogliere dati in contemporanea fino a tre rapporti in tempo reale. Ciascuno deve essere configurato prima che inizi a raccogliere dati in tempo reale.

![Configurazione rapporti in tempo reale](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Posizioni in tempo reale

Le posizioni in tempo reale indicano dove si trovano i visitatori mentre visitano il sito al momento. Per configurare uno dei tre rapporti in tempo reale per visualizzare i dati sulla posizione:

1. Clic [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot di rapporti in tempo reale:
   * Denomina il rapporto in tempo reale, ad esempio &quot;Posizioni&quot;.
   * Istanze viene in genere utilizzato come metrica. Utenti/Visitatori univoci non è al momento disponibile nei rapporti in tempo reale.
   * Per il Dimension principale, in genere viene utilizzato il paese di geosegmentazione. Sono inoltre disponibili le opzioni Regione di geosegmentazione, GeoSegmentation US DMA e Città di geosegmentazione.
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti che desideri visualizzare per questo traffico. Non è necessario che le dimensioni secondarie siano specifiche per la posizione.
3. Fai clic su [!UICONTROL Save and View Report].

## Origini di traffico in tempo reale

Le origini del traffico in tempo reale indicano da dove provengono i visitatori che visitano il sito al momento. Per configurare uno dei tre rapporti in tempo reale per visualizzare i dati delle origini del traffico:

1. Fai clic su Configura accanto al titolo del rapporto in tempo reale.
2. In uno degli slot di rapporti in tempo reale:
   * Denomina il rapporto in tempo reale, ad esempio &quot;Origini del traffico&quot;.
   * Istanze viene in genere utilizzato come metrica. Utenti/Visitatori univoci non è al momento disponibile nei rapporti in tempo reale.
   * Per il Dimension principale, viene in genere utilizzato il dominio di riferimento. Sono disponibili anche motore di ricerca e parola chiave di ricerca.
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti che desideri visualizzare per questo traffico. Le dimensioni secondarie non devono essere specifiche per le origini di traffico.
3. Fai clic su [!UICONTROL Save and View Report].

## Contenuti in tempo reale

Il contenuto in tempo reale indica le pagine attualmente visualizzate dai visitatori. Per configurare uno dei tre rapporti in tempo reale per visualizzare i dati del contenuto:

1. Clic [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot di rapporti in tempo reale:
   * Denomina il rapporto in tempo reale, ad esempio &quot;Contenuto&quot;.
   * Istanze viene in genere utilizzato come metrica. Utenti/Visitatori univoci non è al momento disponibile nei rapporti in tempo reale.
   * Per il Dimension principale, in genere viene utilizzata la pagina. Se l’implementazione definisce queste variabili, sono disponibili anche Sezione sito e Server.
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti che desideri visualizzare per questo traffico. Le dimensioni secondarie non devono essere specifiche per il contenuto.
3. Fai clic su [!UICONTROL Save and View Report].

## Eventi in tempo reale

Eventi in tempo reale indica gli eventi che si verificano maggiormente sul sito. Nelle Google Analytics, un evento acquisisce il numero di volte in cui si è verificata un’azione specifica (in genere un’azione non correlata a una visualizzazione pagina). Gli eventi GA vengono inviati con Categoria, Etichetta e Azione. In Adobe Analytics, gli eventi personalizzati sono metriche a cui vengono assegnati nomi descrittivi nell’Admin Console e che possono essere analizzati insieme a qualsiasi dimensione. Se cerchi in Adobe Analytics una dimensione simile agli eventi Google Analytics, puoi applicare la dimensione Collegamento personalizzato, che spesso viene utilizzata come elemento di riferimento per la raccolta di dati non correlati alle visualizzazioni di pagina (oltre a Collegamenti di uscita per Uscite e Collegamenti di download per Download).

>[!NOTE]
>
>Quando si utilizzano eventi personalizzati nei rapporti in tempo reale, l’elemento dimensionale deve essere definito nello stesso hit dell’evento personalizzato. Ad esempio, se visualizzi un evento personalizzato &quot;Registrazioni&quot; per la dimensione &quot;Dominio di riferimento&quot;, non verranno restituiti dati senza un’implementazione aggiuntiva. Poiché il dominio di riferimento viene visualizzato solo sul primo hit e un evento personalizzato viene in genere visualizzato più avanti nella visita, i dati non possono essere associati in rapporti in tempo reale. Questi dati sono disponibili utilizzando Analysis Workspace con latenza di elaborazione standard, che in genere è di 30-90 minuti.

## Conversioni in tempo reale

Le conversioni in tempo reale presentano i dati in modo diverso tra le piattaforme. Gli obiettivi nelle Google Analytics sono simili alle metriche e agli eventi di successo in Adobe Analytics. Puoi utilizzare la maggior parte delle metriche in Adobe Analytics (metriche personalizzate come eventi di successo e metriche standard come ricavi) nei Rapporti in tempo reale. Analogamente alle Google Analytics, puoi anche applicare dimensioni come nome del prodotto, codice di tracciamento e prestazioni della campagna nei rapporti in tempo reale.

1. Clic [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot di rapporti in tempo reale:
   * Denomina il rapporto in tempo reale, ad esempio &quot;Conversioni&quot;.
   * Istanze viene in genere utilizzato come metrica. Utenti/Visitatori univoci non è al momento disponibile nei rapporti in tempo reale.
   * Per il Dimension principale, in genere viene utilizzato il codice di tracciamento. La dimensione Prodotti è disponibile anche se viene utilizzata dall’implementazione.
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti che desideri visualizzare per questo traffico. Le dimensioni secondarie non devono essere specifiche per le conversioni.
3. Fai clic su [!UICONTROL Save and View Report].

>[!NOTE]
>
>Se utilizzi eventi esterni a Istanze, come Ordini, assicurati che l’implementazione definisca la dimensione e l’evento per lo stesso hit. Se dimensioni ed eventi non vengono attivati sullo stesso hit, tali dati sono disponibili in Analysis Workspace utilizzando la latenza di elaborazione standard, che in genere è di 30-90 minuti.
