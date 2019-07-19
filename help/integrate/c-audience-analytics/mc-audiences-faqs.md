---
description: Risposte alle domande che potresti avere quando implementhi Audience Analytics.
seo-description: Risposte alle domande che potresti avere quando implementhi Audience Analytics.
seo-title: Domande frequenti
solution: Marketing Cloud
title: Domande frequenti
uuid: 9 dfc 8 f 19-f 9 b 2-4 c 2 e-bff 9-3 d 91 cfe 01 bca
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Domande frequenti

Risposte alle domande che potresti avere quando implementhi Audience Analytics.

## Domande frequenti legali {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>D: Come posso sapere se dispongo di dati personali (PII, Personally Identifiable Information) nei miei dati Analytics? E se sì, per cosa li uso?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">Se hai indirizzi e-mail e simili in un prop o eVar, può essere utile usare funzioni hash per dati durante la raccolta. </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">If your country considers IP address to be PII, <a href="https://marketing.adobe.com/resources/help/en_US/reference/exclude_IP.html" format="html" scope="external"> turn on IP obfuscation </a>. </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Parla con il tuo amministratore di Analytics per vedere quali dati stai raccogliendo. </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">Parla con il tuo ufficio legale per capire che cosa è considerato PII. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>D: Come faccio a sapere se le mie suite di rapporti eseguono la personalizzazione in sito o targeting offsite/onsite?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">Ciò non si applica all'invio di dati di Adobe Analytics ad Adobe Audience Manager. </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">Chiediti: Condivideresti un segmento condiviso con Analytics con una dimensione MCA in Experience Cloud? </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">Stai esportando (ad esempio tramite feed di dati) in un sistema di Business Intelligence (BI) usato a tale fine? </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## AAM-Specific FAQs {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Come si crea una destinazione di Analytics in Audience Manager?</b> </p> </td> 
   <td colname="col2"> See <a href="https://marketing.adobe.com/resources/help/en_US/aam/create-analytics-destination.html" format="html" scope="external"> Configure an Analytics Destination in AAM </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Dopo aver creato e salvato una destinazione di Analytics, quanto tempo sarà necessario fino alla visualizzazione dei dati nelle suite di rapporti selezionate?</b> </p> </td> 
   <td colname="col2"> <p>Sono necessarie diverse ore per compilare le suite di rapporti con nuovi dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Ho creato una nuova destinazione Analytics, ma non la vedo nella sezione Mappature destinazioni dei miei segmenti disponibili. Where did that destination go or how do I find it?</b> </p> </td> 
   <td colname="col2"> <p>An Analytics destination disappears from a segment's Destination Mappings section when you select the <span class="uicontrol"> Automatically map all current and future segments </span> option in <span class="uicontrol"> Segment Mappings </span>. </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>To prevent this, select <span class="uicontrol"> Manually map segments </span> instead of the automatic option. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Q: Mi darà tutte le informazioni di AAM, in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>No, solo i dati relativi alle persone che arrivano sul tuo sito durante o dopo l'abilitazione di Audience Manager Audience e durante/dopo la qualifica del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>D: Mi darà un'audience per segmento totalmente indirizzabile?</b> </p> </td> 
   <td colname="col2"> <p>Non esattamente. Ti dirà il numero di visitatori in quel segmento che sono arrivati al tuo sito durante o dopo la qualifica del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>D: In cosa si differenzia dalla destinazione del cookie legacy in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>I segmenti sono qualificati e restituiti in tempo reale, sullo stesso hit. </p> <p>I nomi descrittivi vengono visualizzati automaticamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Cosa succede se alcune delle mie suite di rapporti dispongono di dati personali e alcuni no?</b> </p> </td> 
   <td colname="col2"> <p>Suggerimento: Crea due destinazioni: aggiungi le suite di rapporti personali a una destinazione e le suite di rapporti di dati personali all'altro. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Analytics-Specific FAQs {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Questa superficie di integrazione sarà una dimensione o segmento in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Come dimensioni: ID audience e nome pubblico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Dove posso usare queste dimensioni in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Quasi ovunque; vengono trattati come qualsiasi altra dimensione raccolta in Analytics. Sono disponibili due eccezioni: al momento, i dati non saranno in Workbench dati o Livestream. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Perché non vedo i dati provenienti da Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Probabilmente hai dei controlli sulla privacy AAM in conflitto tra origine dati e destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Perché alcuni dei miei segmenti mancano in Analytics, anche se scelgo di inviare tutti i segmenti?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">I controlli di esportazione dei dati AAM sulla destinazione e nelle origini dati dei segmenti potrebbero essere in conflitto, impedendo l'invio di determinati segmenti. </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">Se utilizzi caratteristiche dati 3 rd-party nei tuoi segmenti, questi segmenti non possono essere condivisi con destinazioni (un set di suite di rapporti) che contengono dati personali. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Perché trovo «Limite pubblico raggiunto» nel mio report Analytics? (Note: this will also be represented as Audience ID = -1 and "::max_audiences_exceeded::" in Data Warehouse)</b> </p> </td> 
   <td colname="col2"> <p>Per impostazione predefinita, l'integrazione di Audience Analytics per AAM invia tutti i segmenti idonei ad Analytics per ogni hit. If a visitor belongs to more than 150 AAM segments on a single hit, the <b>150 most recently qualified segments</b> are sent to Analytics, while the remaining list is truncated. </p> <p>Ad Analytics viene inviato un flag aggiuntivo che indica che l'elenco dei segmenti è stato troncato e viene visualizzato come «Limite pubblico raggiunto» nella dimensione Nome pubblico e «-1» nella dimensione ID pubblico. </p> <p>Benché non sia possibile che un visitatore abbia diritto a più di 150 segmenti su un determinato hit, potrebbe verificarsi una percentuale ridotta di tempo. Se riscontri un'esperienza "Limite pubblico raggiunto" nel reporting, hai due opzioni: </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>Opzione 1</b>: Continua a lasciare che l'integrazione funzioni nel suo stato out-of-the-box, inviando i 150 segmenti idonei più recenti per un particolare visitatore. </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>Opzione 2</b>: In AAM, scegli i 150 segmenti più importanti per l'integrazione. AAM quindi controlla i visitatori rispetto ai soli 150 segmenti. Lo svantaggio di questo approccio è che ricevi solo quei 150 segmenti per tutti i visitatori. D'altra parte, l'approccio Opzione 1 può fornire segmenti illimitati a causa della natura per hit dell'integrazione. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Altre chiamate server verranno addebitate ad Analytics per questa integrazione?</b> </p> </td> 
   <td colname="col2"> <p>No. Le audience AAM sono incorporate nel lato server di Analytics. Ciò non comporta chiamate server aggiuntive ad Analytics (primaria o secondaria). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Server-Side Forwarding (SSF) FAQs {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Q: Se hai implementato SSF precedente, devo anche andare ad Analytics Admin e attivare la suite di rapporti SSF?</b> </p> </td> 
   <td colname="col2"> <p>Sì. Nella configurazione di destinazione AAM, verranno visualizzate solo le suite di rapporti in cui è stato attivato SSF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Perché non posso attivare determinate suite di rapporti per SSF in Analytics Admin?</b> </p> </td> 
   <td colname="col2"> <p>Solo le suite mappate alla tua organizzazione Experience Cloud possono essere attivate. </p> </td> 
  </tr> 
 </tbody> 
</table>

For more FAQs on this topic, see [Server-Side Forwarding FAQ](/help/admin/admin/c-server-side-forwarding/ssf-faq.md).

## Domande frequenti generiche {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>D: Perché i conteggi dei visitatori del segmento sono diversi tra Audience Manager e Analytics?</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../integrate/c-audience-analytics/visitor-count-reconciliation.md#concept_03DD2B594C2B4D23907D5272DDFADFA0" format="dita" scope="local"> Visitor Count Differences </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Qual è la differenza tra «audience» in AAM e «segmenti» in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>See <a href="../../integrate/c-audience-analytics/aam-analytics-segments.md#concept_AB72F76AFAF14F82A5BB17809925813B" format="dita" scope="local"> Understand Segments in Analytics and Audience Manager </a>. </p> <p>Le audience AAM vengono inviate e condivise come componenti "dimensioni" da utilizzare in Analytics. Essi non verranno visualizzati come segmenti nel Generatore di segmenti, ad esempio, ma come dimensioni con cui puoi creare segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Qual è la differenza tra Attributi del cliente e dati cliente integrati da AAM?</b> </p> </td> 
   <td colname="col2"> <p>Gli attributi del cliente non sono temporizzati; vengono applicati in modo retroattivo e avanti. I dati integrati di AAM sono basati sul tempo e sul tempo successivo. Inoltre, gli attributi del cliente sono una tabella di ricerca per gli ID visitatore di Experience Cloud, mentre l'integrazione AAM è data stitched in ogni hit per un visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Q: Cosa succede agli approcci legacy per questo problema, ad esempio la vecchia versione beta o il plug-in di cookie di Consulenza?</b> </p> </td> 
   <td colname="col2"> <p>Vi consigliamo di implementare la nuova integrazione e rimuovere le vecchie destinazioni. </p> </td> 
  </tr> 
 </tbody> 
</table>

