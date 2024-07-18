---
description: Le sessioni in base al contesto nelle suite di rapporti virtuali cambiano il modo in cui Adobe Analytics calcola le visite mobili. Questo articolo descrive le implicazioni di elaborazione degli hit in background e degli eventi di avvio dell’app (entrambi impostati dall’SDK per dispositivi mobili) per la definizione delle visite al cellulare.
title: Adobe Context-Aware Sessions
feature: VRS
exl-id: 5e969256-3389-434e-a989-ebfb126858ef
source-git-commit: beef45403f3c3eb7ac423ca8e0b6db0143ff1b9b
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 0%

---

# Adobe Context-Aware Sessions

Le sessioni in base al contesto nelle suite di rapporti virtuali modificano il modo in cui Adobe Analytics calcola le visite da qualsiasi dispositivo. Questo articolo descrive anche le implicazioni di elaborazione degli hit in background e degli eventi di avvio dell’app (entrambi impostati dall’SDK mobile) per la definizione delle visite al cellulare.

Puoi definire una visita in qualsiasi modo senza alterare i dati sottostanti, in modo che corrisponda al modo in cui i visitatori interagiscono con le esperienze digitali.

Ecco un video sulle sessioni in base al contesto:

>[!VIDEO](https://video.tv.adobe.com/v/23545/?quality=12)

## Parametro URL prospettiva cliente

Il processo di raccolta dati di Adobe Analytics ti consente di impostare un parametro della stringa di query che specifica la prospettiva del cliente (denotato come parametro della stringa di query &quot;cp&quot;). Questo campo specifica lo stato dell&#39;applicazione digitale dell&#39;utente finale. Questo consente di sapere se un hit è stato generato mentre un’app mobile era in background.

## Elaborazione hit in background

Un hit in background è un tipo di hit inviato ad Analytics dalla versione 4.13.6 e successive dell’SDK di Adobe Mobile quando l’app effettua una richiesta di tracciamento mentre è in background. Di seguito sono riportati alcuni esempi tipici:

* Dati inviati durante un attraversamento di recinzione geografica
* Un’interazione di notifica push

Gli esempi seguenti descrivono la logica utilizzata per determinare quando una visita inizia e termina per un visitatore quando l’impostazione &quot;Impedisci agli hit in background di avviare una nuova visita&quot; è abilitata o non è abilitata per una suite di rapporti virtuale.

**Se &quot;Impedisci agli hit in background di avviare una nuova visita&quot; non è abilitato:**

Se questa funzione non è abilitata per una suite di rapporti virtuale, gli hit in background vengono trattati come qualsiasi altro hit, il che significa che iniziano nuove visite e agiscono esattamente come gli hit in primo piano. Ad esempio, se un hit in background si verifica meno di 30 minuti (il timeout di sessione standard per una suite di rapporti) prima di un set di hit in primo piano, l’hit in background fa parte della sessione.

![](assets/nogood1.jpg)

Se l’hit di background si verifica più di 30 minuti prima di qualsiasi hit di primo piano, l’hit di background crea la propria visita, per un numero totale di visite pari a 2.

![](assets/nogood2.jpg)

**Se &quot;Impedisci agli hit in background di avviare una nuova visita&quot; è abilitato:**

Gli esempi seguenti illustrano il comportamento degli hit di sfondo quando questa funzione è abilitata.

Esempio 1: un hit di background si verifica in un periodo di tempo (t) precedente a una serie di hit in primo piano.

![](assets/nogoodexample1.jpg)

In questo esempio, se *t* è maggiore del timeout della visita configurato della suite di rapporti virtuali, l&#39;hit in background viene escluso dalla visita formata dagli hit in primo piano. Ad esempio, se il timeout per la visita della suite di rapporti virtuali era impostato su 15 minuti e *t* era di 20 minuti, la visita formata da questa serie di hit (mostrati dal profilo verde) escluderebbe l&#39;hit in background. Ciò significa che eventuali eVar impostate con una scadenza &quot;visita&quot; sull&#39;hit di background persisterebbero **not** nella visita successiva e un contenitore di segmenti di visita includerebbe solo gli hit di primo piano all&#39;interno del profilo verde.

![](assets/nogoodexample1-2.jpg)

Al contrario, se *t* è inferiore al timeout della visita configurato della suite di rapporti virtuali, l&#39;hit in background viene incluso nella visita come se fosse un hit in primo piano (mostrato dal contorno verde):

![](assets/nogoodexample1-3.jpg)

Ciò significa che:

* Eventuali eVar impostate con scadenza &quot;visita&quot; nell’hit di background persistono i loro valori sugli altri hit di questa visita.
* Tutti i valori impostati nell’hit in background sono inclusi nella valutazione logica del contenitore di segmenti a livello di visita.

In entrambi i casi, il conteggio totale delle visite sarebbe 1.

Esempio 2: se un hit di sfondo si verifica dopo una serie di hit di primo piano, il comportamento è simile:

![](assets/nogoodexample2.jpg)

Se l&#39;hit in background si verifica dopo il timeout configurato della suite di rapporti virtuali, l&#39;hit in background non fa parte di una sessione (evidenziato in verde):

![](assets/nogoodexample2-1.jpg)

Allo stesso modo, se il periodo di tempo *t* è stato inferiore al timeout configurato della suite di rapporti virtuali, l&#39;hit in background viene incluso nella visita formata dagli hit in primo piano precedenti:

![](assets/nogoodexample2-2.jpg)

Ciò significa che:

* Eventuali eVar impostate con scadenza &quot;visita&quot; sugli hit in primo piano precedenti mantengono i loro valori sull’hit di background in questa visita.
* Tutti i valori impostati nell’hit in background sono inclusi nella valutazione logica del contenitore di segmenti a livello di visita.

Come in precedenza, il numero totale di visite in entrambi i casi sarebbe 1.

Esempio 3: in alcune circostanze, un hit di background può causare la combinazione di due visite separate in una singola visita. Nello scenario seguente, un hit in background è preceduto e seguito da una serie di hit in primo piano:

![](assets/nogoodexample3.jpg)

Se, in questo esempio, *t1* e *t2* sono entrambi inferiori al timeout di visita configurato dalla suite di rapporti virtuali, tutti questi hit verranno combinati in una singola visita, anche se *t1* e *t2* insieme sono superiori al timeout della visita:

![](assets/nogoodexample3-1.jpg)

Tuttavia, se *t1* e *t2* sono maggiori del timeout configurato per la suite di rapporti virtuali, questi hit verranno separati in due visite distinte:

![](assets/nogoodexample3-2.jpg)

Analogamente (come negli esempi precedenti), se *t1* è minore del timeout e *t2* è minore del timeout, l&#39;hit di background verrà incluso nella prima visita:

![](assets/nogoodexample3-3.jpg)

Se *t1* è maggiore del timeout e *t2* è minore del timeout, l&#39;hit di background verrà incluso nella seconda visita:

![](assets/nogoodexample3-4.jpg)

Esempio 4: negli scenari in cui si verifica una serie di hit di background entro il periodo di timeout della visita della suite di rapporti virtuali, gli hit formano una &quot;visita di background&quot; invisibile che non viene conteggiata nel conteggio delle visite e non è accessibile utilizzando un contenitore di segmentazione delle visite.

![](assets/nogoodexample4.jpg)

Anche se questa non è considerata una visita, qualsiasi eVar impostata con scadenza visita persiste i suoi valori rispetto agli altri hit di background in questa &quot;visita di background&quot;.

Esempio 5: per gli scenari in cui si verificano più hit di background in successione dopo una serie di hit in primo piano, è possibile (a seconda dell’impostazione di timeout) che gli hit di background mantengano in vita una visita più a lungo del periodo di timeout della visita. Ad esempio, se *t1* e *t2* insieme fossero maggiori del timeout di visita della suite di rapporti virtuale ma singolarmente inferiori al timeout, la visita si estenderebbe comunque per includere entrambi gli hit in background:

![](assets/nogoodexample5.jpg)

Analogamente, se una serie di hit in background si verifica prima di una serie di eventi in primo piano, si verifica un comportamento simile:

![](assets/nogoodexample5-1.jpg)

Gli hit di background si comportano in questo modo per preservare eventuali effetti di attribuzione da eVar o altre variabili impostate durante gli hit di background. Questo consente di attribuire gli eventi di conversione in primo piano a azioni eseguite mentre un’app era in background. Consente inoltre a un contenitore per segmenti di visita di includere hit in background che hanno generato una sessione in primo piano a valle, utile per misurare l’efficacia dei messaggi push.

## Comportamento delle metriche di visita

Il conteggio delle visite si basa esclusivamente sul conteggio delle visite che includono almeno un hit in primo piano. Ciò significa che eventuali hit di background orfani o &quot;visite in background&quot; non vengono conteggiati ai fini della metrica Visita.

## Comportamento della metrica Tempo trascorso per visita

Il tempo trascorso viene ancora calcolato in modo analogo al tempo trascorso tra un hit e l’altro senza hit in background. Anche se, se una visita include hit di background (perché si sono verificati abbastanza vicini agli hit di primo piano), tali hit vengono inclusi nel calcolo del tempo trascorso per visita come se fossero un hit di primo piano.

## Impostazioni elaborazione hit in background

Poiché l’elaborazione degli hit in background è disponibile solo per le suite di rapporti virtuali che utilizzano l’elaborazione dei tempi di report, Adobe Analytics supporta due modi di elaborazione degli hit in background per mantenere il conteggio delle visite nella suite di rapporti di base che non utilizza l’elaborazione dei tempi di report. Per accedere a questa impostazione, vai a Strumenti di amministrazione di Adobe Analytics, vai alle impostazioni della suite di rapporti di base applicabile, quindi vai al menu &quot;Mobile Management&quot;, quindi al sottomenu &quot;Mobile Application Reporting&quot;.

1. &quot;Elaborazione legacy attivata&quot;: questa è l’impostazione predefinita per tutte le suite di rapporti. Lasciare l’elaborazione legacy sugli hit in background dei processi come hit normali nella pipeline di elaborazione per quanto riguarda la suite di rapporti non di base per l’attribuzione del tempo di rapporto. Ciò significa che qualsiasi hit in background visualizzato nella suite di rapporti di base incrementa le visite come un hit normale. Se non desideri che gli hit in background vengano visualizzati nella suite di rapporti di base, modifica questa impostazione su &quot;Off&quot;.
1. &quot;Elaborazione legacy disattivata&quot;: con l’elaborazione legacy per gli hit in background disattivata, tutti gli hit in background inviati alla suite di rapporti di base vengono ignorati dalla suite di rapporti di base e sono accessibili solo quando una suite di rapporti virtuale creata in questa suite di rapporti di base è configurata per l’utilizzo dell’elaborazione dei tempi di report. Ciò significa che tutti i dati acquisiti dagli hit in background inviati a questa suite di rapporti di base vengono visualizzati solo in una suite di rapporti virtuali abilitata per l’elaborazione dei tempi di report.

   Questa impostazione è destinata ai clienti che desiderano sfruttare la nuova elaborazione degli hit in background senza modificare il numero di visite della suite di rapporti di base.

In entrambi i casi, gli hit in background vengono fatturati allo stesso costo di qualsiasi altro hit inviato ad Analytics.

## Avvio Di Nuove Visite A Ogni Avvio Dell’App

Oltre all’elaborazione degli hit in background, le suite di rapporti virtuali possono forzare l’avvio di una nuova visita ogni volta che l’SDK mobile invia un evento di avvio dell’app. Con questa impostazione abilitata, ogni volta che un evento di avvio app viene inviato dall’SDK, viene forzato l’avvio di una nuova visita indipendentemente dal raggiungimento del timeout di una visita aperta. L’hit contenente l’evento di avvio dell’app viene incluso come primo hit nella visita successiva, incrementa il conteggio delle visite e crea un contenitore di visite distinto per la segmentazione.
