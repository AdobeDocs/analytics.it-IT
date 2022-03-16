---
description: Per creare una nuova suite di rapporti, puoi selezionare un modello preimpostato o utilizzare come modello una suite di rapporti esistente.
title: 'Nuova suite di rapporti: impostazioni'
feature: Report Suite Settings
uuid: 3508f684-11a3-4c8f-a233-bea6bafd57c0
exl-id: ea5f8543-058d-4e08-bc66-575e3a7460c2
source-git-commit: 72bd67179e003b70233d863d34153fec77548256
workflow-type: ht
source-wordcount: '535'
ht-degree: 100%

---

# Nuova suite di rapporti: impostazioni

Per creare una nuova suite di rapporti, puoi selezionare un modello preimpostato o utilizzare come modello una suite di rapporti esistente.

Descrizioni degli elementi utilizzati per [creare una suite di rapporti](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md).

>[!NOTE]
>
>La [documentazione delle suite di rapporti virtuali](/help/components/vrs/c-workflow-vrs/vrs-create.md) mostra come creare suite di rapporti virtuali.

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
   <td colname="col2"> <p>Specifica un ID univoco; può contenere solo caratteri alfanumerici. Una volta creato, non è possibile modificare questo ID. Adobe imposta il prefisso ID richiesto, che non può essere modificato. </p> <p>Quando crei più suite di rapporti, assicurati di usare una convenzione di denominazione tale da garantire ID univoci per le suite di rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Titolo sito</span> </td> 
   <td colname="col2">Identifica la suite di rapporti negli <span class="wintitle"> strumenti di amministrazione</span>. Questo titolo viene utilizzato anche nell’elenco a discesa <span class="wintitle"> Suite di rapporti</span> nell’intestazione della suite. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Fuso orario</span> </td> 
   <td colname="col2"> Determina eventi e dati di marca temporale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> URL di base</span> </td> 
   <td colname="col2"> (Facoltativo) Definisce il dominio di base per la suite di rapporti. Questo URL funziona come filtro URL interno se non definisci esplicitamente i filtri URL interni per la suite di rapporti. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Pagina predefinita</span> </td> 
   <td colname="col2"> <p>(Facoltativo) Elimina le occorrenze del valore <span class="wintitle"> Pagina predefinita</span> dagli URL rilevati. Se il rapporto <span class="wintitle"> Pagine più popolari</span> contiene URL anziché nomi di pagina, impedisce l’utilizzo di più URL per la stessa pagina web. </p> <p>Ad esempio, gli URL <span class="filepath">https://example.com</span> e <span class="filepath">https://example.com/index.html</span> corrispondono in genere alla stessa pagina. Puoi rimuovere i nomi di file estranei in modo che, nei rapporti, entrambi questi URL vengano visualizzati come <span class="filepath">https://example.com</span>. </p> <p>Se non imposti questo valore, Analytics rimuove automaticamente i seguenti nomi di file dagli URL: <span class="filepath"> index.htm</span>, <span class="filepath"> index.html</span>, <span class="filepath"> index.cgi</span>, <span class="filepath"> index.asp</span>, <span class="filepath"> default.htm</span>, <span class="filepath"> default.html</span>, <span class="filepath"> default.cgi</span>, <span class="filepath"> default.asp</span>, <span class="filepath"> home.htm</span>, <span class="filepath"> home.html</span>, <span class="filepath"> home.cgi</span> e<span class="filepath"> home.asp</span>. </p> <p>Per disabilitare la rimozione del nome file, specifica un valore di pagina predefinito che non si verifica mai negli URL. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data pubblicazione </p> </td> 
   <td colname="col2">Informa Adobe della data in cui la suite di rapporti diventerà attiva. Se la pianificazione dell’implementazione cambia, fornisci una stima del traffico aggiornata utilizzando lo strumento <span class="wintitle"> Traffico previsto permanente</span> in <a href="/help/admin/c-traffic-management/traffic-management.md"> Gestione del traffico</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Visualizzazioni pagina stimate al giorno</span> </td> 
   <td colname="col2"> Identifica una stima del numero di visualizzazioni di pagina che la suite di rapporti supporterà in un giorno. Volumi di traffico elevati richiedono un processo di approvazione più lungo. Per evitare ritardi nell’elaborazione, specifica una stima che sia quanto più accurata possibile. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Valuta di base</span> </td> 
   <td colname="col2"> <p>Specifica la valuta predefinita utilizzata per memorizzare tutti i dati monetari. La funzione di reporting di Analytics converte le transazioni in altre valute nella valuta di base, utilizzando il tasso di conversione corrente al momento in cui riceve i dati. </p> <p> Per identificare la valuta di una determinata transazione, la funzione di reporting di Analytics utilizza la variabile JavaScript <span class="varname"> currencyCode</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Disabilita supporto caratteri multibyte </span> </td> 
   <td colname="col2"> <p>Disattiva il supporto di caratteri multibyte per la suite di rapporti. Se disattivi il supporto per caratteri multibyte, il sistema presuppone che i dati siano in formato ISO-8859-1. Il set di caratteri delle pagine web deve essere specificato nella variabile JavaScript <span class="varname"> charSet</span>. </p> <p>Il supporto per caratteri multibyte memorizza i caratteri nella suite di rapporti utilizzando il formato UTF-8. Al momento della ricezione, il sistema converte i dati dal set di caratteri della pagina web al set di caratteri UTF-8, in modo da poter utilizzare qualsiasi lingua nei rapporti di marketing. </p> <p>Per modificare il supporto dei caratteri multibyte per una suite di rapporti esistente, contatta il tuo Account Manager o l’Assistenza clienti. </p> </td> 
  </tr>  
 </tbody> 
</table>
