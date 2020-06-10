---
description: La cura consente di limitare i componenti prima di condividere un progetto.
keywords: Analysis Workspace curation
title: Cura progetti Workspace
translation-type: tm+mt
source-git-commit: f7c2a366b409995c1fe790db97de5c708882ab3d
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 41%

---


# Cura progetti Workspace

La cura consente di limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) prima di condividere un progetto. Quando un destinatario apre il progetto, vedrà un set limitato di componenti che avete curato per loro. La cura è un passaggio facoltativo ma consigliato prima di condividere un progetto.

>[!NOTE]
> I profili di prodotto sono il meccanismo principale per determinare quali componenti può vedere un utente. Sono gestite tramite Admin Console. La cura è un filtro secondario.

## Applica cura progetto

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
I componenti utilizzati nel progetto verranno aggiunti automaticamente.
   **Nota**: Se un progetto ha più suite di rapporti, visualizzerai un campo curato per ciascuna suite di rapporti nel progetto.
1. (Facoltativo) Per aggiungere altri componenti, trascinate i componenti da condividere dalla barra a sinistra al [!UICONTROL Curate Components] campo.
1. Fai clic su **[!UICONTROL Done]**.

![](assets/curation-field.png)

Quando un destinatario apre un progetto curato, vedrà solo il set curato di componenti che hai definito:

![](assets/curate-project.png)

È inoltre possibile applicare la cura dal [!UICONTROL Share] menu facendo clic su **[!UICONTROL Curate and Share]**. Questa opzione cura automaticamente il progetto con i componenti in uso nel progetto. Potete aggiungere altri componenti seguendo la procedura descritta sopra.

## Rimuovi cura progetto

Per rimuovere la cura del progetto e ripristinare l’intero set di componenti nella barra a sinistra:
1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Fai clic su **[!UICONTROL Remove Curation]**.
1. Fai clic su **[!UICONTROL Done]**.

## Cura delle suite di rapporti virtuali (VRS)

Per applicare la cura a livello di suite di rapporti, in modo che venga applicata a più progetti contemporaneamente, puoi [curare i componenti in una suite di rapporti virtuale (VRS)](https://docs.adobe.com/content/help/it-IT/analytics/components/virtual-report-suites/vrs-components.html).

>[!NOTE]
> La cura VRS viene sempre applicata prima della cura del progetto. Ciò significa che anche se il progetto curato include alcuni componenti, essi verranno filtrati se la VRS curata non li include.

### Mostra tutti i componenti

In un progetto curato o in una VRS, al destinatario verrà offerta l&#39;opzione per **[!UICONTROL Show All]** i componenti nella barra a sinistra. [!UICONTROL Show All] mostra diversi set di componenti, a seconda:

* il livello di autorizzazione dell&#39;utente (amministratore o non amministratore)
* ruolo progetto (proprietario/editor o meno)
* tipo di cura applicata

| Tipo di cura | Amministratori | Proprietari di progetto non amministratori | Non amministratori |
|---|---|---|---|
| VRS curate | Tutti i componenti VRS non curati | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato | Tutti i componenti di progetto non curati | Tutti i componenti di progetto non curati | I componenti di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato in una VRS curata | Tutti i componenti non curati, visualizzati in  **[!UICONTROL Non-Curated Project Components]** (Componenti di progetto non curati) e **[!UICONTROL Non-Curated VRS Components]** (Componenti VRS non curati) | Tutti i componenti di progetto non curati E i componenti VRS non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti VRS e di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
