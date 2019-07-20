---
description: Tracciando e registrando i siti di riferimento dei visitatori per ogni visita, potete determinare in che modo i visitatori hanno scoperto il sito per ogni visita.
seo-description: Tracciando e registrando i siti di riferimento dei visitatori per ogni visita, potete determinare in che modo i visitatori hanno scoperto il sito per ogni visita.
seo-title: Tipo referente
solution: Analytics
title: Tipo referente
topic: Rapporti
uuid: 7 f 63 d 327-d 223-4537-a 722-4780 aae 05 c 2 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Tipo referente

Tracciando e registrando i siti di riferimento dei visitatori per ogni visita, potete determinare in che modo i visitatori hanno scoperto il sito per ogni visita.

L'elenco seguente definisce i vari tipi di referenti:

**Altri siti Web**: i referenti vengono registrati quando i visitatori fanno clic su un collegamento situato in una pagina su un altro sito Web (non definito come parte del sito) e arrivano sul sito Web.

**Motori di ricerca**: I referenti del motore di ricerca vengono registrati quando i visitatori utilizzano un motore di ricerca per accedere al sito. The referring value must be considered by Adobe to be a search engine, and cannot be a subdomain that is not considered a search engine (e.g. [!DNL mail.yahoo.com] is not a search engine since this domain is used for email).

**[!UICONTROL Social networks]**: Il valore di riferimento deve essere considerato da Adobe come una rete social network. See [List of social networks](https://helpx.adobe.com/analytics/kb/list-social-networks.html).

**E-mail**: Un dominio di riferimento viene considerato come dominio di riferimento e-mail quando i visitatori fanno clic sul collegamento di un messaggio inviato via e-mail contenente il protocollo [!DNL imap://] o [!DNL mail://] arrivano sul sito. For example, anything coming from [!DNL https://mail.yahoo.com] is not counted as an email referrer because the protocol is [!DNL https://]. Le e-mail di Outlook sono riportate nella riga Typed/Bookmarked, mentre qualsiasi referente con un protocollo HTTP in cui il dominio è un motore di ricerca noto è riportato nella riga Motore di ricerca.

**Inserito/con segnalibro**: i referenti vengono registrati quando i visitatori digitano l'URL del sito direttamente nel browser oppure se accedono al sito selezionando segnalibri. Mobile devices report a referrer type of *`typed/bookmarked`* if there is no referrer on the first hit of the visit.

**[!UICONTROL Inside Your Site]**: Questi elementi sono URL con tag dai filtri URL interni. These items are not counted as *`referrer instances`* but can be seen when reporting on other metrics.

## Referrer Types by Interface {#section_4D8CE5E111DD48FBBDCF9B5A1F16E92E}

<table id="table_EC7423532C7E44DE97B7FC0321585A2B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Reporting e analisi di marketing (sitecatalyst) </th> 
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
     <li id="li_C824E6F7F6E748DD827A95B105ADBADD"> Inserito/con segnalibro </li> 
    </ul> <p> Questo rapporto visualizza solo due metriche predefinite: Istanze e Visitatori univoci. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_FD81EB3C1BD949A39C5A9E9688D25271"> 
     <li id="li_6099E7E03F3843D484808258A332BBE9">Altri siti Web </li> 
     <li id="li_5AABC02DA7964D578BF8404DA819245D"> Motori di ricerca </li> 
     <li id="li_B18907AC7FA1429A893B57634EB7DC6F"> Social </li> 
     <li id="li_7674B67897994E1FA99BCD9B604BCB6E"> Inserito/con segnalibro </li> 
    </ul> </td> 
   <td colname="col4"> 
    <ul id="ul_C37ADBEC31D04295BF5CDEA25DB5191A"> 
     <li id="li_81A642C96C674669BA00B2DACA534B8A">Altri siti Web </li> 
     <li id="li_29B9DA9F2AAD46A69886D34D5E6E43D4"> Motori di ricerca </li> 
     <li id="li_E381EEF111F248F99EE39600D616B7C2"> Social </li> 
     <li id="li_596377F4D3C248BEA5191EE2985A2B13"> Inserito/con segnalibro </li> 
     <li id="li_A7A72D3D6B9A4CCFB43EDA77ABFDEDBC"> All'interno del sito </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Note {#section_B83A3571D64E4E7792712FAF740D7955}

* Il referente, il tipo di referente e il dominio di provenienza sono impostati al primo hit della visita, oppure durante una visita quando il referente è esterno (ad esempio, se un visitatore lascia il sito, utilizza un motore di ricerca, quindi ritorna al sito prima della scadenza della prima visita). Questi valori vengono impostati contemporaneamente e persistono nella visita.
* Non tutti i tipi di referrer sono elencati in questo rapporto. Ciò significa che le visite al sito non corrispondono alle visite su questo rapporto.

## Report History {#section_6C0FCEA9DAF04D97BA056E153B7E4628}

| Data | Modifica |
|---|---|
| 1/16/2014 | Data warehouse è stato aggiornato per corrispondere alla logica utilizzata da reporting e analisi di marketing. Prima di questa data, il tipo di referente non era persistente nella visita. |

