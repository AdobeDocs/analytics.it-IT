---
description: Il rapporto Collegamenti riporta i collegamenti presenti nella pagina corrente. Non riporta tutti i collegamenti raccolti per quella pagina.
title: Rapporto dei collegamenti
uuid: 1e7ca5d8-d144-4a21-a2f9-e05bd3232c59
feature: Activity Map
role: User, Admin
exl-id: d17b1bde-1785-461d-a1d8-66bd9739fc78
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 2%

---

# Rapporto dei collegamenti

Il rapporto Collegamenti riporta i collegamenti presenti nella pagina corrente. Non riporta tutti i collegamenti raccolti per quella pagina.

Il rapporto Links On Page (Collegamenti nella pagina) offre una visualizzazione tabulare dei collegamenti. A volte potrebbe essere utile visualizzare i clic di collegamento (o altre metriche) classificati in un’unica vista. Questo consente di confrontare meglio un collegamento con un altro. Creare il report Collegamenti nella pagina, includendo un elenco di tutti i collegamenti della pagina (per ID collegamento), le informazioni sul clic (# e %) e l&#39;area della pagina. Fai clic sul pulsante Collegamenti nel rapporto Pagina nella barra degli strumenti Activity Map.

Il **[!UICONTROL Links On Page]** Il report viene aperto sotto la cornice del browser nel dashboard Activity Map.

## Modalità standard {#section_C8D2A1C07A2A4E3A8F84AC9240603FA7}

![](assets/links_in_page.png)

In modalità standard, il rapporto &quot;Links on Page&quot; (Collegamenti sulla pagina) mostra dati di collegamento che vanno da un singolo giorno a più giorni, aggregati nell’intero intervallo di date. Per ogni collegamento verranno visualizzate le seguenti informazioni:

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
   <td colname="col2"> Classifica nella pagina. In modalità Standard, il valore di classificazione rimane invariato, indipendentemente dalla colonna su cui si fa clic. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">L’ID primario del collegamento (per ulteriori informazioni su come l’ID primario viene definito dal <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md">Nuova metodologia di tracciamento dei collegamenti</a>) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clic </td> 
   <td colname="col2"> Il numero di clic non elaborati per un collegamento specificato e la relativa percentuale sul totale dei clic sulla pagina. Se l’utente sceglie una metrica diversa nella barra degli strumenti, il rapporto Collegamento restituirà invece tale metrica. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l'area della pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_BABCC0F64145407C9D439150A6898E6D">
     <li id="li_9AF0479BDCEB4A44A37292FAABFA83A5"><b>Nascosto</b>: il collegamento si trova attualmente nella pagina ma non è visibile all’utente finale (come un sottomenu in un menu di navigazione che diventa visibile solo se l’utente passa sopra il menu principale) </li>
     <li id="li_C6FA4EC27EDD4341AB9821E2B4BC9E60"><b>Visualizzato</b>: il collegamento viene attualmente visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzata sotto la piega: l’utente dovrebbe scorrere la pagina per visualizzarla. </li>
    </ul><p>Nota: se un collegamento è impostato su "Nascosto", non vengono visualizzate sovrapposizioni. </p></td> 
  </tr> 
 </tbody> 
</table>

**Filtrare i dati**

Se desideri inserire un valore pari a zero in un collegamento specifico, puoi cercare un termine correlato nel **[!UICONTROL Filter Data]** campo. Solo i collegamenti corrispondenti alla ricerca avranno sovrapposizioni. Senza un filtro, le sovrapposizioni specificate nella [Impostazioni Activity Map](/help/analyze/activity-map/activitymap-overlay-settings.md) verrà visualizzato.

## Modalità Live {#section_AC1967217B5A4532ACB01D33636F6770}

In modalità Live, il rapporto Links on Page (Collegamenti nella pagina) mostra dati con tendenze che si estendono su diversi minuti.

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
   <td colname="col2"> Classifica nella pagina. In caso di sovrapposizione sfumatura o bolla, il valore di classifica rimane invariato, indipendentemente dalla colonna su cui fai clic. In caso di sovrapposizione guadagni/perdenti, il valore della classificazione cambia in base ai collegamenti che hanno guadagnato/perso di più. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID collegamento </td> 
   <td colname="col2">ID principale del collegamento. Per ulteriori informazioni su come l'ID primario viene definito dal nuovo <a href="/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md"> Metodologia di tracciamento dei collegamenti</a>. </td>
  </tr> 
  <tr> 
   <td colname="col1"> Clic sui collegamenti </td> 
   <td colname="col2"> Clic totali per il periodo di tempo selezionato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % Modifica </td> 
   <td colname="col2"> % di variazione tra le metriche di collegamento del periodo corrente e le metriche di collegamento del periodo precedente. La variazione percentuale negativa è evidenziata in rosso, quella positiva in verde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tendenza </td> 
   <td colname="col2"> Un grafico a linee per tutti i periodi raccolti. Il periodo attualmente selezionato è indicato da un marcatore verde. Il periodo che si trova al passaggio del mouse è indicato da un indicatore rosso. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Area geografica </td> 
   <td colname="col2"> Rappresenta l'area della pagina in cui si trova il collegamento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visibilità </td> 
   <td colname="col2">Si riferisce allo stato di visibilità del collegamento. Sono possibili due valori: 
    <ul id="ul_B10C55ED4D3C4CF99506DC467E2E7CFB">
     <li id="li_EA646722A51041CC9E62C56DEF92C81F">Nascosto: il collegamento si trova attualmente nella pagina ma non è visibile (ad esempio, qualsiasi collegamento che viene visualizzato dopo il caricamento della pagina). </li>
     <li id="li_F9543614C2894003AC9984A7404E2785">Visualizzato: il collegamento è attualmente visualizzato sulla pagina. Tuttavia, potrebbe essere visualizzato sotto la piega: dovrai scorrere la pagina per vederla. </li>
    </ul></td> 
  </tr> 
 </tbody> 
</table>

## Ordinamento e filtraggio {#section_4B8E8233C21247CAA70DAEC2156548AD}

A volte è necessario analizzare solo i risultati di una specifica area della pagina (ad esempio, il pannello a sinistra) per decidere come organizzare il contenuto di tale area specifica della pagina web.

A questo scopo, è stata creata una funzionalità di ordinamento e filtro per i collegamenti nel rapporto Links on Page (Collegamenti nella pagina). Il filtro è disponibile tramite il campo del filtro e il termine di ricerca verrà applicato alle colonne ID collegamento e Area collegamento. L’ordinamento è disponibile facendo clic sulle chiamate (Classifica, ID collegamento, Clic, Cambia nel tempo, Area, Visibilità) e può essere sia crescente che decrescente. Le sovrapposizioni scompaiono dal sito web quando i collegamenti vengono esclusi dal rapporto Links on Page (Collegamenti nella pagina).
