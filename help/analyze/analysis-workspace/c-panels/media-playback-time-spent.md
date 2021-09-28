---
title: Pannello Tempo di riproduzione dei contenuti multimediali
description: Come utilizzare e interpretare il pannello Tempo di riproduzione multimediale trascorso in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: 74ef44c4afba6d2dffb2b10fa473baee3be16a23
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 49%

---

# Pannello Tempo di riproduzione dei contenuti multimediali

I clienti di Media Analytics possono analizzare il tempo di riproduzione impiegato per comprendere dove si è verificato il picco di concorrenza o dove si è verificato un calo dei contenuti, per fornire informazioni utili sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori e per risolvere eventuali problemi o pianificare il volume o la scala.

In Analysis Workspace, Tempo di riproduzione trascorso è la quantità di tempo impiegato per visualizzare i flussi multimediali in un momento specifico e include pausa, buffer e tempo da avviare.

Il pannello Tempo trascorso di riproduzione multimediale consente l&#39;analisi della riproduzione nel tempo, con dettagli sul picco di concorrenza e la possibilità di suddividere e confrontare. Per accedere al pannello Tempo di riproduzione multimediale trascorso , passa a una suite di rapporti con i componenti Media Analytics abilitati. Fai clic sull’icona del pannello all’estrema sinistra, quindi trascina il pannello nel progetto Analysis Workspace.

Questo pannello include anche una nuova funzionalità nel calendario che consente di selezionare e visualizzare meno di 24 ore. Puoi farlo per l’intero pannello, oppure puoi creare segmenti utilizzando periodi di tempo consecutivi in modo da poter tenere traccia del lead-in/lead-out del pubblico tra programmi o sezioni di programmi. Una volta inseriti almeno due di questi segmenti di data, visualizzerai un&#39;opzione del pulsante di scelta per Visualizzazione sequenza di date che sovrapporrà le linee con un inizio comune dell&#39;asse x o le mostrerà in sequenza con il loro inizio specifico dell&#39;asse x.

## Input del pannello {#Input}

Puoi configurare il pannello Tempo di riproduzione multimediale trascorso utilizzando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi).  È possibile modificarlo per visualizzare uno o più mesi alla volta.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Granularity (Granularità) | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli relativi alla data o all’ora di riproduzione, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso. Somma somma il tempo totale di riproduzione trascorso per la selezione. L’impostazione predefinita del pannello mostra solo Massimo, ma puoi modificarla in Minimo, Somma o qualsiasi combinazione dei tre.<br>Se utilizzi le suddivisioni, per ciascuna viene visualizzato un numero di riepilogo. |
| Suddivisione per serie di dati | Facoltativamente, puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date.<p>- È possibile visualizzare fino a 10 righe alla volta. Le suddivisioni sono limitate a un singolo livello.</p><p>- Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.</p>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di suddivisione per serie. |
| Formato ora | È possibile visualizzare il tempo di riproduzione in ore:Minutes:Secondi (impostazione predefinita) o in minuti (visualizzati in numeri interi, arrotondati a 0,5). |
| Visualizzazione della sequenza di date | Se hai inserito almeno due segmenti di intervallo di date come raggruppamenti di serie, vedrai l’opzione per selezionare sovrapposizione (impostazione predefinita) o sequenziale. La sovrapposizione consente di visualizzare le linee con un inizio comune dell&#39;asse x in modo che vengano eseguite in parallelo, mentre le linee con il loro inizio specifico dell&#39;asse x verranno visualizzate in sequenza. Se i dati si allineano (ad esempio, il segmento 1 termina alle 20:44 e il segmento 2 inizia alle 20:45), le righe vengono visualizzate in sequenza. |

### Vista predefinita

![Vista predefinita](assets/mpts_default_view.png)

## Output del pannello {#Output}

Il pannello Tempo di riproduzione multimediale trascorso restituisce un grafico a linee e numeri di riepilogo per includere dettagli relativi al tempo di riproduzione massimo, minimo e/o totale trascorso. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, puoi modificare il pannello facendo clic sull’icona della matita (Modifica) in alto a destra.

Se hai selezionato la suddivisione per serie, per ciascuna suddivisione viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![tempo di riproduzione dei contenuti](assets/mpts_outputs1.png)

### Origine dati

L&#39;unica metrica che può essere utilizzata in questo pannello è Tempo di riproduzione trascorso.

| Metrica | Descrizione |
|---|---|
| Tempo di riproduzione trascorso | Ore totali:minutes:secondi (o minuti) del contenuto visualizzato durante la granularità selezionata, inclusi pausa, buffer e tempo di avvio. |

## Domande frequenti {#FAQ}

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | <p></p><p>La tabella a forma libera non è disponibile in questa vista. Puoi scaricare l’origine dati facendo clic con il pulsante destro del mouse sul grafico a linee e scaricando il file CSV.</p> |
| <p>Perché la granularità è cambiata?</p> | <p>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe.</p><p></p><p>Quando passi da un intervallo di date più ampio a uno più ridotto, la granularità viene aggiornata al dettaglio più basso consentito dopo la modifica dell’intervallo di date. Per visualizzare una granularità maggiore, modifica il pannello e ricompila.</p> |
| <p></p><p>Come si confrontano nomi video, segmenti, tipi di contenuto, ecc.?</p> | <p>Per confrontare questi elementi in una singola visualizzazione, trascina segmenti, dimensioni o elementi dimensionali specifici nel filtro di suddivisione della serie.</p><p></p><p>La visualizzazione è limitata a 10 suddivisioni. Per visualizzarne più di 10, è necessario utilizzare più pannelli.</p> |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza le suddivisioni per serie trascinando 2 o più intervalli di date. Questi intervalli di date sovrascriveranno l’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | <p></p><p>Questo pannello consente solo la visualizzazione a linee per le serie temporali.</p> |
| Posso eseguire il rilevamento delle anomalie? | <p></p><p>No. Il rilevamento delle anomalie non è disponibile per questo pannello.</p> |
