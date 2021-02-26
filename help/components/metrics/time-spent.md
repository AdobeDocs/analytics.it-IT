---
title: Calcolo del tempo trascorso in  Adobe Analytics
description: Una pagina aggregata di dimensioni e metriche del tempo trascorso.
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '1433'
ht-degree: 9%

---


# Panoramica del tempo trascorso

Diverse metriche e dimensioni [!UICONTROL 'time spent'] sono disponibili  prodotti Adobe Analytics.

## Metriche &quot;Tempo trascorso&quot;

| Metrica | Definizione | Disponibile in |
|---|---|---|
| [!UICONTROL Total seconds spent] | Rappresenta il tempo totale di interazione dei visitatori con un elemento dimensione specifico. Include l’istanza di un valore e una persistenza tra tutti gli hit successivi. Nel caso delle proprietà, il tempo trascorso viene conteggiato anche tra gli eventi di collegamento successivi. |  Analysis Workspace, Reporting e analisi, Report Builder (denominato &quot;tempo totale trascorso&quot;), Data Warehouse |
| [!UICONTROL Time spent per visit] (Seconds) | *Totale secondi passati / (visita-rimbalzi)*<br> Rappresenta la quantità media di tempo che i visitatori interagiscono con un elemento dimensione specifico durante ogni visita. |  Analysis Workspace, Reporting e analisi |
| [!UICONTROL Time spent per visitor] (Secondi) | *Totale secondi passati/*<br> visitatore univocoRappresenta la quantità media di tempo che i visitatori interagiscono con un elemento dimensione specifico per tutta la durata del visitatore (lunghezza del cookie). |  Analysis Workspace, Reporting e analisi |
| [!UICONTROL Average time spent on site] (Secondi) | Rappresenta la quantità totale di tempo che i visitatori interagiscono con un elemento dimensione specifico, per sequenza con un elemento dimensione. Non è limitato alle medie del &quot;sito&quot; come suggerisce il nome. Per ulteriori informazioni sulle sequenze, consulta la sezione &quot;Modalità di calcolo del tempo trascorso&quot;.<br>**Nota**: Questa metrica è molto probabilmente diversa da &#39;Tempo trascorso per visita&#39; a livello di elemento dimensione a causa delle differenze nel denominatore nel calcolo. |  Analysis Workspace, Reporting e analisi (visualizzati in minuti), Report Builder (visualizzati in minuti) |
| [!UICONTROL Average time spent on page] | Metrica obsoleta.<br> Si consiglia invece di utilizzare &quot;Tempo medio trascorso sul sito&quot; se è necessario il tempo medio per un elemento dimensione. | Report Builder (quando una dimensione è nella richiesta) |
| [!UICONTROL Total session length], alias  [!UICONTROL Previous session length] | Solo SDK per app mobili. <br>Determinato al successivo avvio dell’app per la sessione precedente. Calcolata in secondi, questa metrica non conta quando l&#39;app è in background, solo quando è in uso. Si tratta di una metrica a livello di sessione.<br>Esempio: L&#39;app ABC viene installata e avviata e utilizzata per 2 minuti, quindi chiudiamo l&#39;app. Nessun dato inviato per questa ora di sessione. Al successivo avvio dell&#39;app, [!UICONTROL Previous Session Length] verrà inviato con un valore pari a 120. |  Analysis Workspace, Reporting e analisi, Report Builder, interfaccia utente di Mobile Services |
| [!UICONTROL Average session length] (dispositivi mobili) | *Lunghezza totale sessione / (avvii - primi avvii)Solo SDK per app*<br> mobile. Si tratta di una metrica a livello di sessione. | Report Builder, interfaccia utente di Mobile Services |

## Dimensioni &quot;Tempo trascorso&quot;

| Dimensione | Definizione | Disponibile in |
| --- | --- | --- |
| [!UICONTROL Time spent per visit - granular] | Il tempo totale trascorso durante la visita troncato al secondo più vicino e applicato a ogni hit che faceva parte della visita. Si tratta di una dimensione a livello di visita. | Analysis Workspace  |
| [!UICONTROL Time spent per visit - bucketed] | La dimensione granulare si è divisa in 9 intervalli diversi. Si tratta di una dimensione a livello di visita. Gli intervalli includono:<ul><li>Inferiore a 1 minuto</li><li>1-5 minuti</li><li>5-10 minuti</li><li>10-30 minuti</li><li>30-60 minuti</li><li>1-2 ore</li><li>2-5 ore</li><li>5-10 ore</li><li>10-15 ore</li></ul>**Nota**: Non è possibile utilizzare più bucket perché una visita scade dopo 12 ore di attività. | Analysis Workspace, Reports &amp; Analytics, Report Builder |
| [!UICONTROL Time spent on page - granular] | Il tempo totale trascorso su ogni hit, troncato al secondo più vicino. Si tratta di una dimensione a livello di hit e include sia le visualizzazioni della pagina che gli eventi di collegamento. Nonostante il nome, non è limitato alla dimensione &quot;pagina&quot;. | Analysis Workspace  |
| [!UICONTROL Time spent on page - bucketed] | La dimensione granulare si è intrecciata in 10 intervalli diversi; tuttavia, la dimensione esterna conteggia solo le visualizzazioni di pagina (ed esclude gli eventi di collegamento). Si tratta di una dimensione a livello di hit. Gli intervalli includono:<ul><li>inferiore a 15 secondi</li><li>Da 15 a 29 secondi</li><li>30-59 secondi</li><li>Da 1 a 3 minuti</li><li>Da 3 a 5 minuti</li><li>Da 5 a 10 minuti</li><li>da 10 a 15 minuti</li><li>Da 15 a 20 minuti</li><li>20-30 minuti</li><li>più di 30 minuti</li></ul> |  Analysis Workspace, Reporting e analisi |

## Modalità di calcolo di &#39;Time Spent&#39;

 Adobe Analytics utilizza valori espliciti (compresi gli eventi di collegamento e le visualizzazioni video) per calcolare [!UICONTROL Time Spent].

>[!NOTE]
>
>Senza eventi di collegamento come [!UICONTROL Video Views] o [!UICONTROL Exit Links], non è possibile conoscere il tempo trascorso sull&#39;ultimo hit di una visita. Per motivi simili, [!UICONTROL Bounce Visits] (ad es. visite con un solo hit) non dispone anche di un &quot;tempo trascorso&quot; associato.

Il **numeratore** in tutti i calcoli del tempo trascorso è il totale dei secondi trascorsi.

Il **denominatore** non è disponibile come metrica separata in  Adobe Analytics. Per le metriche &quot;tempo trascorso&quot; a livello di hit, il denominatore è sequenze. Una sequenza è un insieme consecutivo di hit in cui una determinata variabile contiene lo stesso valore (sia che venga impostata, estesa in avanti o persistente). Per &quot;Spread forward&quot; si intende la persistenza di prop tra le visualizzazioni di pagina (ossia tra eventi di collegamento successivi), ai fini del calcolo del tempo trascorso.

* Ad esempio, nel caso di [!UICONTROL Page Name] o di altre dimensioni a livello di hit, il denominatore è essenzialmente [!UICONTROL 'Instances'] o [!UICONTROL 'Page Views'], ma con ricariche e valori non impostati (ad esempio, eventi di collegamento) conteggiati come singola interazione (una sequenza).

* Anche gli hit di rimbalzo e di uscita vengono rimossi dal denominatore perché non è possibile conoscere il tempo trascorso.

## Domande frequenti

**Q1: È possibile applicare tutte le metriche &quot;tempo trascorso&quot; a qualsiasi dimensione?**

A: Le metriche &quot;tempo trascorso&quot; che possono essere applicate a qualsiasi dimensione sono:

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (Secondi)

* [!UICONTROL Time spent per visitor] (Secondi)

* [!UICONTROL Average time spent on site] (Secondi)

**Q2: Qual è la dimensione del tempo trascorso più utilizzata nelle suddivisioni con altre dimensioni?**

A: La dimensione [!UICONTROL Time Spent on Page – granular] è una dimensione a livello di hit. Suddividendo questa dimensione per un’altra dimensione, potrai vedere i secondi in cui è durato un hit in cui era presente anche la dimensione di suddivisione.
Nell’esempio seguente, il termine di ricerca &quot;classifieds&quot; è associato a un hit time di 54 secondi, 59 secondi ecc., ad esempio per indicare ai visitatori che stanno trascorrendo del tempo a leggere il contenuto restituito per quel termine.

![](assets/time-spent1.png)

**Q3: Quale metrica è appropriata rispetto alla dimensione di  [!UICONTROL Time Spent on Page – granular]?**

A: Qualsiasi metrica. La dimensione mostra il tempo trascorso sull’hit esatto in cui si è verificato l’evento. Un tempo maggiore impiegato indica che un visitatore è rimasto più a lungo in una pagina (hit) in cui si è verificato l’evento.

![](assets/time-spent2.png)

**Q4: Come  [!UICONTROL Average Time Spent on Site] differisce da  [!UICONTROL Time Spent per Visit]?**

A: La differenza è il denominatore della metrica:

* [!UICONTROL Average time spent on site] utilizza le sequenze che includono un elemento dimensione.

* [!UICONTROL Time spent per visit] utilizza il conteggio visite

Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma saranno diverse a livello di hit.

**Q5: Perché la suddivisione dei totali  [!UICONTROL Average Time Spent on Site] non corrisponde all&#39;elemento della riga padre?**

A: Poiché [!UICONTROL Average Time Spent on Site] dipende da sequenze non interrotte di una dimensione, il rapporto interno non dipende dal rapporto esterno quando si calcolano queste esecuzioni.

Ad esempio, considerare la visita seguente.

| hit# | 1 | 2 | 3 |
|---|---|---|---|
| **Secondi spesi** | 30 | 100 | 10 |
| **Nome pagina** | Home | Prodotto | Home |
| **data** | gen 1 | gen 1 | gen 1 |

Nel calcolare il tempo trascorso per la homepage sarebbe (30+10)/2=20, ma la suddivisione per giorno darebbe (30+10)/1=40, dal momento che il giorno ha una singola esecuzione ininterrotta del 1 gennaio.

Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma saranno diverse a livello di hit.

## Esempi di calcoli [!UICONTROL Time Spent]

Supponiamo che il seguente set di chiamate server riguardi un singolo visitatore all’interno di una singola visita:

| Visita hit# | 1 | 2 | 1 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tempo trascorso visita (in sec)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Secondi spesi** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo di hit** | Pagina | Collegamento | Pagina | Pagina | Pagina | Pagina | Pagina |
| **Nome pagina** | Home | - | Prodotto | Home | Home (ricarica) | Carrello | Conferma d&#39;ordine |
|  |  |  |  |  |  |  |  |
| **prop1** | A (set) | A (differenziale in avanti) | not set | B (set) | B (set) | A(set) | C (set) |
| **prop1 secondi trascorsi** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | Rosso (set) | Rosso (persistente) | (scaduto) | Blu (set) | Blu (set) | Blu (persistente) | Rosso (set) |
| **eVar 1 secondi trascorsi** | 30 | 50 | - | 10 | 40 | 60 | - |

In base alla tabella precedente, le metriche del tempo trascorso sono calcolate come segue:

| prop1 | Totale secondi trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Conteggio delle sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Tempo non attribuito | 100 | - | - | - | - |

| eVar1 | Totale secondi trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Conteggio delle sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| Rosso | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Blu | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Tempo non attribuito | 100 | - | - | - | - |

Tempo trascorso per visita (granulare): 290
Tempo trascorso sulla pagina (granulare): 10, 30, 40, 50, 60, 100

Alcune note aggiuntive a sostegno dell’esempio:

* Tutti i calcoli del tempo trascorso si basano sul tempo trascorso della visita che inizia a zero al primo hit della visita.

* &quot;Secondi passati&quot; è la differenza tra la marca temporale dell’hit corrente e la marca temporale dell’hit successivo. Di conseguenza, l’ultimo hit della visita (e rimbalzi) non ha tempo trascorso.

* Una &quot;sequenza&quot; è un insieme consecutivo di hit in cui una determinata variabile contiene lo stesso valore (sia che venga impostata, estesa in avanti o persistente). Ad esempio, prop1 &quot;A&quot; ha due sequenze: hit 1 e 2 e hit 6. I valori sull’ultimo hit della visita non avviano una nuova sequenza perché l’ultimo hit non ha tempo trascorso. Il tempo medio trascorso sul sito utilizza le sequenze nel denominatore.

   * Solo per il tempo trascorso, le proprietà vengono &quot;distribuite in avanti&quot; dagli hit di pagina agli hit di collegamento successivi, come mostrato sopra per prop1 nell’hit 2. Questo consente al valore impostato per prop1 sull&#39;hit 1 (&quot;A&quot;) di accumulare il tempo trascorso sull&#39;hit 2.

   * Le eVar accumulano il tempo trascorso su qualsiasi hit in cui il eVar  è impostato o persistente.  persistenza dell&#39;eVar è definita dalle impostazioni di  eVar in Analytics > Amministratore.
