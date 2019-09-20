---
description: Crea un elemento dati in Gestione tag dinamica.
keywords: Gestione tag dinamica;elemento dati;creare un nuovo elemento dati;nome;tipo;valore predefinito;forza valore in lettere minuscole;ricorda questo valore per
seo-description: Crea un elemento dati in Gestione tag dinamica.
seo-title: Creare un elemento di dati
solution: Experience Cloud,Analytics,Target,Gestione tag dinamica
title: Creare un elemento di dati
uuid: eacd5c60-6197-4129-a9e1-a39e9a58b38a
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Creare un elemento di dati

Crea un elemento dati in Gestione tag dinamica.

1. [Crea proprietà](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123)Web, se non lo hai già fatto.
1. Nella proprietà Web, fate clic su **[!UICONTROL Rules]** &gt; **[!UICONTROL Data Elements]**.
1. Fai clic su **[!UICONTROL Create New Data Element]**.
1. Completa i campi e le opzioni seguenti:

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> Opzione</th> 
      <th class="chdeschd"> Descrizione</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Nome</strong></td> 
      <td class="chdesc stentry"> <p>Il nome descrittivo dell'elemento dati che un esperto di marketing può riconoscere. Ad esempio, <code>ID prodotto </code>. </p> <p> <p>Nota:  Il generatore di regole fa riferimento al nome, non a un ID. Se si modifica il nome dell'elemento dati, è necessario modificarne il riferimento in ogni regola che lo utilizza. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Tipo</strong></td> 
      <td class="chdesc stentry"> <p> Specifica da dove vengono estratti i dati, ad esempio oggetto JS, selettore CSS, cookie, parametro URL o script personalizzato. </p> <p>A seconda del tipo selezionato, vengono visualizzate opzioni diverse. Per ulteriori informazioni ed esempi, consulta <a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html" format="html" scope="external"> Tipi di elementi</a> di dati nella Documentazione prodotto Gestione tag dinamica. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Valore predefinito</strong></td> 
      <td class="chdesc stentry"> <p>Elemento predefinito. Questo valore assicura che l'elemento dati abbia sempre un valore, anche se un parametro URL non esiste o non può essere trovato da Gestione tag dinamica. </p> <p> <p>Nota:  Se non è presente alcun valore e nessun valore predefinito, non viene restituito nulla. Qualsiasi variabile che fa riferimento a tale elemento dati non verrà impostata. Inoltre, il campo del valore predefinito viene ignorato se si tratta di un elemento dati "codice personalizzato". </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Forza valore in lettere minuscole</strong></td> 
      <td class="chdesc stentry"> <p>Gestione tag dinamica rende automaticamente il valore più basso. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Ricorda questo valore per</strong></td> 
      <td class="chdesc stentry"> <p>Per quanto tempo desiderate che Gestione tag dinamica ricordi questo valore. </p> <p> I valori validi includono: </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>Sessione: I tempi di esecuzione basati sulle sessioni possono variare a seconda dell'implementazione. Gli elementi dei dati della sessione sono impostati sul cookie della sessione. Tuttavia, questa impostazione potrebbe essere basata su un server Web o un browser. Non è correlato alla sessione utilizzata in reporting e analisi di marketing. </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>Pageview </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>Visitatore </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   Per ulteriori informazioni sull'utilizzo degli elementi di dati, consulta [Elementi](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html) di dati nella Documentazione prodotto di Adobe Tag Management.
1. Fai clic su **[!UICONTROL Save Data Element]**.
