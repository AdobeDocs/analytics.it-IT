---
title: Cura di progetti e VRS
description: Scopri come curare i componenti e i progetti VRS
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Cura di progetti e VRS

Quando curi dei progetti o delle suite di rapporti virtuali (VRS), in pratica filtri i componenti in modo che gli utenti possano vedere solo i componenti (dimensioni, metriche, segmenti, intervalli di date) per i progetti o le VRS che vorranno usare.

>[!Note]
>Le autorizzazioni dei componenti sono il meccanismo principale che regola i componenti visibili agli utenti. Sono gestiti tramite Strumenti di amministrazione. La cura è un filtro secondario.

L’esperienza di cura è stata recentemente migliorata. Here is an overview of what the **[!UICONTROL Show All]** button reveals, in addition to the curated components already available, in different curated experiences and by permission level:

| Tipo di cura | Amministratori | Proprietari di progetto non amministratori | Non amministratori |
|---|---|---|---|
| VRS curate | Tutti i componenti VRS non curati | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato | Tutti i componenti di progetto non curati | Tutti i componenti di progetto non curati | I componenti di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato in una VRS curata | Tutti i componenti non curati, visualizzati in Componenti **[di progetto non curati]** UICONTROL e componenti VRS non curati **[UICONTROL]** | Tutti i componenti di progetto non curati E i componenti VRS non curati di cui questo ruolo è proprietario o che sono stati condivisi con essi | I componenti VRS e di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |

>[!IMPORTANT]
>La cura VRS viene sempre applicata prima della cura del progetto, pertanto, anche se il progetto curato include alcuni componenti, verranno esclusi se la VRS curata non li include.
