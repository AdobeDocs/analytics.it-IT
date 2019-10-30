---
description: '[!DNL Activity Map] fornisce due modalità di base per la generazione di rapporti complementari sull''attività della pagina.'
seo-description: '[!DNL Activity Map] fornisce due modalità di base per la generazione di rapporti complementari sull''attività della pagina.'
seo-title: Modalità standard e modalità Live
solution: Analytics
title: Modalità standard e modalità Live
topic: Activity Map
uuid: 8b97b56e-ff20-4a8b-8c37-7f7b45c9a86b
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Modalità standard e modalità Live

[!DNL Activity Map] fornisce due modalità di base per la generazione di rapporti complementari sull'attività della pagina.

* Modalità standard, in cui i [collegamenti ai](/help/analyze/activity-map/activitymap-links-report.md)rapporti sulle pagine mostrano dati di collegamento che vanno da un giorno all’altro, aggregati per l’intero intervallo di date.
* La modalità Live mostra le tendenze dell'attività in tempo reale.

Per attivare/disattivare le due modalità, fare clic sul pulsante Modalità nella barra degli strumenti.

## Modalità standard {#section_0C755F30B7EC4A13A62AB9A391AF51E6}

In modalità **** standard, potete selezionare l’intervallo di date nella barra degli strumenti come mostrato di seguito.

![](assets/standard_mode.png)

In questa modalità, le metriche Commerce per le quali non è abilitata la funzione "Partecipazione" vengono allocate in modo lineare. Ad esempio, supponiamo che un utente faccia clic su un collegamento "IPod mini" nella home page, quindi naviga attraverso altre 3 pagine. Alla 4° pagina, acquista un IPod mini a 200 dollari. Il collegamento "IPod mini" riceverà 200 dollari di entrate di partecipazione e 50 dollari (200/4 dollari) di entrate (entrate allocate linearmente).

D: Cosa succede se una pagina contiene collegamenti con lo stesso nome di collegamento in aree separate? I due collegamenti ricevono credito separatamente in quanto hanno regioni diverse ma lo stesso nome di collegamento in una pagina?

A: Dipende da come si aggregano i dati del collegamento. In [!DNL Activity Map], osserviamo l'ID collegamento|Regione per una determinata pagina, in modo che i dati allocati siano per la combinazione "ID collegamento|Regione". In questo caso, poiché la regione è diversa, il collegamento|regione sarebbe distinto, e quindi qualsiasi ricavo allocato per la prima regione|collegamento sarà diverso da tutti i ricavi allocati per il secondo collegamento. Tuttavia, nell’interfaccia utente di Adobe Analytics, puoi consultare solo il rapporto ID collegamento (invece del rapporto Collegamento|Regione) per una determinata pagina (pagina suddivisa per Collegamento). In tal caso, le entrate sarebbero aggregate tra le due regioni.

## Modalità Live {#section_D619B77D89A840F0B1C2DEA2715A516A}

In modalità **** Live, i dati di Analytics vengono visualizzati in incrementi di 1 minuto-15 minuti, con tendenze. Questa modalità consiste nell'analizzare e monitorare le tendenze a breve termine sulla pagina Web.

La modalità Live risponde alle esigenze delle organizzazioni di pubblicazione. Queste organizzazioni devono monitorare le micro-tendenze sulla popolarità dei collegamenti all'interno di alcune pagine chiave. La capacità di individuare rapidamente i collegamenti che non funzionano correttamente o che stanno diventando attivi è fondamentale per il business della pubblicazione.

>[!IMPORTANT]
>
>Le suite di rapporti virtuali non sono compatibili con la modalità Live, solo con la modalità Standard.

![](assets/live_mode.png)

