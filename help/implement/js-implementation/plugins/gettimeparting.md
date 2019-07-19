---
description: Il plug-in gettimeparting compila le variabili personalizzate con l'ora del giorno, giorno della settimana e fine settimana e i valori del giorno della settimana in variabili personalizzate. Analysis Workspace offre dimensioni suddivise in tempo reale. Il plug-in deve essere utilizzato se le dimensioni suddivise in base al tempo sono necessarie in altre soluzioni Analytics, all'esterno di Analysis Workspace.
keywords: Implementazione di Analytics
seo-description: Il plug-in gettimeparting compila le variabili personalizzate con l'ora del giorno, giorno della settimana e fine settimana e i valori del giorno della settimana in variabili personalizzate. Analysis Workspace offre dimensioni suddivise in tempo reale. Il plug-in deve essere utilizzato se le dimensioni suddivise in base al tempo sono necessarie in altre soluzioni Analytics, all'esterno di Analysis Workspace.
seo-title: Gettimeparting
solution: Analytics
subtopic: Plug-in
title: Gettimeparting
topic: Sviluppatore e implementazione
uuid: 74 f 696 a 3-7169-4560-89 b 2-478 b 3 d 8385 e 1
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Gettimeparting

Il plug-in gettimeparting compila le variabili personalizzate con l'ora del giorno, giorno della settimana e fine settimana e i valori del giorno della settimana in variabili personalizzate. [!UICONTROL Analysis Workspace] offre dimensioni suddivise nel tempo. The plug-in should be used if time parting dimensions are needed in other Analytics solutions, outside of [!UICONTROL Analysis Workspace].

Questo plug-in acquisisce le informazioni relative alla data e all'ora disponibili nel browser Web dell'utente. Ottiene l'ora del giorno e il giorno della settimana da queste informazioni. quindi converte questi dati nel fuso orario desiderato. Inoltre, account Ora legale.

>[!NOTE]
>
>Le istruzioni seguenti richiedono di modificare il codice della raccolta dati sul sito. This can affect data collection on your site, and should only be done by a developer with experience using and implementing [!DNL Analytics].

## Plug-in Code {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**Sezione di configurazione**

Place the following code in the area of the [!DNL s_code.js] file labeled [!UICONTROL CONFIG SECTION], and make the necessary updates as described below.

`s._tpDST` - un array di valori DST. The array is structured in the following format: `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27'}
```

Nota per client Hemisphere settentrionali: nei valori DST dell'array è iniziale DST, end DST.

Nota per client Hemisphere australi: nei valori DST dell'array, inizia DST, inizia DST.

**Parametri**

```js
var tp = s.getTimeParting(h,z);
```

* h = (richiesto) Hemisphere - Specificate l'hemisphere in cui convertire l'ora. Si tratta di un valore'n'o's '. Viene utilizzato per determinare come utilizzare l'array DST passato. Se'n'viene passato, il plug-plugin utilizza le date quando DST è attivato. Se's'viene passato, il plug-plugin utilizza le date quando DST è disattivato.
* z = (facoltativo) Fuso orario - Se si desidera che i dati siano basati su un periodo di tempo specifico, sarà necessario specificare come ore diverse da GMT qui. Nota che deve essere la GMT durante non DST. Se non viene specificato alcun valore, il valore predefinito è GMT (ossia '-5 'per l'ora orientale USA)

**Restituisce**

Restituisce un valore di tempo concatenato al livello e al giorno della settimana, ad esempio:

```
8:03 AM|Monday
```

You can then use [Classifications](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) to group visits into time periods. Ad esempio, potete impostare una regola in Generatore regole di classificazione per bucket delle visite tra le 9:00 e le 9:59 di AM su «9:00 AM - 10:00 AM». In alternativa alle classificazioni, puoi fornire ulteriori logica lato client per indirizzare le visite in javascript.

**Esempio di chiamata**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**PLUGINS SECTION**

Add the following code to the [!UICONTROL PLUGINS SECTION] in the [!DNL s_code.js] file.

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**Note**

* Verifica sempre le installazioni dei plug-in per garantire che la raccolta dati sia come previsto prima di distribuire alla produzione.
* Le variabili di configurazione devono essere impostate per funzionare correttamente.

