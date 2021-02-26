---
description: Puoi creare una nuova suite di rapporti selezionando un modello predefinito o utilizzando una delle suite di rapporti esistenti come modello.
title: 'Nuova suite di rapporti: impostazioni'
topic: Strumenti di amministrazione
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 3%

---


# Nuova suite di rapporti: impostazioni

Puoi creare una nuova suite di rapporti selezionando un modello predefinito o utilizzando una delle suite di rapporti esistenti come modello.

Descrizioni degli elementi utilizzati durante la [creazione di una suite di rapporti](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>La [documentazione della suite di rapporti virtuale](/help/components/vrs/c-workflow-vrs/vrs-create.md) mostra come creare suite di rapporti virtuali.

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
   <td colname="col2"> <p>Specifica un ID univoco che può contenere solo caratteri alfanumerici. Questo ID non può essere modificato dopo che è stato creato.  Adobe imposta il prefisso ID richiesto e non può essere modificato. </p> <p>Quando crei più suite di rapporti, accertati che la convenzione di denominazione utilizzata garantisca ID univoci per le suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Titolo del sito</span> </td> 
   <td colname="col2">Identifica la suite di rapporti in <span class="wintitle"> Strumenti di amministrazione</span>. Questo titolo viene utilizzato anche nell'elenco a discesa <span class="wintitle"> Suite di rapporti</span> nell'intestazione della suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso orario</span> </td> 
   <td colname="col2"> Pianifica eventi e dati di marca temporale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL di base</span> </td> 
   <td colname="col2"> (Facoltativo) Definisce il dominio di base per la suite di rapporti. Questo URL funge da filtro URL interno se non si definiscono in modo esplicito filtri URL interni per la suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Pagina predefinita</span> </td> 
   <td colname="col2"> <p>(Facoltativo) Rimuove le occorrenze del valore <span class="wintitle"> Pagina predefinita</span> dagli URL che incontra. Se il rapporto <span class="wintitle"> Pagine più popolari</span> contiene URL anziché nomi di pagina, questa impostazione impedisce l'utilizzo di più URL per la stessa pagina Web. </p> <p>Ad esempio, gli URL<span class="filepath"> https://example.com</span> e <span class="filepath"> https://example.com/index.html</span> sono in genere la stessa pagina. Potete rimuovere i nomi file estranei in modo che entrambi gli URL vengano visualizzati come <span class="filepath"> https://example.com</span> nei rapporti. </p> <p>Se non imposti questo valore, Analytics rimuove automaticamente i seguenti nomi file dagli URL: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default.cgi</span>, <span class="filepath"> default.asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home.cgi</span> e&lt;a2 2/&gt; home.asp</span>.<span class="filepath"> </span></p> <p>Per disattivare lo stripping del nome file, specificate un valore Pagina predefinita che non si verifica mai negli URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vai alla data in diretta </p> </td> 
   <td colname="col2"> Adobe della data prevista per l'attivazione della suite di rapporti. Se la pianificazione di distribuzione cambia, fornite una stima del traffico aggiornata utilizzando lo strumento <span class="wintitle"> Traffico previsto permanente</span> in <a href="/help/admin/c-traffic-management/traffic-management.md"> Gestione traffico</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Viste stimate per pagina al giorno</span> </td> 
   <td colname="col2"> Identifica il numero stimato di visualizzazioni di pagina che la suite di rapporti supporterà in un giorno. I grandi volumi di traffico richiedono un processo di approvazione più lungo. Per evitare ritardi nell'elaborazione, con questa stima, essere il più accurato possibile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Valuta di base</span> </td> 
   <td colname="col2"> <p>Specifica la valuta predefinita utilizzata per memorizzare tutti i dati monetari. Il reporting di Analytics converte le transazioni in altre valute nella valuta di base, utilizzando il tasso di conversione corrente al momento in cui riceve i dati. </p> <p> Per la generazione dei rapporti di Analytics viene utilizzata la variabile JavaScript <span class="varname"> currencyCode</span> per identificare la valuta di una determinata transazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Disattiva supporto caratteri multibyte  </span> </td> 
   <td colname="col2"> <p>Disattiva il supporto di più caratteri per la suite di rapporti. Se disattivate il supporto per più caratteri, il sistema presuppone che i dati siano in formato ISO-8859-1. Le pagine Web devono specificare il relativo set di caratteri nella variabile JavaScript <span class="varname"> charSet</span>. </p> <p>Il supporto dei caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando UTF-8. Dopo la ricezione, il sistema converte i dati dal set di caratteri della pagina Web al set di caratteri UTF-8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing. </p> <p>Contatta il tuo Account Manager o l'Assistenza clienti per modificare il supporto dei caratteri multibyte per una suite di rapporti esistente. </p> </td> 
  </tr>  
 </tbody> 
</table>

