---
description: I file di registro sono utili per capire quando gli utenti accedono al sistema e per monitorarne l’accesso e l’utilizzo, le suite di rapporti e le modifiche dell’amministratore.
title: Registri
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 20%

---

# Registri

I file di registro sono utili per capire quando gli utenti accedono al sistema e per monitorarne l’accesso e l’utilizzo, le suite di rapporti e le modifiche dell’amministratore.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Logs]**

## Registro amministratore {#section_8ADE8A7204A8401C968ABC20AECA381D}

Il registro di amministrazione segnala tutte le modifiche apportate dagli amministratori negli strumenti di amministrazione. Inoltre permette di creare rapporti definiti dall’utente da uno dei tre registri disponibili. Puoi cercare gli eventi che corrispondono ai criteri selezionati in un intervallo di date specificato.

## Registro di utilizzo e accesso {#section_6FBAF92D9EA244809C45A78A2F0A7232}

Il [!UICONTROL Usage and Access Log] consente di valutare l’utilizzo del rapporto a livello dell’account utente. Tiene traccia ad esempio delle azioni di apertura, creazione, aggiornamento, annullamento della condivisione ed eliminazione in Analysis Workspace. Ciò consente di avere una migliore visibilità degli utenti che utilizzano l’Area di lavoro e della frequenza con cui questa viene utilizzata.

| Elemento | Descrizione |
|---|---|
| Intervallo date | Specifica un filtro per intervalli di date. È possibile immettere manualmente una data nel formato AAAA-MM-GG oppure fare clic sull&#39;icona Calendario per selezionare una data. |
| Login | Filtra il registro in base al nome utente. |
| IP | Filtra il registro in base a un indirizzo IP. |
| Suite di rapporti | Filtra il registro in base a un ID suite di rapporti specifico. |
| Tipo evento | Filtra il registro per tipo di evento. Seleziona un tipo di evento dall’elenco a discesa. Consulta l’elenco completo dei tipi di evento riportato di seguito. |
| Evento | Filtra il registro in base a una parola o a una frase nella descrizione dell’evento. |
| Scarica rapporto | Esporta il contenuto del [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |

### Tipi di evento

| Tipo di evento | Descrizione |
| --- | --- |
| Nessuna categoria | Potrebbe essere qualsiasi tipo di evento. |
| Accesso non riuscito | Processo di accesso utente non riuscito. |
| Accesso riuscito | Utente connesso correttamente. |
| Azione di amministrazione | Si è verificata un’azione di amministrazione, come modificare una suite di rapporti, modificare le impostazioni aziendali, creare un utente e così via. |
| Modifica delle impostazioni di sicurezza | È stata modificata un&#39;impostazione di protezione. |
| Rapporto visualizzato | È stato visualizzato un rapporto Reports &amp; Analytics. |
| Report scaricato | È stato scaricato un rapporto Reports &amp; Analytics. |
| Avviso inviato | È stato inviato un avviso. |
| Azione utente | Informazioni utente modificate. |
| Strumento visualizzato | È stato visualizzato uno strumento. |
| Azione Omniture | Azione eseguita da Adobe. |
| Recupero password | È stata recuperata una password. |
| BookMarks | Un segnalibro è stato gestito. |
| Dashboard | Un dashboard è stato gestito. |
| Avvisi | È stato gestito un avviso. |
| Eventi calendario | Un evento calendario è stato gestito. |
| Target | Destinazione gestita. |
| Impostazioni dei rapporti | È stata gestita un’impostazione di report. |
| Rapporti programmati | Un report pianificato è stato gestito. |
| Escludi per indirizzo IP | L&#39;impostazione IP è stata modificata. |
| Denomina pagine | Obsoleto. |
| Classificazioni | È stata gestita una classificazione. |
| Origini dati | Origine dati gestita. |
| Progetto Workspace | Un progetto Workspace è stato visualizzato o modificato. |
| Segmento | Un segmento è stato creato/modificato. |
| Metrica calcolata | È stata creata/modificata una metrica calcolata. |
| Intervallo date | È stato creato/modificato un intervallo di date. |
| Suite di rapporti virtuali | È stata creata/modificata una suite di rapporti virtuale. |
| Analisi contributi | È stato eseguito un processo di analisi dei contributi. |
| Metodo Api | È stata effettuata una chiamata API. |


## Registro modifiche suite di rapporti {#section_3864966639414BBEA871F4D0352F56B6}

Il registro delle modifiche delle suite di rapporti visualizza le modifiche apportate alle suite di rapporti al di fuori di Admin.

Strumenti che possono modificare una suite di rapporti dall’esterno di [!UICONTROL Admin Tools] include:

* Classificazioni caricate in un browser web (i caricamenti di classificazioni effettuati tramite FTP non sono inclusi nel registro delle modifiche)
* Modifiche apportate nelle versioni precedenti.
* Modifiche apportate da un rappresentante dell’account o dall’Assistenza clienti utilizzando strumenti interni

| Elemento | Descrizione |
|---|---|
| Intervallo date | Specifica un filtro per intervalli di date. È possibile immettere manualmente una data nel formato AAAA-MM-GG oppure fare clic sull&#39;icona Calendario per selezionare una data. |
| Azienda | Filtra il registro in base al nome della società. |
| Login | Filtra il registro in base al nome utente. |
| IP | Filtra il registro in base a un indirizzo IP. |
| Evento | Filtra il registro in base a una parola o a una frase nella descrizione dell’evento. |
| Scarica rapporto | Esporta il contenuto del [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |
