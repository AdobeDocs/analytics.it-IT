---
description: Il plug-in getTimeParting popola le variabili personalizzate con i valori dell'ora del giorno, del giorno della settimana e del fine settimana e del giorno della settimana in variabili personalizzate. Analysis Workspace offre dimensioni pronte per la suddivisione del tempo. Il plug-in deve essere utilizzato se le dimensioni suddivise in base al tempo sono necessarie in altre soluzioni Analytics, al di fuori di Analysis Workspace.
keywords: Analytics Implementation
solution: Analytics
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getTimeParting

Il plug-in getTimeParting popola le variabili personalizzate con i valori dell'ora del giorno, del giorno della settimana e del fine settimana e del giorno della settimana in variabili personalizzate. [!UICONTROL Analysis Workspace] offre dimensioni predefinite per la suddivisione del tempo. Il plug-in deve essere utilizzato se le dimensioni suddivise in base al tempo sono necessarie in altre soluzioni Analytics, al di fuori di [!UICONTROL Analysis Workspace].

Questo plug-in acquisisce le informazioni relative a data e ora disponibili nel browser Web dell'utente. Riceve l'ora del giorno e il giorno della settimana da queste informazioni. Quindi converte questi dati nel fuso orario scelto. Rappresenta anche l'ora legale.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Codice plug-in {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**Sezione di configurazione**

Posizionare il codice seguente nell’area del [!DNL s_code.js] file etichettato [!UICONTROL CONFIG SECTION], quindi eseguire gli aggiornamenti necessari come descritto di seguito.

`s._tpDST` - un array di valori DST. L'array è strutturato nel seguente formato: `YYYY:'MM/DD,MM/DD'`

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
2019:'4/7,10/6',
2020:'4/5,10/4',
2021:'4/4,10/3'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3',
2020:'3/8,11/1',
2021:'3/14,11/7'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27',
2020:'3/29,10/25',
2021:'3/28,10/31'}
```

Nota per i client dell’emisfero boreale: nell'array i valori DST sono DST start, DST end.

Nota per i client dell’emisfero australe: nell'array i valori DST sono DST end, DST start.

**Parametri**

```js
var tp = s.getTimeParting(h,z);
```

* h = (obbligatorio) Emisfero - Specificate a quale emisfero state convertendo il tempo. È un valore di 'n' o 's'. Viene utilizzato per determinare come utilizzare l'array DST passato. Se viene passato 'n', il plugin usa le date quando DST è attivato. Se viene passato 's', il plugin usa le date quando DST è disattivato.
* z = (facoltativo) Fuso orario - Se si desidera che i dati siano basati su un periodo di tempo specifico, allora che dovrà essere specificato come orario diverso da GMT qui. Notate che questo deve essere il GMT durante non DST. Se non viene specificato alcun valore, per impostazione predefinita viene impostato su GMT (es. '-5' per US Eastern Time)

**Restituisce**

Restituisce un valore concatenato di ora a livello di minuto e giorno della settimana, ad esempio:

```
8:03 AM|Monday
```

Potete quindi utilizzare [Classificazioni](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) per raggruppare le visite in periodi di tempo. Ad esempio, è possibile impostare una regola in Generatore di regole di classificazione per effettuare visite senza intervallo tra le 9:00 e le 9:59 alle 9:00 - 10:00 AM. In alternativa alle classificazioni, è possibile fornire logica aggiuntiva lato client per eseguire il bucket delle visite in JavaScript.

**Esempio di chiamata**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**SEZIONE PLUG-IN**

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

* Verificate sempre le installazioni dei plug-in per garantire che la raccolta dei dati sia come previsto prima della distribuzione in produzione.
* Per il corretto funzionamento del plug-in è necessario impostare le variabili di configurazione.

