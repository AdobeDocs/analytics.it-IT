---
title: Rapporti in tempo reale in Adobe Analytics
description: Scopri come creare rapporti in tempo reale in Adobe Analytics rivolti agli utenti che hanno più familiarità con le Google Analytics.
feature: Third-party Integration
exl-id: 0ca27992-fff8-4bb4-8582-31fd401b23f6
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 0%

---

# Rapporti in tempo reale

I rapporti in tempo reale mostrano cosa sta succedendo sul tuo sito in questo momento. Questi tipi di rapporti sono particolarmente utili per visualizzare i risultati immediati degli aggiornamenti apportati al sito. Ad esempio, un&#39;azienda che esegue una vendita su Black Friday può misurare il traffico verso pagine specifiche e determinare quali vendite dare priorità in base alle prestazioni in quel momento.

![Rapporto in tempo reale](/help/technotes/ga-to-aa/assets/realtime.png)

I rapporti in tempo reale sono una delle poche funzionalità che non sono ancora state introdotte in Analysis Workspace. Utilizza Reports &amp; Analytics per ottenere questi dati. Richiedono una configurazione semplice per iniziare a raccogliere i dati.

Per raggiungere la pagina di configurazione del rapporto in tempo reale (sono necessarie le autorizzazioni di amministrazione):

1. Fai clic su [!UICONTROL Reports] nella navigazione dell’intestazione Adobe Analytics.
2. Nel menu a sinistra, fai clic su *[!UICONTROL Site Metrics]* > *[!UICONTROL Real-Time]*.
3. Se la suite di rapporti non è ancora abilitata in tempo reale, viene visualizzato un messaggio con un collegamento per configurare la suite di rapporti. Se la suite di rapporti è abilitata in tempo reale, fai clic su [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.

L’Adobe consente fino a tre rapporti in tempo reale per raccogliere i dati simultaneamente. Devono essere configurate prima di iniziare a raccogliere i dati in tempo reale.

![Configurazione rapporti in tempo reale](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Posizioni in tempo reale

Le posizioni in tempo reale indicano dove risiedono i visitatori quando visitano il tuo sito al momento attuale. Per configurare uno dei tre rapporti in tempo reale in modo da visualizzare i dati relativi alla posizione:

1. Fai clic su [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denomina il rapporto in tempo reale; ad esempio, &quot;Posizioni&quot;.
   * Le istanze vengono generalmente utilizzate come metrica. Al momento i rapporti Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per il Dimension primario, viene in genere utilizzato il campo Paese di geosegmentazione. Sono disponibili anche le aree geografiche di geosegmentazione, GeoSegmentation US DMA e GeoSegmentation City.
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti da visualizzare per questo traffico. Le dimensioni secondarie non devono essere specifiche per la posizione.
3. Fai clic su [!UICONTROL Save and View Report].

## Origini del traffico in tempo reale

Fonti di traffico in tempo reale indicano da dove provengono i visitatori che visitano il tuo sito al momento attuale. Per configurare uno dei tre rapporti in tempo reale in modo da visualizzare i dati delle origini di traffico:

1. Fai clic su &quot;Configura&quot; vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denomina il rapporto in tempo reale; ad esempio, &quot;Origini del traffico&quot;.
   * Le istanze vengono generalmente utilizzate come metrica. Al momento i rapporti Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per il Dimension primario, il dominio di riferimento viene in genere utilizzato. Sono disponibili anche i motori di ricerca e le parole chiave di ricerca.
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti da visualizzare per questo traffico. Le dimensioni secondarie non devono essere specifiche per le origini di traffico.
3. Fai clic su [!UICONTROL Save and View Report].

## Contenuto in tempo reale

Il contenuto in tempo reale indica le pagine che i visitatori visualizzano attualmente. Per configurare uno dei tre rapporti in tempo reale in modo da visualizzare i dati dei contenuti:

1. Fai clic su [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denomina il rapporto in tempo reale; ad esempio, &quot;Content&quot;.
   * Le istanze vengono generalmente utilizzate come metrica. Al momento i rapporti Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per il Dimension primario, la pagina viene generalmente utilizzata. Se l’implementazione definisce queste variabili, sono disponibili anche la sezione del sito e il server .
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti da visualizzare per questo traffico. Le dimensioni secondarie non devono essere specifiche per il contenuto.
3. Fai clic su [!UICONTROL Save and View Report].

## Eventi in tempo reale

Gli eventi in tempo reale ti dicono quali eventi stanno accadendo di più sul tuo sito. In Google Analytics, un evento acquisisce il numero di volte in cui si è verificata un&#39;azione specifica (in genere un&#39;azione non correlata a una visualizzazione di pagina). Gli eventi GA vengono inviati con una categoria, un’etichetta e un’azione. In Adobe Analytics, gli eventi personalizzati sono metriche a cui vengono assegnati nomi descrittivi in Admin Console e che possono essere analizzate insieme a qualsiasi dimensione. Se cerchi una dimensione in Adobe Analytics simile agli eventi Google Analytics, considera l’applicazione della dimensione Custom Link, che viene spesso utilizzata come elemento catch-all per la raccolta di dati non correlati alle visualizzazioni di pagina (oltre ai collegamenti di uscita - per Uscite - e Download dei collegamenti - per i download).

>[!NOTE]
>
>Quando utilizzi eventi personalizzati nei rapporti in tempo reale, l’elemento dimensione deve essere definito nello stesso hit dell’evento personalizzato. Ad esempio, se visualizzi un evento personalizzato &quot;Registrazioni&quot; per la dimensione &quot;Dominio di riferimento&quot;, non verranno restituiti dati senza ulteriore implementazione. Poiché il dominio di riferimento viene visualizzato solo sul primo risultato e in genere un evento personalizzato viene visualizzato più avanti nella visita, i dati non possono essere associati in rapporti in tempo reale. Questi dati sono disponibili tramite Analysis Workspace utilizzando la latenza di elaborazione standard, che in genere dura 30-90 minuti.

## Conversioni in tempo reale

Le conversioni in tempo reale presentano i dati in modo diverso tra le piattaforme. Gli obiettivi in Google Analytics sono simili alle metriche e agli eventi di successo in Adobe Analytics. Puoi utilizzare la maggior parte delle metriche in Adobe Analytics (sia metriche personalizzate come eventi di successo che metriche standard come le entrate) nei rapporti in tempo reale. Simile a Google Analytics, puoi anche applicare dimensioni come nome del prodotto, codice di tracciamento e prestazioni della campagna nei rapporti in tempo reale.

1. Fai clic su [!UICONTROL Configure] vicino al titolo del rapporto in tempo reale.
2. In uno degli slot per report in tempo reale:
   * Denomina il rapporto in tempo reale; ad esempio, &quot;Conversioni&quot;.
   * Le istanze vengono generalmente utilizzate come metrica. Al momento i rapporti Utenti/Visitatori unici non sono disponibili nei rapporti in tempo reale.
   * Per il Dimension primario, il codice di tracciamento viene generalmente utilizzato. La dimensione Prodotti è disponibile anche se utilizzata dall’implementazione.
   * Per le due dimensioni secondarie, utilizza i dati aggiuntivi preferiti da visualizzare per questo traffico. Le dimensioni secondarie non devono essere specifiche per le conversioni.
3. Fai clic su [!UICONTROL Save and View Report].

>[!NOTE]
>
>Se utilizzi eventi esterni a Istanze, ad esempio Ordini, accertati che l’implementazione definisca la dimensione e l’evento sullo stesso hit. Se dimensioni ed eventi non si attivano sullo stesso hit, tali dati sono disponibili in Analysis Workspace utilizzando la latenza di elaborazione standard, che in genere è di 30-90 minuti.
