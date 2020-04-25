---
title: Cura di progetti e VRS
description: Impara a curare i componenti e i progetti VRS
translation-type: tm+mt
source-git-commit: db983980a6ec3db4d60bbc8fc3ba57a4e1219287

---


# Cura di progetti e VRS

Quando curi dei progetti o delle suite di rapporti virtuali (VRS), in pratica filtri i componenti in modo che gli utenti possano vedere solo i componenti (dimensioni, metriche, segmenti, intervalli di date) per i progetti o le VRS che vorranno usare.

>[!NOTE]
>
>I profili di prodotto sono il meccanismo principale per determinare quali componenti può vedere un utente. Sono gestite tramite [Admin Console](https://helpx.adobe.com/it/enterprise/using/manage-products-and-profiles.html#createproductprofiles). La cura è un filtro secondario.

L’esperienza di cura è stata recentemente migliorata. Ecco una panoramica di cosa viene mostrato dal pulsante **[!UICONTROL Show All]** (Mostra tutti), oltre ai componenti curati già disponibili, nelle diverse esperienze curate e in base al livello delle autorizzazioni:

| Tipo di cura | Amministratori | Proprietari di progetto non amministratori | Non amministratori |
|---|---|---|---|
| VRS curate | Tutti i componenti VRS non curati | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato | Tutti i componenti di progetto non curati | Tutti i componenti di progetto non curati | I componenti di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato in una VRS curata | Tutti i componenti non curati, visualizzati in  **[!UICONTROL Non-Curated Project Components]** (Componenti di progetto non curati) e **[!UICONTROL Non-Curated VRS Components]** (Componenti VRS non curati) | Tutti i componenti di progetto non curati E i componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS e di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |

>[!IMPORTANT]
>
>La cura VRS viene sempre applicata prima della cura del progetto. Ciò significa che anche se il progetto curato include alcuni componenti, essi verranno filtrati se la VRS curata non li include.
