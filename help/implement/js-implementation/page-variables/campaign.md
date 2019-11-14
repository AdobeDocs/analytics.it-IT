---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# campaign

La variabile identifica le campagne di marketing utilizzate per portare i visitatori sul sito. Il valore di viene in genere ricavato da un parametro di stringa di query.

<!-- 

campaign.xml

 -->

**Parametri**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 byte </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversione &gt; Campagne &gt; Codice di tracciamento </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

A ogni elemento di una campagna di marketing deve essere associato un codice di tracciamento univoco. Ad esempio, una parola chiave del motore di ricerca a pagamento può avere un codice di tracciamento pari a 112233. Quando un utente fa clic sulla parola chiave con il codice di tracciamento 112233 e viene instradato al sito Web corrispondente, la *`campaign`* variabile registra il codice di tracciamento.

Esistono due modi principali per compilare la *`campaign`* variabile:

* Il [!UICONTROL getQueryParam] plug-in, utilizzato nel file JavaScript, recupera un parametro della stringa di query dall'URL. Per ulteriori informazioni sul [!UICONTROL getQueryParam] plug-in, consultate Plug-in [di](/help/implement/js-implementation/plugins/impl-plugins.md)implementazione.

* Assegnare un valore alla *`campaign`* variabile nell’HTML della pagina Web.

Con entrambi i metodi di compilazione della *`campaign`* variabile, il traffico del pulsante Indietro può aumentare il numero effettivo di click-through da un elemento della campagna.

Ad esempio, un visitatore accede al sito facendo clic su una parola chiave di ricerca a pagamento. Quando il visitatore arriva sulla pagina di destinazione, l’URL contiene un parametro della stringa di query che identifica il codice di tracciamento per la parola chiave. Il visitatore fa clic su un collegamento a un’altra pagina, quindi fa clic immediatamente sul pulsante Indietro per tornare alla pagina di destinazione. Quando il visitatore arriva una seconda volta sulla pagina di destinazione, l’URL con il parametro della stringa di query identifica nuovamente il codice di tracciamento. E un secondo click-through viene registrato, gonfiando falsamente il numero di click-through.

Per evitare questo aumento dei click-through, Adobe consiglia di utilizzare il [!UICONTROL getValOnce] plug-in per forzare il conteggio dei click-through di ogni campagna solo una volta per sessione. Per ulteriori informazioni sul [!UICONTROL getValOnce] plug-in, consultate Plug-in [di](/help/implement/js-implementation/plugins/impl-plugins.md)implementazione.

**Sintassi e valori** possibili {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

La *`campaign`* variabile presenta le stesse limitazioni di tutte le altre variabili. Adobe consiglia di limitare il valore ai caratteri ASCII standard.

**Sensibilità** caso {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

Le eVar non fanno distinzione tra maiuscole e minuscole, ma vengono visualizzate nelle maiuscole della prima occorrenza. Ad esempio, se la prima istanza di eVar1 è impostata su "Accesso", ma tutte le istanze successive vengono passate come "Accesso", i rapporti mostrano sempre "Accesso" come valore dell'eVar.

**Esempi** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Impostazioni** di configurazione {#section_4083F281968443169EAF8C0E8529D7BC}

Ciascun valore della campagna rimane attivo per un utente e riceve credito per le attività e gli eventi di successo di tale utente fino alla scadenza. Puoi modificare la scadenza della variabile della campagna in Admin Console.

**Insidie, domande e suggerimenti**{#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* Per evitare che i click-through vengano ingranditi, usate il [!UICONTROL getValOnce] plug-in per consentire il conteggio dei click-through per una campagna solo una volta per sessione. Per ulteriori informazioni sul [!UICONTROL getValOnce] plug-in, consultate Plug-in [di](/help/implement/js-implementation/plugins/impl-plugins.md)implementazione.

* Per ulteriori informazioni sul tracciamento delle campagne di marketing e degli acquisti di parole chiave, vedi [Campagne](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Utilizzate l'icona [!DNL DigitalPulse Debugger] per visualizzare il valore effettivo delle campagne (v0 nel debugger). Se v0 non viene visualizzato nel debugger, non vengono registrati dati della campagna per quella pagina.
