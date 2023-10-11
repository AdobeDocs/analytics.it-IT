---
description: Activity Map fornisce due modalità di base per fornire rapporti complementari sull’attività della pagina.
title: Modalità standard e modalità Live
uuid: 8b97b56e-ff20-4a8b-8c37-7f7b45c9a86b
feature: Activity Map
role: User, Admin
exl-id: 2364e7b0-443a-49a8-b084-403501f52360
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 2%

---

# Modalità standard e modalità Live

Activity Map fornisce due modalità di base per fornire rapporti complementari sull’attività della pagina.

* Modalità standard, in cui [Collegamenti nel rapporto della pagina](/help/analyze/activity-map/activitymap-links-report.md)mostra i dati dei collegamenti, da uno a più giorni, aggregati per l’intero intervallo di date.
* La modalità Live mostra le tendenze delle attività in tempo reale.

È possibile attivare le due modalità facendo clic sul pulsante Modalità sulla barra degli strumenti.

## Modalità Standard {#section_0C755F30B7EC4A13A62AB9A391AF51E6}

In entrata **Modalità Standard**, è possibile selezionare l’intervallo di date nella barra degli strumenti come illustrato di seguito.

![](assets/standard_mode.png)

In questa modalità, le metriche Commerce per le quali non è abilitata la &quot;Partecipazione&quot; vengono allocate in modo lineare. Ad esempio, supponiamo che un utente faccia clic su un collegamento &quot;IPod mini&quot; nella home page, quindi naviga attraverso altre 3 pagine. Nella quarta pagina, l’utente acquista un mini IPod al prezzo di 200 $. Il collegamento &quot;IPod mini&quot; riceverà 200 dollari di ricavi di partecipazione e 50 dollari (200/4 dollari) di ricavi (ricavi allocati linearmente).

D: cosa succede se una pagina contiene collegamenti con lo stesso nome di collegamento in aree geografiche separate? I due collegamenti ricevono credito separatamente, in quanto hanno aree diverse ma lo stesso nome di collegamento in una pagina?

R: dipende da come aggreghi i dati del collegamento. In Activity Map, esaminiamo ID collegamento|Regione per una determinata pagina, quindi i dati allocati saranno per la combinazione &quot;ID collegamento|Regione&quot;. In questo caso, poiché l’area geografica è diversa, il collegamento|area sarà distinto e pertanto i ricavi allocati per la prima area saranno diversi da tutti i ricavi allocati per il secondo collegamento. Tuttavia, nell’interfaccia utente di Adobe Analytics, puoi visualizzare solo il rapporto ID collegamento (anziché il rapporto Area collegamenti ) per una determinata pagina (suddivisa per Collegamento). In tal caso, le entrate sarebbero aggregate tra le due regioni.

## Modalità Live {#section_D619B77D89A840F0B1C2DEA2715A516A}

In entrata **Modalità Live**, i dati di Analytics vengono visualizzati con incrementi da 1 minuto a 15 minuti, in modo tendenziale. Questa modalità si basa sull’analisi e il monitoraggio delle tendenze a breve termine sulla pagina web.

La modalità Live risponde alle esigenze delle organizzazioni di pubblicazione. Queste organizzazioni devono monitorare le micro-tendenze sulla popolarità dei collegamenti in poche pagine chiave. La capacità di individuare rapidamente i collegamenti con prestazioni insoddisfacenti o che si stanno surriscaldando è fondamentale per la tua attività di pubblicazione.

>[!IMPORTANT]
>
>Le suite di rapporti virtuali non sono compatibili con la modalità Live, ma solo con la modalità Standard.

![](assets/live_mode.png)
