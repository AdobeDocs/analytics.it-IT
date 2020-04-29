---
description: Mostra le aree del sito a cui i visitatori accedono maggiormente. Le sezioni del sito possono includere gruppi di prodotti, simili alle categorie definite dall'utente. Ad esempio, puoi avere un gruppo di pagine Fotocamere, un gruppo Computer e così via. I dati per il report Sezioni sito di conversione vengono importati dal report Sezione sito nel gruppo Traffico, che riceve le informazioni dalla variabile canale nel codice di tracciamento. È possibile utilizzare questo rapporto per identificare l'impatto maggiore sulle statistiche del sito dagli elementi in varie sezioni del sito.
title: Sezione sito
topic: Reports
uuid: 6839c566-f88f-4979-9cf5-52a77c0b0416
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Sezione sito

Mostra le aree del sito a cui i visitatori accedono maggiormente. Le sezioni del sito possono includere gruppi di prodotti, simili alle categorie definite dall&#39;utente. Ad esempio, puoi avere un gruppo di pagine Fotocamere, un gruppo Computer e così via. I dati per il report Sezioni sito di conversione vengono importati dal report Sezione sito nel gruppo Traffico, che riceve le informazioni dalla variabile canale nel codice di tracciamento. È possibile utilizzare questo rapporto per identificare l&#39;impatto maggiore sulle statistiche del sito dagli elementi in varie sezioni del sito.

* Questo rapporto fa riferimento direttamente ai dati della variabile [s.channel](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/channel.html) implementata sul sito Web.
* Questo rapporto può essere visualizzato sia in formato con tendenze che in formato classifica.
* Questo rapporto può utilizzare un filtro di ricerca per individuare specifici elementi di riga.
* Le classificazioni possono essere utilizzate in questo rapporto, consentendo di rinominare e consolidare gli elementi di riga.
* Le correlazioni possono essere create con qualsiasi altra variabile di traffico tramite Strumenti di amministrazione.
* Questo rapporto può utilizzare le metriche seguenti:

   * **Pagevisi**: il numero di volte in cui è stata definita la variabile [pageName](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/pagename.html) o l&#39;URL (impostato come metrica predefinita)

   * **Tutte le metriche** di percorso: Visite, profondità media delle pagine, tempo medio trascorso sulla pagina, voci, uscite, ricariche e accesso singolo
   * A seconda delle impostazioni aziendali e della suite di rapporti: In questo rapporto è possibile abilitare Visitatori univoci giornalieri, settimanali, mensili e trimestrali.
   * **Tutte le metriche** eCommerce standard: Entrate, ordini, unità, carrelli, viste carrello, Checkout, aggiunte carrello e rimozione carrello
   * **Tutti gli eventi** personalizzati: Eventi 1-80 ed Eventi 81-100 se nel codice H22 o versioni successive.

Tutti gli eventi di conversione nell&#39; [!UICONTROL Site Sections Report] ultima allocazione utilizzata. Vedrete la conversione divisa tra le pagine che non contengono eventi di successo all&#39;interno dell&#39;implementazione. È diverso dal report [](/help/components/c-variables/dimensionslist/reports-pages.md)Pagine, che utilizza l&#39;allocazione lineare.

**Informazioni specifiche del prodotto**

<table id="table_525FDF95C8ED4BF2A1E25BE2DA971EFB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Interfaccia </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Contenuto</span> del sito &gt; <span class="uicontrol"> Sezioni del sito</span> </p> <p>Oltre alle correlazioni, questo rapporto può utilizzare le seguenti suddivisioni: </p> 
    <ul id="ul_9CD009D89B134C53807332E3C88D3C44"> 
     <li id="li_566417EB074D425C9A1F4FB28AA7FAB4"> 
      <ul id="ul_3795C7AAE6DA4B7E96FCDC7F3211DFBB"> 
       <li id="li_50B295E961724CFB83D222DE9B4C7FF2">Eventuali rapporti classificati basati su questo rapporto </li> 
       <li id="li_697682892D8841BC8120BEC0E1AE9753"> <span class="wintitle"> Report Codici di tracciamento</span> </li> 
       <li id="li_F6D893FCBA7A4B3EB04715833CA41022"> <span class="wintitle"> Rapporti su prodotti</span> e <span class="wintitle"> categorie</span> </li> 
       <li id="li_9F379E61DB4F4753AE1FFFC8F9C17347"> <span class="wintitle"> Report fedeltà cliente</span> </li> 
       <li id="li_64A6A06F9265410ABB425DA4AF50C440">Qualsiasi variabile di conversione completamente correlata </li> 
       <li id="li_907DDFCC35AB48EEA5B169B4A2598FB1"> <span class="wintitle"> Canali di marketing - Primo e ultimo tocco</span> </li> 
       <li id="li_B08A0DCB40154152AF1033B7629A5B5A"> <span class="uicontrol"> Target</span> &gt; Rapporto <span class="uicontrol"> Campagne</span> (se attivato) </li> 
       <li id="li_6D4E65DD6E2B49C9A8C12181D23F185A">Tempo trascorso per visita </li> 
       <li id="li_C6D3AD5A534243A8A6E17C663FEBA6BA">Sitesections </li> 
       <li id="li_E1F46EED5CE2425D83200A2FCB686EE5">Pagine di entrata </li> 
       <li id="li_1201EE0EBF13476C9A9525E0700F30F3">Rapporti sulla maggior parte delle origini di traffico </li> 
       <li id="li_563E07858FB1473BB22C2B191E8BE620">Numero visita </li> 
       <li id="li_1CAD77ABA6A2454282A4DA7E88C047E8">Molti Rapporti Sul Profilo Dei Visitatori </li> 
       <li id="li_D3A04E4CD8EC4646AAB90BF19F0AFA8A">Tutte le variabili di conversione e di elenco </li> 
       <li id="li_01C194CE0F3E4C0694A34B4C6697F385">Sono disponibili visite e visite univoche giornaliere, settimanali, mensili, trimestrali e arbitrarie. </li> 
      </ul> </li> 
    </ul> <p>Questo rapporto può utilizzare segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis  </td> 
   <td colname="col2"> 
    <ul id="ul_DFF9BFC01FC1424B8905C2D2C0EFD156"> 
     <li id="li_65FDF1C165C84F729E0EE84FF671B5E4">Analisi ad hoc può suddividere il rapporto Sezioni del sito essenzialmente con tutti gli altri rapporti all'interno dell'interfaccia del rapporto di marketing. </li> 
     <li id="li_2159DE10C52D40AA89E4C934FC184641">Oltre a tutti gli eventi precedentemente menzionati, puoi utilizzare tutte le metriche di conversione e traffico, nonché un'allocazione diversa per tutte le metriche di conversione. </li> 
     <li id="li_3A23C6286D314B5D814612469F4F77C5">Questo report può utilizzare più segmenti altamente avanzati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

