---
description: Registra i file per consentirti di vedere quando gli utenti accedono, quando ne usano, quando accedono, quando accedono, quando le suite di rapporti e quando l’amministratore cambia.
title: 'Registri '
feature: Strumenti di amministrazione
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 9%

---

# Registri 

Registra i file per consentirti di vedere quando gli utenti accedono, quando ne usano, quando accedono, quando accedono, quando le suite di rapporti e quando l’amministratore cambia.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Logs]**

## Registro amministratore {#section_8ADE8A7204A8401C968ABC20AECA381D}

Il registro di amministrazione riporta tutte le modifiche apportate dagli amministratori in strumenti di amministrazione. Il registro fornisce un gateway ai rapporti definiti dall’utente da uno qualsiasi dei tre registri. È possibile cercare gli eventi che corrispondono ai criteri selezionati in un intervallo di date specificato.

## Registro di utilizzo e accesso {#section_6FBAF92D9EA244809C45A78A2F0A7232}

La sezione [!UICONTROL Usage and Access Log] consente di valutare l’utilizzo dei rapporti a livello di account utente. Ad esempio, tiene traccia delle azioni aperte, create, aggiornate, non condivise ed eliminate in Analysis Workspace. Ciò consente di avere una migliore visibilità degli utenti che utilizzano l’Area di lavoro e della frequenza con cui questa viene utilizzata.

| Elemento | Descrizione |
|---|---|
| Intervallo date | Specifica un filtro per l’intervallo di date. Puoi immettere manualmente una data nel formato AAAA-MM-GG oppure fare clic sull’icona Calendario per selezionare una data. |
| Login | Filtrare il registro in base al nome utente. |
| IP | Filtra il registro in base a un indirizzo IP. |
| Suite di rapporti | Filtrare il registro in base a un ID suite di rapporti specifico. |
| Tipo evento | Filtrare il registro in base a un tipo di evento. Seleziona un tipo di evento dall’elenco a discesa. Vedi l’elenco completo dei tipi di evento riportati di seguito. |
| Evento | Filtrare il registro per una parola o una frase nella descrizione dell’evento. |
| Download del rapporto | Esporta il contenuto di [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |

### Tipi di evento

| Tipo evento | Descrizione |
| --- | --- |
| Nessuna categoria | Può essere un qualsiasi tipo di evento. |
| Accesso non riuscito | Processo di accesso utente non riuscito. |
| Accesso riuscito | Accesso dell&#39;utente completato. |
| Azione amministratore | Si è verificata un&#39;azione di amministrazione, come la modifica di una suite di rapporti, la modifica delle impostazioni aziendali, la creazione di un utente, ecc. |
| Modifica delle impostazioni di protezione | È stata modificata un&#39;impostazione di protezione. |
| Report visualizzato | È stato visualizzato un rapporto Reports &amp; Analytics . |
| Report scaricato | È stato scaricato un rapporto di Reports &amp; Analytics. |
| Avviso inviato | È stato inviato un avviso. |
| Azione utente | Le informazioni utente sono state modificate. |
| Strumento visualizzato | È stato visualizzato uno strumento. |
| Azione Omniture | Un&#39;azione è stata eseguita da un Adobe. |
| Recupero password | È stata recuperata una password. |
| BookMarks | È stato gestito un segnalibro. |
| Dashboard | È stato gestito un dashboard. |
| Avvisi | È stato gestito un avviso. |
| Eventi calendario | È stato gestito un evento calendario. |
| Target | È stato gestito un target. |
| Impostazioni dei rapporti | È stata gestita un’impostazione di report. |
| Rapporti programmati | È stato gestito un report pianificato. |
| Escludi per indirizzo IP | L&#39;impostazione IP è stata modificata. |
| Pagine dei nomi | Obsoleto. |
| Classificazioni | È stata gestita una classificazione. |
| Origini dati | È stata gestita un&#39;origine dati. |
| Progetto Workspace | È stato visualizzato o modificato un progetto Workspace. |
| Segmento | È stato creato/modificato un segmento. |
| Metrica calcolata | È stata creata/modificata una metrica calcolata. |
| Intervallo date | È stato creato/modificato un intervallo di date. |
| Suite di rapporti virtuali | È stata creata/modificata una suite di rapporti virtuale. |
| Analisi contributi | È stato eseguito un processo di analisi dei contributi. |
| Metodo Api | È stata effettuata una chiamata API. |


## Registro delle modifiche alle suite di rapporti {#section_3864966639414BBEA871F4D0352F56B6}

Il registro delle modifiche alle suite di rapporti visualizza le modifiche apportate alle suite di rapporti al di fuori di Admin.

Gli strumenti che possono modificare una suite di rapporti dall&#39;esterno di [!UICONTROL Admin Tools] includono:

* Caricamenti di classificazioni effettuati in un browser web (i caricamenti di classificazioni effettuati tramite FTP non sono inclusi nel registro delle modifiche)
* Modifiche apportate nelle versioni precedenti.
* Modifiche apportate da un rappresentante di un account o dall’Assistenza clienti utilizzando strumenti interni

| Elemento | Descrizione |
|---|---|
| Intervallo date | Specifica un filtro per l’intervallo di date. Puoi immettere manualmente una data nel formato AAAA-MM-GG oppure fare clic sull’icona Calendario per selezionare una data. |
| Azienda | Filtra il registro in base al nome della società. |
| Login | Filtrare il registro in base al nome utente. |
| IP | Filtra il registro in base a un indirizzo IP. |
| Evento | Filtrare il registro per una parola o una frase nella descrizione dell’evento. |
| Download del rapporto | Esporta il contenuto di [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |
