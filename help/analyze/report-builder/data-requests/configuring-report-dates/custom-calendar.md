---
description: Report Builder utilizza il calendario personalizzato di Analytics. Puoi utilizzare il calendario per definire il primo giorno della settimana e dell’anno oppure utilizzare un diverso stile di calendario per la vendita al dettaglio. I formati del calendario vengono utilizzati per vari scopi, tra cui il confronto delle vendite e la standardizzazione delle previsioni, l’analisi dei costi del ciclo paghe o la regolamentazione del conteggio dell’inventario fisico.
title: Calendario personalizzato
feature: Report Builder
role: User, Admin
exl-id: e65cb6c8-8bb0-4dcd-a3a3-d22adcd024fa
source-git-commit: 244af34b463ea5df55eaca31f3b2df4ada552b5d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 55%

---

# Calendario personalizzato

Report Builder utilizza il calendario personalizzato di Analytics. Puoi utilizzare il calendario per definire il primo giorno della settimana e dell’anno oppure utilizzare un diverso stile di calendario per la vendita al dettaglio. I formati del calendario vengono utilizzati per vari scopi, tra cui il confronto delle vendite e la standardizzazione delle previsioni, l’analisi dei costi del ciclo paghe o la regolamentazione del conteggio dell’inventario fisico.

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
   <td colname="col2"> <p> Utilizza il formato tradizionale del calendario (da gennaio a dicembre, con 30 o 31 giorni e un numero variabile di settimane in ogni mese). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario gregoriano modificato </p> </td> 
   <td colname="col2"> <p> Utilizza il calendario gregoriano tradizionale ma consente di selezionare il primo mese dell’anno e il primo giorno della settimana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario 4-5-4 per vendita al dettaglio </p> </td> 
   <td colname="col2"> <p> Raggruppa ogni mese in base al numero di settimane nel mese. Ciò significa che gennaio ha quattro settimane e così via. La Federazione nazionale del commercio al dettaglio utilizza il formato di calendario 4-5-4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario personalizzato </p> </td> 
   <td colname="col2"> <p> Offre tre formati in base al numero di settimane in ogni mese. Il numero di settimane in ogni mese dipende dal primo giorno dell’anno selezionato. </p> <p>Un anno ha 52 settimane. Dividilo in 4 trimestri e ottieni 13 settimane al trimestre. Ma ci sono 3 mesi in un trimestre. 13 non è divisibile per tre quindi si finisce per inserire la settimana aggiuntiva in uno dei mesi in modo che sia sempre coerente. 5-4-4 significa che il primo mese del trimestre contiene una settimana supplementare. 4-5-4 significa che il secondo mese contiene la settimana supplementare e così via. Nel calendario 5-4-4, la 53a settimana viene aggiunta all’ultimo trimestre dell’anno. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>:gennaio ha quattro settimane, febbraio ha cinque settimane, marzo ha quattro settimane e così via. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: gennaio ha quattro settimane, febbraio ha quattro settimane, marzo ha cinque settimane e così via. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-5-4</b>: gennaio ha cinque settimane, febbraio ha cinque settimane, marzo ha quattro settimane e così via. </li> 
    </ul> <p>Nota: questa opzione del calendario è supportata in tutti gli strumenti di Adobe Analytics: Analysis Workspace, Report Builder e Activity Map. L'eccezione è Data Warehouse, che non supporta i calendari personalizzati. </p> </td> 
  </tr> 
 </tbody> 
</table>
