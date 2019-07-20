---
description: La variabile di conversione personalizzata (o evar) viene inserita nel codice Adobe sulle pagine Web selezionate del sito. Il suo scopo primario è quello di segmentare le metriche di successo conversione nei report di marketing personalizzati. Un evar può essere basato su visite e funziona in modo simile ai cookie. I valori passati nelle variabili evar seguono l'utente per un periodo di tempo predeterminato.
keywords: eVar
seo-description: La variabile di conversione personalizzata (o evar) viene inserita nel codice Adobe sulle pagine Web selezionate del sito. Il suo scopo primario è quello di segmentare le metriche di successo conversione nei report di marketing personalizzati. Un evar può essere basato su visite e funziona in modo simile ai cookie. I valori passati nelle variabili evar seguono l'utente per un periodo di tempo predeterminato.
seo-title: Variabili di conversione (evar)
solution: Analytics
title: Variabili di conversione (evar)
topic: Strumenti di amministrazione
uuid: 1 eed 0 cb 1-0735-4142-be 21-43 f 264216 b 50
translation-type: tm+mt
source-git-commit: 26ea8e41b9a45c87c339d4d4d56c914fbc44bae8

---


# Conversion Variables (Variabili di conversione) (eVars)

La variabile di conversione personalizzata (o evar) viene inserita nel codice Adobe sulle pagine Web selezionate del sito. Il suo scopo primario è quello di segmentare le metriche di successo conversione nei report di marketing personalizzati. Un evar può essere basato su visite e funziona in modo simile ai cookie. I valori passati nelle variabili evar seguono l'utente per un periodo di tempo predeterminato.

Quando un evar è impostato su un valore per un visitatore, Adobe ricorda automaticamente tale valore fino alla scadenza. Tutti gli eventi di successo rilevati da un visitatore mentre il valore evar è attivo vengono conteggiati verso il valore evar.

Le evar sono utilizzate per misurare cause ed effetti, ad esempio:

* Campagne interne influite sui ricavi
* Quali annunci banner hanno generato una registrazione
* Numero di volte in cui è stata utilizzata una ricerca interna prima di effettuare un ordine

Se la misurazione del traffico o i percorsi sono desiderati, si consiglia di utilizzare le variabili di traffico.

>[!NOTE]
>
>In una richiesta di immagine è possibile memorizzare solo un singolo valore. If multiple values are desired in an eVar value, we recommend that you implement [List variables (list vars)](https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html).

## Conversion Variables - Descriptions {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descriptions of fields used when [editing conversion variables](../../../admin/admin/conversion-var-admin/t-conversion-variables-admin.md#task_051920D9B3E24A00A28F32EEBBB0EF97).

<table id="table_E48D50926E6B492183300CA58A886927"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Elemento </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Nome </span> </p> </td> 
   <td colname="col2"> <p>Il nome descrittivo della variabile di conversione. Questo nome è il modo in cui viene fatto riferimento alla evar nel reporting generale, e sarà il nome del report nel menu a sinistra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Tipo</span> </p> <p>(solo evar) </p> </td> 
   <td colname="col2"> <p>Tipo di valore variabile: </p> <p> <b>Stringa di testo</b>:</span> Acquisisce i valori di testo utilizzati sul sito. Questo è il tipo più comune di evar e l'impostazione predefinita. È simile ad altre variabili, in cui il valore al suo interno è una stringa di testo statica. Se si monitora elementi quali campagne interne o parole chiave di ricerca interna, questa è l'impostazione consigliata. </p> <p> <b>Contatore</b>:</span> Conta il numero di volte in cui un'azione si verifica prima dell'evento success. For example, if you use an eVar to track internal searches on your site, set this value to <span class="uicontrol"> Text String</span> to track the use of search terms. Set this value to <span class="uicontrol"> Counter</span> to count the number of searches made, regardless of search terms used. Ad esempio, puoi utilizzare un contatore per tenere traccia del numero di volte in cui qualcuno ha utilizzato la ricerca interna prima di effettuare un acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Allocazione </span> </p> </td> 
   <td colname="col2"> <p>Determina in che modo Analytics assegna credito per un evento di successo se una variabile riceve più valori prima dell'evento. I valori supportati includono: </p> <p> <b>Più recente</b>: L'ultimo valore evar riceve sempre credito per gli eventi di successo fino alla scadenza dell'evar. </p> <p> <b>Valore originale</b>: La prima evar riceve sempre credito per eventi di successo fino alla scadenza dell'evar. </p> <p> <b> Lineare</b>: Alloca gli eventi di successo in modo uniforme su tutti i valori evar. Dato che l'allocazione lineare distribuisce con precisione i valori solo all'interno di una visita, usa l'allocazione lineare con una scadenza evar di visita. </p> <p>Nota: Se si passa da una visualizzazione all'altra o da Lineare, i dati storici non vengono visualizzati. I tipi di allocazione misti nell'interfaccia di reporting possono portare a dati erronei nei report. Ad esempio, l'allocazione lineare potrebbe dividere le entrate su diversi valori evar. Dopo essere tornati all'allocazione Più recente, il 100% delle entrate risulterebbe associato al singolo valore più recente. Questa associazione può portare a conclusioni errate da parte degli utenti. </p> <p>Per evitare la probabilità di confusione nei rapporti, Analytics rende i dati storici non disponibili all'interfaccia. Può essere visualizzato se decidi di posticipare l'impostazione evar all'impostazione di allocazione iniziale, anche se non dovresti modificare le impostazioni di allocazione evar semplicemente per accedere ai dati storici. Adobe consiglia di utilizzare una nuova evar quando sono desiderate nuove impostazioni di allocazione per i dati già in fase di registrazione, piuttosto che modificare le impostazioni di allocazione su un evar che hanno già una quantità significativa di dati storici generati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Scade dopo</span> </p> </td> 
   <td colname="col2"> <p>Specifica un periodo di tempo, o un evento, dopo la scadenza del valore evar (non ricevono più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza evar, il valore None non riceve credito per l'evento (nessuna evar è attiva). </p> <p>Se selezionate un evento come valore di scadenza, la variabile scade solo se si verifica l'evento. Se l'evento non si verifica, la variabile non scade. </p> <p>Le opzioni di scadenza disponibili possono essere classificate in quattro categorie principali: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>A una visualizzazione pagina o a un livello di visita.</b> Gli eventi di conversione oltre la visualizzazione della pagina o la visita non sono associati alla evar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>In base a un periodo di tempo, ad esempio giorno, settimana, mese o anno.</b> Gli eventi di conversione oltre il periodo di tempo specificato non sono associati alla evar. Il periodo di scadenza inizia quando la variabile viene impostata. Le evar scadono in base all'ora in cui sono state impostate, al secondo (minuto, ora, giorno, mese, ecc.): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTO = 60 secondi </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">ORA = 3600 secondi (60 minuti) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DAY = 86400 secondi (24 ore) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">WEEK = 604800 secondi (7 giorni) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MESE = 2678400 secondi (31 giorni) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">TRIMESTRE = 8035200 secondi (93 giorni - 3 mesi di 31 giorni) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">ANNO = 31536000 secondi (365 giorni) </li> 
      </ul> <p> </p> <p>Se una visita inizia dalle 7:00 di lunedì e una evar viene impostata all'interno di quel visitatore alle 7:15, la scadenza è come mostrato di seguito: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Scadenza giorno: Evar scade alle 7:15 di martedì. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Scadenza settimana: Evar scade il lunedì alle 7:15 di domenica. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Scadenza mese: Evar scade 31 giorni a partire da lunedì alle 7:15. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>Eventi di conversione specifici.</b> Qualsiasi altro evento di conversione che viene attivato dopo l'evento specifico associato alla evar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Mai.</b> Fintanto che il cookie <span class="varname"> visitorid</span> è intatto, qualsiasi quantità di tempo può passare tra evar e event. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Stato</span> </p> <p>(solo evar) </p> </td> 
   <td colname="col2"> <p>Definisce lo stato evar: </p> <p><b>Disattivato</b>:</span> Disabilita la evar. Rimuove la evar dall'elenco delle variabili di conversione. </p> <p> <b>Nessuna sottorelazione</b>:</span> Impedisce di suddividere la evar con una relazione secondaria. </p> <p> <b>Sottorelazioni di base</b>: </span>Consente di suddividere una evar in qualsiasi rapporto con sottorelazioni complete (ad esempio, Prodotti o Campaign). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Reset</span> </p> </td> 
   <td colname="col2"> <p>Ripristina qualsiasi valore esistente nella evar. </p> <p>Utilizzate questa impostazione quando rimuovete un evar in modo da combinare un vecchio valore in un nuovo report. La reimpostazione non cancella i dati storici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Merchandising</span> </p> <p>(solo evar) </p> </td> 
   <td colname="col2"> <p>Le variabili merchandising possono seguire una delle due sintassi: </p> <p> <b>Sintassi prodotti</b>:</span> Associa il valore evar a un prodotto. Nota: Se è selezionata l'opzione Sintassi prodotti, la sezione Merchandising Binding Event (Evento di associazione merchandising) è disabilitata e non selezionabile per la modifica. Per questa sintassi, gli Eventi di binding non sono applicabili. </p> </p> <p> <b>Sintassi variabile conversione</b>:</span> Associa la evar a un prodotto solo se si verifica un evento binding. In questo caso, si seleziona gli eventi che fungono da Eventi binding. </p> <p>La modifica di questa impostazione senza aggiornare il codice javascript causa la perdita di dati. See <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=var_merchandising" format="http" scope="external"> Merchandising Variables</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Evento di associazione merchandising</span> </p> <p>(solo evar) </p> </td> 
   <td colname="col2"> <p>If Merchandising is set to <span class="uicontrol"> Conversion Variable Syntax</span>, the selected events bind the current eVar value with a product. </p> <p>To use a Binding Event, set <span class="uicontrol"> Allocation to Most Recent</span>. <span class="uicontrol"> Se Allocazione è un valore originale</span>, il primo binding del prodotto evar resta attivo fino alla scadenza della evar. </p> </td> 
  </tr> 
 </tbody> 
</table>