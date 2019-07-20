---
title: Cura di progetti e VRS
seo-title: Cura di progetti e suite di rapporti virtuali in Analysis Workspace
description: Scopri come curare componenti e progetti vrs
seo-description: Cura di VRS e cura di progetti
translation-type: tm+mt
source-git-commit: 0b56838e966aaf4cfa5c2685dd8335adbbbf11a7

---


# Cura di progetti e VRS

Quando curi dei progetti o delle suite di rapporti virtuali (VRS), in pratica filtri i componenti in modo che gli utenti possano vedere solo i componenti (dimensioni, metriche, segmenti, intervalli di date) per i progetti o le VRS che vorranno usare.

>[!Note]
>Le autorizzazioni dei componenti sono il meccanismo principale per gestire i componenti che l'utente può vedere. Sono gestiti tramite Strumenti di amministrazione. La cura è un filtro secondario.

L’esperienza di cura è stata recentemente migliorata. Here is an overview of what the **[!UICONTROL Show All]** button reveals, in addition to the curated components already available, in different curated experiences and by permission level:

| Tipo di cura | Amministratori | Proprietari di progetto non amministratori | Non amministratori |
|---|---|---|---|
| VRS curate | Tutti i componenti VRS non curati | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato | Tutti i componenti di progetto non curati | Tutti i componenti di progetto non curati | I componenti di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato in una VRS curata | Tutti i componenti non curati, visualizzati in **[Componenti per progetti non curati con UICONTROL]** e **[componenti VRS non curati]** | Tutti i componenti del progetto non curati e non specifici per i componenti VRS che questo ruolo detiene o che sono stati condivisi con loro | I componenti VRS e di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |

>[!IMPORTANT]
>La cura VRS viene applicata sempre prima della cura del progetto, quindi anche se il progetto curato include alcuni componenti, questi verranno filtrati se la VRS selezionata non li include.
