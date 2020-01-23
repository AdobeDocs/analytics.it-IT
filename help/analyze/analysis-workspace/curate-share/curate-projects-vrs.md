---
title: Cura di progetti e VRS
description: Impara a curare i componenti e i progetti VRS
translation-type: tm+mt
source-git-commit: 3a00162c5899ba2d5bb1b5aaed448b2abe93d56d

---


# Cura di progetti e VRS

Quando curi dei progetti o delle suite di rapporti virtuali (VRS), in pratica filtri i componenti in modo che gli utenti possano vedere solo i componenti (dimensioni, metriche, segmenti, intervalli di date) per i progetti o le VRS che vorranno usare.

>[!Note]
>I profili di prodotto sono il meccanismo principale che regola i componenti visibili agli utenti. They are managed through the [Admin Console](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html#createproductprofiles). La cura è un filtro secondario.

L’esperienza di cura è stata recentemente migliorata. Ecco una panoramica di cosa viene mostrato dal pulsante **[!UICONTROL Show All]**(Mostra tutti), oltre ai componenti curati già disponibili, nelle diverse esperienze curate e in base al livello delle autorizzazioni:

| Tipo di cura | Amministratori | Proprietari di progetto non amministratori | Non amministratori |
|---|---|---|---|
| VRS curate | Tutti i componenti VRS non curati | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato | Tutti i componenti di progetto non curati | Tutti i componenti di progetto non curati | I componenti di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato in una VRS curata | Tutti i componenti non curati, visualizzati in **[!UICONTROL Non-Curated Project Components]**e**[!UICONTROL Non-Curated VRS Components]** | Tutti i componenti di progetto non curati E i componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS e di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |

>[!IMPORTANT]
>La cura VRS viene sempre applicata prima della cura del progetto. Ciò significa che anche se il progetto curato include alcuni componenti, questi verranno filtrati se la VRS curata non li include.
