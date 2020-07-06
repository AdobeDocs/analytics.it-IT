---
description: La variabile di conversione Custom Insight (o eVar) viene inserita nel codice Adobe su pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei report di marketing personalizzati. Un eVar può essere basato su visite e funzionare in modo simile ai cookie. I valori passati alle variabili eVar seguono l'utente per un periodo di tempo predeterminato.
keywords: eVar
title: Variabili di conversione (eVar)
topic: Admin tools
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 5%

---


# Conversion Variables (Variabili di conversione) (eVars)

La variabile di conversione Custom Insight (o eVar) viene inserita nel codice Adobe su pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei report di marketing personalizzati. Un eVar può essere basato su visite e funzionare in modo simile ai cookie. I valori passati alle variabili eVar seguono l&#39;utente per un periodo di tempo predeterminato.

Quando un eVar viene impostato su un valore per un visitatore, Adobe ricorda automaticamente tale valore fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar.

Le eVar vengono utilizzate in modo ottimale per misurare la causa e l&#39;effetto, ad esempio:

* Quali campagne interne hanno influenzato le entrate
* Quali banner pubblicitari sono risultati in ultima istanza una registrazione
* Numero di volte in cui è stata utilizzata una ricerca interna prima di eseguire un ordine

Se si desidera misurare il traffico o il percorso, è consigliabile utilizzare le variabili di traffico.

>[!NOTE]
>
>In una richiesta di immagine è possibile memorizzare un solo valore in una eVar. Se più valori sono desiderati in un valore eVar, si consiglia di implementare le variabili [Elenco (variabili elenco)](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/page-variables.html).

## Variabili di conversione - Descrizioni {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descrizioni dei campi utilizzati per [modificare le variabili](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md)di conversione.

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
   <td colname="col2"> <p>Il nome descrittivo della variabile di conversione. Questo nome è il riferimento all'eVar nel reporting generale e sarà il nome del report nel menu a sinistra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Tipo</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Il tipo di valore variabile: </p> <p> <b>Stringa</b>di testo:</span> Acquisisce i valori di testo utilizzati nel sito. Si tratta del tipo di eVar più comune e dell'impostazione predefinita. Funziona in modo simile ad altre variabili, dove il valore al suo interno è una stringa di testo statica. Se tieni traccia di elementi quali campagne interne o parole chiave di ricerca interna, questa è l’impostazione consigliata. </p> <p> <b>Contatore</b>:</span> Conta il numero di volte in cui un'azione si verifica prima dell'evento di successo. Ad esempio, se utilizzate un'eVar per tenere traccia delle ricerche interne sul sito, impostate questo valore su <span class="uicontrol"> Stringa</span> di testo per tenere traccia dell'uso dei termini di ricerca. Impostate questo valore su <span class="uicontrol"> Contatore</span> per calcolare il numero di ricerche effettuate, indipendentemente dai termini di ricerca utilizzati. Ad esempio, è possibile utilizzare un'eVar contatore per tenere traccia del numero di volte in cui un utente ha utilizzato la ricerca interna prima di effettuare un acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Allocazione </span> </p> </td> 
   <td colname="col2"> <p>Determina il modo in cui Analytics assegna il credito per un evento di successo se una variabile riceve valori multipli prima dell’evento. I valori supportati includono: </p> <p> <b>Più recenti</b>: L'ultimo valore eVar riceve sempre credito per gli eventi di successo fino alla scadenza di tale eVar. </p> <p> <b>Valore</b>originale: La prima eVar riceve sempre credito per gli eventi di successo fino alla scadenza di tale eVar. </p> <p> <b> Lineare</b>:alloca gli eventi di successo in modo uniforme tra tutti i valori eVar. Poiché l’allocazione lineare distribuisce accuratamente i valori solo all’interno di una visita, utilizza l’allocazione lineare con una scadenza eVar della visita. </p> <p>Nota:  Il passaggio dell'allocazione a o da Linear impedisce la visualizzazione dei dati storici. La combinazione di tipi di allocazione nell'interfaccia di reporting può portare a dati erronei nei report. Ad esempio, l'allocazione lineare potrebbe dividere le entrate tra un certo numero di valori eVar diversi. Dopo aver ripristinato l'allocazione più recente, il 100% di tali entrate sarebbe associato al valore singolo più recente. Questa associazione può portare a conclusioni errate da parte degli utenti. </p> <p>Per evitare la possibilità di confusione nei report,  Analytics rende i dati storici non disponibili per l'interfaccia. Può essere visualizzato se si decide di ripristinare l'impostazione di allocazione iniziale per l'eVar specificato, anche se non è necessario modificare le impostazioni di allocazione eVar semplicemente per accedere ai dati storici. Adobe consiglia di utilizzare una nuova eVar quando nuove impostazioni di allocazione sono desiderate per i dati già registrati, invece di modificare le impostazioni di allocazione su una eVar che dispone già di una quantità significativa di dati storici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Scade dopo</span> </p> </td> 
   <td colname="col2"> <p>Specifica un periodo di tempo, o un evento, dopo il quale il valore eVar scade (non riceve più credito per gli eventi di successo). Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). </p> <p>Se selezioni un evento come valore di scadenza, la variabile scade solo se si verifica l’evento. Se l’evento non si verifica, la variabile non scade. </p> <p>Le opzioni di scadenza disponibili possono essere classificate in quattro categorie principali: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>A livello di visualizzazione pagina o visita.</b> Gli eventi di conversione oltre la visualizzazione della pagina o la visita non si associano all'eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>In base a un periodo di tempo, ad esempio giorno, settimana, mese o anno.</b> Gli eventi di conversione oltre il periodo di tempo specificato non vengono associati all'eVar. Il periodo di scadenza inizia quando la variabile viene impostata. Le eVar scadono in base all'ora impostata, al secondo (minuto, ora, giorno, mese, ecc.): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTO=60 secondi </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">ORA=3600 secondi (60 minuti) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DAY=86400 secondi (24 ore) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">SETTIMANA=604800 secondi (7 giorni) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MESE=2678400 secondi (31 giorni) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">QUARTER=8035200 secondi (93 giorni - 3 mesi di 31 giorni) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">ANNO=31536000 secondi (365 giorni) </li> 
      </ul> <p> </p> <p>Se una visita inizia alle 7:00 del lunedì e una eVar viene impostata entro tale visita alle 7:15 del mattino, la scadenza è come indicato di seguito: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Scadenza giorno: eVar scade alle 7:15 di martedì. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Scadenza settimana: L'eVar scade il lunedì successivo alle 7:15. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Scadenza mese: eVar scade 31 giorni da lunedì alle 7:15. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>Eventi di conversione specifici.</b> Qualsiasi altro evento di conversione attivato dopo lo specifico evento designato viene associato all'eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Mai.</b> Fintanto che il cookie <span class="varname"> visitorID</span> è intatto, può passare un qualsiasi periodo di tempo tra eVar ed evento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Stato</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Definisce lo stato eVar: </p> <p><b>Disattivato</b>:</span> Disattiva l'eVar. Rimuove l'eVar dall'elenco delle variabili di conversione. </p> <p> <b>Nessuna sottorelazione</b>:</span> Impedisce la suddivisione dell'eVar con una sottorelazione. </p> <p> <b>Subrelazioni</b>di base: </span>Consente di suddividere un'eVar per qualsiasi rapporto con relazioni complete (ad esempio, Prodotti o Campagna). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Reimpostare</span> </p> </td> 
   <td colname="col2"> <p>Reimposta eventuali valori esistenti nell'eVar. </p> <p>Utilizzare questa impostazione quando si ripropone un'eVar in modo da mixare un valore precedente in un nuovo rapporto. La reimpostazione non cancella i dati storici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Merchandising</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Le variabili di merchandising possono seguire una delle due sintassi: </p> <p> <b>Sintassi</b>prodotti:</span> Associa il valore eVar a un prodotto. Nota:  Se Product Syntax (Sintassi prodotto) è selezionata, la sezione Merchandising Binding Event (Evento di binding merchandising) è disabilitata e non è selezionabile per la modifica. Per questa sintassi, gli eventi di binding non sono applicabili. </p> </p> <p> <b>Sintassi</b>variabile di conversione:</span> Associa l'eVar a un prodotto solo se si verifica un evento di binding. In questo caso, è possibile selezionare gli eventi che fungono da eventi di binding. </p> <p>La modifica di questa impostazione senza aggiornare di conseguenza il codice JavaScript causa la perdita di dati. Consultate Variabili <a href="https://docs.adobe.com/content/help/en/analytics/components/variables/merchandising-variables/var-merchandising.html"></a>di merchandising. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Evento di binding Merchandising</span> </p> <p>(solo eVar) </p> </td> 
   <td colname="col2"> <p>Se Merchandising è impostato su <span class="uicontrol"> Conversion Variable Syntax</span>, gli eventi selezionati collegano il valore eVar corrente a un prodotto. </p> <p>Per utilizzare un evento di binding, impostare <span class="uicontrol"> Allocazione su Più recente</span>. Se <span class="uicontrol"> Allocazione è Valore</span>originale, il primo binding di prodotto eVar rimane fino alla scadenza dell'eVar. Per selezionare più eventi, tenete premuto <code>ctrl</code> (Windows) o <code>cmd</code> (Mac) e fate clic su più elementi nell’elenco. È possibile selezionare un evento solo quando è selezionata la "Sintassi variabile di conversione".</p> </td> 
  </tr> 
 </tbody> 
</table>

**Scadenza**

`eVars` scade dopo un periodo di tempo specificato. Dopo la scadenza dell&#39;eVar, non riceve più credito per gli eventi di successo. Le eVar possono anche essere configurate per scadere in caso di eventi di successo. Ad esempio, se si dispone di una promozione interna che scade al termine di una visita, la promozione interna riceve credito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Esistono due modi per scadere di un&#39;eVar:

* Potete impostare la scadenza dell&#39;eVar dopo un periodo di tempo o un evento specificato.
* È possibile utilizzare Forza scadenza di una eVar reimpostandola, utile per riproporre una variabile.

Ad esempio, se cambi la scadenza di un eVar da 30 a 90 giorni, i valori eVar raccolti continueranno a persistere per la durata del nuovo set di scadenza (in questo caso, 90 giorni). Il sistema guarda semplicemente l&#39;impostazione della scadenza corrente e l&#39;ultima marca temporale impostata del valore eVar raccolta per determinare la scadenza. Solo l’ **[!UICONTROL Reset]** opzione scade i valori ed effettua questa operazione immediatamente.

Un altro esempio: Se un eVar viene utilizzato in maggio per riflettere le promozioni interne e scade dopo 21 giorni, e in giugno viene utilizzato per acquisire le parole chiave di ricerca interna, il 1 giugno è necessario forzare la scadenza o reimpostare la variabile. In questo modo, i rapporti di giugno consentiranno di mantenere i valori di promozione interni.

**Sensibilità maiuscole/minuscole**

Le eVar non fanno distinzione tra maiuscole e minuscole, ma vengono visualizzate nelle maiuscole della prima occorrenza. Ad esempio, se la prima istanza di eVar1 è impostata su &quot;Accesso&quot;, ma tutte le istanze successive vengono passate come &quot;Accesso&quot;, i rapporti mostrano sempre &quot;Accesso&quot; come valore dell&#39;eVar.

**Contatori**

Sebbene le eVar siano utilizzate più spesso per contenere valori stringa, possono anche essere configurate per fungere da contatori. Le eVar sono utili come contatori quando si tenta di contare il numero di azioni eseguite da un utente prima di un evento. Ad esempio, potete utilizzare un&#39;eVar per acquisire il numero di ricerche interne prima dell&#39;acquisto. Ogni volta che un visitatore effettua una ricerca, l&#39;eVar deve contenere il valore &#39;+1.&#39; Se un visitatore effettua una ricerca quattro volte prima di un acquisto, verrà visualizzata un’istanza per ciascun conteggio totale: 1,00, 2,00, 3,00 e 4,00. Tuttavia, solo la versione 4.00 riceve credito per l&#39;evento di acquisto (Metriche Ordini e Entrate). Solo i numeri positivi sono consentiti come valori di un contatore eVar.