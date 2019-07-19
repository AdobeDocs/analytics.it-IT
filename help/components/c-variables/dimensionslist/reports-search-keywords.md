---
description: Visualizza una suddivisione delle parole chiave di ricerca.
seo-description: Visualizza una suddivisione delle parole chiave di ricerca.
seo-title: Ricerca parole chiave
solution: Analytics
title: Ricerca parole chiave
topic: Rapporti
uuid: db 9 d 477 b-b 711-4 b 93-9 c 25-3 aebe 5 f 2 ace 6
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Ricerca parole chiave

Visualizza una suddivisione delle parole chiave di ricerca.

**Ricerca parole chiave - Tutto**: Visualizza una suddivisione di ciascuna parola chiave di ricerca utilizzata per trovare il sito. Per ordinare questo elenco in base alle visualizzazioni di pagina o alle parole chiave di ricerca, fai clic sul titolo della colonna sopra l'elenco. Fate clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il sito.

**Cerca parole chiave - Pagato**: Visualizza una suddivisione di ciascuna parola chiave di ricerca pagata utilizzata per trovare il tuo sito. Per ordinare questo elenco in base alle visualizzazioni di pagina o alle parole chiave di ricerca, fai clic sul titolo della colonna sopra l'elenco. Fate clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il sito.

**Parole chiave ricerca - Naturale**: Visualizza una suddivisione di ciascuna parola chiave di ricerca naturale utilizzata per trovare il sito. Per ordinare questo elenco in base alle visualizzazioni di pagina o alle parole chiave di ricerca, fai clic sul titolo della colonna sopra l'elenco. Fate clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il sito.

>[!IMPORTANT]
>
>Per la ricerca pagata e naturale, i motori di ricerca cessavano di fornire (nella maggior parte dei casi) le parole chiave di ricerca come parte del referente. Di conseguenza, Adobe classifica sempre il dominio Google (o Bing o Yahoo) come ricerca. In base al formato e al contenuto del referente (anche senza le parole chiave), Adobe può determinare spesso che è il risultato di una ricerca, quindi la ricerca viene conteggiata con le parole chiave non disponibili. [Altro...](https://helpx.adobe.com/analytics/kb/keyword-unavailable.html)

## Allocation, Expiration, and Special Values {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

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
   <td colname="col2"> <p>Valore originale (predefinito) </p> <p> Può essere cambiato in lineare. </p> </td> 
   <td colname="col3"> Più recente (può essere cambiato in lineare utilizzando la versione lineare di una metrica) </td> 
   <td colname="col4"> <p>Valore originale (predefinito) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori scaduti dopo </td> 
   <td colname="col2"> Visita: può essere abbreviata ma non estesa </td> 
   <td colname="col3"> Visita </td> 
   <td colname="col4"> Visita </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limiti valore </td> 
   <td colname="col2"> Nessun limite (potrebbe subire modifiche in una release futura) </td> 
   <td colname="col3"> Nessun limite (potrebbe subire modifiche in una release futura) </td> 
   <td colname="col4"> none </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori speciali </td> 
   <td colname="col2"> <p>" None ": totali del sito che non avevano una parola chiave durante la visita. </p> «Parola chiave non disponibile»: consente di effettuare ricerche in cui la parola chiave è stata rimossa dalla ricerca e non viene inviata alla raccolta dati. Ciò si verifica in genere quando un cliente ha effettuato l'accesso a un account Google. Si applica a paid and natural. </td> 
   <td colname="col3"> (basso traffico) rappresenta valori oltre i primi 500 k che non hanno ricevuto traffico sufficiente per essere segnalati. </td> 
   <td colname="col4"> <p> Vuoto - equivalente di "None" (Nessuno), totali del sito che non avevano una parola chiave durante la visita. </p> <p>«Parola chiave non disponibile»: consente di effettuare ricerche in cui la parola chiave è stata rimossa dalla ricerca e non viene inviata alla raccolta dati. Ciò si verifica in genere quando un cliente ha effettuato l'accesso a un account Google. Si applica a paid and natural. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Report History {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Data | Modifica |
|---|---|
| 1/16/2014 | Data warehouse è stato aggiornato per corrispondere alla logica utilizzata da reporting e analisi di marketing. Prima di questa data, le parole chiave di ricerca non venivano mantenute nella visita. |

