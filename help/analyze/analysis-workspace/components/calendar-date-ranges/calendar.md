---
description: Nel calendario, puoi specificare date e intervalli di date o selezionare un predefinito.
title: Panoramica del calendario e degli intervalli di date
feature: Calendar
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '931'
ht-degree: 89%

---

# Panoramica del calendario e degli intervalli di date {#date-range}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="Ora di fine"
>abstract="Gli orari di fine includono sempre 59 secondi."

<!-- markdownlint-enable MD034 -->


Nel calendario, puoi specificare date e intervalli di date o selezionare un predefinito.


>[!BEGINSHADEBOX]

Per un video demo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panoramica sul calendario e sugli intervalli di date](https://video.tv.adobe.com/v/329875?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


Le selezioni di calendario sono applicabili a livello del singolo pannello, ma è possibile applicarle a tutti i pannelli. Quando fai clic su un intervallo di date in Workspace, l’interfaccia mostra il mese del calendario corrente e il mese del calendario precedente. È possibile regolare questi due calendari facendo clic sulle frecce destra e sinistra nei rispettivi angoli superiori.

![Calendario](assets/aw_calendar2.png){width="60%"}

## Selezionare e applicare gli intervalli di date {#select-apply}

Il primo clic su un calendario avvia una selezione di intervalli di date. Il secondo clic completa la selezione di un intervallo di date, che viene evidenziato. Se si tiene premuto il tasto `Shift` (o se si fa clic con il pulsante destro del mouse), si aggiunge all’intervallo attualmente selezionato.

È inoltre possibile trascinare le date (e dimensioni orarie) in un progetto Workspace. Puoi selezionare specifici giorni, settimane, mesi, anni, oppure una data continua.

[Utilizzo degli intervalli di date e del calendario in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=it) (4:07)

| Impostazione | Descrizione |
|--- |--- |
| Giorni selezionati | Giorni/settimane/mesi/anni selezionati. |
| Rendi i componenti di intervallo di date relativi al calendario del pannello | Se è disattivato, qualsiasi componente di intervallo di date utilizzato all’interno di una tabella, di una visualizzazione o di una zona di rilascio di un pannello sovrascrive il calendario del pannello. <p>Se abilitati, tutti i componenti dell’intervallo di date utilizzati all’interno di una tabella, di una visualizzazione o di una zona di rilascio di un pannello sono correlati all’intervallo di date del pannello. Ad esempio, se l’intervallo di date del pannello è impostato su 1 novembre fino al 30 novembre e in una tabella a forma libera viene utilizzato un componente Intervallo ultime settimane, le informazioni nella tabella a forma libera si riferiscono all’ultima settimana di ottobre. |
| Utilizzo delle date continue | Le date continue consentono di generare un rapporto dinamico per un determinato periodo di tempo precedente o successivo all’esecuzione del rapporto. Ad esempio, per un rapporto su tutti gli ordini inseriti il “Mese scorso” (in base al campo Data creazione) eseguito in dicembre, vengono presentati gli ordini di novembre. Se esegui di nuovo lo stesso rapporto a gennaio, puoi vedere gli ordini di dicembre.<ul><li>**[!UICONTROL Date Preview]** (Anteprima data): indica il periodo di tempo coperto dal calendario continuo.</li><li>**[!UICONTROL Start]**: puoi scegliere il giorno, la settimana, il mese, il trimestre o l’anno corrente.</li><li>**[!UICONTROL End]**: puoi scegliere il giorno, la settimana, il mese, il trimestre o l’anno corrente.</li></ul>Per visualizzare un esempio, consulta [Intervalli di date personalizzati](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Selezionato per impostazione predefinita. |
| Intervallo date | Consente di scegliere un intervallo di date predefinito. Il valore predefinito è Ultimi 30 giorni. **[!UICONTROL This week/month/quarter/year (excluding today)]** consente di scegliere tra intervalli di date che non includono dati per giorni parziali a partire da oggi. |
| Applica a tutti i pannelli | Consente di selezionare l’intervallo di date per il pannello corrente e per tutti gli altri pannelli del progetto. |
| Applica | Applica l’intervallo di date solo al pannello corrente. |

## Informazioni sugli intervalli di date relativi al pannello {#relative-panel-dates}

Se stai utilizzando Workspace, puoi rendere i componenti dell’intervallo di date relativi al calendario del pannello.
Tre casi d’uso comuni in cui vengono applicate le date relative al pannello sono i grafici combinati, il riepilogo delle metriche chiave e gli intervalli di date delle tabelle a forma libera.

Per utilizzare gli intervalli di date relativi al pannello

1. Seleziona la scheda **Workspace**.
1. Seleziona **Progetto vuoto**.
1. Aggiungi dimensioni, metriche e segmenti dalla barra a sinistra.
1. Fai clic sul campo per intervallo di date del pannello per attivare/disattivare l’impostazione dell’intervallo di date relative al pannello.
1. Seleziona **Rendi i componenti di intervallo di date relativi al calendario del pannello**.
   * Seleziona l’opzione per rendere i componenti dell’intervallo di date relativi al calendario del pannello.
Se vengono selezionate date relative, le date continue verranno basate sulla data di inizio del calendario del pannello e non su quella odierna.
   * Se questa opzione non è selezionata, le date continue saranno basate sulla data odierna.

   ![date relative del pannello](assets/relative-date-selected.png){width="60%"}

1. Fai clic su **Applica**.
Le date relative sono visualizzate in alto a destra.

   ![date relative a forma libera](assets/relative-date-range1.png)

## Linee guida per gli intervalli di date relative del pannello {#guidelines}

Quando utilizzi gli intervalli di date relativi del pannello, tieni presenti le seguenti linee guida.

### Formule e intervalli di date relativi {#formula-relative-dates}

Se hai selezionato date relative, tutte le formule di date utilizzeranno la data di inizio del pannello come punto iniziale.

### Calendari personalizzati e intervalli di date relativi {#custom-calendar-formulas}

Quando si utilizza un calendario personalizzato basato su settimane e si aggiungono mesi o anni, la formula calcola l’offset del giorno nel periodo specificato. La data effettiva può essere diversa a causa dell’offset. La formula sceglie il giorno di destinazione nello stesso punto del calendario personalizzato. Ad esempio, il terzo venerdì della terza settimana in un calendario personalizzato.

### Informazioni sui segmenti che utilizzano date continue e intervalli di date del pannello relativo {#segments-relative-dates}

Se crei un segmento o utilizzi un segmento con una data continua, ad esempio gli ultimi 7 giorni o le ultime 2 settimane, e fai clic sull’anteprima del segmento, la data continua inizierà da *Oggi* invece che dalla data di inizio del pannello. Di conseguenza, l’anteprima del segmento non corrisponderà a quando lo utilizzavi effettivamente nella tabella. L’anteprima è interessata, non il segmento stesso.

## Linee guida per intervalli di date e anteprime del pannello {#guidelines-panel-dates}

* A partire dalla versione di febbraio, le anteprime dei dati e dei componenti saranno basate sull’intervallo di date del pannello e non sugli ultimi 90 giorni.
* Tutti i componenti elencati nella barra a sinistra saranno disponibili in base all’intervallo di date del pannello.
* Tutte le anteprime di date nel segmento e i generatori di metriche calcolate saranno basati sull’intervallo di date del pannello (a meno che non siano accessibili dai gestori dei componenti che non hanno un pannello associato, saranno comunque basati sugli ultimi 90 giorni).
* Tutte le anteprime dei dati mostreranno dati o componenti in base all’intervallo di date del pannello.