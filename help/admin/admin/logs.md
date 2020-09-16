---
description: Registrate i file per consentirvi di vedere quando gli utenti accedono, quando ne utilizzano, quando accedono, quando le suite di rapporti e quando l'amministratore cambia.
title: Registri
topic: Admin tools
uuid: d5d4723d-f4cf-403e-ae9c-76d7faed2be6
translation-type: tm+mt
source-git-commit: fff1fb97f9224b7e68f85b24ac440083503df54f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 7%

---


# Registri

Registrate i file per consentirvi di vedere quando gli utenti accedono, quando ne utilizzano, quando accedono, quando le suite di rapporti e quando l&#39;amministratore cambia.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Logs]**

## Registro Amministratore {#section_8ADE8A7204A8401C968ABC20AECA381D}

Il registro di amministrazione riporta tutte le modifiche apportate dagli amministratori negli strumenti di amministrazione. Il registro fornisce un gateway ai rapporti definiti dall’utente da uno dei tre registri. È possibile cercare gli eventi che corrispondono ai criteri selezionati in un intervallo di date specificato.

## Registro di utilizzo e accesso {#section_6FBAF92D9EA244809C45A78A2F0A7232}

Consente di [!UICONTROL Usage and Access Log] valutare l&#39;utilizzo dei rapporti a livello di account utente. Ad esempio, tiene traccia delle azioni aperte, create, aggiornate, annullate la condivisione ed eliminate in  Analysis Workspace. Ciò consente di avere una migliore visibilità degli utenti che utilizzano l’Area di lavoro e della frequenza con cui questa viene utilizzata.

| Elemento | Descrizione |
|---|---|
| Intervallo di date | Specifica un filtro per l’intervallo di date. È possibile immettere una data manualmente nel formato AAAA-MM-GG oppure fare clic sull&#39;icona Calendario per selezionare una data. |
| Login | Filtrare il registro per nome utente. |
| IP | Filtrare il registro per un indirizzo IP. |
| Suite di rapporti | Filtrare il registro per un ID suite di rapporti specifico. |
| Tipo evento | Filtrare il registro in base a un tipo di evento. Selezionate un tipo di evento dall&#39;elenco a discesa. Consultate l&#39;elenco completo dei tipi di evento riportati di seguito. |
| Evento | Filtrare il registro per parola o frase nella descrizione dell&#39;evento. |
| Scarica rapporto | Esporta il contenuto del file [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |

### Tipi di evento

| Tipo evento | Descrizione |
| --- | --- |
| Nessuna categoria | Può essere un qualsiasi tipo di evento. |
| Login non riuscito | Il processo di accesso dell&#39;utente non è riuscito. |
| Login riuscito | Accesso dell&#39;utente completato. |
| Azione amministratore | Si è verificata un&#39;azione di amministrazione, come la modifica di una suite di rapporti, la modifica delle impostazioni aziendali, la creazione di un utente ecc. |
| Modifica delle impostazioni di protezione | È stata modificata un&#39;impostazione di protezione. |
| Report visualizzato | È stato visualizzato un rapporto Reporting e analisi. |
| Report scaricato | È stato scaricato un report Reporting e analisi. |
| Avviso inviato | È stato inviato un avviso. |
| Azione utente | Le informazioni utente sono state modificate. |
| Strumento visualizzato | È stato visualizzato uno strumento. |
| Azione  Omniture | Un&#39;azione è stata eseguita dal Adobe . |
| Recupero password | Una password è stata recuperata. |
| BookMarks | È stato gestito un segnalibro. |
| Dashboard | È stato gestito un dashboard. |
| Avvisi | È stato gestito un avviso. |
| Eventi calendario | È stato gestito un evento del calendario. |
| Target | È stato gestito un target. |
| Impostazioni dei rapporti | È stata gestita un&#39;impostazione di report. |
| Rapporti pianificati | È stato gestito un report pianificato. |
| Escludi per IP | L&#39;impostazione IP è stata modificata. |
| Nome pagine | Obsoleto. |
| Classificazioni | È stata gestita una classificazione. |
| Origini dati | È stata gestita un&#39;origine dati. |
| Progetto Workspace | Un progetto Workspace è stato visualizzato o modificato. |
| Segmento | È stato creato/modificato un segmento. |
| Metrica calcolata | È stata creata/modificata una metrica calcolata. |
| Intervallo di date | È stato creato/modificato un intervallo di date. |
| Suite di rapporti virtuali | È stata creata/modificata una suite di rapporti virtuale. |
| Analisi contributi | È stato eseguito un processo di analisi dei contributi. |
| Richiesta blocco dati Excel |  |
| Login di Excel non riuscito |  |
| Accesso Excel completato |  |
| Errore di accesso mobile |  |
| Accesso mobile completato |  |
| Metodo Api | È stata effettuata una chiamata API. |


## Registro modifiche suite di rapporti {#section_3864966639414BBEA871F4D0352F56B6}

Il registro delle modifiche delle suite di rapporti visualizza le modifiche apportate alle suite di rapporti al di fuori di Admin.

Gli strumenti che possono modificare una suite di rapporti dall&#39;esterno [!UICONTROL Admin Tools] includono:

* Classificazioni caricate in un browser Web (le classificazioni caricate mediante FTP non sono incluse nel registro delle modifiche)
* Modifiche apportate nelle versioni precedenti.
* Modifiche apportate da un rappresentante commerciale o da un&#39;Assistenza clienti con strumenti interni

| Elemento | Descrizione |
|---|---|
| Intervallo di date | Specifica un filtro per l’intervallo di date. È possibile immettere una data manualmente nel formato AAAA-MM-GG oppure fare clic sull&#39;icona Calendario per selezionare una data. |
| Azienda | Filtrare il registro in base al nome della società. |
| Login | Filtrare il registro per nome utente. |
| IP | Filtrare il registro per un indirizzo IP. |
| Evento | Filtrare il registro per parola o frase nella descrizione dell&#39;evento. |
| Scarica rapporto | Esporta il contenuto del file [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |

