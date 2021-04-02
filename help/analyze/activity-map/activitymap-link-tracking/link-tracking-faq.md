---
description: Domande frequenti sul tracciamento dei collegamenti in Activity Map.
title: Domande frequenti sul tracciamento dei collegamenti
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: f9d9c7dbaf5fde5bd51c929d927d4cd3f61cb63b
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 1%

---


# Domande frequenti sul tracciamento dei collegamenti

Domande frequenti sul tracciamento dei collegamenti in Activity Map.

>[!CAUTION]
>
>Attivando il tracciamento di Activity Map, **è possibile che tu stia raccogliendo dati personali identificabili (PII).** Questi dati possono essere utilizzati da soli o con altre informazioni per identificare, contattare o individuare una singola persona o per identificare un individuo nel contesto.

Di seguito sono riportati alcuni casi noti in cui i dati PII potrebbero essere raccolti utilizzando il tracciamento di Activity Map:

* `Mailto` link. Un collegamento mailto è un tipo di collegamento HTML che attiva il client di posta elettronica predefinito sul computer per l’invio di un messaggio di posta elettronica.
* `User ID` collegamenti che possono essere visualizzati nell’intestazione/piè di pagina di un sito web dopo l’accesso dell’utente.
* Per gli istituti finanziari, il numero del conto può essere indicato come collegamento. Facendo clic su di esso verrà raccolto il testo del collegamento.
* I siti web sanitari possono anche avere dati PII mostrati come link. Facendo clic su questi collegamenti si raccoglierà il testo del collegamento, raccogliendo quindi dati PII.

<table id="table_0951EAC617344156BAE43000CCD838AF">
 <tbody>
  <tr>
   <td colname="col1"> <b>D: Quando si verifica il tracciamento dei collegamenti?</b> </td>
   <td colname="col2"> R: L’identificazione del collegamento e dell’area geografica di Activity Map si verifica quando gli utenti fanno clic su una pagina. </td>
  </tr>
  <tr>
   <td colname="col1"> <b>D: Cosa viene tracciato per impostazione predefinita?</b> </td>
   <td colname="col2"> R: Se si verifica un evento di clic su un elemento, l’elemento deve superare alcuni controlli per determinare se AppMeasurement lo tratterà come un collegamento. Questi sono i controlli:
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0">
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">Si tratta di un tag <code>&lt;A&gt;</code> o <code>&lt;AREA&gt;</code> con una proprietà <code>"href"</code>? </li>
     <li id="li_77828D24D54343E5B9A1FF7345221781">Esiste un attributo <code>"onclick"</code> che imposta una variabile <code>s_objectID</code>? </li>
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">Si tratta di un tag <code>&lt;INPUT&gt;</code> o di un pulsante <code>&lt;SUBMIT&gt;</code> con un valore o un testo secondario? </li>
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">Si tratta di un tag <code>&lt;INPUT&gt;</code> con tipo <code>&lt;IMAGE&gt;</code> e una proprietà <code>"src"</code>? </li>
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">Si tratta di un <code>&lt;BUTTON&gt;</code>? </li>
    </ul>
    Se la risposta è <b>Sì</b> a una delle domande precedenti, l’elemento viene trattato come un collegamento e verrà tracciato. <br/>
     <br/>
    Importante: I tag pulsante con l’attributo non  <code>type="button"</code> sono considerati collegamenti da AppMeasurement. Prendi in considerazione la rimozione di <code>type="button"</code> sui tag pulsante e l’aggiunta di <code>role="button"</code> o <code>submit="button"</code> al posto di . <br/>
     <br/>
    Importante: Un tag di ancoraggio con un  <code>"href"</code> che inizia con  <code>"#"</code> è considerato una posizione di destinazione interna da AppMeasurement, non un collegamento (in quanto non si esce dalla pagina). Per impostazione predefinita, Activity Map non tiene traccia di queste posizioni di destinazione interne. Traccia solo i collegamenti che navigano verso una nuova pagina. </td> 
  </tr>
  <tr>
   <td colname="col1"> <b>D: In che modo Activity Map tiene traccia degli altri elementi HTML visivi?</b> </td>
   <td colname="col2">
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5">
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>Tramite la  <code>s.tl()</code> </b> <br/>
       <br/>
      funzioneSe il clic si è verificato tramite una  <code>s.tl()</code> chiamata, anche Activity Map riceverà questo evento click e determinerà se è stata trovata una variabile  <code>linkName</code> stringa. Durante l’esecuzione di <code>s.tl()</code>, tale impostazione verrà impostata come ID collegamento di Activity Map. <code>linkName</code> L’elemento su cui è stato fatto clic per la chiamata <code>s.tl()</code> viene utilizzato per determinare l’area. <br/>
       <br/>
      Esempio:  <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s.tl(true,'o','abc')"&nbsp;src="someimageurl.png"/&gt;</code><br/>
       
     </li>
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>Tramite la  <code>s_objectID</code> </b> <br/>
       <br/>
      variabileExample:  <br/>
       <br/>
      <code>&lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt;</code><br/>
      <code>&lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;</code><br/>
      <code>&nbsp;&nbsp;Link&nbsp;Text&nbsp;Here</code><br/>
      <code>&lt;/a&gt;</code> <br/>
       <br/>
      Importante: Tenere presente che è necessario un punto e virgola finale (<code>;</code>) quando si utilizza  <code>s_objectID</code> in Activity Map.
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>D: Potete fornirmi alcuni esempi di collegamenti che verranno tracciati?</b> </td>
   <td colname="col2">
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA">
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0">
      <code>&lt;a&nbsp;href="/home"&gt;Home&lt;/a&gt;</code>
     </li>
     <li id="li_76F3DB36ED734132A2386871E6EB4929">
      <code>&lt;input&nbsp;type="submit"&nbsp;value="Submit"/&gt;</code>
     </li>
     <li id="li_10CF9EDA224645169E7CDF74956DB98B">
      <code>&lt;input&nbsp;type="image"&nbsp;src="submit-button.png"/&gt;</code>
     </li>
     <li id="li_9FA171D7F49547E798DE21869F73A402">
      <code>&lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code>
     </li>
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF">
      <code>&lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/div&gt;</code>
     </li>
    </ol>
   </td>
  </tr>
  <tr>
   <td colname="col1"> <b>D: Puoi fornirmi alcuni esempi di collegamenti che NON verranno tracciati?</b> </td>
   <td colname="col2">
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547">
     <li id="li_99372060646B43EF94C13A9C682CE693">Motivo: Il tag di ancoraggio non dispone di un <code>"href"</code> <br/> valido
       <br/>
      <code>&lt;a&nbsp;name="innerAnchor"&gt;Section&nbsp;header&lt;/a&gt;</code><br/>
       
     </li>
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Motivo: Né <code>s_ObjectID</code> né <code>s.tl()</code> presenti <br/>
       <br/>
      <code>&lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;</code><br/>
      <code>&nbsp;&nbsp;&lt;span&nbsp;class="subtitle"&gt;1.45USD&lt;/span&gt;</code><br/>
      <code>&lt;/p&gt;</code><br/>
       
     </li>
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Motivo: Né <code>s_ObjectID</code> né <code>s.tl()</code> presenti <br/>
       <br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt;</code><br/>
      <code>&lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;</code><br/>
       
     </li>
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">Motivo: Alla proprietà <code>"src"</code> manca un elemento <code>input</code> del modulo <br/>
       <br/>
      <code>&lt;input&nbsp;type="image"/&gt;</code><br/>
       
     </li>
    </ol>
   </td>
  </tr>
 </tbody>
</table>
