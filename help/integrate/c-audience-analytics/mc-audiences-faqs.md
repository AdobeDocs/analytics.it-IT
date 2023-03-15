---
description: Risposte alle domande che potresti avere durante l’implementazione di Audience Analytics.
solution: Experience Cloud
title: Domande frequenti per Audience Analytics
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '1094'
ht-degree: 15%

---

# Domande frequenti

Risposte alle domande che potresti avere durante l’implementazione di Audience Analytics.

## Domande frequenti legali {#section_B51CFC961C0B45A2BE5F4A4404620764}

<table id="table_22037CCB516C4231BF5820004FBB351A"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>D: Come posso sapere se dispongo di dati personali (PII, Personally Identifiable Information) nei miei dati Analytics? E se sì, per cosa li uso?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_71E0ECD5981D4B65BCDA065BE07A43AA"> 
     <li id="li_F8FF61A4D7B54BA39DAA6F28DB51D749">Se hai indirizzi e-mail e simili in un prop o eVar, può essere utile usare funzioni hash per dati durante la raccolta. </li> 
     <li id="li_57A8B4C7BB784FFCBC1DC363B35D9FF7">Se il tuo paese considera l’indirizzo IP come PII, <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/exclude-ip.html"  > attivare l’offuscamento dell’IP </a>. </li> 
     <li id="li_C7AA02B831AE47A59E783623126A7789">Parla con il tuo amministratore di Analytics per vedere quali dati stai raccogliendo. </li> 
     <li id="li_F6AAE868141E486AB8CAB291BD8EDB71">Parla con il tuo ufficio legale per capire che cosa è considerato PII. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>D: Come faccio a sapere se le mie suite di rapporti eseguono la personalizzazione in sito o targeting offsite/onsite?</b> </td> 
   <td colname="col2"> 
    <ul id="ul_F0984CEF80DB4B589716BC55549E32B8"> 
     <li id="li_9BC3819784A9408F846D60FF0F20AAF9">Queste non si applicano all’invio di dati di Adobe Analytics a Adobe Audience Manager. </li> 
     <li id="li_050A1BF9978E436895B5C7E33A82527D">Chiediti: condividerai un segmento condiviso con Analytics con una dimensione MCA nell’Experience Cloud? </li> 
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
   <td colname="col1"> <p><b>D: Dopo aver creato e salvato una destinazione Analytics, quanto tempo ci vorrà prima che i dati vengano visualizzati nelle suite di rapporti selezionate?</b> </p> </td> 
   <td colname="col2"> <p>Possono essere necessarie diverse ore per popolare le suite di rapporti con nuovi dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: ho creato una nuova destinazione Analytics, ma non la vedo nella sezione Mappature di destinazione dei segmenti disponibili. Dove è andata la destinazione o come la trovo?</b> </p> </td> 
   <td colname="col2"> <p>Una destinazione Analytics scompare dalla sezione Mappature di destinazione di un segmento quando selezioni il <span class="uicontrol"> Mappa automaticamente tutti i segmenti correnti e futuri </span> opzione in <span class="uicontrol"> Mappature dei segmenti </span>. </p> <p><img placement="break" align="left"  src="assets/auto-mapping.png" id="image_670ED5A306784FCBA8A0B336AC1F0FC6" width="300px" /> </p> <p>Per evitare questo problema, seleziona <span class="uicontrol"> Mappare manualmente i segmenti </span> invece dell’opzione automatica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>D: Questo mi darà tutte le informazioni dall’AAM, in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>No, solo i dati relativi alle persone che arrivano sul tuo sito durante o dopo l’abilitazione di Audiences Audience Manager e durante/dopo la qualificazione dei segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>D: Mi darà un'audience per segmento totalmente indirizzabile?</b> </p> </td> 
   <td colname="col2"> <p>Non esattamente. Ti dirà il numero di visitatori in quel segmento che sono arrivati al tuo sito durante o dopo la qualifica del segmento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>D: In cosa si differenzia dalla destinazione del cookie legacy in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>I segmenti vengono qualificati e restituiti in tempo reale - sullo stesso hit. </p> <p>I nomi descrittivi vengono visualizzati automaticamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: cosa succede se alcune delle mie suite di rapporti contengono dati personali e altre no?</b> </p> </td> 
   <td colname="col2"> <p>Suggerimento: crea due destinazioni: aggiungi le suite di rapporti sui dati personali a una destinazione e le suite di rapporti sui dati non personali all’altra. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Domande frequenti specifiche per Analytics {#section_67BFB1B1E48D4113A38B075C020931BA}

<table id="table_19AEAE0A3575423CB4F5F164DB5626D5"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>D: questa integrazione emergerà come dimensione o segmento in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Come dimensioni: ID e nome del pubblico. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Dove posso utilizzare queste dimensioni in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Quasi ovunque; vengono trattati come qualsiasi altra dimensione raccolta in Analytics. C'è un'eccezione: per ora, i dati non saranno in Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché non vedo i dati provenienti da Analytics?</b> </p> </td> 
   <td colname="col2"> <p>È probabile che tu disponga di controlli sulla privacy AAM in conflitto tra l’origine dati e la destinazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché mancano alcuni dei miei segmenti in Analytics, anche se ho scelto di inviare tutti i segmenti?</b> </p> </td> 
   <td colname="col2"> 
    <ul id="ul_B8938FD08C6F4F2387EDADDEF8089319"> 
     <li id="li_50A9BDF612304062913370F16BC882EF">I controlli sull’esportazione dei dati AAM sulla destinazione e nelle origini dati dei segmenti potrebbero essere in conflitto, impedendo l’invio di alcuni segmenti. </li> 
     <li id="li_AF5D6F883D6F4D3192E0BF23CF12ADEA">Se utilizzi caratteristiche di dati di terze parti nei segmenti, tali segmenti non possono essere condivisi con destinazioni (un set di suite di rapporti) che contengono dati personali. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché vedo "Limite di pubblico raggiunto" nel mio rapporto Analytics? (Nota: verrà rappresentato anche come Audience ID = -1 e "::max_audiences_exceeded::" nella Data Warehouse)</b> </p> </td> 
   <td colname="col2"> <p>Per impostazione predefinita, l’integrazione Audience Analytics per l’AAM invia ad Analytics tutti i segmenti per i quali un visitatore si qualifica, in base all’hit. Se un visitatore appartiene a più di 150 segmenti AAM in un singolo hit, il <b>150 segmenti qualificati più di recente</b> vengono inviati ad Analytics, mentre l’elenco rimanente viene troncato. </p> <p>Ad Analytics viene inviato un flag aggiuntivo che indica che l’elenco dei segmenti è stato troncato e viene visualizzato come "Limite di pubblico raggiunto" nella dimensione Nome pubblico e "-1" nella dimensione ID pubblico. </p> <p>Anche se è improbabile che un visitatore sia idoneo per più di 150 segmenti su un particolare hit, ciò può accadere per una piccola percentuale di tempo. Se nei rapporti si verifica il "Limite di pubblico raggiunto", sono disponibili due opzioni: </p> 
    <ul id="ul_8E290B2E32DC49738F6FD00CB0CE2BBB"> 
     <li id="li_12F498981EA949B5BCBD40ECC954C339"><b>Opzione 1</b>: continua a lasciare che l’integrazione funzioni nel suo stato predefinito, inviando gli ultimi 150 segmenti qualificati per un visitatore specifico. </li> 
     <li id="li_CA4D5747AA4A4452929097807B604959"><b>Opzione 2</b>: in AAM, scegli i 150 segmenti più importanti per la tua azienda per l’integrazione. L’AAM controlla quindi i visitatori solo rispetto a quei 150 segmenti. Lo svantaggio di questo approccio è che ricevi solo quei 150 segmenti su tutti i visitatori. D’altro canto, l’approccio dell’opzione 1 può offrire segmenti illimitati a causa della natura specifica dell’integrazione. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: verranno fatturate chiamate server aggiuntive ad Analytics per questa integrazione?</b> </p> </td> 
   <td colname="col2"> <p>No. I tipi di pubblico AAM sono incorporati nell’hit di Analytics lato server. Questo non comporta chiamate server aggiuntive ad Analytics (primaria o secondaria). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Domande frequenti sull&#39;inoltro lato server (SSF) {#section_ADDE84ABCA0D4906B6235E92D185E0C6}

<table id="table_B7067B70FF85498896801F58D716202F"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>D: se hai implementato un SSF legacy, devo andare anche dall’amministratore di Analytics e attivare l’SSF della suite di rapporti?</b> </p> </td> 
   <td colname="col2"> <p>Sì. Nell’impostazione della destinazione AAM, vedrai solo le suite di rapporti che hanno SSF attivato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Perché non posso attivare alcune suite di rapporti per SSF in Analytics Admin?</b> </p> </td> 
   <td colname="col2"> <p>È possibile abilitare solo le suite mappate sull’organizzazione di Experienci Cloud. </p> </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori domande frequenti su questo argomento, consulta [Domande frequenti sull&#39;inoltro lato server](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf-faq.md).

## Domande frequenti generiche {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

<table id="table_1F7C0C785F9C472286A96F8C25E8440B"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>D: Perché i conteggi dei visitatori del segmento sono diversi tra Audience Manager e Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="/help/integrate/c-audience-analytics/visitor-count-reconciliation.md"  > Differenze nel numero di visitatori </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Qual è la differenza tra "pubblico" in AAM e "segmenti" in Analytics?</b> </p> </td> 
   <td colname="col2"> <p>Consulta <a href="/help/integrate/c-audience-analytics/aam-analytics-segments.md"  > Comprendere i segmenti in Analytics e Audience Manager </a>. </p> <p>I tipi di pubblico dell’AAM vengono inviati e condivisi come componenti "dimensionali" da utilizzare in Analytics. Ad esempio, non verranno visualizzati come segmenti nel Generatore di segmenti, ma come dimensioni con cui puoi creare i segmenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: Qual è la differenza tra Attributi del cliente e dati del cliente integrati dall’AAM?</b> </p> </td> 
   <td colname="col2"> <p>Gli attributi del cliente non sono basati sul tempo, ma vengono applicati retroattivamente e successivamente. I dati integrati dell’AAM sono basati solo sul tempo e possono essere utilizzati solo in futuro. Inoltre, Attributi del cliente è una tabella di ricerca per ID visitatore di Experience Cloud, mentre l’integrazione AAM è costituita dai dati uniti in ogni hit di un visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>D: cosa succede con gli approcci legacy a questo problema, ad esempio le destinazioni dei cookie plug-in beta o Consulting precedenti?</b> </p> </td> 
   <td colname="col2"> <p>È consigliabile implementare la nuova integrazione e rimuovere le destinazioni obsolete. </p> </td> 
  </tr> 
 </tbody> 
</table>
