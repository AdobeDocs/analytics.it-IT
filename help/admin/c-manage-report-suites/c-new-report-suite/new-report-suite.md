---
description: Puoi creare una nuova suite di rapporti selezionando un modello predefinito o utilizzando una delle suite di rapporti esistenti come modello.
seo-description: Puoi creare una nuova suite di rapporti selezionando un modello predefinito o utilizzando una delle suite di rapporti esistenti come modello.
seo-title: 'Nuova suite di rapporti: impostazioni'
solution: Analytics
title: 'Nuova suite di rapporti: impostazioni'
topic: Strumenti di amministrazione
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Nuova suite di rapporti: impostazioni

Puoi creare una nuova suite di rapporti selezionando un modello predefinito o utilizzando una delle suite di rapporti esistenti come modello.

Descrizioni degli elementi utilizzati per [creare una suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)di rapporti.

> [!NOTE] La documentazione [della suite di rapporti](/help/components/vrs/c-workflow-vrs/vrs-create.md) virtuale illustra come creare suite di rapporti virtuali.

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
   <td colname="col2"> <p>Specifica un ID univoco che può contenere solo caratteri alfanumerici. Questo ID non può essere modificato dopo la creazione. Adobe imposta il prefisso ID richiesto e non può essere modificato. </p> <p>Quando crei più suite di rapporti, assicurati che la convenzione di denominazione utilizzata garantisca ID univoci per le suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Titolo sito</span> </td> 
   <td colname="col2">Identifica la suite di rapporti in <span class="wintitle"> Strumenti</span>di amministrazione. Questo titolo viene utilizzato anche nell’elenco a discesa <span class="wintitle"> Report Suite</span> (Suitedi rapporti) nell’intestazione della suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso orario</span> </td> 
   <td colname="col2"> Pianifica eventi e dati di marca temporale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL di base</span> </td> 
   <td colname="col2"> (Facoltativo) Definisce il dominio di base per la suite di rapporti. Questo URL funge da filtro URL interno se non si definiscono esplicitamente filtri URL interni per la suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Pagina predefinita</span> </td> 
   <td colname="col2"> <p>(Facoltativo) Rimuove le occorrenze del valore Pagina <span class="wintitle"></span> predefinita dagli URL che incontra. Se il rapporto Pagine <span class="wintitle"></span> più popolari contiene URL invece dei nomi di pagina, questa impostazione impedisce l'utilizzo di più URL per la stessa pagina Web. </p> <p>Ad esempio, gli URL<span class="filepath"> https://mysite.com</span> e <span class="filepath"> https://mysite.com/index.html</span> sono in genere la stessa pagina. Potete rimuovere i nomi file estranei in modo che entrambi gli URL vengano visualizzati come <span class="filepath"> https://mysite.com</span> nei rapporti. </p> <p>Se non imposti questo valore, Analytics rimuove automaticamente i seguenti nomi file dagli URL: <span class="filepath"> index.html</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span><span class="filepath"></span>, default.html, default.htmlpredefinito.cgi, default.cgi, default.cgi.html, home.cgi.htmle htmhome.asp. </p> <p>Per disattivare lo stripping del nome file, specificate un valore Pagina predefinita che non si verifica mai negli URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Vai alla data in diretta </p> </td> 
   <td colname="col2">Indica ad Adobe la data prevista per l'attivazione di questa suite di rapporti. Se la pianificazione della distribuzione cambia, fornite una stima del traffico aggiornata utilizzando lo strumento <span class="wintitle"> Traffic</span> previsto permanente in <a href="/help/admin/c-traffic-management/traffic-management.md"> Traffic Management</a>(Gestionetraffico). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Viste stimate per pagina al giorno</span> </td> 
   <td colname="col2"> Identifica il numero stimato di visualizzazioni di pagina che la suite di rapporti supporterà in un giorno. I grandi volumi di traffico richiedono un processo di approvazione più lungo. Per evitare ritardi nell'elaborazione, con questa stima, essere il più accurato possibile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Valuta di base</span> </td> 
   <td colname="col2"> <p>Specifica la valuta predefinita utilizzata per memorizzare tutti i dati monetari. Il reporting di Analytics converte le transazioni in altre valute nella valuta di base, utilizzando il tasso di conversione corrente al momento in cui riceve i dati. </p> <p> I report di analisi utilizzano la variabile JavaScript <span class="varname"> currencyCode</span> per identificare la valuta di una determinata transazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Disattiva supporto caratteri multibyte </span> </td> 
   <td colname="col2"> <p>Disattiva il supporto di più caratteri per la suite di rapporti. Se disattivate il supporto per più caratteri, il sistema presuppone che i dati siano in formato ISO-8859-1. Le pagine Web devono specificare il relativo set di caratteri nella variabile JavaScript <span class="varname"> charSet</span> . </p> <p>Il supporto dei caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando UTF-8. Dopo la ricezione, il sistema converte i dati dal set di caratteri della pagina Web al set di caratteri UTF-8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing. </p> <p>Contatta il tuo Account Manager o l'Assistenza clienti per modificare il supporto dei caratteri multibyte per una suite di rapporti esistente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Attiva Analisi ad hoc per questa suite</span> </td> 
   <td colname="col2"> Abilita la visualizzazione di questa suite di rapporti quando esegui analisi ad hoc. </td> 
  </tr> 
 </tbody> 
</table>

