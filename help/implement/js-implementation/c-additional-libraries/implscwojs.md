---
description: Implementate Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded).
keywords: Analytics Implementation;html image tag;hardcoded image request
seo-description: Implementate Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded).
seo-title: Implementazione di Analytics tramite tag immagine HTML
solution: Analytics
title: Implementazione di Analytics tramite tag immagine HTML
topic: Sviluppatore e implementazione
uuid: 0c098a57-7c71-4362-812c-36e37848a5ae
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Implementazione di Analytics tramite tag immagine HTML

Implementate Analytics utilizzando un tag immagine HTML (richiesta immagine hardcoded).

Il browser richiede quindi l’immagine. I dati si spostano con questa richiesta di immagine tramite variabili nella stringa di query della richiesta di immagine. JavaScript combina variabili a livello di browser con variabili a livello di pagina per una soluzione completa di raccolta dati. In alcuni casi, è appropriato un tag immagine creato completamente dal server. Gli elementi standard di un'implementazione basata su JavaScript sono elencati di seguito:

<table id="table_20BBE4387F234CF199E6C99741AF265C"> 
 <tbody> 
  <tr> 
   <td> Codice HTML </td> 
   <td> Questa parte è costituita dal codice JavaScript inserito in pagine HTML (o modelli) che impostano il valore delle variabili JavaScript. </td> 
  </tr> 
  <tr> 
   <td> Libreria JavaScript </td> 
   <td> <p>Questo file contiene codice comune che: </p> 
    <ul id="ul_ED50D66F2B2B476E8D9063099995998D"> 
     <li id="li_E88F6F28EC8946469ADCEAFF2F0A4EBA">Interroga il browser su diverse proprietà, come la versione JavaScript, il sistema operativo, la dimensione e la risoluzione del monitor in uso e altre variabili </li> 
     <li id="li_5CEBE37709D943B7921447FA7054A565">Codifica e concatena tutte le variabili in una richiesta di immagine (&lt;img&gt;) che trasporta queste variabili ai server di raccolta dati. Quindi fa riferimento a un file libreria JavaScript caricato ed eseguito. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td> Tag &lt;noscript&gt; </td> 
   <td> Una versione semplificata della richiesta di immagine viene inserita all'interno di un tag &lt;noscript&gt; che viene eseguito se l'utente ha disabilitato JavaScript o non dispone di funzionalità JavaScript. Questa parte dell'implementazione è facoltativa e si applica generalmente a circa il 2% della popolazione Internet. </td> 
  </tr> 
 </tbody> 
</table>

JavaScript è in grado di rilevare le impostazioni del browser che non sono disponibili per un server, ad esempio altezza/larghezza della finestra del browser, risoluzione del monitor e plug-in Netscape. Non è possibile acquisire queste variabili utilizzando un metodo lato server per creare un tag immagine. JavaScript imposta un numero casuale nella richiesta di immagine per superare il caching del browser e del server proxy. Questo consente di tenere traccia con precisione di tutte le visualizzazioni di pagina. In alcune situazioni, il codice lato server presenta vantaggi rispetto al codice basato su JavaScript, tra cui:

* JavaScript è molto accurato (98-100%). In alcuni casi, la massima precisione è desiderata, anche in situazioni in cui l'utente fa clic rapidamente su un'altra pagina prima dell'esecuzione di JavaScript. La creazione del server tag immagine aumenta il livello di precisione di diversi punti percentuali.
* Per tenere traccia degli eventi di conversione, come gli acquisti, dove la precisione è molto importante.
* Questa strategia può essere utilizzata anche per compilare completamente la richiesta di immagini nel pannello <noscript> per tenere traccia degli utenti senza JavaScript o con JavaScript disattivato.

> [!NOTE] L’utilizzo di tag immagine generati dal server richiede un tempo aggiuntivo per l’implementazione ed è più difficile da eseguire per il debug, la distribuzione e la manutenzione. Adobe incoraggia vivamente i client a utilizzare, ove possibile, la raccolta di dati basata su JavaScript in ogni pagina. Vari rapporti e funzionalità, tra cui mappa clic del visitatore, collegamenti per il download, collegamenti di uscita e variabili basate su browser (larghezza/altezza del browser, ecc.) non può essere raccolto o supportato utilizzando questo metodo di implementazione.

