---
description: Il rapporto Collegamenti riporta i collegamenti presenti nella pagina corrente. Non crea rapporti su tutti i collegamenti raccolti per quella pagina.
title: Rapporto dei collegamenti
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
feature: Activity Map
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 2%

---


# Rapporto dei collegamenti

Il rapporto Collegamenti riporta i collegamenti presenti nella pagina corrente. Non crea rapporti su tutti i collegamenti raccolti per quella pagina.

Il rapporto Collegamenti sulla pagina offre una visualizzazione tabulare dei collegamenti. A volte può essere utile visualizzare i clic sui collegamenti (o altre metriche) classificati in una singola vista. Ciò ti consente di confrontare meglio un collegamento con un altro. Crea il rapporto Collegamenti alla pagina , con un elenco classificato di tutti i collegamenti della pagina (per ID collegamento), delle informazioni sui clic (# e %) e della regione nella pagina. Fai clic sul pulsante Rapporto Collegamenti nella pagina nella barra degli strumenti di Activity Map.

Il rapporto **[!UICONTROL Links On Page]** si apre sotto il frame del browser nel dashboard di Activity Map.

## Modalità standard {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

In modalità standard, il rapporto &quot;Collegamenti sulla pagina&quot; mostra dati di collegamento che vanno da un giorno all’altro, aggregati sull’intero intervallo di date. Per ogni collegamento vengono visualizzate le seguenti informazioni:

<table id="table_3DE41B2CFA644B70AF802A3123CE51D9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Colonna </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Classificazione </td> 
   <td colname="col2"> Classifica nella pagina. In Modalità standard, il valore di classificazione rimane invariato, indipendentemente dalla colonna su cui fai clic. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">L'ID principale del collegamento (per ulteriori informazioni su come l'ID principale è definito dalla <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">nuova metodologia di tracciamento dei collegamenti</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clic </td> 
   <td colname="col2"> Numero di clic non elaborati per un collegamento specificato e relativa percentuale dei clic totali sulla pagina. Se l’utente sceglie una metrica diversa nella barra degli strumenti, il rapporto Collegamento ne segnalerà la metrica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l'area della pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>Nascosto</b>: il collegamento è attualmente nella pagina ma non è visibile all’utente finale (come un sottomenu di un Menu di navigazione che diventa visibile solo se l’utente passa sopra il Menu principale) </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>Visualizzato</b>: il collegamento è attualmente visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzato sotto la piega: l’utente dovrebbe scorrere la pagina per visualizzarla. </li>
    </ul><p>Nota:  Se un collegamento è impostato su "Nascosto", non verranno visualizzate sovrapposizioni. </p></td> 
  </tr> 
 </tbody> 
</table>

**Filtrare i dati**

Se desideri eseguire la ricerca di zero in un collegamento specifico, puoi cercare un termine correlato nel campo **[!UICONTROL Filter Data]** . Solo i collegamenti che corrispondono alla ricerca avranno sovrapposizioni. Senza un filtro, verranno visualizzate le sovrapposizioni specificate in [Impostazioni di Activity Map](/help/analyze/activity-map/activitymap-overlay-settings.md).

## Modalità live {#section_AC1967217B5A4532ACB01D33636F6770}

In modalità Live, il rapporto Links on Page (Collegamenti sulla pagina) mostra i dati con tendenze nell’arco di diversi minuti.

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
   <td colname="col1"> Classificazione </td> 
   <td colname="col2"> Classifica nella pagina. In caso di sovrapposizione sfumatura o bolla, il valore di classificazione rimane lo stesso, indipendentemente dalla colonna su cui fai clic. In caso di sovrapposizione guadagni/perdenti, il valore di rango cambia in base a quali collegamenti guadagnato/perso di più. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">L'ID principale del collegamento. Per ulteriori informazioni sulla definizione dell'ID primario tramite la nuova <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> Metodologia di tracciamento dei collegamenti</a>. </td>
  </tr> 
  <tr> 
   <td colname="col1"> Clic sui collegamenti </td> 
   <td colname="col2"> Totale clic per il periodo di tempo selezionato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % Modifica </td> 
   <td colname="col2"> % di variazione tra le metriche di collegamento del periodo corrente e le metriche di collegamento del periodo precedente. Le variazioni negative della percentuale sono indicate in rosso, positive in verde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tendenza </td> 
   <td colname="col2"> Grafico a linee per tutti i periodi raccolti. Il periodo attualmente selezionato è indicato da un marcatore verde. Il periodo attualmente in cui si passa il mouse è indicato da un marcatore rosso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l'area della pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">Nascosto: Il collegamento si trova attualmente nella pagina ma non è visibile (ad esempio, qualsiasi collegamento visualizzato dopo il caricamento della pagina). </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">Visualizzato: il collegamento è attualmente visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzato sotto la piega: per visualizzarla, è necessario scorrere la pagina. </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Ordinamento e filtraggio {#section_4B8E8233C21247CAA70DAEC2156548AD}

A volte è necessario analizzare solo i risultati di una specifica area di pagina (ad esempio il pannello a sinistra) per decidere come organizzare il contenuto di tale area specifica della pagina web.

A questo scopo, abbiamo creato una funzionalità di ordinamento e filtro per i collegamenti nel rapporto Collegamenti alla pagina . Il filtro è disponibile tramite il campo filtro e il termine di ricerca viene applicato alla colonna ID collegamento e alla colonna Regione collegamento . L’ordinamento è disponibile facendo clic sulle chiamate (Classifica, ID collegamento, Clic, Modifica nel tempo, Area geografica, Visibilità) e può essere sia crescente che decrescente. Le sovrapposizioni scompaiono dal sito web quando i collegamenti vengono filtrati dal rapporto Collegamenti sulla pagina .
