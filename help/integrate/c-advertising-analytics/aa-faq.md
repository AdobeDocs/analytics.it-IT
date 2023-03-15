---
description: Domande frequenti su Advertising Analytics.
title: Domande frequenti per l’analisi della pubblicità
feature: Advertising Analytics
exl-id: 664a5641-1c79-439f-a9fb-2ff134574412
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '1414'
ht-degree: 2%

---

# Domande frequenti

## Accesso/Diritti {#section_5F558C5981F747F0AF375A9E4B75C93C}

<table id="table_6713C3B0B6734F768370F974EB5AC5E8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>D: Devo essere un <b>Cliente Adobe Advertising Cloud o Adobe Advertising Cloud (AMO)</b> per accedere a questa funzionalità? </p> </td> 
   <td colname="col2"> <p>R: No, questa funzionalità è disponibile per i clienti non Advertising Cloud e AMO. </p> <p>I clienti AMO possono sfruttare l’integrazione Analytics-AMO esistente; non potranno utilizzare Ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Quale <b>SKU di Adobe Analytics</b> ti autorizza a utilizzare Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Advertising Analytics è disponibile per Adobe Analytics <a href="https://www.adobe.com/it/data-analytics-cloud/analytics/select.html"  > Seleziona </a>, <a href="https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html"  > Prime </a>, e <a href="https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html"  > Ultimate </a> SKU. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Dobbiamo <b>pagare un extra</b> utilizzare Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: No, al di fuori di un provisioning SKU appropriato, Advertising Analytics non comporta costi aggiuntivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Advertising Analytics conteggerà nel mio <b>utilizzo delle chiamate al server</b>? </p> </td> 
   <td colname="col2"> <p>R: No, Advertising Analytics utilizza un tipo di origine dati speciale che non comporta costi di chiamata al server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Se <b>già in uso Advertising Cloud/AMO</b>, è ancora possibile utilizzare la funzionalità Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Qualsiasi account del motore di ricerca compatibile passerà ad Advertising Analytics e verrà visualizzato come di sola lettura. Tutte le modifiche o gli aggiornamenti devono essere gestiti in Advertising Cloud/AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Possiedo lo SKU corretto, ma <b>impossibile accedere</b> Advertising Analytics, perché? </p> </td> 
   <td colname="col2"> <p>R: Advertising Analytics è disponibile solo per gli amministratori di Adobe Analytics; tuttavia, gli amministratori possono concedere l’accesso agli utenti non amministratori. Contatta l’amministratore per i diritti di accesso. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Utilizzo di Advertising Analytics {#section_3A70C6C4D5A842B2981F0257A01F95FF}

<table id="table_4EC69262B7AB4DF49E736CF3B0362302"> 
 <thead> 
  <tr> 
   <th colname="col01" class="entry"> </th> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>D: Quale <b>account motore di ricerca</b> sono inclusi in Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Gli account dei motori di ricerca includono Google AdWords e Microsoft Bing. </p> <p>Nota: Yahoo Gemini è stata assorbita da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Dove devo andare <b>accesso</b> Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Dopo aver effettuato l’accesso ad Adobe Analytics, passa alla pagina <span class="uicontrol"> Amministratore </span> menu. Quindi seleziona la nuova opzione del menu <span class="uicontrol"> Advertising Analytics </span> per aggiungere gli account del motore di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Qual è la <b>dati raccolti e trasmessi in Analytics</b>? </p> </td> 
   <td colname="col2"> <p>R: Advertising Analytics utilizza una serie di API personalizzate per trasmettere i dati dai motori di ricerca tramite Adobe Advertising Cloud ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Cosa <b>dati di ricerca</b> posso ottenere con questa integrazione? </p> </td> 
   <td colname="col2"> <p>R: otterrai 1) impressioni, 2) clic, 3) costi, 4) punteggio di qualità e 5) posizione media direttamente dai motori di ricerca nonché 6) istanze AMO ID (Istanze di clic). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Posso <b>suddividi i miei dati di Advertising Analytics</b> da altri dati di Analytics (metriche/dimensioni)? </p> </td> 
   <td colname="col2"> <p>R: No, i dati di ricerca non elaborati verranno inseriti come set di dati indipendente. Tuttavia, esiste una versione Istanze dei dati di clic che può essere suddivisa per altri dati di Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Qual è la definizione dei vari <b>indicatori di stato</b> per i miei account (In sospeso, Attivo, In pausa, ecc.)? </p> </td> 
   <td colname="col2"> <p>R: Ciascuno di questi indicatori di stato identifica la fase del ciclo di vita di ciascun account del motore di ricerca. </p> 
    <ul id="ul_F68AD377B2F04A47B20355B2FF4CF345"> 
     <li id="li_05F8D7C6D00E4742A65373BE6FAA0448"><b>In sospeso</b> significa che l’account è stato configurato, ma i dati non vengono ancora estratti. </li> 
     <li id="li_42B1557A8AEC41008B85AF6E3F625CAB"><b>In pausa</b> significa che l’account è stato precedentemente configurato ma è stato messo in uno stato inattivo. </li> 
     <li id="li_30B72CC171874F308A2B8CE552EA6930"><b>Attivo</b> significa che l’account è stato configurato completamente e sta estraendo i dati di ricerca. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Sto cercando di <b>mappa i miei account Advertising Analytics su una suite di rapporti specifica</b>, ma non è disponibile nella finestra modale Suite di rapporti. Perché? </p> </td> 
   <td colname="col2"> <p>R: Prima di poter assegnare una suite di rapporti a un account Advertising Analytics, la suite di rapporti desiderata deve essere <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > predisposto per il reporting di Advertising Analytics </a>. </p> <p>Questa operazione viene eseguita tramite una pagina Amministratore separata accessibile da: <span class="ignoretag"> <span class="uicontrol"> Amministratore </span>  &gt; <span class="uicontrol"> Suite di rapporti </span>  &gt; <span class="uicontrol"> [seleziona suite di rapporti abilitata per gli Experienci Cloud] </span>  &gt; <span class="uicontrol"> Modifica impostazioni </span>  &gt; <span class="uicontrol"> Configurazione Advertising Analytics </span> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: È possibile assegnare una <b>Suite di rapporti virtuale</b> (VRS) a un account Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Le suite di rapporti virtuali non raccolgono dati, pertanto non puoi mappare direttamente un account Advertising Analytics a una VRS. </p> <p>Tuttavia, puoi mappare l’account Advertising Analytics alla suite di rapporti principale della suite di rapporti virtuale in cui desideri visualizzare i dati. </p> <p>Le metriche del motore di ricerca (clic/costo/impression) potrebbero non essere visualizzate nella VRS, a meno che non includi una condizione "o" nella logica del segmento in base all’AMO ID (o alla relativa classificazione). Esempio: l’aggiunta di "tutti gli hit in cui esiste un AMO ID" includerebbe le metriche del motore di ricerca nel segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Le metriche di Advertising Analytics sono segnalabili in <b>Canali di marketing</b> rapporto? </p> </td> 
   <td colname="col2"> <p>R: No, non sono inclusi nel rapporto Canali di marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: <b>Quando</b> i dati di ricerca vengono inseriti in Analytics? </p> </td> 
   <td colname="col2"> <p>R: I dati di ricerca vengono estratti dai motori di ricerca intorno alle 6 (06:00) nel fuso orario del centro dati di Analytics. ovvero quando i dati AMO vengono raccolti e inseriti nella suite di rapporti; Viene quindi convertito nel fuso orario della suite di rapporti come parte dell’inserimento dei dati in Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Cosa può essere <b>acquisito prima del clic</b>? Portiamo impressioni, costi, posizione media, ecc.? anche senza clic? </p> </td> 
   <td colname="col2"> <p>R: AMO ID acquisisce le metriche del motore di ricerca: impression, costo, clic, posizione media e punteggio di qualità medio. Se non ci sono clic ma sono presenti impression, i dati di impression/posizione/punteggio di qualità verranno comunque inviati ad Analytics. In genere, se non ci sono clic, allora non c'è anche alcun costo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: A che livello vengono acquisiti questi dati? <b>Visitatore? Hit?</b> </p> </td> 
   <td colname="col2"> <p>R: Le metriche del motore di ricerca vengono acquisite a livello di hit e collegate all’AMO ID (e alle relative classificazioni). Si tratta di dati a livello di riepilogo e non collegati a visite/visitatori. Di conseguenza, le metriche del motore di ricerca possono essere utilizzate solo in segmenti con ambito a livello di hit e basati sull’AMO ID (o sulle relative classificazioni). </p> <p>L’AMO ID viene anche acquisito nella pagina di destinazione dell’hit per quella pagina (che lo collega alla visita/visitatore) e persiste a valle per ottenere credito per altre metriche di Analytics (fino alla scadenza o alla sovrascrittura da parte di un nuovo AMO ID). È completamente incorporato nel set di dati come qualsiasi altro eVar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Acquisiamo solo google.com o <b>versioni per paese</b> (come google.co.uk, google.it, google.fr o google.de)? </p> </td> 
   <td colname="col2"> <p>R: La classificazione della piattaforma di annunci acquisisce questi valori: "Google Adwords" e "Bing Ads". </p> <p>Una best practice comune consiste nell’includere il codice del paese come parte della denominazione delle campagne. Puoi quindi filtrare verso il basso o segmentare (ad esempio, se tutte le campagne iniziano con country code_, la creazione di un segmento in cui Campagne (AMO ID) inizia con "UK_" ti fornirebbe solo i dati per il Regno Unito). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: La metrica "AMO Cost" è il costo pagato per ogni parola chiave/annuncio riportato dal motore di ricerca. È il costo netto o il costo lordo? </p> </td> 
   <td colname="col2"> <p>R: "AMO cost" è solo il costo pagato per i motori di ricerca. Non sono incluse le tariffe per agenzie o piattaforme di ottimizzazione/gestione delle ricerche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Sono previsti altri canali pubblicitari come <b>Visualizzazione</b> o <b>Social</b>? </p> </td> 
   <td colname="col2"> <p>R: No, al momento non abbiamo piani per questi altri canali nella roadmap. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tracciamento automatico e manuale {#section_7437C4698A6D482EB7ED94A948390119}

<table id="table_9738FF8459574ED2937A860A665BE739"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>D: Quando configuro il mio account Advertising, indica che<b> Tracciamento automatico</b> può portare a conseguenze indesiderate. Che tipo di conseguenze possono verificarsi? </p> </td> 
   <td colname="col2"> <p>A: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">La modalità automatica tenta di aggiungere i parametri URL alla fine dei modelli di tracciamento o degli URL di destinazione nel formato corretto. <b>Tuttavia, è tua responsabilità verificare che i parametri URL aggiunti persistano correttamente nella pagina di destinazione finale. </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">La modalità automatica può inserire parole chiave nell’URL di destinazione e il server web potrebbe non supportare parole chiave con caratteri speciali. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Se si imposta la registrazione manuale o automatica inizialmente, <b>posso cambiare</b> all’altra modalità di tracciamento in un secondo momento? Quali sono le implicazioni? </p> </td> 
   <td colname="col2"> <p>R: Sì, puoi passare, ma prima di effettuare il passaggio dovrai rimuovere la vecchia logica di tracciamento. Ciò può comportare tempi di inattività del tracciamento nel giorno in cui viene effettuato il passaggio (specialmente se si passa da manuale a automatico). Di conseguenza, si consiglia di non cambiare se non in caso di assoluta necessità. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Passaggio da manuale ad automatico</b>: rimuovi le aggiunte manuali ai modelli di tracciamento, quindi cambia l’opzione nell’interfaccia utente di Advertising Analytics da manuale a automatica e salva l’impostazione. Potrebbero essere necessarie fino a x ore affinché il sistema possa compilare i codici di tracciamento automatico. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Passaggio da automatico a manuale</b>: aggiorna il passaggio da manuale ad automatico nell’interfaccia utente di configurazione di Advertising Analytics, quindi distribuisci i codici di tracciamento manuali il più rapidamente possibile. Durante la distribuzione dei codici di tracciamento manuali, rimuovili se nei modelli di tracciamento dei motori di ricerca trovi i codici di tracciamento automatici. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>
