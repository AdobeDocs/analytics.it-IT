---
description: I file di registro sono utili per capire quando gli utenti accedono al sistema e per monitorarne l’accesso e l’utilizzo, le suite di rapporti e le modifiche dell’amministratore.
title: Registri
feature: Admin Tools
exl-id: 43f79e2a-2cb9-47eb-982a-54714c9cbafc
role: Admin
TQID: https://experienceleague.adobe.com/TsWKmf74-b1RhjP0CSGZatLrGN39xDylj9tbFZg5R-Y
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2: id: c6a85389-fb1b-4b26-96ea-08f17fed0c9fid: e44bec7e-8653-4d5b-b53e-60b1ae7c3475id: e499b847-6dc4-408a-9f0b-70d35ce9b711id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 578
ht-degree: 20%

---

# Registri

I file di registro sono utili per capire quando gli utenti accedono al sistema e per monitorarne l’accesso e l’utilizzo, le suite di rapporti e le modifiche dell’amministratore.

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Logs]**

## Registro amministratore {#section_8ADE8A7204A8401C968ABC20AECA381D}

Il registro di amministrazione segnala tutte le modifiche apportate dagli amministratori negli strumenti di amministrazione. Inoltre permette di creare rapporti definiti dall’utente da uno dei tre registri disponibili. Puoi cercare gli eventi che corrispondono ai criteri selezionati in un intervallo di date specificato.

## Registro di utilizzo e accesso {#section_6FBAF92D9EA244809C45A78A2F0A7232}

[!UICONTROL Usage and Access Log] consente di valutare l&#39;utilizzo del report a livello dell&#39;account utente. Tiene traccia ad esempio delle azioni di apertura, creazione, aggiornamento, annullamento della condivisione ed eliminazione in Analysis Workspace. Ciò consente di avere una migliore visibilità degli utenti che utilizzano l’Area di lavoro e della frequenza con cui questa viene utilizzata.

| Elemento | Descrizione |
|---|---|
| Intervallo date | Specifica un filtro per intervalli di date. È possibile immettere manualmente una data nel formato AAAA-MM-GG oppure fare clic sull&#39;icona Calendario per selezionare una data. |
| Accedi | Filtra il registro in base al nome utente. |
| IP | Filtra il registro in base a un indirizzo IP. |
| Suite di rapporti | Filtra il registro in base a un ID suite di rapporti specifico. |
| Tipo evento | Filtra il registro per tipo di evento. Seleziona un tipo di evento dall’elenco a discesa. Consulta l’elenco completo dei tipi di evento riportato di seguito. |
| Evento | Filtra il registro in base a una parola o a una frase nella descrizione dell’evento. |
| Scarica rapporto | Esporta il contenuto di [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |

### Tipi di evento

| Tipo di evento | Descrizione |
| --- | --- |
| Nessuna categoria | Potrebbe essere qualsiasi tipo di evento. |
| Accesso non riuscito | Processo di accesso utente non riuscito. |
| Accesso riuscito | Utente connesso correttamente. |
| Azione di amministrazione | Si è verificata un’azione di amministrazione, come modificare una suite di rapporti, modificare le impostazioni aziendali, creare un utente, annullare una richiesta di reporting, ecc. |
| Modifica delle impostazioni di sicurezza | È stata modificata un&#39;impostazione di protezione. |
| Avviso inviato | È stato inviato un avviso. |
| Azione utente | Informazioni utente modificate. |
| Strumento visualizzato | È stato visualizzato uno strumento. |
| Azione Omniture | Azione eseguita da Adobe. |
| Recupero password | È stata recuperata una password. |
| Segnalibri | Un segnalibro è stato gestito. |
| Dashboard | Un dashboard è stato gestito. |
| Avvisi | È stato gestito un avviso. |
| Eventi calendario | Un evento calendario è stato gestito. |
| Target | Destinazione gestita. |
| Impostazioni dei rapporti | È stata gestita un’impostazione di report. |
| Rapporti pianificati | Un report pianificato è stato gestito. |
| Escludi per indirizzo IP | L&#39;impostazione IP è stata modificata. |
| Pagine dei nomi | Obsoleto. |
| Classificazioni | È stata gestita una classificazione. |
| Origini dati | Origine dati gestita. |
| Progetto Workspace | Un progetto Workspace è stato visualizzato o modificato. |
| Segmento | Un segmento è stato creato/modificato. |
| Metrica calcolata | È stata creata/modificata una metrica calcolata. |
| Intervallo date | È stato creato/modificato un intervallo di date. |
| Suite di rapporti virtuale | È stata creata/modificata una suite di rapporti virtuale. |
| Analisi contributi | È stato eseguito un processo di analisi dei contributi. |
| Metodo Api | È stata effettuata una chiamata API. |


## Registro modifiche suite di rapporti {#section_3864966639414BBEA871F4D0352F56B6}

Il registro delle modifiche delle suite di rapporti visualizza le modifiche apportate alle suite di rapporti al di fuori di Admin.

Gli strumenti che possono modificare una suite di rapporti dall&#39;esterno di [!UICONTROL Admin Tools] includono:

* Classificazioni caricate in un browser web (i caricamenti di classificazioni effettuati tramite FTP non sono inclusi nel registro delle modifiche)
* Modifiche apportate nelle versioni precedenti.
* Modifiche apportate da un rappresentante dell’account o dall’Assistenza clienti utilizzando strumenti interni

| Elemento | Descrizione |
|---|---|
| Intervallo date | Specifica un filtro per intervalli di date. È possibile immettere manualmente una data nel formato AAAA-MM-GG oppure fare clic sull&#39;icona Calendario per selezionare una data. |
| Azienda | Filtra il registro in base al nome della società. |
| Accedi | Filtra il registro in base al nome utente. |
| IP | Filtra il registro in base a un indirizzo IP. |
| Evento | Filtra il registro in base a una parola o a una frase nella descrizione dell’evento. |
| Scarica rapporto | Esporta il contenuto di [!UICONTROL Usage & Access Log] in un file delimitato da tabulazioni. |
