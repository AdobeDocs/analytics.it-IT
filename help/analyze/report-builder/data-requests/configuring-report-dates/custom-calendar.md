---
description: Report Builder utilizza il calendario personalizzato di Analytics. È possibile utilizzare il calendario per definire il primo giorno della settimana e dell'anno oppure utilizzare un diverso stile di calendario per la vendita al dettaglio. I formati calendario vengono utilizzati per vari scopi, tra cui il confronto delle vendite e la standardizzazione delle previsioni, l'analisi dei costi del ciclo paghe o la regolamentazione del conteggio delle scorte fisiche.
title: Calendario personalizzato
uuid: 88d24bf9-de46-41e0-937e-b8a1fe36c55d
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---

# Calendario personalizzato

Report Builder utilizza il calendario personalizzato di Analytics. È possibile utilizzare il calendario per definire il primo giorno della settimana e dell&#39;anno oppure utilizzare un diverso stile di calendario per la vendita al dettaglio. I formati calendario vengono utilizzati per vari scopi, tra cui il confronto delle vendite e la standardizzazione delle previsioni, l&#39;analisi dei costi del ciclo paghe o la regolamentazione del conteggio delle scorte fisiche.

Di seguito sono descritti tutti i formati del calendario.

<table id="table_E609632569EB499184E56618C2CEF742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Calendario </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Calendario gregoriano </p> </td> 
   <td colname="col2"> <p> Utilizza il formato calendario tradizionale (da gennaio a dicembre, con 30 o 31 giorni e un numero variabile di settimane in ogni mese). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario gregoriano modificato </p> </td> 
   <td colname="col2"> <p> Utilizza il Calendario gregoriano tradizionale ma ti consente di selezionare il primo mese dell'anno e il primo giorno della settimana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario Retail 4-5-4 </p> </td> 
   <td colname="col2"> <p> Scomposizione mensile per numero di settimane nel mese. Ciò significa che gennaio ha quattro settimane, e così via. La Federazione nazionale del commercio al dettaglio utilizza il formato calendario 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario personalizzato </p> </td> 
   <td colname="col2"> <p> Offre tre formati in base al numero di settimane in ogni mese. Il numero di settimane in ogni mese dipende dal primo giorno dell’anno selezionato. </p> <p>Un anno ha 52 settimane. Dividetelo in 4 quarti e ottenete 13 settimane al trimestre. Ma ci sono 3 mesi in un trimestre. 13 non è divisibile per tre quindi si finisce per mettere la settimana extra in uno dei mesi in modo che è sempre coerente. 5/4/4 significa che il primo mese del trimestre ha la settimana supplementare. 4/5/4 significa che il secondo mese ha la settimana supplementare, ecc. Nel calendario 5-4-4, la 53a settimana viene aggiunta all'ultimo trimestre dell'anno. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>: gennaio ha quattro settimane, febbraio ha cinque settimane, marzo ha quattro settimane, e così via. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: Gennaio ha quattro settimane, Febbraio ha quattro settimane, Marzo ha cinque settimane, e così via. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: Gennaio ha cinque settimane, Febbraio ha cinque settimane, Marzo ha quattro settimane, e così via. </li> 
    </ul> <p>Nota:  Questa opzione del calendario è supportata in tutti gli strumenti di Adobe Analytics (Analysis Workspace, Reports &amp; Analytics, Report Builder e Activity Map). L'eccezione è Data Warehouse, che non supporta i calendari personalizzati. </p> </td> 
  </tr> 
 </tbody> 
</table>
