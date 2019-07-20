---
description: Domande frequenti sul tracciamento dei collegamenti nella Activity Map.
seo-description: Domande frequenti sul tracciamento dei collegamenti nella Activity Map.
seo-title: Domande frequenti sul tracciamento dei collegamenti
solution: Analytics
title: Domande frequenti sul tracciamento dei collegamenti
topic: Activity map
uuid: 10172073-b 98 b -4950-8397-67 a 18 b 37 b 3 b 4
translation-type: tm+mt
source-git-commit: d877f86dd5a05d0aa452ecebce47468ebf94cbb2

---


# Domande frequenti sul tracciamento dei collegamenti

Domande frequenti sul tracciamento dei collegamenti nella Activity Map.

>[!CAUTION]
>
>By turning on Activity Map tracking, **you may be** **collecting personally identifiable information (PII) data.** Questi dati possono essere utilizzati autonomamente o con altre informazioni per identificare, contattare o individuare una sola persona, oppure per identificare un individuo nel contesto.

Di seguito sono indicati alcuni casi noti in cui i dati PII possono essere raccolti utilizzando Tracciamento mappa dell'attività:

* `Mailto` collegamenti. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta elettronica predefinito sul computer per l'invio di un messaggio e-mail.
* `User ID` collegamenti che possono essere visualizzati nell'intestazione o piè di pagina di un sito Web dopo che l'utente ha effettuato l'accesso.
* Per gli istituti finanziari, il numero di account può essere visualizzato come collegamento. Facendo clic su di esso viene raccolto il testo del collegamento.
* I siti Web per l'igiene possono inoltre presentare dati PII visualizzati come collegamenti. Facendo clic su tali collegamenti viene raccolto il testo del collegamento, raccogliendo quindi i dati PII.

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Q: Quando si verifica il tracciamento dei collegamenti?</b> <p> </p> </td> 
   <td colname="col2"> A: Il collegamento Mappa dell'attività e l'identificazione dell'area si verificano quando gli utenti fanno clic su una pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Cosa viene tracciato per impostazione predefinita?</b> <p> </p> </td> 
   <td colname="col2"> A: Se si verifica un evento click su un elemento, l'elemento deve superare alcuni controlli per determinare se appmeasurement la tratterà come collegamento. I controlli sono i seguenti: 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">È un tag &lt; A &gt; o &lt; AREA &gt; con una proprietà HREF? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">È presente un attributo on-clic che imposta una variabile s_ objectid? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">È presente un pulsante di input o di invio di input con un valore o un testo secondario? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">È presente un tag INPUT con tipo IMAGE e una proprietà src? </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">This this a &lt; Button &gt;? </li> 
    </ul> <p>If the answer is <b>Yes</b> to any of the questions above, then the element is treated as a link and will be tracked. </p> <p>Importante: I tag pulsante con attributo type = "button" non sono considerati collegamenti da appmeasurement. Prendete in considerazione la rimozione di "type ='button '" nei tag del pulsante e l'aggiunta di un pulsante = "button" o submit = "button". </p> <p>Importante: Un tag di ancoraggio con un href che inizia con " #" viene considerato come percorso di destinazione interno da appmeasurement, non un collegamento (poiché non si lascia la pagina). Per impostazione predefinita, la Mappa dell'attività non tiene traccia di queste posizioni interne di destinazione. Tiene traccia solo dei collegamenti che consentono di passare a una nuova pagina.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: In che modo la Mappa dell'attività tiene traccia di altri elementi HTML visivi?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Tramite la <code></code> funzione s. tl ()</b> <p>Se il clic si verifica tramite una chiamata s. tl, anche Activity Map riceve questo evento click e determinerà se è stata trovata una variabile di stringa linkname. Durante l'esecuzione di s. tl, il linkname viene impostato come ID collegamento mappa dell'attività. L'elemento selezionato che ha originato la chiamata s. tl () sarà utilizzato per determinare l'area geografica. Esempio: </p> <p> 
       <code>&lt; img &amp; amp; nbsp; onclick = "s. tl (true,'o ','abc ')" &amp; amp; nbsp; src = "someimageurl. png"/&gt; </code>
  </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Tramite la <code></code> variabile s_ objectid</b> <p>Esempio: </p> <p> 
       <code>&lt; img onclick = "s_ objectid ='abc '; " src = "someimageurl. png"/&gt; &lt; a href = "some-url.html" onclick = "s_ objectid ='abc '; " &gt; Collegamento testo &lt;/a &gt; </code>
  </p> <p>Importante: È necessario un punto e virgola finale (;) quando si utilizza s_ objectid nella Activity Map. </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Potete darmi alcuni esempi di collegamenti che verranno tracciati?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>&lt; a &amp; amp; nbsp; href = "/home" &gt; Home &lt;/a &gt; </code>
  </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>&lt; input &amp; amp; nbsp; type = "submit" &amp; amp; nbsp; value = "Submit"/&gt; </code>
  </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>&lt; input &amp; amp; nbsp; type = "image" &amp; amp; nbsp; src = "submit-button. png"/&gt; </code>
  </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>&lt; p onclick = "var s_ objectid ='ID collegamento personalizzato '; " &gt; &lt; span class = "title" &gt; Current Market Rates &lt;/span &gt; &lt; span class = "subtitle" &gt; 1.45 USD &lt;/span &gt; &lt;/p &gt; </code>
  </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>&lt; div onclick = "s. tl (true,'o ','custom link id ')" &gt; &lt; span class = "title" &gt; Current Market Rates &lt;/span &gt; &lt; span class = "subtitle" &gt; 1.45 USD &lt;/span &gt; &lt;/div &gt; </code>
  </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Q: Potete darmi alcuni esempi di collegamenti che NON verranno tracciati?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">Reason: Anchor tag does not have a valid href 
      <code>
        &lt;a&amp;nbsp;name="innerAnchor"&gt;Section&amp;nbsp;header&lt;/a&gt; 
      </code> </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;p onclick="showPanel('market rates')"&gt;     &lt;span class="title"&gt;Current Market Rates&lt;/span&gt;&lt;span  class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;input type="radio" onclick="changeState(this)" name="group1" value="A"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="B"/&gt; &lt;input type="radio" onclick="changeState(this)" name="group1" value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Reason: src property is missing a form input element 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

