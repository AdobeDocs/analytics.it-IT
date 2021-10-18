---
title: Pannello Tempo di riproduzione dei contenuti multimediali
description: Come utilizzare e interpretare il pannello Media Playback Time Spent in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: null
source-git-commit: 74ef44c4afba6d2dffb2b10fa473baee3be16a23
workflow-type: ht
source-wordcount: '981'
ht-degree: 100%

---

# Pannello Tempo di riproduzione dei contenuti multimediali

I clienti di Media Analytics possono analizzare il tempo di riproduzione per capire dove si è verificato un picco di concorrenza o un calo, per fornire informazioni approfondite sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori, utili per risolvere eventuali problemi o pianificare un adeguamento per volume o scala.

In Analysis Workspace, Playback Time Spent (Tempo di riproduzione trascorso) corrisponde alla quantità di tempo impiegato per visualizzare i flussi multimediali in un momento specifico e include pausa, buffer e tempo di avvio.

Il pannello Playback Time Spent (Tempo di riproduzione trascorso) consente di analizzare le riproduzioni nel tempo, con dettagli sul picco di concorrenza e con la possibilità di suddividerli e confrontarli. Per accedere al pannello Playback Time Spent (Tempo di riproduzione trascorso), passa a una suite di rapporti i cui sono abilitati i componenti Media Analytics. Fai clic sull’icona del pannello all’estrema sinistra, quindi trascina il pannello nel progetto Analysis Workspace.

Questo pannello include anche una nuova funzionalità calendario che consente di selezionare e visualizzare meno di 24 ore. Questo può essere applicato all’intero pannello, oppure puoi creare dei segmenti con periodi di tempo consecutivi in modo da poter tenere traccia del lead-in/lead-out del pubblico tra diversi programmi o sezioni di programmi. Una volta inseriti almeno due di questi segmenti di date, un’opzione con pulsanti di scelta per Date Sequence Display (Visualizzazione sequenza di date) consente di scegliere se sovrapporre le linee con un inizio comune dell’asse X oppure se mostrarle in sequenza ciascuna con un proprio inizio dell’asse X.

## Input del pannello {#Input}

Puoi configurare il pannello Media Playback Time Spent (Tempo di riproduzione trascorso) usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Granularity (Granularità) | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli di data o ora per il tempo di riproduzione trascorso, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso. Somma effettua la somma del tempo totale di riproduzione trascorso per la selezione. Per impostazione predefinita, il pannello mostra solo il valore Maximum (Massimo), ma puoi impostarlo su Minimum (Minimo), Sum (Somma) o qualsiasi combinazione dei tre.<br>Se utilizzi le suddivisioni, per ciascuna viene visualizzato un numero di riepilogo. |
| Suddivisione per serie di dati | Facoltativamente, puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date.<p>- È possibile visualizzare fino a 10 righe alla volta. Le suddivisioni sono limitate a un singolo livello.</p><p>- Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.</p>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di suddivisione per serie. |
| Formato ora | È possibile visualizzare il tempo di riproduzione in Ore:Minutes:Secondi (impostazione predefinita) oppure in Minuti (visualizzati in numeri interi, arrotondati a 0,5). |
| Visualizzazione della sequenza di date | Se hai inserito almeno due segmenti di intervallo di date come raggruppamenti di serie, vedrai l’opzione per scegliere tra Overlay (Sovrapposizione, impostazione predefinita) o Sequential (Sequenziale). La visualizzazione in sovrapposizione presenta le linee con un inizio comune dell’asse X, in parallelo; quella sequenziale presenta le linee in sequenza, ciascuna con il proprio inizio dell’asse X. Se i dati sono allineati (ad esempio, il segmento 1 termina alle 20:44 e il segmento 2 inizia alle 20:45), le linee vengono visualizzate in sequenza. |

### Vista predefinita

![Vista predefinita](assets/mpts_default_view.png)

## Output del pannello {#Output}

Il pannello Tempo di riproduzione multimediale trascorso restituisce un grafico a linee e numeri di riepilogo che include dettagli relativi al tempo di riproduzione massimo, minimo e/o totale trascorso. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, puoi modificare il pannello facendo clic sull’icona della matita (Modifica) in alto a destra.

Se hai selezionato la suddivisione per serie, per ciascuna suddivisione viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![Output tempo di riproduzione dei contenuti multimediali](assets/mpts_outputs1.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è Playback Time Spent (Tempo di riproduzione trascorso).

| Metrica | Descrizione |
|---|---|
| Tempo di riproduzione trascorso | Totale in ore:minutes:secondi (o minuti) del contenuto visualizzato durante la granularità selezionata, inclusi pausa, buffer e tempo di avvio. |

## Domande frequenti {#FAQ}

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | <p></p><p>La tabella a forma libera non è disponibile in questa vista. Per scaricare l’origine dati, fai clic con il pulsante destro del mouse sul grafico a linee e scarica il file CSV.</p> |
| <p>Perché la granularità è cambiata?</p> | <p>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe.</p><p></p><p>Quando passi da un intervallo di date più ampio a uno più ridotto, la granularità viene aggiornata al dettaglio più basso consentito dopo la modifica dell’intervallo di date. Per visualizzare una granularità maggiore, modifica il pannello e ricompila.</p> |
| <p></p><p>Come si confrontano nomi video, segmenti, tipi di contenuto, ecc.?</p> | <p>Per confrontare questi elementi in una singola visualizzazione, trascina segmenti, dimensioni o elementi dimensionali specifici nel filtro di raggruppamento per serie.</p><p></p><p>La visualizzazione è limitata a 10 suddivisioni. Per visualizzarne più di 10, è necessario utilizzare più pannelli.</p> |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza le suddivisioni per serie trascinando 2 o più intervalli di date. Questi intervalli di date sovrascriveranno l’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | <p></p><p>Questo pannello consente solo la visualizzazione a linee per le serie temporali.</p> |
| Posso eseguire il rilevamento delle anomalie? | <p></p><p>No. Il rilevamento delle anomalie non è disponibile per questo pannello.</p> |
