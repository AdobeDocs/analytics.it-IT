---
title: Pannello Visualizzatori simultanei di contenuti multimediali
description: Come utilizzare e interpretare il pannello Media Concurrent Viewers (Visualizzatori simultanei di contenuti) in Analysis Workspace.
feature: Pannelli
role: User, Admin
exl-id: 29575b51-e319-4156-9834-aa0b671afb31
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: ht
source-wordcount: '1005'
ht-degree: 100%

---

# Pannello Visualizzatori simultanei di contenuti multimediali

I clienti di Media Analytics possono analizzare i visualizzatori simultanei per capire dove si è verificato il picco di concorrenza o dove si è verificato un calo, per fornire informazioni sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori, utili per risolvere eventuali problemi o pianificare un adeguamento per volume o scala.

In Analysis Workspace, per visualizzatori simultanei si intende il numero di visitatori univoci che visualizzano i flussi multimediali in un determinato momento, indipendentemente dal numero di sessioni.

Il pannello Media Concurrent Viewers (Visualizzatori simultanei di contenuti) consente di analizzare i visualizzatori simultanei nel tempo, con dettagli sul picco di concorrenza e con la possibilità di suddividerli e confrontarli.  Per accedere al pannello Media Concurrent Viewers (Visualizzatori simultanei di contenuti), passa a una suite di rapporti con i componenti Media Analytics abilitati. Fai clic sull’icona del pannello all’estrema sinistra, quindi trascina il pannello nel progetto Analysis Workspace.

## Input del pannello {#Input}

Puoi configurare il pannello Media Concurrent Viewers (Visualizzatori simultanei di contenuti) usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi).  È possibile modificarlo per visualizzare uno o più mesi alla volta. <br> <br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto).  Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Granularity (Granularità) | L’impostazione predefinita della granularità è Minuto. <br> <br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto).  Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli di data o ora per i visualizzatori simultanei, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso.  Per impostazione predefinita il pannello mostra solo il valore massimo, ma puoi impostarlo sul valore minimo o su entrambi.<br><br>Se utilizzi le suddivisioni, per ciascuna viene visualizzato un numero di riepilogo. |
| Suddivisione per serie di dati | Facoltativamente, puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date. <br><br>- È possibile visualizzare fino a 10 righe alla volta. Le suddivisioni sono limitate a un singolo livello.<br><br>- Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.<br><br>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di suddivisione per serie. |

### Vista predefinita

![Vista predefinita](assets/concurrent-viewers-default.png)


### Vista di suddivisione per serie

![vista di suddivisione per serie](assets/concurrent-viewers-series-breakdown.png)

## Output del pannello {#Output}

Il pannello Visualizzatori simultanei di contenuti multimediali restituisce un grafico a linee e numeri di riepilogo che includono i dettagli del numero massimo e/o minimo di visualizzatori simultanei.  Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, puoi modificare il pannello facendo clic sull’icona della matita (Modifica) in alto a destra.

Se hai selezionato la suddivisione per serie, per ciascuna suddivisione viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![output visualizzatori simultanei](assets/concurrent-viewers-output.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è Visualizzatori simultanei:

| Metrica | Descrizione |
|---|---|
| Visualizzatori simultanei | Numero di visitatori unici che visualizzano i flussi multimediali in un determinato momento, indipendentemente dal numero di sessioni.<br><br>È diverso dal reporting Visualizzatore simultaneo nella sezione Rapporti, che utilizza sessioni attive simultanee.  L’utilizzo di visitatori univoci consente di rimuovere i “picchi” indesiderati in corrispondenza dei confini tra dati da visualizzare (dove le sessioni terminano e iniziano allo stesso momento). |

In questa visualizzazione non è disponibile una tabella a forma libera.  Per visualizzare l’origine dati, fai clic con il pulsante destro del mouse sul grafico a linee e scarica come file .csv.  Saranno incluse le suddivisioni per serie di dati.


![output visualizzatori simultanei](assets/concurrent-viewers-download-csv.png)

## Domande frequenti {#FAQ}

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | La tabella a forma libera non è disponibile in questa vista. Per scaricare l’origine dati, fai clic con il pulsante destro del mouse sul grafico a linee e scarica il file CSV. |
| Perché la granularità è cambiata? | Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe.<br><br>Quando passi da un intervallo di date più ampio a uno più ridotto, la granularità viene aggiornata al dettaglio più basso consentito dopo la modifica dell’intervallo di date. Per visualizzare una granularità maggiore, modifica il pannello e ricompila. |
| Come si confrontano nomi video, segmenti, tipi di contenuto, ecc.? | Per confrontare questi elementi in una singola visualizzazione, trascina segmenti, dimensioni o elementi dimensionali specifici nel filtro di suddivisione per serie.<br><br>La visualizzazione è limitata a 10 suddivisioni.  Per visualizzarne più di 10, è necessario utilizzare più pannelli. |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza le suddivisioni per serie trascinando 2 o più intervalli di date.  Questi intervalli di date sovrascriveranno l’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | Questo pannello consente solo la visualizzazione a linee per le serie temporali. |
| Posso eseguire il rilevamento delle anomalie? | No.  Il rilevamento delle anomalie non è disponibile per questo pannello. |
| Perché utilizzare visitatori univoci invece di sessioni attive? | L’utilizzo di visitatori univoci consente di rimuovere i picchi indesiderati in corrispondenza dei confini tra dati da visualizzare (dove le sessioni terminano e iniziano allo stesso momento). |
| Cosa significa avere visualizzatori simultanei con granularità maggiore del minuto? | Con una granularità maggiore di un minuto, i visualizzatori simultanei sono la somma dei visualizzatori simultanei univoci per tutti i minuti entro l’intervallo di tempo in questione. Ad esempio, i visualizzatori simultanei con granularità a livello di ora corrispondono alla somma dei visualizzatori simultanei univoci per tutti i minuti all’interno di quell’ora. |
| Il pannello Workspace mostra le stesse informazioni del rapporto Visualizzatori simultanei? | No.  In Analysis Workspace, per visualizzatori simultanei si intende il numero di visitatori univoci che visualizzano il flusso multimediale in un momento specifico, indipendentemente dal numero di sessioni.<br><br>È diverso dal reporting sui visualizzatori simultanei nella sezione Rapporti, in cui vengono utilizzate sessioni attive simultanee.  L’utilizzo di visitatori univoci consente di rimuovere i picchi indesiderati in corrispondenza dei confini tra dati da visualizzare (dove le sessioni terminano e iniziano allo stesso momento). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->
