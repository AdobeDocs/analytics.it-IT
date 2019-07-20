---
description: Implementa Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded).
keywords: Implementazione di Analytics; html image tag; richiesta immagine hardcoded
seo-description: Implementa Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded).
seo-title: Implementazione di Analytics tramite tag immagine HTML
solution: Analytics
title: Implementazione di Analytics tramite tag immagine HTML
topic: Sviluppatore e implementazione
uuid: 0 c 098 a 57-7 c 71-4362-812 c -36 e 37848 a 5 ae
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementazione di Analytics tramite tag immagine HTML

Implementa Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded).

Il browser quindi richiede l'immagine. I dati si spostano con questa richiesta di immagine tramite variabili nella stringa query della richiesta di immagine. Javascript combina le variabili a livello di browser a variabili a livello di pagina per una soluzione completa di raccolta dati. In alcuni casi, è appropriato un tag immagine creato completamente dal server. Gli elementi standard di un'implementazione basata su javascript sono elencati di seguito:

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> Codice HTML </td> 
   <td> Questa sezione è costituita da codice javascript posizionato in pagine HTML (o modelli) che impostano il valore delle variabili javascript. </td> 
  </tr> 
  <tr> 
   <td> Libreria javascript </td> 
   <td> <p>Questo file contiene codice comune che: </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">Interroga il browser su diverse proprietà, come la versione javascript, la versione del sistema operativo, la dimensione e la risoluzione del monitor utilizzato e altre variabili. </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">Codifica e concatena tutte le variabili in una richiesta di immagine (&lt; img &gt;) che trascina queste variabili nei server di raccolta dati. Quindi fa riferimento a un file libreria javascript caricato ed eseguito. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Tag &lt; noscript &gt; </td> 
   <td> Una versione semplificata della richiesta di immagine viene inserita all'interno di un tag &lt; noscript &gt; che viene eseguito se l'utente ha disabilitato javascript o non dispone delle funzionalità javascript. Questa parte dell'implementazione è facoltativa e generalmente si applica al 2% circa della popolazione Internet. </td> 
  </tr> 
 </tbody> 
</table>

Javascript consente di rilevare le impostazioni del browser non disponibili per un server, ad esempio l'altezza/larghezza della finestra del browser, la risoluzione del monitor e i plug-in Netscape. Utilizzando un metodo lato server per creare un tag immagine, queste variabili non possono essere acquisite. Javascript imposta un numero casuale nella richiesta dell'immagine per superare il caching del browser e del server proxy. In questo modo tutte le visualizzazioni pagina vengono tracciate con precisione. In alcune situazioni, il codice lato server presenta vantaggi rispetto al codice basato su javascript, compresi i seguenti:

* Javascript è molto accurato (98-100 %). Ci sono volte in cui si desiderano più precisione, anche nelle situazioni in cui un utente fa clic rapidamente su un'altra pagina prima che sia eseguito javascript. La creazione del tag lato server aumenta il livello di precisione per diversi punti percentuali.
* Per tenere traccia degli eventi di conversione, ad esempio acquisti, dove la precisione è molto importante.
* Questa strategia può essere utilizzata anche per compilare completamente la richiesta di immagine all'interno della variabile <noscript> per il monitoraggio di utenti senza javascript o con javascript disabilitato.

>[!NOTE]
>
>L'utilizzo dei tag immagine generati dal server richiede un tempo aggiuntivo per l'implementazione ed è più difficile eseguire il debug, la distribuzione e l'aggiornamento. Adobe consiglia vivamente ai client di utilizzare la raccolta dati basata su javascript in ogni pagina, laddove possibile. Vari rapporti e funzioni, inclusi mappa clic visitatore, collegamenti di download, connettori di uscita e variabili basate su browser (larghezza/altezza del browser, ecc.) non può essere raccolto o supportato utilizzando questo metodo di implementazione.

