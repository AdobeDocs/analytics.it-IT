---
description: Puoi creare una nuova suite di rapporti selezionando un modello predefinito, oppure utilizzando una delle suite di rapporti esistenti da distribuire come modello.
seo-description: Puoi creare una nuova suite di rapporti selezionando un modello predefinito, oppure utilizzando una delle suite di rapporti esistenti da distribuire come modello.
seo-title: Nuova suite di rapporti - Impostazioni
solution: Analytics
title: Nuova suite di rapporti - Impostazioni
topic: Strumenti di amministrazione
uuid: 3508 f 684-11 a 3-4 c 8 f-a 233-bea 6 bafd 57 c 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Nuova suite di rapporti - Impostazioni

Puoi creare una nuova suite di rapporti selezionando un modello predefinito, oppure utilizzando una delle suite di rapporti esistenti da distribuire come modello.

Descriptions of the elements used when [creating a report suite](../../../admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md#task_67033B9710CB49F9B71A4DE374A538A0).

>[!NOTE]
>
>The [Virtual Report Suite documentation](/help/components/vrs/c-workflow-vrs/vrs-create.md) shows you how to create virtual report suites.

<table id="table_F739FBD8DB8D409E916F12F61C5953D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> ID suite di rapporti </span> </td> 
   <td colname="col2"> <p>Specifica un ID univoco che può contenere solo caratteri alfanumerici. Questo ID non può essere modificato dopo la creazione. Adobe imposta il prefisso ID richiesto e non può essere modificato. </p> <p>Quando crei più suite di rapporti, assicurati che la convenzione di denominazione che utilizzi garantisca ID di suite di rapporti univoci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Titolo sito</span> </td> 
   <td colname="col2">Identifies the report suite in <span class="wintitle"> Admin Tools</span>. This title is also used in the <span class="wintitle"> Report Suite</span> drop-down list in the suite header. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso orario</span> </td> 
   <td colname="col2"> Pianifica eventi e dati di marca temporale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL di base</span> </td> 
   <td colname="col2"> (Facoltativo) Definisce il dominio di base per la suite di rapporti. Questa funzione URL funziona come filtro URL interno se non definiti in modo esplicito i filtri URL interni per la suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Pagina predefinita</span> </td> 
   <td colname="col2"> <p>(Optional) Strips occurrences of the <span class="wintitle"> Default Page</span> value from URLs it encounters. If your <span class="wintitle"> Most Popular Pages</span> report contains URLs rather than page names, this setting prevents multiple URLs for the same web page. </p> <p>For example, the URLs<span class="filepath"> https://mysite.com</span> and <span class="filepath"> https://mysite.com/index.html</span> are typically the same page. You can remove extraneous filenames so that both these URLs show up as <span class="filepath"> https://mysite.com</span> in your reports. </p> <p>If you do not set this value, Analytics automatically removes the following filenames from URLs: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default.cgi</span>, <span class="filepath"> default.asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home.cgi</span>, and<span class="filepath"> home.asp</span>. </p> <p>Per disattivare il filtro del nome file, specificate un valore Pagina predefinita che non si verifica mai negli URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vai a data live </p> </td> 
   <td colname="col2">Informa Adobe della data in cui si prevede che questa suite di rapporti diventi attiva. If your deployment schedule changes, provide an updated traffic estimate using the <span class="wintitle"> Permanent Expected Traffic</span> tool in <a href="../../../admin/c-traffic-management/traffic-management.md#concept_8BD651EE8B84434CB4D6308BC6C01B79" format="dita" scope="local"> Traffic Management</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Visualizzazioni di pagina stimate al giorno</span> </td> 
   <td colname="col2"> Identifica il numero stimato di visualizzazioni di pagina che si prevede che questa suite di rapporti supporti in un giorno. Volumi di traffico grandi richiedono un processo di approvazione più lungo. Per evitare ritardi di elaborazione, usate il più possibile con questa stima. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Valuta di base</span> </td> 
   <td colname="col2"> <p>Specifica la valuta predefinita utilizzata per memorizzare tutti i dati monetari. Il reporting di Analytics converte le transazioni in altre valute alla valuta di base, utilizzando il tasso di conversione corrente al momento della ricezione dei dati. </p> <p> Analytics reporting uses the <span class="varname"> currencyCode</span> JavaScript variable to identify the currency of a given transaction. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Disabilita supporto caratteri multibyte </span> </td> 
   <td colname="col2"> <p>Disabilita il supporto dei caratteri multibyte per la suite di rapporti. Se disabilitate il supporto dei caratteri multibyte, il sistema presuppone che i dati siano in formato ISO -8859-1. Web pages must specify their character set in the <span class="varname"> charSet</span> JavaScript variable. </p> <p>Il supporto dei caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando UTF -8. Dopo la ricezione, il sistema converte i dati dal set di caratteri della pagina Web al set di caratteri UTF -8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing. </p> <p>Contatta il tuo Account Manager o l'Assistenza clienti per cambiare il supporto dei caratteri multibyte per una suite di rapporti esistente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Attiva Analisi ad hoc per questa suite</span> </td> 
   <td colname="col2"> Abilita la visualizzazione di questa suite di rapporti quando esegui analisi ad hoc. </td> 
  </tr> 
 </tbody> 
</table>

