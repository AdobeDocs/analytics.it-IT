---
description: Il rapporto Collegamenti riporta i collegamenti presenti nella pagina corrente. Non crea rapporti su tutti i collegamenti raccolti per quella pagina.
seo-description: Il rapporto Collegamenti riporta i collegamenti presenti nella pagina corrente. Non crea rapporti su tutti i collegamenti raccolti per quella pagina.
seo-title: Rapporto dei collegamenti
solution: Analytics
title: Rapporto dei collegamenti
topic: Activity Map
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
translation-type: tm+mt
source-git-commit: 36637b76b8026fbf87ad48adcfa47386c530e732

---


# Rapporto dei collegamenti

Il rapporto Collegamenti riporta i collegamenti presenti nella pagina corrente. Non crea rapporti su tutti i collegamenti raccolti per quella pagina.

Il rapporto Collegamenti sulla pagina offre una visualizzazione tabulare dei collegamenti. A volte può essere utile visualizzare clic sui collegamenti (o altre metriche) classificati in una singola vista. Questo consente di confrontare meglio un collegamento con un altro. Create il rapporto Collegamenti sulla pagina, compreso un elenco classifica di tutti i collegamenti della pagina (per ID collegamento), delle informazioni sul clic (# e %) e della regione della pagina. Fate clic sul pulsante Collegamenti nel rapporto Pagina nella [!DNL Activity Map] barra degli strumenti.

Il **[!UICONTROL Links On Page]** rapporto si apre sotto la cornice del browser nel [!DNL Activity Map] dashboard.

## Modalità standard {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

In modalità standard, il report "Links on Page" (Collegamenti sulla pagina) mostra dati di collegamento che vanno da un giorno all'altro, aggregati sull'intero intervallo di date. Per ogni collegamento verranno mostrate le seguenti informazioni:

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Colonna </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Classifica </td> 
   <td colname="col2"> Classifica nella pagina. In modalità standard, il valore della classificazione rimane invariato, indipendentemente dalla colonna su cui si fa clic. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">L’ID principale del collegamento (per ulteriori informazioni su come l’ID principale è definito dalla [Nuova metodologia di tracciamento dei collegamenti] (/home/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clic </td> 
   <td colname="col2"> Numero di clic non elaborati per un collegamento specificato e relativa percentuale dei clic totali sulla pagina. Se l’utente sceglie una metrica diversa nella barra degli strumenti, il rapporto Collegamento effettuerà il rapporto sulla metrica in questione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l’area della pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>Nascosto</b>: il collegamento è attualmente nella pagina ma non è visibile all’utente finale (come un sottomenu di un menu di navigazione che diventa visibile solo se l’utente passa sopra al menu principale) </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>Visualizzato</b>: il collegamento è attualmente visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzato sotto la piega: l'utente dovrebbe scorrere la pagina per visualizzarla. </li>
    </ul><p>Nota:  Se un collegamento è impostato su "Nascosto", non verrà visualizzata alcuna sovrapposizione. </p></td> 
  </tr> 
 </tbody> 
</table>

**Filtrare i dati**

Se si desidera zero in un collegamento specifico, è possibile cercare un termine correlato nel **[!UICONTROL Filter Data]** campo. Solo i collegamenti corrispondenti alla ricerca avranno sovrapposizioni. Senza un filtro, verranno visualizzate le sovrapposizioni specificate nelle impostazioni [](/help/analyze/activity-map/activitymap-overlay-settings.md) [!DNL Activity Map].

## Modalità Live {#section_AC1967217B5A4532ACB01D33636F6770}

In modalità Live, il rapporto Links on Page (Collegamenti sulla pagina) mostra i dati con tendenze relativi a diversi minuti.

![](assets/links_on_page.png)

<table id="table_61D1FB0F02894055A1AB394DE4FE4742"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Colonna </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Classifica </td> 
   <td colname="col2"> Classifica nella pagina. Nel caso di una sovrapposizione sfumatura o bolla, il valore della classificazione rimane invariato, indipendentemente dalla colonna su cui fate clic. Nel caso di una sovrapposizione di tipo "guadagno/perdente", il valore della classifica cambia in base al tipo di collegamenti guadagnati/persi di più. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">L'ID principale del collegamento. Per ulteriori informazioni su come l’ID primario è definito dalla nuova [Metodo di tracciamento dei collegamenti] (/help/analyze/activity-map/activity-map/activity-link-tracking/activitymap-)ink-tracking-methods.md). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clic collegamento </td> 
   <td colname="col2"> Totale clic per il periodo di tempo selezionato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % Modifica </td> 
   <td colname="col2"> % di variazione tra le metriche del collegamento del periodo corrente e quelle del periodo precedente. La variazione negativa % è indicata in rosso, positiva in verde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tendenza </td> 
   <td colname="col2"> Un grafico a linee per tutti i periodi raccolti. Il periodo selezionato è indicato da un marcatore verde. Il periodo di passaggio del puntatore è indicato da un marcatore rosso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l’area della pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">Nascosto: il collegamento è attualmente nella pagina ma non è visibile (ad esempio, qualsiasi collegamento che viene visualizzato dopo il caricamento della pagina). </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">Visualizzato: il collegamento è attualmente visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzato sotto la piega: è necessario scorrere la pagina per visualizzarla. </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Ordinamento e filtro {#section_4B8E8233C21247CAA70DAEC2156548AD}

A volte è necessario analizzare solo i risultati di un’area specifica della pagina (ad esempio, il pannello a sinistra) per decidere come organizzare il contenuto di tale area specifica della pagina Web.

A questo scopo, abbiamo creato una funzionalità di ordinamento e filtro per i collegamenti nel rapporto Collegamenti sulla pagina. Il filtro è disponibile nel campo del filtro e il termine di ricerca viene applicato alla colonna ID collegamento e alla colonna Regione collegamento. L’ordinamento è disponibile facendo clic sulle chiamate (Classifica, ID collegamento, clic, Modifica nel tempo, Regione, Visibilità) e può essere sia crescente che decrescente. Le sovrapposizioni scompaiono dal sito Web quando i collegamenti vengono filtrati dal rapporto Collegamenti sulla pagina.
