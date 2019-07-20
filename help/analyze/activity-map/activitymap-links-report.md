---
description: Nei rapporti sono riportati i rapporti sui collegamenti trovati nella pagina corrente. Non viene fornito alcun rapporto su tutti i collegamenti raccolti per quella pagina.
seo-description: Nei rapporti sono riportati i rapporti sui collegamenti trovati nella pagina corrente. Non viene fornito alcun rapporto su tutti i collegamenti raccolti per quella pagina.
seo-title: Rapporto collegamenti
solution: Analytics
title: Rapporto collegamenti
topic: Activity map
uuid: 1 e 7 ca 5 d 8-d 144-4 a 21-a 2 f 9-e 05 bd 3232 c 59
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporto collegamenti

Nei rapporti sono riportati i rapporti sui collegamenti trovati nella pagina corrente. Non viene fornito alcun rapporto su tutti i collegamenti raccolti per quella pagina.

Il rapporto Collegamenti sulla pagina offre una visualizzazione tabulare dei collegamenti. A volte potrebbe essere utile visualizzare i clic di collegamento (o altre metriche) in una sola visualizzazione. Questo consente di confrontare meglio un collegamento a un altro. Crea il rapporto Collegamenti sulla pagina, compreso un elenco classifica di tutti i collegamenti della pagina (per ID collegamento), le informazioni sul clic (# e %) e l'area della pagina. Fate clic sul pulsante Collegamenti nella pagina nella barra degli strumenti Activity Map (Mappa dell'attività).

The **[!UICONTROL Links On Page]** report opens below the browser frame in the Activity Map dashboard.

## Standard mode {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

In modalità Standard, il rapporto «Links on Page» (Collegamenti nella pagina) mostra i dati dei collegamenti che vanno da un giorno a un giorno, aggregati sull'intervallo di date completo. Per ogni collegamento vengono visualizzate le seguenti informazioni:

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
   <td colname="col2"> Classifica nella pagina. In modalità Standard, il valore di classificazione resta invariato, a prescindere dalla colonna che si fa clic. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">L'ID primario del collegamento (per ulteriori informazioni sul modo in cui l'ID principale è definito dalla [nuova metodologia di tracciamento dei collegamenti] (/home/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-threshold. md) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clic </td> 
   <td colname="col2"> Numero di clic non elaborati per un collegamento specificato e la percentuale del clic totale sulla pagina. Se l'utente sceglie una metrica diversa nella barra degli strumenti, il report Collegamento si riferisce a tale metrica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l'area nella pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>Nascosto</b>: il collegamento è attualmente nella pagina ma non è visibile all'utente finale (come un sottomenu in un Menu di navigazione che diventa visibile solo se l'utente si trova sopra il menu principale) </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>Visualizzato</b>: il collegamento è attualmente visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzato sotto la piega: l'utente deve scorrere la pagina per visualizzarla. </li>
    </ul><p>Nota: Se un collegamento è impostato su «Nascosto», non verrà visualizzata alcuna sovrapposizione. </p></td> 
  </tr> 
 </tbody> 
</table>

**Filtrare i dati**

When you want to zero in on a specific link, you can search for a related term in the **[!UICONTROL Filter Data]** field. Verranno sovrapposizioni solo i collegamenti che corrispondono alla ricerca. Without a filter, the overlays specified in the [Activity Map Settings](/help/analyze/activity-map/activitymap-overlay-settings.md) will be shown.

## Live mode {#section_AC1967217B5A4532ACB01D33636F6770}

In modalità Live, il report Links on Page (Collegamenti nella pagina) mostra i dati con tendenze diversi minuti.

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
   <td colname="col2"> Classifica nella pagina. Nel caso di una sovrapposizione sfumatura o bolla, il valore di classificazione resta invariato, a prescindere dalla colonna che si fa clic. Nel caso di una sovrapposizione gainers/losers, questo valore di classificazione cambia in base ai collegamenti generati/persi di più. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">L'ID primario del collegamento. Per ulteriori informazioni su come l'ID principale è definito dalla nuova [Metodologia di tracciamento collegamenti] (/help/analyze/activity-map/activitymap-link-tracking/activitymap-) ink-tracking-method. md). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clic sul collegamento </td> 
   <td colname="col2"> Clic totali per il periodo di tempo selezionato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % Modifica </td> 
   <td colname="col2"> % change tra metriche collegate ai collegamenti correnti e metriche collegate ai collegamenti precedenti. La modifica negativa % viene visualizzata in rosso, positiva in verde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tendenza </td> 
   <td colname="col2"> Grafico a linee per tutti i periodi raccolti. Il periodo selezionato è indicato da un indicatore verde. Il periodo al passaggio del mouse è indicato da un marcatore rosso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l'area nella pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">Nascosto: il collegamento è attualmente nella pagina ma non è visibile (ad esempio, un collegamento che viene visualizzato dopo il caricamento della pagina). </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">Visualizzato: attualmente è visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzato sotto la piega: è necessario scorrere la pagina per visualizzarla. </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Sorting and filtering {#section_4B8E8233C21247CAA70DAEC2156548AD}

A volte è necessario analizzare solo i risultati di un'area della pagina specifica (ad es. pannello a sinistra) per decidere come organizzare il contenuto di quella specifica area della pagina Web.

A questo scopo, abbiamo creato una funzionalità di ordinamento e filtro per i collegamenti nel report Links on Page (Collegamenti nella pagina). Il filtro è disponibile tramite il campo filtro e il termine di ricerca verrà applicato alle colonne ID collegamento e Area collegamento. L'ordinamento è disponibile facendo clic sulle call-ons (Classifica, ID collegamento, Clic, Cambia nel tempo, Regione, Visibilità) e può essere crescente e decrescente. Le sovrapposizioni vengono eliminate dal sito Web quando i collegamenti vengono filtrati nel rapporto Collegamenti della pagina.
