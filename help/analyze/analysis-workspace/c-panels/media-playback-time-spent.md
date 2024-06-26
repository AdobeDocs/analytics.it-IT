---
title: Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)
description: Come utilizzare e interpretare il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 9268baf7-b50b-4c09-a722-7bfcd4172f15
source-git-commit: 4633225cc35658a7de39a40cd77df00137a54461
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 73%

---

# Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)

In Analysis Workspace, Playback Time Spent (Tempo di riproduzione trascorso) corrisponde alla quantità di tempo impiegato per visualizzare i flussi multimediali in un determinato momento. Include pausa, buffer e tempo di avvio.

Il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) consente di analizzare le riproduzioni nel tempo, con dettagli sul picco di concorrenza e con la possibilità di suddividerli e confrontarli.

I clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection possono analizzare il tempo di riproduzione per ottenere informazioni approfondite sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori, utili per risolvere eventuali problemi o pianificare un adeguamento per volume o scala.

Playback Time Spent (Tempo di riproduzione trascorso) consente di comprendere:

* Dove si è verificato il picco di concorrenza

* Dove si è verificato il calo

Di seguito è riportata una panoramica video di questo pannello:

>[!VIDEO](https://video.tv.adobe.com/v/338699)

## Utilizzare il pannello Tempo trascorso su contenuti multimediali

1. Vai a una suite di rapporti con i componenti multimediali in streaming abilitati.
1. Seleziona l’icona del pannello all’estrema sinistra, quindi trascina il pannello nel progetto Analysis Workspace.
1. Continua con le sezioni seguenti per personalizzare il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)

   * [Input del pannello](#panel-inputs)
   * [Output del pannello](#panel-output)

## Input del pannello {#Input}

Puoi configurare il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Granularity (Granularità) | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli di data o ora per il tempo di riproduzione trascorso, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso. Somma effettua la somma del tempo totale di riproduzione trascorso per la selezione. Per impostazione predefinita, il pannello mostra solo il valore Maximum (Massimo), ma puoi impostarlo su Minimum (Minimo), Sum (Somma) o qualsiasi combinazione dei tre.<br>Se utilizzi i raggruppamenti, per ciascuno viene visualizzato un numero di riepilogo. |
| Raggruppamento per serie | Facoltativamente, puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date.<p>- È possibile visualizzare fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.</p><p>- Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.</p>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di raggruppamento per serie. |
| Formato ora | È possibile visualizzare il tempo di riproduzione trascorso in `Hours:Minutes:Seconds` (impostazione predefinita) o in `Minutes` (visualizzato in numeri interi, arrotondato a 0,5). |
| Visualizzazione della sequenza di date | Se hai inserito almeno due segmenti di intervallo di date come raggruppamenti di serie, vedrai l’opzione per selezionare Sovrapponi (impostazione predefinita) o Sequenziale. La visualizzazione in sovrapposizione presenta le linee con un inizio comune dell’asse X, in parallelo; quella sequenziale presenta le linee in sequenza, ciascuna con il proprio inizio dell’asse X. Se i dati sono allineati (ad esempio, il segmento 1 termina alle 20:44 e il segmento 2 inizia alle 20:45), le linee vengono visualizzate in sequenza. |

## Vista predefinita

![Vista predefinita](assets/mpts_default_view.png)

## Output del pannello {#Output}

Il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) restituisce un grafico a linee e numeri di riepilogo che include dettagli relativi al tempo di riproduzione massimo, minimo e/o totale trascorso. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, puoi modificare il pannello facendo clic sull’icona della matita (Modifica) in alto a destra.

Se hai selezionato il raggruppamento per serie, per ciascun raggruppamento viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![Output Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)](assets/mpts_outputs1.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è Playback Time Spent (Tempo di riproduzione trascorso).

| Metrica | Descrizione |
|---|---|
| Tempo di riproduzione trascorso | Totale `hours:minutes:seconds` (o `minutes`) del contenuto visualizzato durante la granularità selezionata, inclusi pausa, buffer e tempo di avvio. |

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | La tabella a forma libera non è disponibile in questa vista. Per scaricare l’origine dati, fai clic con il pulsante destro del mouse sul grafico a linee e scarica il file CSV. |
| Perché la granularità è cambiata? | Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. <p>Quando passi da un intervallo di date più ampio a uno più ridotto, la granularità viene aggiornata al dettaglio più basso consentito dopo la modifica dell’intervallo di date. Per visualizzare una granularità maggiore, modifica il pannello e ricompila.</p> |
| Come si confrontano nomi video, segmenti, tipi di contenuto, ecc.? | Per confrontare questi elementi in una singola visualizzazione, trascina segmenti, dimensioni o elementi dimensionali specifici nel filtro di raggruppamento per serie. La visualizzazione è limitata a 10 raggruppamenti. Per visualizzarne più di 10, è necessario utilizzare più pannelli. |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza i raggruppamenti di serie trascinando 2 o più intervalli di date. Questi intervalli di date sovrascriveranno l’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | Questo pannello consente solo la visualizzazione a linee per le serie temporali. |
| Posso eseguire il rilevamento delle anomalie? | No. Il rilevamento delle anomalie non è disponibile per questo pannello. |
