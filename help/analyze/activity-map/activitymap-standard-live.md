---
description: Activity Map fornisce due modalità di base per la generazione di rapporti complementari per l’attività della pagina.
title: Modalità standard e modalità Live
uuid: 8b97b56e-ff20-4a8b-8c37-7f7b45c9a86b
feature: Activity Map
role: User, Admin
exl-id: 2364e7b0-443a-49a8-b084-403501f52360
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 3%

---

# Modalità standard e modalità Live

Activity Map fornisce due modalità di base per la generazione di rapporti complementari per l’attività della pagina.

* Modalità standard, in cui i [Collegamenti al rapporto pagina](/help/analyze/activity-map/activitymap-links-report.md)mostrano dati di collegamento che vanno da un giorno all’altro, aggregati per l’intervallo di date completo.
* La modalità Live mostra le tendenze dell’attività in tempo reale.

Per attivare o disattivare le due modalità, fai clic sul pulsante Modalità sulla barra degli strumenti.

## Modalità standard {#section_0C755F30B7EC4A13A62AB9A391AF51E6}

In **Modalità standard**, puoi selezionare l’intervallo di date nella barra degli strumenti come mostrato di seguito.

![](assets/standard_mode.png)

In questa modalità, le metriche Commerce prive di &quot;Partecipazione&quot; abilitate vengono allocate in modo lineare. Ad esempio, supponiamo che un utente faccia clic su un collegamento &quot;IPod mini&quot; nella home page, quindi naviga in altre 3 pagine. Alla quarta pagina, acquista un IPod mini per 200 dollari. Il link &quot;IPod mini&quot; riceverà 200 dollari di entrate di partecipazione e 50 dollari (200/4 dollari) di entrate (entrate assegnate in modo lineare).

D: Cosa succede se una pagina ha collegamenti con lo stesso nome di collegamento in aree diverse? I due collegamenti ricevono credito separatamente in quanto hanno aree geografiche diverse ma lo stesso nome di collegamento in una pagina?

R: Dipende da come aggreghi i dati del collegamento. In Activity Map, esaminiamo l’ID collegamento|Regione per una determinata pagina, in modo che i dati allocati siano per la combinazione &quot;ID collegamento|Regione&quot;. In questo caso, poiché l&#39;area è diversa, il collegamento|regione sarebbe distinto e pertanto tutti i ricavi allocati per il primo collegamento|regione saranno diversi da tutti i ricavi allocati per il secondo collegamento. Ma nell’interfaccia utente di Adobe Analytics puoi guardare solo il rapporto ID collegamento (anziché il rapporto Collegamento|Regione) per una determinata pagina (pagina suddivisa per Collegamento). In tal caso, le entrate saranno aggregate tra le due regioni.

## Modalità Live {#section_D619B77D89A840F0B1C2DEA2715A516A}

In **Modalità live**, i dati di Analytics vengono visualizzati in incrementi di 1 minuto-15 minuti, in modo con tendenze. Questa modalità si basa sull&#39;analisi e il monitoraggio delle tendenze a breve termine sulla pagina web.

La modalità Live risponde alle esigenze delle organizzazioni di pubblicazione. Queste organizzazioni devono monitorare le micro-tendenze sulla popolarità dei collegamenti all&#39;interno di alcune pagine chiave. La capacità di individuare rapidamente quali collegamenti sono poco efficienti o sono sempre più attivi è fondamentale per il business della pubblicazione.

>[!IMPORTANT]
>
>Le suite di rapporti virtuali non sono compatibili con la modalità Live, ma solo con la modalità Standard.

![](assets/live_mode.png)
