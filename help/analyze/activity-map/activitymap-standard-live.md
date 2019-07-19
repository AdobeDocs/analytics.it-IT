---
description: Activity Map fornisce due modalità di base per fornire rapporti complementari sull'attività della pagina.
seo-description: Activity Map fornisce due modalità di base per fornire rapporti complementari sull'attività della pagina.
seo-title: Modalità standard rispetto alla modalità Live
solution: Analytics
title: Modalità standard rispetto alla modalità Live
topic: Activity map
uuid: 8 b 97 b 56 e-ff 20-4 a 8 b -8 c 37-7 f 7 b 45 c 9 a 86 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modalità standard rispetto alla modalità Live

Activity Map fornisce due modalità di base per fornire rapporti complementari sull'attività della pagina.

* Standard mode, in which the [Links on Page Report](/help/analyze/activity-map/activitymap-links-report.md)shows link data ranging from single day to multi-day, aggregated over the full date range.
* La modalità Live visualizza le tendenze dell'attività in tempo reale.

Per attivare o disattivare due modalità, fate clic sul pulsante Modalità nella barra degli strumenti.

## Standard Mode {#section_0C755F30B7EC4A13A62AB9A391AF51E6}

In **Standard Mode**, you can select the date range in the toolbar as shown below.

![](assets/standard_mode.png)

In questa modalità, le metriche Commerce senza abilitazione sono allocate in modo lineare. Ad esempio, supponiamo che un utente faccia clic su un collegamento "IPod mini" sulla home page, quindi naviga su altre 3 pagine. Nella pagina 4, acquista un IPod mini per $ 200. Il collegamento "IPod mini" riceverà $ 200 delle entrate della partecipazione e $ 50 ($ 200/4) delle entrate (entrate allocate linearmente).

Q: Cosa succede se una pagina include collegamenti con lo stesso nome di collegamento in aree separate? I due collegamenti ricevono separatamente i crediti perché hanno regioni diverse ma lo stesso nome di collegamento su una pagina?

A: Dipende dalla modalità di aggregazione dei dati del collegamento. Nella Mappa dell'attività, vediamo l'ID collegamento | Regione per una determinata pagina, quindi i dati allocati si riferiscono alla combinazione «Collegamento ID | Regione». In questo caso, poiché l'area è diversa, il collegamento | regione è distinto e quindi qualsiasi ricavo allocato per il primo collegamento | regione sarà diverso da tutte le entrate allocate per il secondo collegamento. Tuttavia, nell'interfaccia utente di Adobe Analytics, puoi visualizzare solo il rapporto ID collegamento (invece del rapporto Collega | Regione) per una determinata pagina (pagina suddivisa per collegamento). In tal caso, le entrate vengono aggregate su entrambe le aree.

## Live Mode {#section_D619B77D89A840F0B1C2DEA2715A516A}

In **Live Mode**, Analytics data is shown in 1-minute to 15-minute increments, in a trended fashion. Questa modalità riguarda l'analisi e il monitoraggio delle tendenze a breve termine sulla pagina Web.

La modalità Live risponde alle esigenze delle organizzazioni pubblicate. Queste organizzazioni devono monitorare le micro-tendenze sulla popolarità dei collegamenti all'interno di poche pagine chiave. La possibilità di comprendere rapidamente quali collegamenti rendere più performanti o quali rendere più efficace il business editoriale.

>[!IMPORTANT]
>
>Le suite di rapporti virtuali non sono compatibili con la modalità Live, solo con la modalità Standard.

![](assets/live_mode.png)

