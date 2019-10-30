---
description: La tabella seguente mostra la mappatura della variabile per il report per le variabili utilizzate per compilare i report di Analytics.
keywords: Implementazione di Analytics
seo-description: La tabella seguente mostra la mappatura della variabile per il report per le variabili utilizzate per compilare i report di Analytics.
seo-title: Variabile per mappatura rapporti
solution: Analytics
title: Variabile per mappatura rapporti
topic: Sviluppatore e implementazione
uuid: fd81f97d-dd1a-47d5-9157-b7932fe13490
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Variabile per mappatura rapporti

La tabella seguente mostra la mappatura della variabile per il report per le variabili utilizzate per compilare i report di Analytics.

Ciascuna variabile è elencata con i rapporti che utilizzano la variabile indicata accanto ad essa.

<table id="table_16443E46AC0E46509F8533D26EDE1BCC"> 
 <thead> 
  <tr> 
   <th class="entry"> Variabile </th> 
   <th class="entry"> Report compilati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> s.pageName </td> 
   <td> <p>Report conversione &gt; Report percorso &gt; Valore pagina </p> <p>Report conversione &gt; Report percorso &gt; Pagina di entrata </p> <p>Rapporti di conversione &gt; Report percorso &gt; Pagine di entrata originali </p> <p>Rapporti sul traffico &gt; Traffico del sito &gt; Visualizzazioni pagina </p> <p>Rapporti sul traffico &gt; Traffico del sito &gt; Visitatori unici orari </p> <p>Rapporti sul traffico &gt; Traffico del sito &gt; Visitatori univoci giornalieri </p> <p>Rapporti sul traffico &gt; Traffico del sito &gt; Visitatori univoci mensili </p> <p>Rapporti sul traffico &gt; Traffico del sito &gt; Visitatori univoci annuali </p> <p>Rapporti sul traffico &gt; Profilo visitatore &gt; Pagine visualizzate dai visitatori principali </p> <p>Rapporti sul traffico &gt; Segmentazione &gt; Pagine più popolari </p> <p>Report percorso &gt; Pagine &gt; Riepilogo pagina </p> <p>Report percorso &gt; Pagine &gt; Valore pagina </p> <p>Report percorso &gt; Pagine &gt; Pagine più popolari </p> <p>Report percorso &gt; Pagine &gt; Ricarica </p> <p>Report percorso &gt; Pagine &gt; Clic sulla pagina </p> <p>Report percorso &gt; Pagine &gt; Tempo trascorso sulla pagina </p> <p>Report percorso &gt; Voci ed uscite &gt; Pagine di entrata </p> <p>Report percorso &gt; Voci ed uscite &gt; Esci da pagine </p> <p>Report percorso &gt; Voci ed uscite &gt; Esci dai collegamenti </p> <p>Rapporti percorso &gt; Percorsi completi &gt; Percorsi completi </p> <p>Report percorso &gt; Percorsi completi &gt; Percorsi più lunghi </p> <p>Rapporti percorso &gt; Percorsi completi &gt; Lunghezza tracciato </p> <p>Report percorso &gt; Percorsi completi &gt; Tempo trascorso per visita </p> <p>Report percorso &gt; Percorsi completi &gt; Visite a pagina singola </p> <p>Report percorso &gt; Analisi avanzata &gt; Pagina precedente </p> <p>Report percorso &gt; Analisi avanzata &gt; Pagina successiva </p> <p>Report percorso &gt; Analisi avanzata &gt; Flusso pagina precedente </p> <p>Report percorso &gt; Analisi avanzata &gt; Flusso pagina successivo </p> <p>Report percorso &gt; Analisi avanzata &gt; PathFinder </p> <p>Report percorso &gt; Analisi avanzata &gt; Abbandono </p> <p> <b></b> NOTA: In tutti i report <span class="wintitle"> Traffico</span> elencati sopra, ad eccezione del report Pagine <span class="wintitle"> più popolari, se la variabile</span> s.pageName <span class="wintitle"></span> non è impostata, viene utilizzato l'URL. </p> </td> 
  </tr> 
  <tr> 
   <td> s.server </td> 
   <td> Rapporti sul traffico &gt; Segmentazione &gt; Server più comuni </td> 
  </tr> 
  <tr> 
   <td> s.pageType </td> 
   <td> Report percorso &gt; Pagine &gt; Pagine non trovate </td> 
  </tr> 
  <tr> 
   <td> s.channel </td> 
   <td> <p>Rapporti di conversione &gt; Rapporti percorso sito &gt; Sezione sito </p> <p>Rapporti sul traffico &gt; Segmentazione &gt; Sezioni del sito più comuni </p> </td> 
  </tr> 
  <tr> 
   <td> s.prop1 - s.prop20 </td> 
   <td> Rapporti sul traffico &gt; Custom Insight &gt; Custom Insight 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.campaign </td> 
   <td> <p>Report conversione &gt; Campagne &gt; Conversione e medie </p> <p>Report conversione &gt; Campagne &gt; Codice tracciamento </p> </td> 
  </tr> 
  <tr> 
   <td> s.state </td> 
   <td> Report di conversione &gt; Profilo visitatore &gt; Stati </td> 
  </tr> 
  <tr> 
   <td> s.zip </td> 
   <td> Report di conversione &gt; Profilo visitatore &gt; Codici postali ZIP </td> 
  </tr> 
  <tr> 
   <td> s.events </td> 
   <td> <p>Report conversione &gt; Acquisti &gt; Conversione e medie </p> <p>Report conversione &gt; Acquisti &gt; Ricavi </p> <p>Report conversione &gt; Acquisti &gt; Ordini </p> <p>Report conversione &gt; Acquisti &gt; Unità </p> <p>Report Conversione &gt; Carrello acquisti &gt; Conversione e medie </p> <p>Report Conversione &gt; Carrello acquisti &gt; Carrello </p> <p>Report conversione &gt; Carrello acquisti &gt; Visualizzazioni carrello </p> <p>Report Conversione &gt; Carrello acquisti &gt; Aggiunte carrello </p> <p>Report Conversione &gt; Carrello acquisti &gt; Rimozioni carrello </p> <p>Report conversione &gt; Carrello acquisti &gt; Checkout </p> <p>Report di conversione &gt; Eventi personalizzati &gt; Evento personalizzato 1-20 </p> <p>Report conversione &gt; Prodotti &gt; Conversione e medie </p> <p>Report di conversione &gt; Prodotti &gt; Vendita incrociata </p> <p>Report di conversione &gt; Prodotti &gt; Categorie </p> <p>Report conversione &gt; Campagne &gt; Conversione e medie </p> <p>Report di conversione &gt; Fedeltà cliente &gt; Fedeltà cliente </p> <p>Report conversione &gt; Ciclo vendite &gt; Giorni prima del primo acquisto </p> <p>Report conversione &gt; Ciclo vendite &gt; Giorni dall'ultimo acquisto </p> <p>Report conversione &gt; Ciclo vendite &gt; Numero visita </p> <p>Report conversione &gt; Ciclo vendite &gt; Clienti giornalieri univoci </p> <p>Report Conversione &gt; Ciclo vendite &gt; Clienti univoci mensili </p> <p>Report conversione &gt; Ciclo vendite &gt; Clienti annuali univoci </p> <p>Report di conversione &gt; Percorso sito &gt; Valore pagina </p> </td> 
  </tr> 
  <tr> 
   <td> s.products </td> 
   <td> <p>Report conversione &gt; Acquisti &gt; Conversione e medie </p> <p>Report conversione &gt; Acquisti &gt; Ricavi </p> <p>Report conversione &gt; Acquisti &gt; Ordini </p> <p>Report conversione &gt; Acquisti &gt; Unità </p> <p>Report Conversione &gt; Carrello acquisti &gt; Conversione e medie </p> <p>Report conversione &gt; Prodotti &gt; Conversione e medie </p> <p>Report di conversione &gt; Prodotti &gt; Vendita incrociata </p> <p>Report di conversione &gt; Prodotti &gt; Categorie </p> <p>Report conversione &gt; Campagne &gt; Conversione e medie </p> <p>Report di conversione &gt; Fedeltà cliente &gt; Fedeltà cliente </p> <p>Report conversione &gt; Ciclo vendite &gt; Giorni prima del primo acquisto </p> <p>Report conversione &gt; Ciclo vendite &gt; Giorni dall'ultimo acquisto </p> <p>Report conversione &gt; Ciclo vendite &gt; Numero visita </p> <p>Report conversione &gt; Ciclo vendite &gt; Clienti giornalieri univoci </p> <p>Report Conversione &gt; Ciclo vendite &gt; Clienti univoci mensili </p> <p>Report conversione &gt; Ciclo vendite &gt; Clienti annuali univoci </p> <p>Report di conversione &gt; Percorso sito &gt; Valore pagina </p> </td> 
  </tr> 
  <tr> 
   <td> s.purchaseID </td> 
   <td> <p>Report conversione &gt; Acquisti &gt; Conversione e medie </p> <p>Report conversione &gt; Acquisti &gt; Ricavi </p> <p>Report conversione &gt; Acquisti &gt; Ordini </p> <p>Report conversione &gt; Acquisti &gt; Unità </p> <p>Report Conversione &gt; Carrello acquisti &gt; Conversione e medie </p> <p>Report conversione &gt; Prodotti &gt; Conversione e medie </p> <p>Report di conversione &gt; Prodotti &gt; Vendita incrociata </p> <p>Report di conversione &gt; Fedeltà cliente &gt; Fedeltà cliente </p> <p>Report conversione &gt; Ciclo vendite &gt; Giorni prima del primo acquisto </p> <p>Report conversione &gt; Ciclo vendite &gt; Giorni dall'ultimo acquisto </p> <p>Report conversione &gt; Ciclo vendite &gt; Numero visita </p> <p>Report conversione &gt; Ciclo vendite &gt; Clienti giornalieri univoci </p> <p>Report Conversione &gt; Ciclo vendite &gt; Clienti univoci mensili </p> <p>Report conversione &gt; Ciclo vendite &gt; Clienti annuali univoci </p> <p>Report di conversione &gt; Percorso sito &gt; Valore pagina </p> </td> 
  </tr> 
  <tr> 
   <td> s.eVar1 - s.eVar20 </td> 
   <td> Report conversione &gt; Variabili personalizzate &gt; eVar cliente 1-20 </td> 
  </tr> 
  <tr> 
   <td> s.linkName </td> 
   <td> Rapporti sul traffico &gt; Custom Insight &gt; Collegamenti personalizzati </td> 
  </tr> 
  <tr> 
   <td> s.hier1 - s.hier5 </td> 
   <td> Rapporti sul traffico &gt; Gerarchie &gt; Gerarchia 1-5 </td> 
  </tr> 
 </tbody> 
</table>

