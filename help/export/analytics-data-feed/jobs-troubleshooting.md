---
description: Se si verifica un errore, viene riportato un errore nella colonna Stato processo.
keywords: Feed dati;processo;risoluzione dei problemi;errore;ftp;chdir;connect;login;put
seo-description: Se si verifica un errore, viene riportato un errore nella colonna Stato processo.
seo-title: Risoluzione dei problemi dei processi
solution: Analytics
title: Risoluzione dei problemi dei processi
uuid: 8fbb914e-03db-434e-b4d3-8594144ff2b7
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Risoluzione dei problemi dei processi

Se si verifica un errore, viene riportato un errore nella colonna Stato processo.

Gli errori e le possibili cause sono elencati di seguito:

<table id="table_BE2921B8E7C94B0EB88774321B8692F0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Errore </th> 
   <th colname="col2" class="entry"> Possibili cause </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Errore Chdir FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_79AB3EA974CC46A0A645A439BC612D88"> 
      <li id="li_4A6A5922275946908E06499E8EAAF18B"> Errore del server di rete o di destinazione </li> 
      <li id="li_33393FF286624A63B12991DCE079841D">Problema di autorizzazione di lettura/scrittura </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Errore di connessione FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5F926078850D4495B83BC938395CAC6B"> 
      <li id="li_A72A357F6289438EA1A091AC4FD3A3D0"> Problema di autenticazione </li> 
      <li id="li_48532C78285E4DB6A47B1435A5FA549B"> Errore del server di rete o di destinazione </li> 
      <li id="li_11DF6FA218CA48539C4561695234CA4D"> Problema di autorizzazione di lettura/scrittura </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Errore FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_020BA1DC81F645FFABCAD07E51351D1E"> 
      <li id="li_8566EECEFD344BFDB638259474A8E8EA"> Limite massimo disco o spazio su disco superato </li> 
      <li id="li_15CD50ED54F846F79BFDF25359864C59"> Errore del server di rete o di destinazione </li> 
      <li id="li_741A3315C0B940D3A9874F15C78B4F28"> Problema di autorizzazione di lettura/scrittura </li> 
      <li id="li_49F707F7F65A443F8AC6E058E3D89B96"> Problema di autenticazione </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Errore di accesso FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_F7F128ADF1FD4E9D8B79424A6432378E"> 
      <li id="li_68C377CAD50346B1B9937B77E7EB2AAD"> Problema di autenticazione </li> 
      <li id="li_7EA91C90FFC0493EA156292620EF1589"> Errore del server di rete o di destinazione </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Errore di caricamento FTP </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_760DA2CBD46B4C348BE3B7B43E803FD9"> 
      <li id="li_6578482722E14E998515B4B3EA370C44"> Limite massimo disco o spazio su disco superato </li> 
      <li id="li_342240DDD9D3423198C23123473D539C"> Errore del server di rete o di destinazione </li> 
      <li id="li_44CEFE1D92A74842A6321C416637421F"> Problema di autorizzazione di lettura/scrittura </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>
