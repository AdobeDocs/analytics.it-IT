---
title: Calcolo del tempo trascorso in Adobe Analytics
description: Una pagina aggregata di dimensioni e metriche relative al tempo trascorso.
feature: Metrics
exl-id: 71e9b856-8a0a-47be-a73f-4dc7d639a5de
source-git-commit: 03502f42473791bec930cc688c0b7905acf12de6
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 8%

---

# Panoramica del tempo trascorso

Varie [!UICONTROL 'time spent'] [metriche](overview.md) e dimensioni sono offerte tra i prodotti Adobe Analytics. Questa pagina consente di distinguere la dimensione o la metrica desiderata che stai cercando.

## Metriche &quot;Tempo trascorso&quot;

| Metrica | Definizione | Disponibile in |
|---|---|---|
| [[!UICONTROL Total seconds spent]](total-seconds-spent.md) | Rappresenta il tempo totale in cui i visitatori interagiscono con un elemento dimensione specifico. Include l’istanza di un valore e la persistenza in tutti gli hit successivi. Nel caso di prop, il tempo trascorso viene conteggiato anche negli eventi di collegamento successivi. | Analysis Workspace, Report Builder (denominato &quot;tempo totale trascorso&quot;), Data Warehouse |
| [[!UICONTROL Time spent per visit] (secondi)](time-spent-per-visit.md) | Circa *Secondi totali trascorsi / (rimbalzi di visita)*<br> Rappresenta la quantità media di tempo in cui i visitatori interagiscono con un elemento di dimensione specifico durante ogni visita. **Nota**: questa metrica non può essere calcolata in modo indipendente perché il denominatore di questa funzione è una metrica interna. | Analysis Workspace |
| [[!UICONTROL Time spent per visitor] (secondi)](time-spent-per-visitor.md) | Circa *Totale secondi trascorsi / visitatore univoco*<br> Rappresenta il tempo medio di interazione dei visitatori con un elemento dimensione specifico nel corso della vita del visitatore (durata del cookie). **Nota**: questa metrica non può essere calcolata in modo indipendente perché il denominatore di questa funzione è una metrica interna. | Analysis Workspace |
| [!UICONTROL Time Spent/User (State)] | Circa *Totale secondi trascorsi in app mobili/visitatori univoci in app mobili*<br> Rappresenta il tempo medio di interazione dei visitatori di un&#39;app mobile con uno specifico elemento di dimensione nell&#39;arco della vita del visitatore (durata del cookie). **Nota**: questa metrica non può essere calcolata in modo indipendente perché il denominatore di questa funzione è una metrica interna. | Analysis Workspace |
| [[!UICONTROL Average time spent on site] (secondi)](average-time-on-site.md) | Rappresenta il tempo totale in cui i visitatori interagiscono con un elemento dimensione specifico, per sequenza con un elemento dimensione. Non è limitato solo alle medie &quot;del sito&quot;, come suggerisce il nome. Per ulteriori informazioni sulle sequenze, consulta la sezione &quot;Modalità di calcolo del tempo trascorso&quot;.<br>**Nota**: è molto probabile che questa metrica differisca da &quot;Tempo trascorso per visita&quot; a livello di elemento dimensione a causa delle differenze nel denominatore nel calcolo. | Analysis Workspace, Report Builder (in minuti) |
| [[!UICONTROL Average time on site]](average-time-on-site.md) | Questa è la stessa metrica di *Tempo medio trascorso sul sito (secondi)*, ad eccezione del formato Tempo (`hh:mm:ss`) | Analysis Workspace |
| [!UICONTROL Average time spent on page] | Metrica obsoleta.<br> Al contrario, Adobe consiglia di utilizzare [[!UICONTROL Average time spent on site]](average-time-on-site.md) se è necessario il tempo medio per un elemento della dimensione. | Report Builder (quando una dimensione è nella richiesta) |

## Dimensioni &quot;Tempo trascorso&quot;

| Dimensione | Definizione | Disponibile in |
| --- | --- | --- |
| [[!UICONTROL Time spent per visit - granular]](../dimensions/time-spent-per-visit.md) | Il tempo totale trascorso durante la visita viene troncato al secondo più vicino e viene applicato a ogni hit che faceva parte della visita. Si tratta di una dimensione a livello di visita. | Analysis Workspace |
| [[!UICONTROL Time spent per visit - bucketed]](../dimensions/time-spent-per-visit.md) | La dimensione granulare racchiusa in 9 intervalli diversi. Si tratta di una dimensione a livello di visita. Gli intervalli includono:<ul><li>Meno di 1 minuto</li><li>1-5 minuti</li><li>5-10 minuti</li><li>10-30 minuti</li><li>30-60 minuti</li><li>1-2 ore</li><li>2-5 ore</li><li>5-10 ore</li><li>10-15 ore</li></ul>**Nota**: non possono essere presenti contenitori superiori a questo, perché una visita scade dopo 12 ore di attività. | Analysis Workspace, Report Builder |
| [[!UICONTROL Time spent on page - granular]](../dimensions/time-spent-on-page.md) | Il tempo totale trascorso su ogni hit, troncato al secondo più vicino. Si tratta di una dimensione a livello di hit che include sia visualizzazioni di pagina che eventi di collegamento. Nonostante il nome, non è limitato alla dimensione &quot;pagina&quot;. | Analysis Workspace |
| [[!UICONTROL Time spent on page - bucketed]](../dimensions/time-spent-on-page.md) | La dimensione granulare racchiusa in 10 intervalli diversi; tuttavia, la dimensione a blocchi conta solo le visualizzazioni di pagina (ed esclude gli eventi di collegamento). Si tratta di una dimensione a livello di hit. Gli intervalli includono:<ul><li>meno di 15 secondi</li><li>Da 15 a 29 secondi</li><li>Da 30 a 59 secondi</li><li>Da 1 a 3 minuti</li><li>Da 3 a 5 minuti</li><li>Da 5 a 10 minuti</li><li>Da 10 a 15 minuti</li><li>Da 15 a 20 minuti</li><li>Da 20 a 30 minuti</li><li>più di 30 minuti</li></ul> | Analysis Workspace |

## Come viene calcolato il tempo trascorso

Adobe Analytics utilizza valori espliciti (inclusi eventi di collegamento e visualizzazioni video) per calcolare il tempo trascorso.

>[!NOTE]
>
>Senza eventi di collegamento come [!UICONTROL Video Views] o [!UICONTROL Exit Links], non è possibile conoscere il tempo trascorso sull&#39;ultimo hit di una visita. Per motivi simili, anche [!UICONTROL Bounce Visits] (ovvero visite con un singolo hit) non ha un &#39;tempo trascorso&#39; associato.

Il **numeratore** in tutti i calcoli relativi al tempo trascorso è il totale dei secondi trascorsi.

Il **denominatore** non è disponibile come metrica separata in Adobe Analytics. Per le metriche &quot;tempo trascorso&quot; a livello di hit, il denominatore è sequenze. Una sequenza è un set consecutivo di hit in cui una determinata variabile contiene lo stesso valore (sia tramite impostazione, distribuzione in avanti o persistenza). &quot;Diffondi in avanti&quot; si riferisce alla persistenza di proprietà tra le visualizzazioni di pagina (ovvero tra eventi di collegamento successivi), ai fini del calcolo del tempo trascorso.

* Ad esempio, nel caso di [!UICONTROL Page Name] o altre dimensioni a livello di hit, il denominatore è essenzialmente [!UICONTROL 'Instances'] o [!UICONTROL 'Page Views'], ma con ricaricamenti e valori non impostati (ad esempio eventi di collegamento) conteggiati come una singola interazione (una sequenza).

* Anche gli hit di mancato recapito e di uscita vengono rimossi dal denominatore perché non è possibile conoscere il tempo trascorso.

## Domande frequenti

+++Tutte le metriche &quot;tempo trascorso&quot; possono essere applicate a qualsiasi dimensione?

Le metriche &quot;tempo trascorso&quot; che possono essere applicate a qualsiasi dimensione sono:

* [[!UICONTROL Total seconds spent]](total-seconds-spent.md)

* [[!UICONTROL Time spent per visit] (secondi)](time-spent-per-visit.md)

* [[!UICONTROL Time spent per visitor] (secondi)](time-spent-per-visitor.md)

* [[!UICONTROL Average time spent on site] (secondi)](average-time-on-site.md)

+++

+++Quale dimensione Tempo trascorso è più indicata nelle suddivisioni con altre dimensioni?

La dimensione [[!UICONTROL Time Spent on Page – granular]](../dimensions/time-spent-on-page.md) è a livello di hit. Suddividendo questa per un’altra dimensione, potrai sapere in quali secondi è durato un hit in cui era presente anche la dimensione di raggruppamento.
Nell’esempio seguente, il termine di ricerca &quot;classificifieds&quot; è associato a hit time di 54 secondi, 59 secondi, ecc., che indicano probabilmente che i visitatori dedicano tempo alla lettura del contenuto restituito per quel termine.

![Schermata del tempo trascorso sul report della pagina](assets/time-spent1.png)

+++

+++Quale metrica è appropriata rispetto alla dimensione di [!UICONTROL Time Spent on Page – granular]?

Qualsiasi metrica. La dimensione mostra il tempo trascorso sull’hit esatto in cui si è verificato l’evento. Maggiore è il tempo trascorso, più un visitatore è rimasto a lungo su una pagina (hit) in cui si è verificato l’evento.

![Rapporto Workspace che mostra una metrica personalizzata utilizzata con una dimensione tempo trascorso](assets/time-spent2.png)

+++

+++Differenze tra [!UICONTROL Average Time Spent on Site] e [!UICONTROL Time Spent per Visit]

La differenza è il denominatore nella metrica:

* [[!UICONTROL Average time spent on site]](average-time-on-site.md) utilizza le sequenze che includono un elemento dimensione.

* [[!UICONTROL Time spent per visit]](time-spent-per-visit.md) utilizza il conteggio delle visite

Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma sono diverse a livello di hit.

+++

+++Perché i totali delle suddivisioni con [!UICONTROL Average Time Spent on Site] non corrispondono all&#39;elemento riga padre?

Poiché [!UICONTROL Average Time Spent on Site] dipende da sequenze non interrotte di una dimensione e il report interno non dipende dal report esterno durante il calcolo di queste esecuzioni.

Ad esempio, considera la visita seguente.

| Hit # | 1 | 2 | 3 |
|---|---|---|---|
| **Secondi trascorsi** | 30 | 100 | 10 |
| **Nome pagina** | Pagina Home | Prodotto | Pagina Home |
| **Data** | Gen 1 | Gen 1 | Gen 1 |

Quando si calcola il tempo trascorso per la homepage, questo sarebbe (30+10)/2=20, ma suddividendo tale dato per giorno si otterrebbe (30+10)/1=40 in quanto il giorno presenta un’unica esecuzione ininterrotta il 1° gennaio.

Di conseguenza, queste metriche possono produrre risultati simili a livello di visita, ma sono diverse a livello di hit.

+++

## Esempi di [!UICONTROL Time Spent] calcoli

Supponiamo che il seguente set di chiamate al server sia per un singolo visitatore all’interno di una singola visita:

| N. hit visita | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|
| **Tempo trascorso per la visita (in sec)** | 0 | 30 | 80 | 180 | 190 | 230 | 290 |
| **Secondi trascorsi** | 30 | 50 | 100 | 10 | 40 | 60 | - |
| **Tipo di hit** | Pagina | Collegamento | Pagina | Pagina | Pagina | Pagina | Pagina |
| **Nome pagina** | Pagina Home | - | Prodotto | Pagina Home | Home (ricarica) | Carrello | Conferma dell’ordine |
|  |  |  |  |  |  |  |  |
| **prop1** | A (impostato) | A (diffusione in avanti) | non impostato | B (impostato) | B (impostato) | A(set) | C (set) |
| **prop1 secondi trascorsi** | 30 | 50 | - | 10 | 40 | 60 | - |
|  |  |  |  |  |  |  |  |
| **eVar 1** | Rosso (impostato) | Rosso (persistente) | (scaduto) | Blu (impostato) | Blu (impostato) | Blu (persistente) | Rosso (impostato) |
| **eVar 1 secondi trascorsi** | 30 | 50 | - | 10 | 40 | 60 | - |

In base alla tabella precedente, le metriche tempo trascorso vengono calcolate come segue:

| prop1 | Totale secondi trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Numero di sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| A | 30+50+60=140 | 140/1=140 | 140/1=140 | 2 | 140/2=70 |
| B | 10+40=50 | 50/1=50 | 50/1=50 | 1 | 50/1=50 |
| C | 0 | 0 | 0 | 0 | 0 |
| Ora non attribuita | 100 | - | - | - | - |

| eVar1 | Totale secondi trascorsi | Tempo trascorso per visita | Tempo trascorso per visitatore | Numero di sequenze | Tempo medio trascorso sul sito |
|---|---|---|---|---|---|
| Rosso | 30+50=80 | 80/1=80 | 80/1=80 | 1 | 80/1=80 |
| Blu | 10+40+60=110 | 110/1=110 | 110/1=110 | 1 | 110/1=110 |
| Ora non attribuita | 100 | - | - | - | - |

Tempo trascorso per visita (granulare): 290
Tempo trascorso sulla pagina (granulare): 10, 30, 40, 50, 60, 100

Alcune note aggiuntive a sostegno dell’esempio:

* Tutti i calcoli del tempo trascorso si basano sul tempo trascorso della visita che inizia da zero al primo hit della visita.

* &quot;Secondi trascorsi&quot; è la differenza tra la marca temporale dell’hit corrente e la marca temporale dell’hit successivo. Di conseguenza, l’ultimo hit della visita (e i mancati recapiti) non hanno tempo trascorso.

* Una &quot;sequenza&quot; è un insieme consecutivo di hit in cui una data variabile contiene lo stesso valore (sia esso impostato, diffuso in avanti o persistente). Ad esempio, prop1 &quot;A&quot; ha due sequenze: hit 1 e 2 e hit 6. I valori dell’ultimo hit della visita non iniziano una nuova sequenza perché l’ultimo hit non ha tempo trascorso. Il tempo medio trascorso sul sito utilizza le sequenze nel denominatore.

   * Solo ai fini del tempo trascorso, le proprietà vengono &quot;distribuite in avanti&quot; dagli hit di pagina agli hit di collegamento successivi, come mostrato in precedenza per prop1 sull’hit 2. Questo consente al valore impostato per prop1 sull’hit 1 (&quot;A&quot;) di accumulare il tempo trascorso sull’hit 2.

   * Le eVar accumulano il tempo trascorso su qualsiasi hit in cui l’eVar viene impostato o mantenuto. La persistenza in eVar è definita dalle impostazioni in eVar in Analytics > Amministratore.
