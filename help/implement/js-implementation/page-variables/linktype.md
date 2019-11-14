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



# linkType

La variabile è una variabile opzionale utilizzata nel tracciamento dei collegamenti che determina quale rapporto viene visualizzato un nome o un URL di collegamento (collegamenti personalizzati, di download o di uscita).

<!-- 

linkType.xml

 -->

La *`linkType`* variabile non è normalmente necessaria perché il secondo parametro della *`tl()`* funzione la sostituisce.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
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
   <td> Un carattere </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Download dei file </p> <p>Collegamenti personalizzati </p> <p>Esci dai collegamenti </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

I collegamenti personalizzati inviano dati ad Analytics. La *`linkType`* variabile (o il secondo parametro nella *`tl()`* funzione) viene utilizzato per identificare il rapporto in cui viene visualizzato il nome del collegamento o l'URL ( [!UICONTROL Custom], [!UICONTROL Download]o [!UICONTROL Exit Links] rapporto).

Per i collegamenti di uscita e di download, la *`linkType`* variabile viene compilata automaticamente a seconda che il collegamento selezionato sia un collegamento di uscita o di download. È possibile configurare un collegamento personalizzato per inviare dati a uno qualsiasi dei tre rapporti con questa variabile o con il secondo parametro della *`tl()`* funzione. Impostando *`linkType`* su 'o', 'e' o 'd', l'URL *`linkName`* o il collegamento viene inviato rispettivamente al [!UICONTROL Custom Links], [!UICONTROL Exit Links]o [!UICONTROL File Downloads] report.

**Sintassi e valori** possibili {#section_18DB3A8083FB4F75B970055ED336DA4E}

La sintassi della *`linkType`* variabile dipende dall'utilizzo di una stringa XML o di query.

Se si utilizza XML, la variabile può contenere solo un singolo carattere, ad esempio 'o,' 'e,' o 'd'.

```js
s.tl(this,'o','Link Name');
```

Se si utilizza la stringa di query `pe`, è necessario utilizzare `lnk_d`, `lnk_e`o `lnk_o`.

**Esempi** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Impostazioni** di configurazione {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Nessuno

**Insidie, domande e suggerimenti**{#section_F0D01DDE3FDA486C987162DA50A79C45}

* Se non *`linkType`* viene specificato, vengono utilizzati collegamenti personalizzati ('o').
