---
description: Le seguenti variabili e funzioni consentono di memorizzare chiamate di misurazione quando l'applicazione è offline.
keywords: Implementazione di Analytics
seo-description: Le seguenti variabili e funzioni consentono di memorizzare chiamate di misurazione quando l'applicazione è offline.
seo-title: Tracciamento offline
solution: Analytics
title: Tracciamento offline
topic: Sviluppatore e implementazione
uuid: f 7 c 55 aef -28 a 4-4 f 2 f -8 f 47-792 a 05 f 9525 b
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Tracciamento offline

Le seguenti variabili e funzioni consentono di memorizzare chiamate di misurazione quando l'applicazione è offline.

>[!NOTE]
>
>Per abilitare il tracciamento offline, è necessario abilitare le marche temporali nella suite di rapporti. If timestamps are enabled on your report suite, your `trackOffline` configuration property *must* be true. Se le marche temporali non sono abilitate nella suite di rapporti, la proprietà di configurazione `trackOffline` *deve* essere false. Se questo non viene configurato correttamente, i dati andranno perduti. Se non sei sicuro se le marche temporali sono abilitate o meno nella suite di rapporti, [contattare l’assistenza clienti](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

Quando abilitata, appmeasurement si comporta come segue:

* L'applicazione invia una chiamata al server, ma la trasmissione dati non riesce.
* Appmeasurement genera un timestamp per l'hit corrente.
* Appmeasurement buffer i dati di hit ed eseguono il backup dei dati di hit con bufferizzazione fino a memorizzazione persistente per evitare la perdita di dati.

At each subsequent hit, or at the interval defined by `offlineThrottleDelay`, AppMeasurement attempts to send the buffered hit data, maintaining the original hit order. Se la trasmissione dati non riesce, continua a bufferizzare i dati hit (questa continua mentre il dispositivo è offline).

<table id="table_E8FD8C89025C4E819FE2FEBC7A78984D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Proprietà o metodo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>trackOffline </p> </td> 
   <td colname="col2"> <p>Valore predefinito: false. </p> <p>Abilita o disabilita il tracciamento offline per la libreria delle misurazioni. </p> <p> <b>Esempi:</b> </p> 
    <code class="syntax c">s. trackoffline = true; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p>Predefinito: nessun limite </p> <p>Numero massimo di hit offline memorizzati nella coda. </p> <p> <b>Esempi:</b> </p> 
    <code class="syntax c">s. offlinehitlimit = 100; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Offlinethrottledelay </p> </td> 
   <td colname="col2"> <p>Impostazione predefinita: 0 </p> <p>Specifica una cadenza (o ritardo), in millisecondi, per l'invio di dati hit bufferizzati quando appmeasurement rileva una connessione di rete attiva. Ciò limita l'impatto sulle prestazioni dell'invio di più hit nell'applicazione. </p> <p>Ad esempio, se offlinethrottledelay = 1000 e sono necessari 300 ms per inviare i dati hit, appmeasurement attende 700 ms prima di inviare il successivo hit bufferizzato. </p> 
    <code class="syntax c">s. offlinethrottledelay = 1000; </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p> Imposta manualmente lo stato online o offline dell'oggetto di misurazione. La libreria rileva automaticamente quando il dispositivo è offline o online, quindi questi metodi sono necessari solo se desiderate forzare la misurazione offline. <code> Forceonline </code> viene utilizzato solo per tornare allo stato online dopo che sono stati manualmente offline. </p> <p>Quando la misurazione è offline: </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> If <code> trackOffline </code> is true: hits are stored until measurement is online. </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> If <code> trackOffline </code> is false: hits are discarded. </li> 
    </ul> <p> <b>Esempi:</b> </p> 
    <code class="syntax c">s. forceoffline ();

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
