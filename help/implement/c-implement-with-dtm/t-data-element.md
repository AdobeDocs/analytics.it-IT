---
description: Crea un elemento dati in Gestione tag dinamica.
keywords: Gestione tag dinamica; elemento dati; creare un nuovo elemento dati; name; type; valore predefinito; forza il valore minuscolo; ricorda questo valore
seo-description: Crea un elemento dati in Gestione tag dinamica.
seo-title: Creare un elemento dati
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Creare un elemento dati
uuid: eacd 5 c 60-6197-4129-a 9 e 1-a 39 e 9 a 58 b 38 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Creare un elemento dati

Crea un elemento dati in Gestione tag dinamica.

1. [Create la proprietà Web](../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123), se non lo avete già fatto.
1. In the web property, click **[!UICONTROL Rules]** &gt; **[!UICONTROL Data Elements]**.
1. Fai clic su **[!UICONTROL Create New Data Element]**.
1. Completa i campi e le opzioni seguenti:

   <table id="choicetable_681F7D5B86534FF0B6DB67E117B8E381"> 
    <thead class="chhead sthead"> 
      <th class="choptionhd"> Opzione</th> 
      <th class="chdeschd"> Descrizione</th> 
    </thead> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Nome</strong></td> 
      <td class="chdesc stentry"> <p>Nome descrittivo degli elementi dati che un esperto di marketing può riconoscere. For example, 
        <code>
          Product ID
        </code>. </p> <p> <p>Nota: Il generatore di regole viene fatto riferimento al nome, non a un ID. Se modificate il nome dell'elemento dati, dovete modificarne il riferimento in tutte le regole che lo utilizzano. </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Tipo</strong></td> 
      <td class="chdesc stentry"> <p> Specifica dove vengono estratti i dati, ad esempio Oggetto JS, Selettore CSS, Cookie, Parametro URL o Script personalizzato. </p> <p>A seconda del tipo selezionato, vengono visualizzate diverse opzioni. See <a href="https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html" format="html" scope="external"> Types of Data Elements</a> in the Dynamic Tag Management Product Documentation for more information and examples. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Valore predefinito</strong></td> 
      <td class="chdesc stentry"> <p>Un elemento predefinito. Questo valore assicura che l'elemento dati abbia sempre un valore, anche se un parametro URL non esiste o non è possibile trovare in Gestione tag dinamica. </p> <p> <p>Nota: In assenza di valore e nessun valore predefinito, non viene restituito nulla. Qualsiasi variabile che fa riferimento a tale elemento dati non viene impostata. Inoltre, il campo valore predefinito viene ignorato se si tratta di un elemento di dati "codice personalizzato". </p> </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Forza valore minuscolo</strong></td> 
      <td class="chdesc stentry"> <p>Gestione tag dinamica rende il valore ridotto automaticamente. </p> </td> 
    </tr> 
    <tr class="chrow strow"> 
      <td class="choption"><strong>Ricorda questo valore per</strong></td> 
      <td class="chdesc stentry"> <p>Per quanto tempo si desidera che Gestione tag dinamica memorizzi questo valore. </p> <p> I valori validi includono: </p> 
      <ul id="ul_52F6CD8FC22942208F3F45492E914104"> 
        <li id="li_32E4366C5B2E46D788CD8478620FE3E0"> <p>Sessione: Il tempo basato su sessioni può variare a seconda dell'implementazione. Gli elementi di dati della sessione sono impostati sul cookie della sessione. Tuttavia, questa impostazione potrebbe essere basata su un server Web o sul browser. Non si riferisce alla sessione utilizzata in reporting e analisi di marketing. </p> </li> 
        <li id="li_8A944564BF7643E4B21F0EF2394B3FE8"> <p>Visualizzazione pagina </p> </li> 
        <li id="li_5C8A2F2392FD475AA89DDA7D5B5CF88B"> <p>Visitatore </p> </li> 
      </ul> </td> 
    </tr> 
   </table>

   See [Data Elements](https://marketing.adobe.com/resources/help/en_US/dtm/data_elements.html) in the Adobe Tag Management Product Documentation for more information about how to use data elements.
1. Fai clic su **[!UICONTROL Save Data Element]**.
