---
description: Domande frequenti sul tracciamento dei collegamenti in [!DNL Activity Map].
seo-description: Domande frequenti sul tracciamento dei collegamenti in [!DNL Activity Map].
seo-title: Domande frequenti sul tracciamento dei collegamenti
solution: Analytics
title: Domande frequenti sul tracciamento dei collegamenti
topic: Activity Map
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# Domande frequenti sul tracciamento dei collegamenti

Domande frequenti sul tracciamento dei collegamenti in [!DNL Activity Map].

> [!CAUTION] Attivando [!DNL Activity Map] il tracciamento, **potresti** raccogliere dati personali identificabili (PII) **per la raccolta di dati.** Questi dati possono essere utilizzati in modo indipendente o con altre informazioni per identificare, contattare o individuare una singola persona, o per identificare un individuo nel contesto.

Di seguito sono riportati alcuni casi noti in cui i dati PII potrebbero essere raccolti utilizzando [!DNL Activity Map] Tracking:

* `Mailto` collegamenti. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta elettronica predefinito sul computer per l'invio di un messaggio e-mail.
* `User ID` collegamenti che possono essere visualizzati nell’intestazione o piè di pagina di un sito Web dopo che l’utente ha eseguito l’accesso.
* Per gli istituti finanziari, il numero del conto può essere indicato come collegamento. Facendo clic su di esso verrà raccolto il testo del collegamento.
* I siti Web per il settore sanitario possono anche avere dati PII visualizzati come collegamenti. Facendo clic su questi collegamenti si raccoglierà il testo del collegamento, raccogliendo quindi i dati PII.

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>D: Quando si verifica il tracciamento dei collegamenti?</b> <p> </p> </td> 
   <td colname="col2"> A: Il collegamento [!DNL Activity Map] e l'identificazione dell'area si verificano quando gli utenti fanno clic su una pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>D: Cosa viene tracciato per impostazione predefinita?</b> <p> </p> </td> 
   <td colname="col2"> A: Se si verifica un evento click su un elemento, l'elemento deve superare alcuni controlli per determinare se AppMeasurement lo tratterà come un collegamento. Questi sono i controlli: 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">Si tratta di un tag &lt;A&gt; o &lt;AREA&gt; con una proprietà HREF? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">Esiste un attributo on-click che imposta una variabile s_objectID? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">È un tag INPUT o un pulsante SUBMIT con un valore o un testo secondario? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">È un tag INPUT con tipo IMAGE e una proprietà src? </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Si tratta di un &lt;Button&gt;? </li> 
    </ul> <p>Se la risposta è <b>Sì</b> a una delle domande precedenti, l'elemento viene trattato come un collegamento e verrà monitorato. </p> <p>Importante:  I tag pulsante con l'attributo type="button" non sono considerati collegamenti da AppMeasurement. È consigliabile rimuovere "type='button'" sui tag dei pulsanti e aggiungere role="button" o submit="button". </p> <p>Importante: I tag di ancoraggio con un href che inizia con "#" vengono considerati come posizione di destinazione interna da AppMeasurement, non come collegamento (poiché non si esce dalla pagina). Per impostazione predefinita, [!DNL Activity Map] non tiene traccia di queste posizioni di destinazione interne. Consente di tenere traccia solo dei collegamenti che consentono all’utente di passare a una nuova pagina.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>D: In che modo [!DNL Activity Map] tiene traccia di altri elementi HTML visivi?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Tramite la <code> s.tl() </code> funzione</b> <p>Se il clic si è verificato tramite una chiamata s.tl, [!DNL Activity Map] riceverà anche questo evento click e determinerà se è stata trovata una variabile di stringa linkName. Durante l'esecuzione di s.tl, linkName verrà impostato come ID collegamento [!DNL Activity Map]. L’elemento selezionato che ha originato la chiamata s.tl() verrà utilizzato per determinare la regione. Esempio: </p> <p> 
       <code>
         &lt;img&amp;nbsp;onclick="s.tl(true,'o','abc')"&amp;nbsp;src="someimageurl.png"/&gt; 
       </code> </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Tramite la <code> s_objectID </code> variabile</b> <p>Esempio: </p> <p> 
       <code>
         &lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt; &lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;Link&nbsp;Text&nbsp;Here&lt;/a&gt;
       </code> </p> <p>Importante:  È necessario un punto e virgola finale (;) quando si utilizza s_objectID in [!DNL Activity Map]. </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>D: Potete fornirmi alcuni esempi di collegamenti che verranno tracciati?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>
        &lt;a&amp;nbsp;href="/home"&gt;Home&lt;/a&gt; 
      </code> </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>
        &lt;input&amp;nbsp;type="submit"&amp;nbsp;value="Submit"/&gt; 
      </code> </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>
        &lt;input&amp;nbsp;type="image"&amp;nbsp;src="submit-button.png"/&gt; 
      </code> </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>
        &lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>
        &lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/div&gt;
      </code> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>D: Potete fornirmi alcuni esempi di collegamenti che NON verranno tracciati?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">Motivo: Il tag Anchor non dispone di un href valido <code>
        &lt;a&amp;nbsp;name="innerAnchor"&gt;Section&amp;nbsp;header&lt;/a&gt; 
      </code> </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Motivo: Né <code> s_ObjectID </code> né <code> s.tl() </code> presente <code>
        &lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Motivo: Né <code> s_ObjectID </code> né <code> s.tl() </code> presente <code>
        &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Motivo: manca un elemento di input modulo per la proprietà src <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
