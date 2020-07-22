---
title: Rapporti in tempo reale in Adobe  Analytics
description: Scoprite come creare rapporti in tempo reale in Adobe  Analytics, rivolti agli utenti che hanno familiarità con Google  Analytics.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 0%

---


# Rapporti in tempo reale

I rapporti in tempo reale mostrano cosa sta accadendo sul sito in questo momento. Questi tipi di rapporti sono particolarmente importanti per visualizzare i risultati immediati degli aggiornamenti apportati al sito. Ad esempio, una società che esegue una vendita il Black Friday può misurare il traffico su pagine specifiche e determinare quali vendite dare la priorità in base alle prestazioni in quel momento.

![Report in tempo reale](/help/technotes/ga-to-aa/assets/realtime.png)

I report in tempo reale sono una delle poche funzionalità che non sono ancora state introdotte  Analysis Workspace. Utilizzate Reporting e  Analytics per ottenere questi dati. Richiedono una configurazione semplice per iniziare a raccogliere i dati.

Per accedere alla pagina di configurazione del rapporto in tempo reale (sono necessarie le autorizzazioni di amministratore):

1. Fate clic [!UICONTROL Reports] nella navigazione dell’intestazione di Adobe  Analytics.
2. Nel menu a sinistra, fate clic su *[!UICONTROL Site Metrics]* > *[!UICONTROL Real-Time]*.
3. Se la suite di rapporti non dispone ancora dell&#39;attivazione in tempo reale, viene visualizzato un messaggio con un collegamento per configurare la suite di rapporti. Se la suite di rapporti ha l&#39;abilitazione in tempo reale, fai clic [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.

Adobe consente fino a tre report in tempo reale per la raccolta simultanea di dati. Ciascuna deve essere configurata prima che inizi la raccolta dei dati in tempo reale.

![Configurazione report in tempo reale](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Posizioni in tempo reale

Le posizioni in tempo reale indicano dove risiedono i visitatori durante la visita del sito al momento attuale. Per configurare uno dei tre rapporti in tempo reale per visualizzare i dati sulla posizione:

1. Fate clic [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denominate il rapporto in tempo reale; ad esempio, &quot;Locations&quot;.
   * Le istanze vengono in genere utilizzate come metrica. Al momento, Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per la dimensione primaria, viene in genere utilizzato il Paese di segmentazione geografica. Sono inoltre disponibili le seguenti aree geografiche: regione di segmentazione geografica, geosegmentazione US DMA e GeoSegmentation City.
   * Per le due dimensioni secondarie, utilizzare i dati aggiuntivi preferiti che si desidera visualizzare per il traffico. Le dimensioni secondarie non devono essere specifiche per la posizione.
3. Fai clic su [!UICONTROL Save and View Report].

## Origini di traffico in tempo reale

Le origini del traffico in tempo reale indicano da dove sono arrivati i visitatori durante la visita del sito al momento attuale. Per configurare uno dei tre rapporti in tempo reale per visualizzare i dati delle origini di traffico:

1. Fai clic su &quot;Configura&quot; vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denominate il rapporto in tempo reale; ad esempio, &quot;Sorgenti di traffico&quot;.
   * Le istanze vengono in genere utilizzate come metrica. Al momento, Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per la dimensione primaria viene in genere utilizzato il dominio di riferimento. Sono disponibili anche Motore di ricerca e Parola chiave di ricerca.
   * Per le due dimensioni secondarie, utilizzare i dati aggiuntivi preferiti che si desidera visualizzare per il traffico. Le dimensioni secondarie non devono essere specifiche per le origini di traffico.
3. Fai clic su [!UICONTROL Save and View Report].

## Contenuto in tempo reale

Il contenuto in tempo reale indica le pagine che i visitatori visualizzano attualmente. Per configurare uno dei tre rapporti in tempo reale per visualizzare i dati dei contenuti:

1. Fate clic [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denominate il rapporto in tempo reale; ad esempio, &quot;Content&quot;.
   * Le istanze vengono in genere utilizzate come metrica. Al momento, Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per Dimensione principale, la pagina viene in genere utilizzata. Site Section e Server sono disponibili anche se l’implementazione definisce queste variabili.
   * Per le due dimensioni secondarie, utilizzare i dati aggiuntivi preferiti che si desidera visualizzare per il traffico. Le dimensioni secondarie non devono essere specifiche per il contenuto.
3. Fai clic su [!UICONTROL Save and View Report].

## Eventi in tempo reale

Gli eventi in tempo reale indicano quali eventi si verificano di più sul sito. In Google  Analytics, un evento cattura il numero di volte in cui si è verificata un&#39;azione specifica (in genere un&#39;azione non correlata a una visualizzazione di pagina). Gli eventi GA vengono inviati con Categoria, Etichetta e Azione. In Adobe  Analytics, gli eventi personalizzati sono metriche alle quali vengono assegnati nomi descrittivi nella console di amministrazione e che possono essere analizzate insieme a qualsiasi dimensione. Se cerchi una dimensione in Adobe  Analytics simile agli eventi di Google  Analytics, puoi prendere in considerazione l’applicazione della dimensione Collegamento personalizzato, spesso utilizzata come elemento catch-all per la raccolta di dati non correlati alle visualizzazioni di pagina (oltre a Collegamenti di uscita - per le uscite - e Collegamenti di download - per i download).

>[!NOTE]
>
>Quando si utilizzano eventi personalizzati nei rapporti in tempo reale, l&#39;elemento dimensione deve essere definito nello stesso hit dell&#39;evento personalizzato. Ad esempio, se visualizzi un evento personalizzato &#39;Registrazioni&#39; per la dimensione &#39;Dominio di riferimento&#39;, nessun dato verrà restituito senza un&#39;implementazione aggiuntiva. Poiché il dominio di riferimento viene visualizzato solo sul primo hit e un evento personalizzato viene generalmente visualizzato più avanti nella visita, i dati non possono essere associati in rapporti in tempo reale. Questi dati sono disponibili utilizzando  Analysis Workspace con latenza di elaborazione standard, che in genere è di 30-90 minuti.

## Conversioni in tempo reale

Le conversioni in tempo reale presentano i dati in modo diverso tra le piattaforme. Gli obiettivi in Google  Analytics sono simili alle metriche e agli eventi di successo in Adobe  Analytics. Puoi utilizzare la maggior parte delle metriche in Adobe  Analytics (sia metriche personalizzate come eventi di successo che metriche standard come le entrate) in Real Time Reports. Come per Google  Analytics, puoi anche applicare dimensioni come il nome del prodotto, il codice di tracciamento e le prestazioni della campagna nei report in tempo reale.

1. Fate clic [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denominate il rapporto in tempo reale; ad esempio, &quot;Conversioni&quot;.
   * Le istanze vengono in genere utilizzate come metrica. Al momento, Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per la dimensione primaria, viene in genere utilizzato il codice di tracciamento. La dimensione Prodotti è disponibile anche se utilizzata dall’implementazione.
   * Per le due dimensioni secondarie, utilizzare i dati aggiuntivi preferiti che si desidera visualizzare per il traffico. Le dimensioni secondarie non devono essere specifiche per le conversioni.
3. Fai clic su [!UICONTROL Save and View Report].

>[!NOTE]
>
>Se si utilizzano eventi esterni a Istanze, ad esempio Ordini, assicurarsi che l&#39;implementazione definisca la dimensione e l&#39;evento sullo stesso hit. Se dimensioni ed eventi non vengono attivati sullo stesso hit, tali dati sono disponibili in  Analysis Workspace utilizzando la latenza di elaborazione standard, che in genere è di 30-90 minuti.
