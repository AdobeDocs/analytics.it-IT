---
description: Tracciando e registrando i siti di riferimento dei visitatori per ogni visita, puoi determinare in che modo i visitatori hanno scoperto il sito per ogni visita.
solution: Analytics
title: Tipo di riferimento
topic: Reports
uuid: 7f63d327-d223-4537-a722-4780aae05c2b
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tipo di riferimento

Tracciando e registrando i siti di riferimento dei visitatori per ogni visita, puoi determinare in che modo i visitatori hanno scoperto il sito per ogni visita.

L'elenco seguente definisce i vari tipi di referenti:

**Altri siti web**: i referenti vengono registrati quando i visitatori fanno clic su un collegamento situato su una pagina di un altro sito Web (non definito come parte del sito) e arrivano al sito Web.

**Motori** di ricerca:I referenti del motore di ricerca vengono registrati quando i visitatori accedono al sito tramite un motore di ricerca. Il valore di riferimento deve essere considerato da Adobe come un motore di ricerca e non può essere un sottodominio che non viene considerato un motore di ricerca (ad es. [!DNL mail.yahoo.com] non è un motore di ricerca, in quanto questo dominio viene utilizzato per le e-mail).

**[!UICONTROL Social networks]**: Il valore di riferimento deve essere considerato da Adobe come un social network. Consultate [Elenco dei social network](https://helpx.adobe.com/analytics/kb/list-social-networks.html).

**E-mail**: Un dominio di riferimento è considerato come un dominio di provenienza e-mail quando i visitatori fanno clic su un collegamento di messaggio e-mail contenente il protocollo [!DNL imap://] o [!DNL mail://] e arrivano sul sito. Ad esempio, qualsiasi cosa proveniente da [!DNL https://mail.yahoo.com] viene conteggiata come referente e-mail perché il protocollo è [!DNL https://]. Le e-mail di Outlook vengono riportate nella riga Typed/Bookmarked, mentre qualsiasi referente con un protocollo HTTP in cui il dominio è un motore di ricerca noto viene riportato nella riga Motore di ricerca.

**Digitato/Segnalibro**: i referenti vengono registrati quando i visitatori digitano l’URL del sito direttamente nel browser o se accedono al sito selezionando i segnalibri. I dispositivi mobili segnalano un tipo di referente *`typed/bookmarked`* se non è presente alcun referente sul primo hit della visita.

**[!UICONTROL Inside Your Site]**: Questi elementi sono URL ai quali vengono assegnati tag dai filtri URL interni. Questi elementi non vengono contati come *`referrer instances`* ma possono essere visualizzati durante la generazione di rapporti su altre metriche.

## Tipi di referente per interfaccia {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reporting e analisi di marketing (SiteCatalyst) </th> 
   <th colname="col3" class="entry"> Analisi ad hoc </th> 
   <th colname="col4" class="entry"> Data warehouse </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tipi di referente segnalati </td> 
   <td colname="col2"> 
    <ul id="ul_EFC8E81EC6DF4CC2AC0E290244FD5859"> 
     <li id="li_686FCAEB04054B9F8A7D2434E8C49F04">Altri siti Web </li> 
     <li id="li_C232868230AA4A54958B524F3D8FDA35"> Motori di ricerca </li> 
     <li id="li_A89BFD0468F74ED7822F64BE4A7332AE"> Social </li> 
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> Digitato/Segnalato </li> 
    </ul> <p> Questo rapporto visualizza solo due metriche predefinite: Istanze e Visitatori unici. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">Altri siti Web </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> Motori di ricerca </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> Digitato/Segnalato </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">Altri siti Web </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> Motori di ricerca </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> Digitato/Segnalato </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> All'interno del sito </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Note {#section_B83A3571D64E4E7792712FAF740D7955}

* Il referente, il tipo di referente e il dominio di provenienza vengono impostati sul primo hit della visita o durante una visita quando il referente è esterno (ad esempio, se un visitatore lascia il sito, utilizza un motore di ricerca e quindi ritorna al sito prima della scadenza della prima visita). Questi valori vengono impostati allo stesso tempo e persistono per tutta la visita.
* Non tutti i tipi di referente sono elencati in questo rapporto. Ciò significa che le visite a livello di sito non corrispondono alle visite in questo rapporto.

## Cronologia report {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Data | Modifica |
|---|---|
| 1/16/2014 | Il data warehouse è stato aggiornato in base alla logica utilizzata da reporting e analisi di marketing. Prima di tale data, il tipo di referente non era persistente per tutta la visita. |

