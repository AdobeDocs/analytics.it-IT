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



# linkName

La variabile è una variabile opzionale utilizzata in [!UICONTROL Link Tracking] che determina il nome di un collegamento personalizzato, di download o di uscita.

<!-- 

linkName.xml

 -->

La *`linkName`* variabile non è normalmente necessaria perché il terzo parametro della *`tl()`* funzione la sostituisce.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
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
   <td> 100 byte </td> 
   <td> pev2 </td> 
   <td> <p>Download dei file </p> <p>Collegamenti personalizzati </p> <p>Esci dai collegamenti </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Custom Links] fare riferimento ai collegamenti che inviano dati di tracciamento. La *`linkName`* variabile (o il terzo parametro della *`tl()`* funzione) viene utilizzato per identificare il valore visualizzato nel [!UICONTROL Custom], [!UICONTROL Download]o [!UICONTROL Exit Links] report. Se non *`linkName`* viene popolato, l'URL del collegamento viene visualizzato nel rapporto.

**Sintassi e valori** possibili {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

Non esistono limitazioni *`linkName`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Impostazioni** di configurazione {#section_F15FF429FC274F708D50DF79D4668EA3}

Nessuno

**Insidie, domande e suggerimenti**{#section_170A78452A7340B5B229713AC1FB71FA}

* La *`linkName`* variabile viene sostituita dal terzo parametro della *`tl()`* funzione.

* Se la *`linkName`* variabile e il terzo parametro della *`tl()`* funzione sono vuoti, l'URL completo del collegamento (ad eccezione della stringa di query) viene visualizzato nel rapporto (anche se il collegamento è relativo).
