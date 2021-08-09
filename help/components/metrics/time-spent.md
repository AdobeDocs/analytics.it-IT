---
title: Calcolo del tempo trascorso in Adobe Analytics
description: Pagina aggregata di dimensioni e metriche del tempo trascorso.
exl-id: 71e9b856-8a0a-47be-a73f-4dc7d639a5de
source-git-commit: 085fd95da383671a51ce1e5888bea3db92c038bd
workflow-type: tm+mt
source-wordcount: '1453'
ht-degree: 9%

---

# Panoramica del tempo trascorso

Diverse metriche e dimensioni [!UICONTROL 'time spent'] sono disponibili nei prodotti Adobe Analytics.

## Metriche &quot;Tempo trascorso&quot;

| Metrica | Definizione | Disponibile in |
|---|---|---|
| [!UICONTROL Total seconds spent] | Rappresenta la quantità totale di tempo che i visitatori interagiscono con un elemento dimensione specifico. Include l’istanza di un valore e una persistenza in tutti gli hit successivi. Nel caso delle proprietà, il tempo trascorso viene conteggiato anche tra gli eventi di collegamento successivi. | Analysis Workspace, Reports &amp; Analytics, Report Builder (chiamato &quot;tempo totale trascorso&quot;), Data Warehouse |
| [!UICONTROL Time spent per visit] (Seconds) | *Totale secondi trascorsi / (rimbalzi a visita)*<br> Rappresenta la quantità media di tempo che i visitatori interagiscono con un elemento dimensione specifico durante ogni visita. | Analysis Workspace, Reports &amp; Analytics |
| [!UICONTROL Time spent per visitor] (Secondi) | *Totale secondi trascorsi/*<br> visitatore univocoRappresenta il tempo medio di interazione dei visitatori con un elemento dimensione specifico per tutta la durata del visitatore (lunghezza del cookie). | Analysis Workspace, Reports &amp; Analytics |
| [!UICONTROL Average time spent on site] (Secondi) | Rappresenta la quantità totale di tempo che i visitatori interagiscono con un elemento dimensione specifico, per sequenza con un elemento dimensione. Non è limitato alle medie del &quot;sito&quot; come suggerisce il nome. Per ulteriori informazioni sulle sequenze, consulta la sezione &quot;Modalità di calcolo del tempo trascorso&quot;.<br>**Nota**: Questa metrica è molto probabilmente diversa da &quot;Tempo trascorso per visita&quot; a livello di elemento dimensione a causa delle differenze nel denominatore nel calcolo. | Analysis Workspace, Reports &amp; Analytics (in minuti), Report Builder (in minuti) |
| [!UICONTROL Average time on site] | Si tratta della stessa metrica di *Tempo medio trascorso sul sito (Secondi)*, eccetto formattato come Tempo (hh:mm:ss) | Analysis Workspace |
| [!UICONTROL Average time spent on page] | Metrica obsoleta.<br> È invece consigliabile utilizzare &quot;Tempo medio trascorso sul sito&quot; se è necessario il tempo medio per un elemento dimensione. | Report Builder (quando una dimensione si trova nella richiesta) |
| [!UICONTROL Total session length], anche noto come  [!UICONTROL Previous session length] | Solo SDK per app mobili. <br>Determinata la prossima volta che l’app viene avviata, per la sessione precedente. Calcolata in secondi, questa metrica non conta quando l’app è in background, solo quando è in uso. Questa è una metrica a livello di sessione.<br>Esempio: Possiamo installare l’app ABC e avviarla e utilizzarla per 2 minuti, quindi chiudere l’app. Nessun dato inviato per l&#39;ora di sessione corrente. Al prossimo avvio dell’app, [!UICONTROL Previous Session Length] verrà inviato con un valore di 120. | Analysis Workspace, Reports &amp; Analytics, Report Builder, interfaccia utente di Mobile Services |
| [!UICONTROL Average session length] (dispositivi mobili) | *Lunghezza totale della sessione / (Lanci - Primi avvii)*<br> Solo SDK per app mobile. Questa è una metrica a livello di sessione. | Report Builder, interfaccia utente di Mobile Services |

## Dimensioni &quot;Tempo trascorso&quot;

| Dimensione | Definizione | Disponibile in |
| --- | --- | --- |
| [!UICONTROL Time spent per visit - granular] | Il tempo totale trascorso durante la visita è stato troncato al secondo più vicino e applicato a ogni hit che faceva parte della visita. Si tratta di una dimensione a livello di visita. | Analysis Workspace |
| [!UICONTROL Time spent per visit - bucketed] | La dimensione granulare è divisa in 9 intervalli diversi. Si tratta di una dimensione a livello di visita. Gli intervalli includono:<ul><li>Inferiore a 1 minuto</li><li>1-5 minuti</li><li>5-10 minuti</li><li>10-30 minuti</li><li>30-60 minuti</li><li>1-2 ore</li><li>2-5 ore</li><li>5-10 ore</li><li>10-15 ore</li></ul>**Nota**: Non possono esserci blocchi più grandi di questo, perché una visita scade dopo 12 ore di attività. | Analysis Workspace, Reports &amp; Analytics, Report Builder |
| [!UICONTROL Time spent on page - granular] | Il tempo totale trascorso su ciascun hit, troncato al secondo più vicino. Si tratta di una dimensione a livello di hit e include sia le visualizzazioni di pagina che gli eventi di collegamento. Nonostante il nome, non è limitato alla dimensione &quot;page&quot;. | Analysis Workspace |
| [!UICONTROL Time spent on page - bucketed] | La dimensione granulare è divisa in 10 intervalli diversi; tuttavia, la dimensione a blocchi conta solo le visualizzazioni di pagina (ed esclude gli eventi di collegamento). Si tratta di una dimensione a livello di hit. Gli intervalli includono:<ul><li>inferiore a 15 secondi</li><li>da 15 a 29 secondi</li><li>da 30 a 59 secondi</li><li>da 1 a 3 minuti</li><li>da 3 a 5 minuti</li><li>Da 5 a 10 minuti</li><li>da 10 a 15 minuti</li><li>da 15 a 20 minuti</li><li>20-30 minuti</li><li>più di 30 minuti</li></ul> | Analysis Workspace, Reports &amp; Analytics |

## Calcolo del valore di Tempo trascorso

Adobe Analytics utilizza valori espliciti (comprese le visualizzazioni di collegamento e video) per calcolare [!UICONTROL Time Spent].

>[!NOTE]
>
>Senza eventi di collegamento come [!UICONTROL Video Views] o [!UICONTROL Exit Links], non è possibile conoscere il tempo trascorso sull’ultimo hit di una visita. Per motivi simili, anche [!UICONTROL Bounce Visits] (cioè visite con un singolo hit) non ha un &quot;tempo trascorso&quot; associato ad esso.

Il **numeratore** in tutti i calcoli del tempo trascorso è il totale dei secondi trascorsi.

Il **denominatore** non è disponibile come metrica separata in Adobe Analytics. Per le metriche &quot;tempo trascorso&quot; a livello di hit, il denominatore è sequenze. Una sequenza è un insieme consecutivo di hit in cui una determinata variabile contiene lo stesso valore (sia che venga impostata, distribuita in avanti o persistente). Per &quot;Diffusione in avanti&quot; si intende la persistenza delle prop tra le visualizzazioni di pagina (cioè tra eventi di collegamento successivi), ai fini del calcolo del tempo trascorso.

* Ad esempio, nel caso di [!UICONTROL Page Name] o di altre dimensioni a livello di hit, il denominatore è essenzialmente [!UICONTROL 'Instances'] o [!UICONTROL 'Page Views'], ma con ricaricamenti e valori non impostati (ad esempio, eventi di collegamento) conteggiati come una singola interazione (una sequenza).

* Anche gli hit di mancato recapito e di uscita vengono rimossi dal denominatore perché non è possibile conoscere il tempo trascorso.

## Domande frequenti

**Q1: Tutte le metriche &quot;tempo trascorso&quot; possono essere applicate a qualsiasi dimensione?**

R: Le metriche &quot;tempo trascorso&quot; che possono essere applicate a qualsiasi dimensione sono:

* [!UICONTROL Total seconds spent]

* [!UICONTROL Time spent per visit] (Secondi)

* [!UICONTROL Time spent per visitor] (Secondi)

* [!UICONTROL Average time spent on site] (Secondi)

**Q2: Quale dimensione tempo trascorso è più utilizzata nelle suddivisioni con altre dimensioni?**

R: La dimensione [!UICONTROL Time Spent on Page – granular] è una dimensione a livello di hit. Se suddividi questo per un’altra dimensione, potrai sapere in quali secondi è durato un hit dove era presente anche la dimensione di suddivisione.
Nell’esempio seguente, il termine di ricerca &quot;annunci&quot; è associato a periodi di hit di 54 secondi, 59 secondi, ecc., ad esempio per indicare ai visitatori che trascorrono del tempo a leggere il contenuto restituito per quel termine.

![](assets/time-spent1.png)

**Q3: Quale metrica è appropriata rispetto alla dimensione di  [!UICONTROL Time Spent on Page – granular]?**

R: Qualsiasi metrica. La dimensione mostra il tempo trascorso sull’hit esatto in cui si è verificato l’evento. Un tempo più lungo trascorso indica che un visitatore è rimasto più a lungo in una pagina (hit) in cui si è verificato l’evento.

![](assets/time-spent2.png)

**Q4: Quali sono le  [!UICONTROL Average Time Spent on Site] differenze tra  [!UICONTROL Time Spent per Visit]?**

R: La differenza è il denominatore della metrica:

* [!UICONTROL Average time spent on site] utilizza le sequenze che includono un elemento dimensione.

* [!UICONTROL Time spent per visit] utilizza il conteggio delle visite

Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma saranno diverse a livello di hit.

**Q5: Perché la suddivisione dei totali  [!UICONTROL Average Time Spent on Site] non corrisponde alla riga padre?**

R: Poiché [!UICONTROL Average Time Spent on Site] dipende da sequenze non interrotte di una dimensione e il rapporto interno non dipende dal rapporto esterno durante il calcolo di tali esecuzioni.

Ad esempio, considera la visita seguente.

| hit# | 1 | 2 | 3 |
|---|---|---|---|
| **Secondi spesi** | 30 | 100 | 10 |
| **Nome pagina** | Home | Prodotto | Pagina principale |
| **data** | Gen. 1 | Gen. 1 | Gen. 1 |

Quando si calcola il tempo trascorso per la Homepage sarebbe (30+10)/2=20, ma la suddivisione per giorno darebbe (30+10)/1=40 dal momento che il giorno ha una singola esecuzione ininterrotta del 1 gennaio.

Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma saranno diverse a livello di hit.

## Esempi di calcoli [!UICONTROL Time Spent]

Supponiamo che il seguente set di chiamate server sia per un singolo visitatore all’interno di una singola visita:

| Visita l&#39;hit# | 1 | 2 | 1 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tempo trascorso della visita (in secondi)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Secondi spesi** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo di hit** | Pagina | Collegamento | Pagina | Pagina | Pagina | Pagina | Pagina |
| **Nome pagina** | Pagina principale | - | Prodotto | Pagina principale | Home (ricarica) | Carrello | Conferma d&#39;ordine |
|  |  |  |  |  |  |  |  |
| **prop1** | A (set) | A (differita in avanti) | non impostato | B (set) | B (set) | A(set) | C (set) |
| **prop1 secondi trascorsi** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar1** | Rosso (set) | Rosso (persistente) | (scaduto) | Blu (set) | Blu (set) | Blu (persistente) | Rosso (set) |
| **eVar1 secondi trascorsi** | 30 | 50 | - | 10 | 40 | 60 | - |

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
| Blu | 10+40+60=110 | 10/1=110 | 10/1=110 | 1 | 10/1=110 |
| Tempo non attribuito | 100 | - | - | - | - |

Tempo trascorso per visita (granulare): 290
Tempo trascorso sulla pagina (granulare): 10, 30, 40, 50, 60, 100

Alcune note aggiuntive a supporto dell’esempio:

* Tutti i calcoli del tempo trascorso si basano sul tempo trascorso della visita che inizia a zero al primo hit della visita.

* &quot;Secondi trascorsi&quot; è la differenza tra il timestamp dell&#39;hit corrente e il timestamp dell&#39;hit successivo. Di conseguenza, l’ultimo hit della visita (e rimbalzi) non ha tempo trascorso.

* Una &quot;sequenza&quot; è un insieme consecutivo di risultati in cui una determinata variabile contiene lo stesso valore (sia mediante impostazione, distribuzione in avanti o persistenza). Ad esempio, la prop1 &quot;A&quot; ha due sequenze: hit 1 e 2 e hit 6. I valori sull’ultimo hit della visita non iniziano una nuova sequenza perché l’ultimo hit non ha tempo trascorso. Il tempo medio trascorso sul sito utilizza sequenze nel denominatore.

   * Solo ai fini del tempo trascorso, le proprietà vengono &quot;distribuite in avanti&quot; dagli hit di pagina agli hit di collegamento successivi, come mostrato in precedenza per prop1 nell’hit 2. Questo consente al valore impostato per prop1 sull&#39;hit 1 (&quot;A&quot;) di accumulare il tempo trascorso sull&#39;hit 2.

   * Le eVar accumulano il tempo trascorso per qualsiasi hit in cui l’eVar è impostato o mantenuto. La persistenza eVar è definita dalle impostazioni di eVar in Analytics > Amministratore.
