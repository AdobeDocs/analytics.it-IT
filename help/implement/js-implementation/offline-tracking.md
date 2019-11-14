---
description: Le seguenti variabili e funzioni consentono di memorizzare le chiamate di misurazione quando l’applicazione è offline.
keywords: Analytics Implementation
solution: Analytics
title: Tracciamento offline
topic: Developer and implementation
uuid: f7c55aef-28a4-4f2f-8f47-792a05f9525b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tracciamento offline

Le seguenti variabili e funzioni consentono di memorizzare le chiamate di misurazione quando l’applicazione è offline.

> [!NOTE] Per abilitare il tracciamento offline, le marche temporali devono essere abilitate nella suite di rapporti. Se le marche temporali sono abilitate nella suite di rapporti, la proprietà di configurazione `trackOffline` *deve* essere true. Se le marche temporali non sono abilitate nella suite di rapporti, la proprietà di configurazione `trackOffline` *deve* essere false. Se questo non viene configurato correttamente, i dati andranno perduti. Se non sei sicuro se le marche temporali sono abilitate o meno nella suite di rapporti, [contattare l’assistenza clienti](https://helpx.adobe.com/contact/enterprise-support.ec.html#analytics)

Quando abilitata, AppMeasurement offline si comporta come segue:

* L'applicazione invia una chiamata al server, ma la trasmissione dei dati non riesce.
* AppMeasurement genera un timestamp per l’hit corrente.
* AppMeasurement esegue il buffer dei dati hit ed effettua il backup dei dati hit nel buffer allo storage permanente per evitare la perdita di dati.

Ad ogni hit successivo, o all’intervallo definito da `offlineThrottleDelay`, AppMeasurement tenta di inviare i dati dell’hit nel buffer, mantenendo l’ordine di hit originale. Se la trasmissione dei dati ha esito negativo, continua a bufferizzare i dati di hit (questa operazione continua mentre il dispositivo è offline).

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
    <code class="syntax c">
      s.trackOffline=true; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineLimit </p> </td> 
   <td colname="col2"> <p> Predefinito: nessun limite </p> <p>Numero massimo di hit offline memorizzati nella coda. </p> <p> <b>Esempi:</b> </p> 
    <code class="syntax c">
      s.offlineHitLimit=100; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>offlineThrottleDelay </p> </td> 
   <td colname="col2"> <p>Impostazione predefinita: 0 </p> <p>Specifica una cadenza (o ritardo), in millisecondi, per l'invio di dati di hit nel buffer quando AppMeasurement rileva una connessione di rete attiva. In questo modo si riduce l'impatto sulle prestazioni dell'invio di più hit sull'applicazione. </p> <p>Ad esempio, se offlineThrottleDelay=1000 e l’invio dei dati dell’hit richiede 300 ms, AppMeasurement attende 700 ms prima dell’invio dell’hit del buffer successivo. </p> 
    <code class="syntax c">
      s.offlineThrottleDelay=1000; 
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceOnline </p> <p>forceOffline </p> </td> 
   <td colname="col2"> <p>  Impostare manualmente lo stato online o offline dell'oggetto di misura. La libreria rileva automaticamente quando il dispositivo è offline o online, pertanto questi metodi sono necessari solo se si desidera forzare la misurazione offline. <code> forceOnline </code> viene utilizzato solo per tornare allo stato online dopo essere stato disconnesso manualmente. </p> <p>Quando la misurazione è offline: </p> 
    <ul id="ul_5A9CFD2968F64F938652C1D779EB7589"> 
     <li id="li_AF074C55DFED4DC8BD8CF3D25805040C"> Se <code> trackOffline </code> è vero: gli hit vengono memorizzati finché la misurazione non è online. </li> 
     <li id="li_6A623377462548DB97C31654EADCFAF3"> Se <code> trackOffline </code> è false: gli hit vengono scartati. </li> 
    </ul> <p> <b>Esempi:</b> </p> 
    

s.forceOnline();
</code> </td>
</tr> 
 </tbody> 
</table>
