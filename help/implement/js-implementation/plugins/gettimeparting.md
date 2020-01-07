---
description: Il plug-in getTimeParting popola le variabili personalizzate con i valori dell'ora del giorno, del giorno della settimana e del fine settimana e del giorno della settimana in variabili personalizzate. Analysis Workspace offre dimensioni pronte per la suddivisione del tempo. Il plug-in deve essere utilizzato se le dimensioni suddivise in base al tempo sono necessarie in altre soluzioni Analytics, al di fuori di Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 73d20b23e38bc619c156c418c95096a94d2fdfce

---


# getTimeParting

Il plug-in getTimeParting fornisce una soluzione di analisi completa che consente di acquisire i dettagli del momento in cui qualsiasi attività misurabile ha luogo sul sito.

È consigliabile utilizzare il plug-in getTimeParting se si desidera suddividere le metriche per una suddivisione ripetibile del tempo in un determinato intervallo di date.  Ad esempio, il plug-in getTimeParting consente di confrontare i tassi di conversione tra due giorni diversi della settimana (ad esempio, tutti i giorni di domenica e tutti i giovedì), due periodi diversi del giorno (ad es. tutte le mattine rispetto a tutte le serate) o anche due minuti successivi (ad es. tutte le istanze delle ore 10:00 rispetto a tutte le istanze delle ore 10:01) per l&#39;intervallo di data specificate nel rapporto.

[!DNL Analysis Workspace] fornisce dimensioni simili e pronte all&#39;uso, formattate in modo leggermente diverso rispetto a quanto fornito da questo plug-in (vedere [qui](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html)).  Adobe Consulting consiglia di consultare il resto della sezione della guida per stabilire se il plug-in fornisce i dati in modo più adatto alle proprie esigenze.

Se non è necessario suddividere le metriche per una divisione ripetibile del tempo in un intervallo di date specifico, non sarà necessario utilizzare il plug-in getTimeParting.  Inoltre, se trovate sufficienti le dimensioni [!DNL Analysis Workspace] di suddivisione del tempo, non dovrete implementare questo plug-in.

>[!CAUTION] La soluzione fornita dalla versione 4.0+ del plug-in getTimeParting è molto diversa da quella fornita dalle versioni precedenti del plug-in.  Se si sceglie di effettuare l&#39;aggiornamento da una versione precedente alla 4.0, è necessario implementare la soluzione &quot;da zero&quot;.  In altre parole, è necessario impostare una eVar completamente nuova - una eVar - per contenere i dati forniti dal plugin e leggere attentamente questa documentazione prima di implementare la soluzione.

>[!CAUTION] Inoltre: Questa versione del plugin non è *completamente* compatibile con i browser Microsoft Internet Explorer, anche se il plugin è completamente compatibile con i browser Microsoft Edge.   I visitatori che utilizzano Internet Explorer saranno in grado di fornire l&#39;ora, ma solo nel loro fuso orario *locale* , anziché di convertirla nel fuso orario specificato.  Vedere gli esempi di seguito per una soluzione che non includerà i dati dai browser Internet Explorer ma che terrà conto della loro presenza.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

> [!WARNING] Verificate sempre tutte le implementazioni dei plug-in prima di distribuirli in produzione, in modo da garantire il funzionamento previsto della raccolta dei dati.

## Prerequisiti

Nessuno

## Come implementare

* Copia + Incolla il seguente codice in qualsiasi punto della sezione Plugins del codice AppMeasurement:

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] Puoi anche utilizzare un gestore di tag come Adobe Launch per distribuire il codice del plug-in senza doverlo collegare ad AppMeasurement o ad altre soluzioni di analisi

* Eseguire la funzione getTimeParting come descritto di seguito all&#39;interno della funzione doPlugins o in qualsiasi altra posizione in cui è necessario acquisire i dati di suddivisione del tempo

**Argomenti per passare**

* t: (stringa **OPZIONALE ma consigliata**) Il nome del fuso orario in cui convertire l&#39;ora locale del visitatore.  Il valore predefinito è &quot;Etc/GMT&quot;, oppure &quot;UTC/GMT&quot; se non è impostato.  Per un elenco completo dei valori da immettere, visitate [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones] .

I valori comuni includono:

* &quot;America/New_York&quot; per Ora orientale
* &quot;America/Chicago&quot; per ora centrale
* &quot;America/Denver&quot; per il tempo di montagna
* &quot;America/Los_Angeles&quot; per l&#39;ora del Pacifico

## Restituisce

Il plug-in getTimeParting restituisce una stringa contenente quanto segue:

* L&#39;anno in corso
* Il mese corrente
* Data corrente (giorno del mese)
* Il giorno corrente (cioè il giorno della settimana)
* Ora corrente (tempo non militare)

Ciascuno degli elementi sopra elencati è delimitato da un carattere barra verticale (&quot;|&quot;).

## Chiamate di esempio

Utilizzate il seguente codice se vi trovate a Parigi, in Francia e desiderate utilizzare eVar10 (in Adobe Analytics) per acquisire i dati relativi alla suddivisione del tempo:

```s.eVar10 = getTimeParting("Europe/Paris")```

Utilizzate il seguente codice se vi trovate a San Jose, California:

```s.eVar10 = getTimeParting("America/Los_Angeles")```

Usa il seguente codice se ti trovi nel paese africano del Ghana:

```s.eVar10 = getTimeParting();```

Il Ghana si trova entro il fuso orario UTC/GMT.  Pertanto, questo esempio mostra che nessun argomento del plugin sarà necessario in tali circostanze.

Utilizzate il seguente codice se vi trovate a New York e non desiderate includere i dati dei visitatori di Internet Explorer (poiché i valori restituiti dai browser IE possono essere forniti solo nell&#39;ora locale del visitatore)

```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**Risultati Da Chiamate**

Se un visitatore di Denver visita un sito il 31 agosto 2020 alle 09:15, nel seguente codice...

```s.eVar10 = getTimeParting("Europe/Athens");```

...imposta s.eVar10 come **anno=2020| mese=agosto| date=31| day=Monday| time=6:15 PM**

Codice seguente...

```s.eVar10 = getTimeParting("America/Nome");```

... imposterebbe s.eVar10 come **anno=2020| mese=agosto| date=31| day=Monday| time=6:15 AM**

Codice seguente...

```s.eVar10 = getTimeParting("Asia/Calcutta");```

... imposterebbe s.eVar10 come **anno=2020| mese=agosto| date=31| day=Monday| time=8:45 PM**

Codice seguente...

```s.eVar10 = getTimeParting("Australia/Sydney");```

... imposterebbe s.eVar10 come **anno=2020| mese=settembre| date=1| giorno=martedì| time=1:15 AM**

## Configurazione di Adobe Analytics

Se desiderate acquisire i dati di suddivisione del tempo in Adobe Analytics, configurate una nuova eVar con le seguenti caratteristiche:

* Nome: Suddivisione tempo
* Allocazione: Più recente (ultimo)
* Scadenza dopo: Visita
* Tutti gli altri attributi utilizzano i valori predefiniti forniti
