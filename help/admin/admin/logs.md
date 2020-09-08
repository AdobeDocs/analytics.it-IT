---
description: Registrate i file per consentirvi di vedere quando gli utenti accedono, quando ne utilizzano, quando accedono, quando le suite di rapporti e quando l'amministratore cambia.
title: Registri
topic: Admin tools
uuid: d5d4723d-f4cf-403e-ae9c-76d7faed2be6
translation-type: tm+mt
source-git-commit: 3603722ee3cbaf64b6d7bc0cbfa4af176f85a87a
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 10%

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
| --- |--- |
| Nessuna categoria |  |
| Login non riuscito |  |
| Login riuscito |  |
| Azione amministratore |  |
| Modifica delle impostazioni di protezione |  |
| Report visualizzato |  |
| Report scaricato |  |
| Avviso inviato |  |
| Azione utente |  |
| Strumento visualizzato |  |
| Azione  Omniture |  |
| Recupero password |  |
| BookMarks |  |
| Dashboard |  |
| Avvisi |  |
| Eventi calendario |  |
| Target |  |
| Impostazioni dei rapporti |  |
| Rapporti pianificati |  |
| Escludi per IP |  |
| Nome pagine |  |
| Classificazioni |  |
| Origini dati |  |
| Progetto Workspace |  |
| Segmento |  |
| Metrica calcolata |  |
| Intervallo di date |  |
| Suite di rapporti virtuali |  |
| Analisi contributi |  |
| Richiesta blocco dati Excel |  |
| Login di Excel non riuscito |  |
| Accesso Excel completato |  |
| Errore di accesso mobile |  |
| Accesso mobile completato |  |
| Metodo Api |  |


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

