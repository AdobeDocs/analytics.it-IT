---
description: Risposte alle domande che potrebbero sorgere durante l’implementazione di Audience Analytics.
solution: Experience Cloud
title: Domande frequenti
uuid: 9dfc8f19-f9b2-4c2e-bff9-3d91cfe01bca
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 15%

---

# Domande frequenti

Risposte alle domande che potrebbero sorgere durante l’implementazione di Audience Analytics.

## Domande frequenti legali {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>D: Come posso sapere se dispongo di dati personali (PII, Personally Identifiable Information) nei miei dati Analytics? E se sì, per cosa li uso?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">Se hai indirizzi e-mail e simili in un prop o eVar, può essere utile usare funzioni hash per dati durante la raccolta. </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">Se il tuo paese considera l’indirizzo IP come PII, <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html"  > attiva l’offuscamento dell’IP </a>. </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Parla con il tuo amministratore di Analytics per vedere quali dati stai raccogliendo. </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">Parla con il tuo ufficio legale per capire che cosa è considerato PII. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>D: Come faccio a sapere se le mie suite di rapporti eseguono la personalizzazione in sito o targeting offsite/onsite?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">Ciò non si applica all’invio di dati Adobe Analytics a Adobe Audience Manager. </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">Chiedetevi: Condividerai nuovamente sull’Experience Cloud un segmento condiviso di Analytics con una dimensione MCA? </li> 
     <li id="li_C52D969681B94F4AAA18FDEB21EC5B49">Stai esportando (ad esempio tramite feed di dati) in un sistema di Business Intelligence (BI) usato a tale fine? </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Domande frequenti specifiche per AAM {#section_6BDF746BA6464359A6A89A64EB025D12}

<table id="table_15B44592161240BDA79F3B020EA9CC9D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>D: Come si crea una destinazione Analytics in Audience Manager?</b> </p> </td> 
   <td colname="col2"> Consulta <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html"  > Configurare una destinazione Analytics in AAM </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Dopo aver creato e salvato una destinazione Analytics, quanto tempo ci vorrà fino a quando i dati non verranno visualizzati nelle suite di rapporti selezionate?</b> </p> </td> 
   <td colname="col2"> <p>Possono essere necessarie diverse ore per compilare le suite di rapporti con nuovi dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Ho creato una nuova destinazione Analytics, ma non la vedo nella sezione Mappature di destinazione dei segmenti disponibili. Dove è andata quella destinazione o come la trovo?</b> </p> </td> 
   <td colname="col2"> <p>Una destinazione Analytics scompare dalla sezione Destination Mappings (Mappature di destinazione) di un segmento quando selezioni l'opzione <span class="uicontrol"> Mappa automaticamente tutti i segmenti correnti e futuri </span> in <span class="uicontrol"> Segment Mappings </span> (Mappature di segmento). </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>Per evitare questo problema, seleziona <span class="uicontrol"> Mappa manualmente i segmenti </span> invece dell’opzione automatica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>D: Questo mi darà tutte le informazioni da AAM, in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>No, solo i dati relativi alle persone che arrivano sul tuo sito durante o dopo l'abilitazione di Audience Manager Audiences e durante/dopo la qualifica del segmento. </p> </td> 
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
   <td colname="col1"> <p><b>D: Cosa succede se alcune suite di rapporti hanno dati personali e altre no?</b> </p> </td> 
   <td colname="col2"> <p>Suggerimento: Crea due destinazioni: aggiungi le suite di rapporti sui dati personali a una destinazione e le suite di rapporti sui dati non personali all’altra. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Domande frequenti specifiche per Analytics {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>D: Questa integrazione apparirà come dimensione o segmento in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Come dimensioni: ID audience e nome audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Dove posso utilizzare queste dimensioni in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>quasi ovunque; vengono trattati come qualsiasi altra dimensione raccolta in Analytics. C'è un'eccezione: per ora, i dati non saranno in Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché non vedo i dati in arrivo in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>È probabile che vi siano controlli di privacy AAM in conflitto tra origine dati e destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché mancano alcuni dei miei segmenti in Analytics, anche se ho scelto di inviare tutti i segmenti?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">I controlli sull’esportazione dei dati AAM sulla destinazione e nelle origini dati dei segmenti potrebbero essere in conflitto, impedendo l’invio di determinati segmenti. </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">Se utilizzi caratteristiche di dati di terze parti nei segmenti, questi segmenti non possono essere condivisi con destinazioni (un set di suite di rapporti) che contengono dati personali. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché viene visualizzato il "limite di pubblico raggiunto" nel rapporto di Analytics? (Nota: sarà anche rappresentato come ID pubblico = -1 e "::max_audiences_superata::" nella Data Warehouse)</b> </p> </td> 
   <td colname="col2"> <p>Per impostazione predefinita, l’integrazione di Audience Analytics per AAM invia ad Analytics tutti i segmenti per i quali un visitatore si qualifica, in base all’hit. Se un visitatore appartiene a più di 150 segmenti di AAM in un singolo hit, gli <b>150 segmenti qualificati più di recente</b> vengono inviati ad Analytics, mentre l'elenco rimanente viene troncato. </p> <p>Viene inviato un flag aggiuntivo ad Analytics che indica che l’elenco dei segmenti è stato troncato e viene visualizzato come "Limite di pubblico raggiunto" nella dimensione Nome pubblico e come "-1" nella dimensione ID pubblico. </p> <p>Anche se è improbabile che un visitatore sia idoneo per più di 150 segmenti su un particolare hit, può accadere una piccola percentuale del tempo. Se si verifica un "limite di pubblico raggiunto" nel rapporto, si hanno due opzioni: </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>Opzione 1</b>: Continua a far funzionare l’integrazione nel suo stato predefinito, inviando i 150 segmenti qualificati più di recente per un particolare visitatore. </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>Opzione 2</b>: In AAM, scegli i 150 segmenti più importanti per la tua azienda per l’integrazione. AAM quindi confronta i visitatori solo con quei 150 segmenti. Lo svantaggio di questo approccio è che ricevi solo quei 150 segmenti su tutti i visitatori. D'altro canto, l'approccio Option 1 può offrire segmenti illimitati a causa della natura dell'integrazione per hit. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Verranno fatturate ad Analytics chiamate server aggiuntive per questa integrazione?</b> </p> </td> 
   <td colname="col2"> <p>No. AAM tipi di pubblico sono incorporati nell’hit lato server di Analytics. Questo non comporta chiamate server aggiuntive ad Analytics (primaria o secondaria). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Domande frequenti su Server-Side Forwarding (SSF) {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>D: Se ho implementato SSF legacy, devo anche accedere all’amministratore di Analytics e attivare SSF suite per report?</b> </p> </td> 
   <td colname="col2"> <p>Sì. Nella configurazione della destinazione AAM, vedrai solo le suite di rapporti che hanno attivato SSF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché non posso attivare alcune suite di rapporti per SSF nell’amministrazione di Analytics?</b> </p> </td> 
   <td colname="col2"> <p>È possibile abilitare solo le suite mappate all’organizzazione Experience Cloud. </p> </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori domande frequenti su questo argomento, consulta [Domande frequenti sull&#39;inoltro lato server](/help/admin/admin/c-server-side-forwarding/ssf-faq.md).

## Domande frequenti generiche {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>D: Perché i conteggi dei visitatori del segmento sono diversi tra Audience Manager e Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  > Differenze tra i conteggi dei visitatori </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Qual è la differenza tra "pubblico" nei AAM e "segmenti" in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > Comprendere i segmenti in Analytics ed Audience Manager </a>. </p> <p>I tipi di pubblico AAM vengono inviati e condivisi come componenti "dimensione" da utilizzare in Analytics. Ad esempio, non verranno visualizzati come segmenti nel Generatore di segmenti, ma come dimensioni con cui puoi creare i segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Qual è la differenza tra gli attributi del cliente e i dati del cliente integrati da AAM?</b> </p> </td> 
   <td colname="col2"> <p>Gli attributi del cliente non sono basati sul tempo; si applicano retroattivamente e proseguono. AAM dati integrati si basano solo sul tempo e proseguono. Inoltre, Attributi del cliente è una tabella di ricerca per ID visitatore di Experience Cloud, mentre l'integrazione AAM è costituita da dati uniti in ogni hit per un visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Cosa succede con gli approcci legacy a questo problema, ad esempio, le vecchie destinazioni di cookie beta o di consulenza?</b> </p> </td> 
   <td colname="col2"> <p>È consigliabile implementare la nuova integrazione e rimuovere le destinazioni obsolete. </p> </td> 
  </tr> 
 </tbody> 
</table>
