---
description: Visualizza una suddivisione delle parole chiave di ricerca.
solution: Analytics
title: Parole chiave di ricerca
topic: Reports
uuid: db9d477b-b711-4b93-9c25-3aebe5f2ace6
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Parole chiave di ricerca

Visualizza una suddivisione delle parole chiave di ricerca.

**Cerca parole chiave - Tutto**: Visualizza una suddivisione di ogni parola chiave di ricerca utilizzata per trovare il sito. Potete ordinare l’elenco per visualizzazioni di pagina o per parole chiave di ricerca facendo clic sul titolo della colonna sopra l’elenco. Fai clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il tuo sito.

**Cerca parole chiave - A pagamento**: Visualizza una suddivisione di ogni parola chiave di ricerca a pagamento utilizzata per trovare il sito. Potete ordinare l’elenco per visualizzazioni di pagina o per parole chiave di ricerca facendo clic sul titolo della colonna sopra l’elenco. Fai clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il tuo sito.

**Cerca parole chiave - Naturale**: Visualizza una suddivisione di ogni parola chiave di ricerca naturale utilizzata per trovare il sito. Potete ordinare l’elenco per visualizzazioni di pagina o per parole chiave di ricerca facendo clic sul titolo della colonna sopra l’elenco. Fai clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il tuo sito.

>[!IMPORTANT]
>
>Per la ricerca a pagamento e naturale, i motori di ricerca hanno smesso di fornire (nella maggior parte dei casi) le parole chiave di ricerca come parte del referente. Di conseguenza, Adobe classifica sempre il dominio Google (o Bing, o Yahoo) come ricerca. In base al formato e al contenuto del referente (anche senza le parole chiave), Adobe può determinare spesso che si tratti del risultato di una ricerca, pertanto la ricerca viene conteggiata con Parole chiave non disponibili. [Altro...](https://helpx.adobe.com/analytics/kb/keyword-unavailable.html)

## Assegnazione, scadenza e valori speciali {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> <p>Analysis Workspace </p> <p>Reporting e analisi </p> </th> 
   <th colname="col3" class="entry"> Ad Hoc Analysis </th> 
   <th colname="col4" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Allocazione metrica </td> 
   <td colname="col2"> <p>Valore originale (predefinito) </p> <p> Può essere modificato in lineare. </p> </td> 
   <td colname="col3"> Più recente (può essere modificato in lineare utilizzando la versione lineare di un metic) </td> 
   <td colname="col4"> <p>Valore originale (predefinito) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> I valori scadono dopo </td> 
   <td colname="col2"> Visita - può essere ridotta ma non allungata </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limiti valore </td> 
   <td colname="col2"> Nessun limite (potrebbe essere modificato in una versione futura) </td> 
   <td colname="col3"> Nessun limite (potrebbe essere modificato in una versione futura) </td> 
   <td colname="col4"> none </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori speciali </td> 
   <td colname="col2"> <p>"None": totali a livello di sito che non avevano una parola chiave durante la visita. </p> Per "Parola chiave non disponibile" si intendono le ricerche nelle aree in cui la parola chiave è stata rimossa dalla ricerca e non viene inviata alla raccolta di dati. Ciò si verifica in genere quando un cliente accede a un account Google. Si applica a pagato e naturale. </td> 
   <td colname="col3"> (traffico limitato) rappresenta valori oltre i primi 500 k che non hanno ricevuto abbastanza traffico per essere segnalati. </td> 
   <td colname="col4"> <p> Vuoto - equivalente a "None" (Nessuno), totali per tutto il sito che non avevano una parola chiave durante la visita. </p> <p>Per "Parola chiave non disponibile" si intendono le ricerche nelle aree in cui la parola chiave è stata rimossa dalla ricerca e non viene inviata alla raccolta di dati. Ciò si verifica in genere quando un cliente accede a un account Google. Si applica a pagato e naturale. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cronologia report {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Data | Modifica |
|---|---|
| 1/16/2014 | Il data warehouse è stato aggiornato in base alla logica utilizzata da reporting e analisi di marketing. Prima di tale data, le parole chiave di ricerca non restavano invariate durante la visita. |

