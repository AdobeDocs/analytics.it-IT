---
description: Mostra le aree del sito accessibili maggiormente dai visitatori. Le sezioni del sito possono includere gruppi di prodotti simili alle categorie definite dall'utente. Ad esempio, potrebbe essere presente un gruppo di videocamere, un gruppo di computer e così via. I dati per il report Sezioni del sito conversione vengono importati dal report Sezione sito nel gruppo Traffico, che riceve le informazioni dalla variabile canale nel codice di tracciamento. Potete utilizzare questo rapporto per identificare il maggior impatto sulle statistiche del sito dagli elementi in sezioni di siti variabili.
seo-description: Mostra le aree del sito accessibili maggiormente dai visitatori. Le sezioni del sito possono includere gruppi di prodotti simili alle categorie definite dall'utente. Ad esempio, potrebbe essere presente un gruppo di videocamere, un gruppo di computer e così via. I dati per il report Sezioni del sito conversione vengono importati dal report Sezione sito nel gruppo Traffico, che riceve le informazioni dalla variabile canale nel codice di tracciamento. Potete utilizzare questo rapporto per identificare il maggior impatto sulle statistiche del sito dagli elementi in sezioni di siti variabili.
seo-title: Sezione sito
solution: Analytics
title: Sezione sito
topic: Rapporti
uuid: 6839 c 566-f 88 f -4979-9 cf 5-52 a 77 c 0 b 0416
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Sezione sito

Mostra le aree del sito accessibili maggiormente dai visitatori. Le sezioni del sito possono includere gruppi di prodotti simili alle categorie definite dall'utente. Ad esempio, potrebbe essere presente un gruppo di videocamere, un gruppo di computer e così via. I dati per il report Sezioni del sito conversione vengono importati dal report Sezione sito nel gruppo Traffico, che riceve le informazioni dalla variabile canale nel codice di tracciamento. Potete utilizzare questo rapporto per identificare il maggior impatto sulle statistiche del sito dagli elementi in sezioni di siti variabili.

* This report references data directly from the [s.channel](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_channel) variable implemented on your website.
* Questo rapporto può essere visualizzato sia nei formati con tendenze che in quelli classificati.
* Questo rapporto può utilizzare un filtro di ricerca per individuare elementi di righe specifiche.
* In questo rapporto possono essere utilizzate classificazioni che consentono di rinominare e consolidare gli elementi della riga.
* Le correlazioni possono essere create con qualsiasi altra variabile di traffico tramite Strumenti di amministrazione.
* Questo rapporto può utilizzare le metriche seguenti:

   * **Visualizzazioni**: Il numero di volte in cui è stata definita la variabile [pagename](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_pagename) o l'URL (impostato come metrica predefinita)

   * **Tutte le metriche di percorsi**: Visite, Profondità pagina media, Tempo medio trascorso sulla pagina, Entrate, Uscite, Ricariche e Accesso singolo
   * A seconda delle impostazioni della tua organizzazione e della suite di rapporti: Giornalieri, Settimanali, Mensili e Trimestrali possono essere attivati su questo rapporto.
   * **Tutte le metriche standard ecommerce**: Entrate, ordini, unità, carrelli, visualizzazioni carrello, pagamenti, aggiunte carrello e rimozioni carrello
   * **Tutti gli eventi personalizzati**: Eventi 1-80 e Eventi 81-100 se sul codice H 22 o superiore.

All conversion events in the [!UICONTROL Site Sections Report] use last allocation. La conversione viene visualizzata dividendo in pagine che non contengono eventi di successo all'interno della tua implementazione. This is different than the [Pages Report](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5), which uses linear allocation.

**Informazioni specifiche sui prodotti**

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Interfaccia </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reporting e analisi </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Contenuto del sito</span> &gt; <span class="uicontrol"> Sezioni del sito</span> </p> <p>Oltre alle correlazioni, questo rapporto può utilizzare le seguenti suddivisioni: </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">Eventuali rapporti classificati basati su questo rapporto </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> Report sui codici di tracciamento</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> <span class="wintitle"> Rapporti Prodotti</span> e <span class="wintitle"> categorie</span> </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> Report sulla fedeltà dei clienti</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">Qualsiasi variabile di conversione completamente sottocorrelata </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> Marketing Channels First and Last Touch</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> <span class="uicontrol"> Report Target</span> &gt; <span class="uicontrol"> Campagne</span> (se abilitato) </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">Tempo trascorso per visita </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">Sitesections </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">Pagine di immissione </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">La maggior parte dei rapporti Origini traffico </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">Numero visita </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">Molti rapporti profilo visitatore </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">Tutte le variabili di conversione e le variabili elenco </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">Sono disponibili Visite e Visitatori giornalieri, settimanali, trimestrali e arbitrari arbitrari. </li> 
      </ul> </li> 
    </ul> <p>Questo rapporto può utilizzare segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Analisi ad hoc può suddividere il report Sezioni sito in base sostanzialmente a tutti gli altri rapporti nell'interfaccia del rapporto di marketing. </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">Oltre a tutti gli eventi precedentemente indicati, può utilizzare tutte le metriche di conversione e traffico, nonché utilizzare allocazione diversa per tutte le metriche di conversione. </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">Questo rapporto può utilizzare più segmenti altamente avanzati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

