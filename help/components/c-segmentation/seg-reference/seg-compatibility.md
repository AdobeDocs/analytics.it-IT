---
description: Non tutti i segmenti creati in Segment Builder (Generatore segmenti) sono compatibili con Data Warehouse. In questa tabella sono elencate le funzioni supportate.
seo-description: Non tutti i segmenti creati in Segment Builder (Generatore segmenti) sono compatibili con Data Warehouse. In questa tabella sono elencate le funzioni supportate.
seo-title: Compatibilità con i segmenti di Data Warehouse
solution: Analytics
title: Compatibilità con i segmenti di Data Warehouse
topic: Segmenti
uuid: 370258 c 5-8614-4434-871 c -41753 ed 77 f 5 c
translation-type: tm+mt
source-git-commit: 26bba9528873c983852754056a5495c4004d25e6

---


# Compatibilità con i segmenti di Data Warehouse

Not all segments created in the Segment Builder are compatible with [!DNL Data Warehouse]. In questa tabella sono elencate le funzioni supportate.

<table id="table_BBB1DAFDF85041598FA4AF869172CF7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> </th> 
   <th colname="col2" class="entry"> Analysis Workspace, Reporting e analisi, Analisi ad hoc </th> 
   <th colname="col3" class="entry"> Data Warehouse </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Excludes</b> </td> 
   <td colname="col2"> Supportato a qualsiasi livello </td> 
   <td colname="col3"> Supportato solo in casi speciali al livello principale </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Segmenti sequenziali</b> </td> 
   <td colname="col2"> Supportate </td> 
   <td colname="col3"> Non supportato </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>AND e OR possono essere combinati senza limiti</b> </td> 
   <td colname="col2"> Supportate </td> 
   <td colname="col3"> Alcune limitazioni </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Contenitori nidificati</b> </td> 
   <td colname="col2"> Supportate </td> 
   <td colname="col3"> Alcune limitazioni (devono diminuire nell'ambito, ad esempio i visitatori possono contenere hit, ma non viceversa) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Dimensioni</b> </td> 
   <td colname="col2">Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions</span> field to find out about its product compatibility. Ad esempio, queste dimensioni sono supportate solo in Analysis Workspace, Reporting e analisi e Analisi ad hoc: 
    <ul id="ul_BD708CC3A16743F49F998D1046EC70A3"> 
     <li id="li_240DA619D50B4336ACD9117BF59AF10A">Server di immissione </li> 
     <li id="li_222D4D4116674EF8A52945CCB9C78719">Categoria di immissione </li> 
     <li id="li_5A43C846E2EA4EFCB892DE9E0607C68C">Data di entrata </li> 
     <li id="li_8E9CABBE04FC4A7A9A5D2BDD34AD3C87">Tutte le classificazioni di ricerca </li> 
    </ul> </td> 
   <td colname="col3"> Drag and drop a dimension into the Segment Builder's <span class="uicontrol"> Definitions</span> field to find out about its product compatibility. Ad esempio, queste dimensioni sono supportate solo in Data Warehouse: 
    <ul id="ul_61A5B314CCCF497DB0385324E3309E22"> 
     <li id="li_1254089BDFAE4E0F8E51CB1511BBBF53">Indirizzo IP </li> 
     <li id="li_D8E040F77A8C46A084547F4FE685CB10">URL della pagina </li> 
     <li id="li_4C79AE900CF6458780C124143DC6FA5B">Visitor ID </li> 
     <li id="li_4EC10645DE9740609D8DDFD4F668FE67">ID visitatore Experience Cloud </li> 
    </ul> <p>The following dimensions <b>cannot </b>be used in Data Warehouse segments: </p> 
    <ul id="ul_FE143F6D1ABF45DAA444E1B5691C7D4F"> 
     <li id="li_E77F3CC45BA04674B857FE5AB19D56F1">Tutte le classificazioni di ricerca </li> 
     <li id="li_95E1549C13F14BA0B32686401EE78E31">AM/PM </li> 
     <li id="li_6F1C8FC2E7674A0CA14B70B65784D896">Giorno del mese </li> 
     <li id="li_79D1A91D741D4CCC937D07906D71F964">Giorno della settimana </li> 
     <li id="li_4008565353084611BD782B98D50C0611">Giorno dell’anno </li> 
     <li id="li_F87D78F125874087BFF74FAAE2BA46F5">Unità aziendale </li> 
     <li id="li_53DA4E64C6714CFF90D164245D01C16A">Voce (Tutte le dimensioni iniziano con Entrata, eccetto Pagina di immissione) </li> 
     <li id="li_7F26B0E54A4A48319F31D8FC499D1CF2">Uscita (tutte le dimensioni iniziano con Uscita, tranne Uscita e Uscita dalla pagina) </li> 
     <li id="li_1877D2D8A95B43F29CAA426BF2FE4996">Gerarchia (Tutte le dimensioni iniziano con la gerarchia) </li> 
     <li id="li_DF0BCC63ED274ABEA1C5A28274936310">Profondità hit </li> 
     <li id="li_98BE56213E1A4FD28D4858D53C46D23E">Tipo di hit </li> 
     <li id="li_52ECB31657DF4180BDB9C8D21CC74313">Giorno ora </li> 
     <li id="li_93716207F2614822ACB84100B35D27BC">Mese dell’anno </li> 
     <li id="li_FFC8E1F7092C4876A7E9F2365CC234B9">Pagine non trovate </li> 
     <li id="li_7A070C8E0F664F5AB554555B17D0E4E6">Ricerca pagata </li> 
     <li id="li_12228C18BF90463C8D8394FB810843D3">Trimestre dell’anno </li> 
     <li id="li_1833B6E2011C4757A60CAA2C98B35AFA">Restituisci frequenza </li> 
     <li id="li_39154CD74A534D9AA09C701FE1E2C521">Visite a pagina singola </li> 
     <li id="li_84BDE34DD577488881E8842D2DE72D3C">Tempo precedente all'evento </li> 
     <li id="li_552BE3414CC949B3B24BE99298945874">Tempo trascorso sulla pagina - Piegato </li> 
     <li id="li_33D815E04CB3493C82BE33E958C2D7B9">Tempo trascorso per visita - Perforato </li> 
     <li id="li_76F2BB88B8CD456DB50D04F36BB7854B">Motivo di rifiuto del tracciamento </li> 
     <li id="li_07345E08D0584CEC99128A0542587019">Stati Uniti </li> 
     <li id="li_3D6BD9E927334B9BBC29E602D1103F7A">Settimana/fine settimana </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Sovrapposizione segmenti</b> </td> 
   <td colname="col2"> Supportate </td> 
   <td colname="col3"> Non supportato </td> 
  </tr> 
 </tbody> 
</table>

