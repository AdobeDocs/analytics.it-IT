---
description: Domande frequenti su Advertising Analytics.
title: Domande frequenti
uuid: 05724f56-cf98-4ad8-ad0d-83a5a4b1944a
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '1411'
ht-degree: 3%

---


# Domande frequenti

## Accesso/diritti {#section_5F558C5981F747F0AF375A9E4B75C93C}

<table id="table_6713C3B0B6734F768370F974EB5AC5E8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>D: È necessario essere un <b>cliente Adobe Advertising Cloud o Adobe Advertising Cloud (AMO)</b> per accedere a questa funzionalità? </p> </td> 
   <td colname="col2"> <p>R: No, questa funzionalità è disponibile per i clienti non Advertising Cloud e AMO. </p> <p>I clienti AMO possono sfruttare l’integrazione esistente Analytics-AMO; non potranno utilizzare Ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Quali <b>SKU Adobe Analytics</b> ti consentono di utilizzare Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Advertising Analytics è disponibile per gli SKU di Adobe Analytics <a href="https://www.adobe.com/it/data-analytics-cloud/analytics/select.html"  > Select </a>, <a href="https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html"  > Prime </a> e <a href="https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html"  > Ultimate </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: È necessario <b>pagare extra</b> per utilizzare Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: No, al di fuori del provisioning SKU appropriato, Advertising Analytics non comporta costi aggiuntivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Advertising Analytics verrà conteggiato in base all' <b>utilizzo della chiamata al server</b>? </p> </td> 
   <td colname="col2"> <p>R: No, Advertising Analytics utilizza un tipo di origine dati speciale che non comporta costi di chiamata al server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Se <b>uso già Advertising Cloud/AMO</b>, posso comunque utilizzare la funzionalità Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Qualsiasi account del motore di ricerca compatibile passerà ad Advertising Analytics e verrà visualizzato come di sola lettura. Tutte le modifiche o gli aggiornamenti devono essere gestiti in Advertising Cloud/AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Possiedo la SKU corretta, ma <b>non posso accedere a</b> Advertising Analytics, perché? </p> </td> 
   <td colname="col2"> <p>R: Advertising Analytics è disponibile solo per gli amministratori di Adobe Analytics; tuttavia, gli amministratori possono concedere l’accesso agli utenti non amministratori. Contatta il tuo amministratore per i diritti di accesso. </p> </td> 
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
   <td colname="col1"> <p>D: Quali <b>account del motore di ricerca</b> sono inclusi in Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Gli account del motore di ricerca includono Google AdWords e Microsoft Bing. </p> <p>Nota: Yahoo Gemini è stata assorbita da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Dove vado su <b>access</b> Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Dopo aver effettuato l'accesso ad Adobe Analytics, passa al menu <span class="uicontrol"> Admin </span> . Quindi seleziona la nuova opzione di menu <span class="uicontrol"> Advertising Analytics </span> per aggiungere gli account del motore di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: In che modo i dati <b>vengono raccolti e trasmessi in Analytics</b>? </p> </td> 
   <td colname="col2"> <p>R: Advertising Analytics utilizza una serie di API personalizzate per trasmettere dati dai motori di ricerca tramite Adobe Advertising Cloud ad Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Cosa ottengo <b>dati di ricerca</b> con questa integrazione? </p> </td> 
   <td colname="col2"> <p>R: Otterrai 1) Impression, 2) Clic, 3) Costi, 4) Punteggio qualità e 5) Posizione media direttamente dai motori di ricerca e 6) Istanze AMO ID (Clic Istances). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Posso <b>suddividere i miei dati di Advertising Analytics</b> con altri dati di Analytics (metriche/dimensioni)? </p> </td> 
   <td colname="col2"> <p>R: No, i dati di ricerca non elaborati verranno inseriti come un set di dati indipendente. Tuttavia, esiste una versione Istanze dei dati di clic che può essere suddivisa per altri dati di Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Qual è la definizione dei vari <b>indicatori di stato</b> per i miei account (In sospeso, Attivo, In pausa, ecc.)? </p> </td> 
   <td colname="col2"> <p>R: Ciascuno di questi indicatori di stato identifica la fase del ciclo di vita di ciascun account del motore di ricerca. </p> 
    <ul id="ul_F68AD377B2F04A47B20355B2FF4CF345"> 
     <li id="li_05F8D7C6D00E4742A65373BE6FAA0448"><b></b> Pendinging significa che l’account è stato configurato, ma i dati non vengono ancora estratti. </li> 
     <li id="li_42B1557A8AEC41008B85AF6E3F625CAB"><b></b> Sospeso significa che l’account era già configurato ma è stato messo in uno stato inattivo. </li> 
     <li id="li_30B72CC171874F308A2B8CE552EA6930"><b></b> Attiva : l’account è stato configurato completamente ed è in fase di estrazione dei dati di ricerca. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Sto cercando di <b>mappare i miei account Advertising Analytics a una specifica suite di rapporti</b>, ma non è disponibile nel modale Suite di rapporti. Perché? </p> </td> 
   <td colname="col2"> <p>R: Prima di poter assegnare una suite di rapporti a un account Advertising Analytics, è necessario eseguire il provisioning della suite di rapporti <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md"  > per il reporting di Advertising Analytics </a>. </p> <p>Questa operazione viene eseguita tramite una pagina Amministratore separata accessibile da: <span class="ignoretag"> <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol"> Suite di rapporti </span> &gt; <span class="uicontrol"> [selezionare suite di rapporti abilitata per Experience Cloud] </span> &gt; <span class="uicontrol"> Modifica impostazioni </span> &gt; <span class="uicontrol"> Configurazione Advertising Analytics </span> </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: È possibile assegnare una <b>suite di rapporti virtuali</b> (VRS) a un account Advertising Analytics? </p> </td> 
   <td colname="col2"> <p>R: Le suite di rapporti virtuali non raccolgono dati, pertanto non puoi mappare direttamente un account Advertising Analytics su una VRS. </p> <p>Tuttavia, puoi mappare l’account Advertising Analytics alla suite di rapporti principale della VRS in cui desideri visualizzare i dati. </p> <p>Le metriche del motore di ricerca (clic/costo/impression) possono essere visualizzate nella VRS solo se includi una condizione "o" nella logica del segmento in base all’AMO ID (o alla relativa classificazione). Esempio: L’aggiunta di "tutti gli hit in cui esiste AMO ID" includerebbe le metriche del motore di ricerca nel segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Le metriche Advertising Analytics sono segnalate nel rapporto <b>Marketing Channels</b> ? </p> </td> 
   <td colname="col2"> <p>R: No, non sono inclusi nel rapporto Marketing Channels (Canali di marketing). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: <b>Quando</b> i dati di ricerca vengono inseriti in Analytics? </p> </td> 
   <td colname="col2"> <p>R: I dati di ricerca vengono estratti dai motori di ricerca intorno alle 6 del mattino (06:00) nel fuso orario del datacenter di Analytics. Questo si verifica quando i dati AMO vengono raccolti e inseriti nella suite di rapporti. Viene quindi convertito nel fuso orario della suite di rapporti come parte dell’inserimento dei dati in Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Cosa è possibile acquisire <b>prima del clic</b>? Portiamo impressioni, costi, posizione media, ecc. anche senza il click? </p> </td> 
   <td colname="col2"> <p>R: L’AMO ID acquisirà le metriche del motore di ricerca: Impression, costo, clic, posizione media e punteggio medio di qualità. Se non ci sono clic, ma sono presenti impression, i dati del punteggio impression/posizione/qualità saranno comunque inviati ad Analytics. In genere, se non ci sono clic, non ci sono costi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: A che livello vengono acquisiti i dati? <b>Visitatore? Hit?</b> </p> </td> 
   <td colname="col2"> <p>R: Le metriche del motore di ricerca vengono acquisite a livello di hit e collegate all’AMO ID (e alle relative classificazioni). Si tratta di dati di livello di riepilogo e non sono connessi a visite/visitatori. Di conseguenza, le metriche del motore di ricerca possono essere utilizzate solo in segmenti con ambito a livello di hit e in base all’AMO ID (o alle relative classificazioni). </p> <p>L’AMO ID viene anche acquisito nella pagina di destinazione nell’hit per la pagina (che la collega alla visita/visitatore) e persisterà a valle per ottenere credito per altre metriche di Analytics (fino alla scadenza o alla sovrascrittura da un nuovo AMO ID). È completamente incorporato nel set di dati come qualsiasi altro eVar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Catturiamo solo google.com o <b>versioni nazionali</b> (come google.co.uk, google.it, google.fr o google.de)? </p> </td> 
   <td colname="col2"> <p>R: La classificazione di Ad Platform acquisisce questi valori: "Google Adwords", e "Bing Ads". </p> <p>Una best practice comune consiste nell’includere il codice del paese come parte della denominazione delle campagne. Puoi quindi filtrare in basso o segmentare (ad esempio, se tutte le campagne iniziano con country code_, la creazione di un segmento in cui Campagne (AMO ID) inizia con "UK_" ti fornirà solo i dati per il Regno Unito). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: La metrica "AMO Cost" è il costo pagato per ogni parola chiave/annuncio riportato dal motore di ricerca. Questo è il costo netto o il costo lordo? </p> </td> 
   <td colname="col2"> <p>R: "costo AMO" è solo il costo pagato ai motori di ricerca. Non include le tariffe di agenzie o piattaforme di ottimizzazione/gestione delle ricerche. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Sono previsti altri canali pubblicitari come <b>Display</b> o <b>Social</b>? </p> </td> 
   <td colname="col2"> <p>R: No, al momento non abbiamo piani per questi altri canali nella tabella di marcia. </p> </td> 
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
   <td colname="col1"> <p>D: Quando configuri il mio account Advertising, dichiara che<b> Auto Tracking</b> può portare a conseguenze non previste. Che tipo di conseguenze possono verificarsi? </p> </td> 
   <td colname="col2"> <p>A: 
     <ul id="ul_59EFF4A2ECE947EBBDB6A9FF6D072FE0"> 
      <li id="li_8731E4B7D6ED4F0996B3630A35D5BAC4">La modalità automatica tenta di aggiungere parametri URL alla fine dei modelli di tracciamento/URL di destinazione nel formato corretto. <b>Tuttavia, è tua responsabilità assicurarsi che i parametri URL aggiunti persistano correttamente nella pagina di destinazione finale.  </b> </li> 
      <li id="li_1202FE1FC88342378A60E8FE65E5426B">La modalità automatica può inserire parole chiave nell’URL di destinazione e il server web potrebbe non supportare parole chiave con caratteri speciali. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D: Se inizialmente ho impostato il tracciamento manuale o automatico, <b>posso passare</b> all'altra modalità di tracciamento in un secondo momento? Quali sono le implicazioni? </p> </td> 
   <td colname="col2"> <p>R: Sì è possibile cambiare, ma sarà necessario rimuovere la vecchia logica di tracciamento prima di effettuare lo switch. Questo può comportare tempi di inattività del tracciamento nel giorno in cui viene effettuato l'interruttore (in particolare se si passa da manuale a automatico). Come tale, si raccomanda di non cambiare a meno che non sia assolutamente necessario. </p> 
    <ul id="ul_3F3CADD1C97B4947A13837CEE63A599D"> 
     <li id="li_CB9265951FD040388AEAB9EAD790A36E"><b>Passaggio da Manuale a Automatico</b>: Rimuovi le aggiunte manuali ai modelli di tracciamento, quindi passa l’interruttore nell’interfaccia utente di Advertising Analytics da manuale a automatico e salva l’impostazione. Tieni presente che potrebbero essere necessarie fino a x ore per compilare i codici di tracciamento automatico. </li> 
     <li id="li_2B6ED1342E2D443B8AF26D03532AB8E4"><b>Passaggio da Automatico a Manuale</b>: Aggiorna il passaggio da manuale a automatico nell'interfaccia utente di configurazione di Advertising Analytics, quindi distribuisci i codici di tracciamento manuali il più rapidamente possibile. Durante la distribuzione dei codici di tracciamento manuali, rimuovili se vedi i codici di tracciamento automatici nei modelli di tracciamento dei motori di ricerca. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

