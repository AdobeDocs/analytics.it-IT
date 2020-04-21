---
description: Le sessioni in base al contesto nelle suite di rapporti virtuali cambiano il modo in cui Adobe Analytics calcola le visite per dispositivi mobili. Questo articolo descrive le implicazioni di elaborazione degli hit in background e degli eventi di avvio dell’app (entrambi impostati dall’SDK per dispositivi mobili) per la definizione delle visite per dispositivi mobili.
title: Adobe Context-Aware Sessions
uuid: d354864a-9163-4970-a3a0-f2e9729bdbe3
translation-type: tm+mt
source-git-commit: 3997889ae72920d719203edbb159b55b983158e7

---


# Adobe Context-Aware Sessions

Le sessioni in base al contesto nelle suite di rapporti virtuali cambiano il modo in cui Adobe Analytics calcola le visite da qualsiasi dispositivo. Questo articolo descrive anche le implicazioni di elaborazione degli hit in background e degli eventi di avvio dell’app (entrambi impostati dall’SDK per dispositivi mobili) per definire le modalità di definizione delle visite per dispositivi mobili.

Puoi definire una visita nel modo desiderato, senza alterare i dati sottostanti, in modo che i visitatori possano interagire con le tue esperienze digitali.

## Parametro URL prospettiva cliente

Il processo di raccolta dei dati di Adobe Analytics consente di impostare un parametro della stringa di query che specifica la prospettiva del cliente (indicata come parametro della stringa di query &quot;cp&quot;). Questo campo specifica lo stato dell&#39;applicazione digitale dell&#39;utente finale. Questo consente di sapere se un hit è stato generato mentre un’app mobile era in stato di background.

## Elaborazione hit in background

Un hit in background è un tipo di hit inviato ad Analytics dalla versione SDK di Adobe Mobile 4.13.6 e successiva quando l&#39;app effettua una richiesta di tracciamento mentre è in stato di background. Esempi tipici di questo tipo:

* Dati inviati durante l&#39;attraversamento di una recinzione geografica
* Un&#39;interazione di notifica push

Gli esempi seguenti delineano la logica utilizzata per determinare quando una visita inizia e termina per qualsiasi visitatore quando l&#39;impostazione &quot;Impedisci agli hit in background di avviare una nuova visita&quot; è abilitata o non è abilitata per una suite di rapporti virtuale.

**Se l&#39;opzione &quot;Impedisci agli hit in background di avviare una nuova visita&quot; non è abilitata:**

Se questa funzione non è abilitata per una suite di rapporti virtuale, gli hit in background vengono trattati come qualsiasi altro hit, il che significa che iniziano nuove visite e agiscono esattamente come gli hit in primo piano. Ad esempio, se un hit in background si verifica meno di 30 minuti (il timeout sessione standard per una suite di rapporti) prima di un set di hit in primo piano, l’hit in background fa parte della sessione.

![](assets/nogood1.jpg)

Se l’hit in background si verifica più di 30 minuti prima di qualsiasi hit in primo piano, l’hit in background crea una propria visita, per un conteggio totale di visite pari a 2.

![](assets/nogood2.jpg)

**Se è abilitata l&#39;opzione &quot;Impedisci agli hit in background di avviare una nuova visita&quot;:**

Gli esempi seguenti illustrano il comportamento degli hit di sfondo quando questa funzione è attivata.

Esempio 1: Un hit in background si verifica in un periodo di tempo (t) prima di una serie di hit in primo piano.

![](assets/nogoodexample1.jpg)

In questo esempio, se *è superiore* al timeout di visita configurato dalla suite di rapporti virtuale, l&#39;hit in background viene escluso dalla visita formata dagli hit in primo piano. Ad esempio, se il timeout della visita della suite di rapporti virtuale era impostato su 15 minuti e *fosse* di 20 minuti, la visita formata da questa serie di hit (mostrata dal contorno verde) escluderebbe l’hit in background. Ciò significa che qualsiasi eVar impostato con una scadenza &quot;visita&quot; sull&#39;hit in background **non** persiste nella visita successiva e un contenitore di segmenti di visita includerebbe solo gli hit in primo piano all&#39;interno del contorno verde.

![](assets/nogoodexample1-2.jpg)

Al contrario, se *è inferiore* al timeout della visita configurato dalla suite di rapporti virtuale, l&#39;hit in background viene incluso come parte della visita come se fosse un hit in primo piano (mostrato dal contorno verde):

![](assets/nogoodexample1-3.jpg)

Ciò significa che:

* Tutte le eVar impostate con scadenza &quot;visita&quot; sull’hit in background persistono i loro valori sugli altri hit di questa visita.
* Tutti i valori impostati nell’hit di sfondo vengono inclusi nella valutazione logica del contenitore del segmento a livello di visita.

In entrambi i casi, il numero totale di visite sarebbe 1.

Esempio 2: Se si verifica un hit di sfondo dopo una serie di hit in primo piano, il comportamento è simile:

![](assets/nogoodexample2.jpg)

Se l&#39;hit in background si verifica dopo il timeout configurato della suite di rapporti virtuali, l&#39;hit in background non fa parte di una sessione (evidenziato in verde):

![](assets/nogoodexample2-1.jpg)

Analogamente, se il periodo di tempo *è inferiore* al timeout configurato della suite di rapporti virtuali, l&#39;hit in background viene incluso nella visita formata dagli hit in primo piano precedenti:

![](assets/nogoodexample2-2.jpg)

Ciò significa che:

* Tutte le eVar impostate con scadenza &quot;visita&quot; sugli hit in primo piano precedenti persistono i loro valori sull’hit in background in questa visita.
* Tutti i valori impostati nell’hit di sfondo vengono inclusi nella valutazione logica del contenitore del segmento a livello di visita.

Come prima, il numero totale di visite in entrambi i casi sarebbe 1.

Esempio 3: In alcune circostanze, un hit in background può causare la combinazione di due visite separate in una singola visita. Nel seguente scenario, un hit in background viene preceduto e seguito da una serie di hit in primo piano:

![](assets/nogoodexample3.jpg)

Se, in questo esempio, *t1* e *t2* sono entrambi inferiori al timeout della visita configurato nella suite di rapporti virtuale, tutti questi hit vengono combinati in una singola visita, anche se *t1* e *t2* insieme sono maggiori del timeout della visita:

![](assets/nogoodexample3-1.jpg)

Tuttavia, se *t1* e *t2* sono maggiori del timeout configurato per la suite di rapporti virtuali, questi hit saranno separati in due visite distinte:

![](assets/nogoodexample3-2.jpg)

Analogamente (come negli esempi precedenti), se *t1* è minore del timeout e *t2* è minore del timeout, l’hit in background viene incluso nella prima visita:

![](assets/nogoodexample3-3.jpg)

Se *t1* è maggiore del timeout e *t2* è minore del timeout, l&#39;hit in background verrà incluso nella seconda visita:

![](assets/nogoodexample3-4.jpg)

Esempio 4: Negli scenari in cui si verifica una serie di hit in background nel periodo di timeout della visita della suite di rapporti virtuali, gli hit formano una &quot;visita in background&quot; invisibile che non viene conteggiata nel conteggio delle visite e non è accessibile tramite un contenitore di segmentazione delle visite.

![](assets/nogoodexample4.jpg)

Anche se questa non è considerata una visita, qualsiasi eVar impostato con scadenza visita persiste nei valori corrispondenti agli altri hit di sfondo presenti in questa &quot;visita in background&quot;.

Esempio 5: Per gli scenari in cui si verificano più hit in background in successione dopo una serie di hit in primo piano, è possibile (a seconda dell’impostazione di timeout) che gli hit in background mantengano una visita in vita più lunga del periodo di timeout della visita. Ad esempio, se *t1* e *t2* insieme fossero maggiori del timeout della visita della suite di rapporti virtuale ma singolarmente inferiori al timeout, la visita continuerebbe ad estendersi per includere entrambi gli hit in background:

![](assets/nogoodexample5.jpg)

Analogamente, se una serie di hit di sfondo si verifica prima di una serie di eventi in primo piano, si verifica un comportamento simile:

![](assets/nogoodexample5-1.jpg)

Gli hit di sfondo si comportano in questo modo per mantenere eventuali effetti di attribuzione delle eVar o di altre variabili impostate durante gli hit di sfondo. Questo consente di attribuire gli eventi di conversione in primo piano a valle alle azioni eseguite mentre un&#39;app era nello stato di background. Consente inoltre al contenitore del segmento della visita di includere hit in background che hanno determinato una sessione in primo piano a valle, utile per misurare l’efficacia dei messaggi push.

## Comportamento delle metriche delle visite

Il conteggio delle visite si basa esclusivamente sul conteggio delle visite che includono almeno un hit in primo piano. Ciò significa che eventuali hit in background orfani o &quot;visite in background&quot; non vengono conteggiati per la metrica Visita.

## Comportamento della metrica Tempo trascorso per visita

Il tempo trascorso è ancora calcolato in modo analogo per quanto riguarda il modo in cui è senza hit di sfondo, utilizzando il tempo tra gli hit. Anche se, se una visita include hit di sfondo (perché si sono verificati abbastanza vicino agli hit in primo piano), tali hit vengono inclusi nel tempo trascorso per il calcolo della visita come se fossero un hit in primo piano.

## Impostazioni di elaborazione degli hit in background

Poiché l&#39;elaborazione degli hit in background è disponibile solo per le suite di rapporti virtuali che utilizzano l&#39;elaborazione del tempo di rapporto, Adobe Analytics supporta due modi di elaborare gli hit in background, al fine di mantenere i conteggi delle visite nella suite di rapporti di base che non utilizza l&#39;elaborazione del tempo di rapporto. Per accedere a questa impostazione, passa ad Adobe Analytics Admin Console, passa alle impostazioni della suite di rapporti di base applicabile, quindi al menu &quot;Mobile Management&quot;, quindi al sottomenu &quot;Mobile Application Reporting&quot;.

1. &quot;Elaborazione legacy su&quot;: Questa è l&#39;impostazione predefinita per tutte le suite di rapporti. Lasciare l&#39;elaborazione legacy sui processi gli hit di background come hit normali nella nostra pipeline di elaborazione per quanto riguarda la suite di rapporti di base per l&#39;attribuzione dei tempi non-report. Ciò significa che qualsiasi hit in background visualizzato nella suite di rapporti di base incrementa le visite come un hit normale. Se non desiderate che gli hit di sfondo vengano visualizzati nella suite di rapporti di base, modificate questa impostazione su &quot;Off&quot;.
1. &quot;Elaborazione legacy disattivata&quot;: Con l&#39;elaborazione legacy per gli hit in background disattivata, tutti gli hit in background inviati alla suite di rapporti di base vengono ignorati dalla suite di rapporti di base e sono accessibili solo quando una suite di rapporti virtuale creata in questa suite di rapporti di base è configurata per l&#39;utilizzo dell&#39;elaborazione dei tempi di rapporto. Ciò significa che tutti i dati acquisiti dagli hit in background inviati a questa suite di rapporti di base vengono visualizzati solo in una suite di rapporti virtuali abilitata per l&#39;elaborazione del tempo di rapporto.

   Questa impostazione è destinata ai clienti che desiderano sfruttare la nuova elaborazione degli hit in background senza modificare il conteggio delle visite della suite di rapporti di base.

In entrambi i casi, gli hit in background vengono fatturati allo stesso costo di qualsiasi altro hit inviato ad Analytics.

## Avvio di nuove visite all&#39;avvio di ogni app

Oltre all’elaborazione degli hit in background, le suite di rapporti virtuali possono forzare l’avvio di una nuova visita ogni volta che l’SDK di Mobile invia un evento di avvio dell’app. Con questa impostazione abilitata, ogni volta che un evento App Launch viene inviato dall’SDK, viene forzata l’avvio di una nuova visita, a prescindere dal fatto che sia stato raggiunto il timeout di una visita aperta. L’hit contenente l’evento di avvio dell’app viene incluso come primo hit nella visita successiva, incrementa il conteggio delle visite e crea un contenitore di visite distinto per la segmentazione.
