---
description: La variabile di conversione Custom Insight (o eVar) viene inserita nel codice di Adobe nelle pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un eVar può essere basato su visite e funziona in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l'utente per un periodo di tempo predeterminato.
keywords: eVar
title: Variabili di conversione (eVar)
feature: Strumenti di amministrazione
uuid: 1eed0cb1-0735-4142-be21-43f264216b50
exl-id: 822ecaff-a06c-42e1-aee8-ef4a43df4230
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1581'
ht-degree: 6%

---

# Conversion Variables (Variabili di conversione) (eVars)

La variabile di conversione Custom Insight (o eVar) viene inserita nel codice di Adobe nelle pagine Web selezionate del sito. Il suo scopo principale è segmentare le metriche di successo della conversione nei rapporti di marketing personalizzati. Un eVar può essere basato su visite e funziona in modo simile ai cookie. I valori trasmessi nelle variabili eVar seguono l&#39;utente per un periodo di tempo predeterminato.

Quando un eVar è impostato su un valore per un visitatore, Adobe ricorda automaticamente tale valore fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar.

Le eVar vengono utilizzate in modo più efficace per misurare la causa e l’effetto, ad esempio:

* Quali campagne interne hanno influenzato i ricavi
* Quali banner pubblicitari sono stati alla fine il risultato di una registrazione
* Numero di volte in cui è stata utilizzata una ricerca interna prima di effettuare un ordine

Se desideri misurare il traffico o tracciare un percorso, si consiglia di utilizzare le variabili di traffico.

>[!NOTE]
>
>In una richiesta di immagine è possibile memorizzare un solo valore in un eVar. Se in un valore eVar desideri valori multipli, ti consigliamo di implementare [Variabili elenco (variabili elenco)](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/page-variables.html).

## Variabili di conversione - Descrizioni {#section_7C317BB0287A4B8EB0A1A4ECC40627BF}

Descrizioni dei campi utilizzati durante la [modifica delle variabili di conversione](/help/admin/admin/conversion-var-admin/t-conversion-variables-admin.md).

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
   <td colname="col2"> <p>Nome descrittivo della variabile di conversione. Questo nome è il modo in cui l’eVar viene indicato nel reporting generale e sarà il nome del rapporto nel menu a sinistra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Tipo</span> </p> <p>(Solo eVar) </p> </td> 
   <td colname="col2"> <p>Il tipo di valore della variabile: </p> <p> <b>Stringa di testo</b>:</span> acquisisce i valori di testo utilizzati sul sito. Si tratta del tipo di eVar più comune e dell’impostazione predefinita. Agisce in modo simile ad altre variabili, dove il valore al suo interno è una stringa di testo statica. Se tieni traccia di elementi quali campagne interne o parole chiave di ricerca interne, questa è l’impostazione consigliata. </p> <p> <b>Contatore</b>:</span> conta il numero di volte in cui un’azione si verifica prima dell’evento di successo. Ad esempio, se utilizzi un eVar per tenere traccia delle ricerche interne sul sito, imposta questo valore su <span class="uicontrol"> Text String</span> per tenere traccia dell'uso dei termini di ricerca. Imposta questo valore su <span class="uicontrol"> Contatore</span> per contare il numero di ricerche effettuate, indipendentemente dai termini di ricerca utilizzati. Ad esempio, è possibile utilizzare un eVar contatore per tenere traccia del numero di volte in cui un utente ha utilizzato la ricerca interna prima di effettuare un acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Allocazione  </span> </p> </td> 
   <td colname="col2"> <p>Determina il modo in cui Analytics assegna il credito per un evento di successo se una variabile riceve valori multipli prima dell’evento. I valori supportati includono: </p> <p> <b>Più recente</b>: L’ultimo valore di eVar riceve sempre crediti per eventi di successo fino alla scadenza di tale eVar. </p> <p> <b>Valore</b> originale: Il primo eVar riceve sempre crediti per eventi di successo fino alla scadenza di tale eVar. </p> <p> <b> Lineare</b>: consente di allocare gli eventi di successo in modo uniforme tra tutti i valori eVar. Poiché l’allocazione lineare distribuisce accuratamente i valori solo all’interno di una visita, utilizza l’allocazione lineare con una scadenza eVar della visita. </p> <p>Nota:  Il passaggio dell’allocazione a o da Lineare impedisce la visualizzazione dei dati storici. La combinazione di tipi di allocazione nell’interfaccia di reporting può portare a dati errati nei rapporti. Ad esempio, l’allocazione lineare potrebbe dividere i ricavi in diversi valori di eVar. Dopo aver ripristinato l'allocazione più recente, il 100% di tali entrate sarebbe associato al valore singolo più recente. Questa associazione può portare a conclusioni errate da parte degli utenti. </p> <p>Per evitare la probabilità di confusione nei rapporti, Analytics rende i dati storici non disponibili nell’interfaccia. Può essere visualizzato se si decide di ripristinare l'eVar specificato all'impostazione di allocazione iniziale, anche se non è necessario modificare le impostazioni di allocazione eVar semplicemente per accedere ai dati storici. L’Adobe consiglia di utilizzare un nuovo eVar quando si desidera impostare nuove impostazioni di allocazione per i dati già registrati, anziché modificare le impostazioni di allocazione su un eVar che dispone già di una quantità significativa di dati storici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Scade dopo</span> </p> </td> 
   <td colname="col2"> <p>Specifica un periodo di tempo, o un evento, dopo la scadenza del valore eVar (non riceve più crediti per eventi di successo). Se un evento di successo si verifica dopo la scadenza eVar, il valore None non riceve credito per l’evento (nessun eVar è attivo). </p> <p>Se selezioni un evento come valore di scadenza, la variabile scade solo se si verifica l’evento. Se l’evento non si verifica, la variabile non scade. </p> <p>Le opzioni di scadenza disponibili possono essere classificate in quattro categorie principali: </p> 
    <ul id="ul_810A37C9B6624F429F2FB45C18F7B43F"> 
     <li id="li_654D9D9044EC4E61AA7ABA372DBF8A93"><b>A livello di visualizzazione della pagina o di visita.</b> Gli eventi di conversione che vanno oltre la visualizzazione della pagina o la visita non si associano all’eVar. </li> 
     <li id="li_689FBC8B4DAC41B3B0166E6586DD1990"><b>In base a un periodo di tempo, ad esempio giorno, settimana, mese o anno.</b> Gli eventi di conversione oltre il periodo di tempo specificato non si associano all'eVar. Il periodo di scadenza inizia quando la variabile viene impostata. Le eVar scadono in base al tempo impostato, al secondo (minuto, ora, giorno, mese, ecc.): 
      <ul id="ul_80C7E3182B6B4356B8A3CA920B81C6D5"> 
       <li id="li_F16F60319CCE406D9EDEFEC0A200BC4D">MINUTO=60 secondi </li> 
       <li id="li_45F47F3F5691415B84052B235DF3BB54">ORA=3600 secondi (60 minuti) </li> 
       <li id="li_5288CE7D168E4C85B3D9BB67A44D32EC">DAY=86400 secondi (24 ore) </li> 
       <li id="li_60FC8BCD657745EE87B4E458CBA69583">WEEK=604800 secondi (7 giorni) </li> 
       <li id="li_7A05A66613C84F929F030310B9567CF5">MESE=2678400 secondi (31 giorni) </li> 
       <li id="li_DCD3CABF59E34D5999B03E606B08AD85">TRIMESTRE=8035200 secondi (93 giorni - 3 mesi di 31 giorni) </li> 
       <li id="li_54351D2899454D39A8BA205910D2CCB1">ANNO=31536000 secondi (365 giorni) </li> 
      </ul> <p> </p> <p>Se una visita inizia alle 7:00 del lunedì e un eVar è impostato entro tale visita alle 7:15 del mattino, la scadenza è come illustrato di seguito: </p> 
      <ul id="ul_72B311006BE6428698313D251C0940DB"> 
       <li id="li_50925D4A40AD4ACA88704A523138C5B9">Scadenza del giorno: L'eVar scade alle 7:15 del mattino di martedì. </li> 
       <li id="li_25846328766D4B4BAF407236C65C956C">Scadenza settimana: L'eVar scade il lunedì successivo alle 7:15. </li> 
       <li id="li_82DB2D7F53304623A5E1241D75C7DF94">Scadenza mese: L'eVar scade 31 giorni a partire da lunedì alle 7:15. </li> 
      </ul> </li> 
     <li id="li_C132C5C5A5344B91BDF5EB6A1C717C37"><b>Eventi di conversione specifici.</b> Qualsiasi altro evento di conversione che si attiva dopo l’evento specifico designato viene associato all’eVar. </li> 
     <li id="li_5A782D743FB940649E6CB3E4BEA9B8B6"><b>Mai.</b> Finché il  <span class="varname"> </span> visitorIDcookie è intatto, può trascorrere qualsiasi periodo di tempo tra eVar ed evento. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Stato</span> </p> <p>(Solo eVar) </p> </td> 
   <td colname="col2"> <p>Definisce lo stato di eVar: </p> <p><b>Disabilitato</b>:</span> disabilita l’eVar. Rimuove l’eVar dall’elenco delle variabili di conversione. </p> <p> <b>Nessuna sottorelazione</b>:</span> impedisce la suddivisione dell’eVar con una sottorelazione. </p> <p> <b>Sottorelazioni</b> di base:  </span>Consente di suddividere un eVar per qualsiasi rapporto con sottorerelazioni complete (ad esempio, Prodotti o Campaign). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Ripristino</span> </p> </td> 
   <td colname="col2"> <p>Reimposta eventuali valori esistenti nell'eVar. </p> <p>Utilizza questa impostazione quando riutilizzi un eVar in modo da combinare un valore precedente in un nuovo rapporto. La reimpostazione non cancella i dati storici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Merchandising</span> </p> <p>(Solo eVar) </p> </td> 
   <td colname="col2"> <p>Le variabili merchandising possono seguire una delle due sintassi: </p> <p> <b>Sintassi dei prodotti</b>:</span> associa il valore eVar a un prodotto. Nota:  Se è selezionata l’opzione Sintassi prodotti , la sezione Evento di associazione Merchandising è disabilitata e non selezionabile per la modifica. Per questa sintassi, gli eventi di binding non sono applicabili. </p> </p> <p> <b>Sintassi della variabile di conversione</b>:</span> associa l’eVar a un prodotto solo se si verifica un evento di associazione. In questo caso, è possibile selezionare gli eventi che fungono da eventi di binding. </p> <p>La modifica di questa impostazione senza aggiornare di conseguenza il codice JavaScript causa la perdita di dati. Consulta <a href="https://docs.adobe.com/content/help/en/analytics/components/variables/merchandising-variables/var-merchandising.html"> Variabili di merchandising</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="uicontrol"> Evento di associazione Merchandising</span> </p> <p>(Solo eVar) </p> </td> 
   <td colname="col2"> <p>Se Merchandising è impostato su <span class="uicontrol"> Sintassi variabile di conversione</span>, gli eventi selezionati associano il valore di eVar corrente a un prodotto. </p> <p>Per utilizzare un evento di binding, impostare <span class="uicontrol"> Allocazione su Più recente</span>. Se <span class="uicontrol"> Allocazione è Valore originale</span>, il primo binding del prodotto eVar rimane fino alla scadenza dell'eVar. Per selezionare più eventi, tenere premuto <code>ctrl</code> (Windows) o <code>cmd</code> (Mac) e fare clic su più elementi nell’elenco. È possibile selezionare un evento solo quando è selezionata la "Sintassi della variabile di conversione".</p> </td> 
  </tr> 
 </tbody> 
</table>

**Scadenza**

`eVars` scadono dopo un periodo di tempo specificato. Dopo la scadenza dell’eVar, non riceve più crediti per eventi di successo. Le eVar possono anche essere configurate in modo da scadere in caso di eventi di successo. Ad esempio, se hai una promozione interna che scade alla fine di una visita, la promozione interna riceve credito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Ci sono due modi per scadere un eVar:

* Puoi impostare l’eVar in modo che scada dopo un determinato periodo di tempo o evento.
* È possibile utilizzare la forza della scadenza di un eVar reimpostandolo, utile quando si ripropone una variabile.

Ad esempio, se modifichi la scadenza di un eVar da 30 a 90 giorni, i valori eVar raccolti continueranno a persistere per la durata del nuovo set di scadenza (in questo caso, 90 giorni). Il sistema controlla semplicemente l&#39;impostazione di scadenza corrente e l&#39;ultima marca temporale impostata del valore eVar raccolto per determinare la scadenza. Solo l’opzione **[!UICONTROL Reset]** scade i valori e lo fa immediatamente.

Un altro esempio: Se un eVar viene utilizzato a maggio per riflettere le promozioni interne e scade dopo 21 giorni, e a giugno viene utilizzato per acquisire le parole chiave di ricerca interne, il 1° giugno è necessario forzare la scadenza o reimpostare la variabile. In questo modo sarà possibile mantenere i valori di promozione interni al di fuori dei rapporti di giugno.

**Sensibilità ai casi**

Le eVar non distinguono tra maiuscole e minuscole, ma sono visualizzate nella maiuscola della prima occorrenza. Ad esempio, se la prima istanza di eVar1 è impostata su &quot;Logged In&quot;, ma tutte le istanze successive vengono passate come &quot;logged in&quot;, i rapporti mostrano sempre &quot;Logged In&quot; come valore dell’eVar.

**Contatori**

Sebbene le eVar siano utilizzate più spesso per contenere valori stringa, possono anche essere configurate per fungere da contatori. Le eVar sono utili come contatori quando si tenta di contare il numero di azioni eseguite da un utente prima di un evento. Ad esempio, puoi utilizzare un eVar per acquisire il numero di ricerche interne prima dell’acquisto. Ogni volta che un visitatore esegue una ricerca, l’eVar deve contenere un valore di &quot;+1.&quot; Se un visitatore esegue ricerche quattro volte prima di un acquisto, visualizzerai un’istanza per ogni conteggio totale: 1.00, 2.00, 3.00 e 4.00. Tuttavia, solo il 4.00 riceve credito per l’evento di acquisto (Metriche Ordini e Entrate). Solo i numeri positivi sono consentiti come valori di un contatore eVar.
