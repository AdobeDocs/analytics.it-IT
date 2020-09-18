---
description: Opzioni di calendario diverse dal modello gregoriano. Le opzioni includono i modelli di calendario 4-4-5, 4-5-4 e 5-4-4, tutti utilizzati come standard per il settore retail. Inoltre, il reporting offre un'opzione per un calendario completamente personalizzabile che è possibile configurare autonomamente.
title: Personalizza calendario
topic: Admin tools
uuid: 4e5e538b-54c9-4c2f-8b6c-9f91b6c7bcc7
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---


# Personalizza calendario

Opzioni di calendario diverse dal modello gregoriano. Le opzioni includono i modelli di calendario 4-4-5, 4-5-4 e 5-4-4, tutti utilizzati come standard per il settore retail. Inoltre, il reporting offre un&#39;opzione per un calendario completamente personalizzabile che è possibile configurare autonomamente.

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Customize Calendar]**

>[!CAUTION]
>
>Modificando il calendario si modifica il modo in cui i dati vengono elaborati (ovvero la definizione di visitatori univoci settimanali e mensili). Quando la definizione di un calendario di settimane e mesi cambia, i dati storici non vengono modificati. Questa impostazione interessa anche i segmenti basati su intervalli di date.

Potete utilizzare il calendario per definire il primo giorno della settimana e dell&#39;anno, oppure utilizzare un diverso stile di calendario per la vendita al dettaglio. I formati del calendario sono utilizzati per vari scopi, tra cui il confronto delle vendite e la standardizzazione delle previsioni, l&#39;analisi dei costi del ciclo paghe o la regolamentazione del conteggio delle scorte fisiche. Ad esempio, il settore retail utilizza il calendario contabile 4-5-4 per supportare la particolare stagione di vendita per il settore retail. Ciascuno dei formati di calendario è descritto di seguito.

## Personalizzare le descrizioni del calendario {#section_B0D224DACB914A378902A4E0E1234889}

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
   <td colname="col2"> <p> Utilizza il Calendario gregoriano tradizionale, ma consente di selezionare il primo mese dell'anno e il primo giorno della settimana. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>4-5-4 Retail Calendar </p> </td> 
   <td colname="col2"> <p> Scomposizione mensile per numero di settimane nel mese. Cioè, gennaio ha quattro settimane, e così via. La Federazione Nazionale Retail utilizza il formato 4-5-4 del calendario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Calendario personalizzato </p> </td> 
   <td colname="col2"> <p> Offre tre formati in base al numero di settimane in ogni mese. Il numero di settimane in ogni mese dipende dal primo giorno dell'anno selezionato. </p> <p>Un anno ha 52 settimane. Dividetelo in 4 quarti e ottenete 13 settimane al trimestre. Ma ci sono 3 mesi in un trimestre. 13 non è divisibile per tre quindi si finisce per mettere la settimana supplementare in uno dei mesi in modo che sia sempre coerente. 5/4/4 significa che il primo mese del trimestre contiene la settimana supplementare. 4/5/4 significa che il secondo mese ha la settimana supplementare, ecc. Nel calendario 5-4-4, la 53a settimana è aggiunta all'ultimo trimestre dell'anno. </p> 
    <ul id="ul_1579FD106A47419486B03E248A5E6ED5"> 
     <li id="li_E9B9E8F03E324DBDA9139C2D0D599092"><b>4-5-4</b>:gennaio ha quattro settimane, febbraio ha cinque settimane, marzo ha quattro settimane, e così via. </li> 
     <li id="li_D0675DBDEC4641D2A8645B5CDFC565AB"><b>4-4-5</b>: Gennaio ha quattro settimane, Febbraio ha quattro settimane, Marzo ha cinque settimane, e così via. </li> 
     <li id="li_6743BBB9AC9A4CFEAA0CBCE51052BC29"><b>5-4-4</b>: Gennaio ha cinque settimane, Febbraio ha quattro settimane, Marzo ha quattro settimane, e così via. </li> 
    </ul> <p>Nota:  Questa opzione di calendario è supportata in tutti  strumenti Adobe Analytics ( Analysis Workspace, Reporting e analisi, Report Builder,  Activity Map,  Ad Hoc Analysis) tranne che per Data Warehouse, che non supporta i calendari personalizzati. </p> </td> 
  </tr> 
 </tbody> 
</table>

