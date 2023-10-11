---
description: La cura ti permette di limitare i componenti prima di condividere un progetto.
keywords: Cura di Analysis Workspace
title: Curare progetti
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: 266cf18050d60f08f7e170c56453d1e1d805cb7b
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 63%

---

# Curare progetti

La cura ti consente di limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) prima di condividere un progetto. Quando un destinatario apre il progetto, vedrà un set limitato di componenti che hai curato per lui. La cura è un passaggio facoltativo ma consigliato prima di condividere un progetto.

>[!NOTE]
> I profili di prodotto sono il meccanismo principale per determinare quali componenti può vedere un utente. Vengono gestiti tramite l’Admin Console di Adobe Experience Cloud. La cura è un filtro secondario.

Ecco un video sulla cura e la condivisione dei progetti:

>[!VIDEO](https://video.tv.adobe.com/v/24711/?quality=12)

## Applicare la cura del progetto

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
I componenti utilizzati nel progetto verranno aggiunti automaticamente.
   **Nota**: se un progetto ha più suite di rapporti, visualizzerai un campo curato per ciascuna suite di rapporti presente nel progetto.
1. Per aggiungere altri componenti, trascina i componenti da condividere dalla barra a sinistra al campo [!UICONTROL Curate Components] (facoltativo).
1. Fai clic su **[!UICONTROL Done]**.

È inoltre possibile applicare la cura dal menu [!UICONTROL Share] facendo clic su **[!UICONTROL Curate and Share]**. Questa opzione cura automaticamente il progetto con i componenti in uso nel progetto. Puoi aggiungere altri componenti seguendo la procedura descritta sopra.

![](assets/curation-field.png)

## Vista del progetto curato

Quando un destinatario apre un progetto curato, vedrà solo il set curato di componenti che hai definito:

![](assets/curate-project.png)

## Rimuovere la cura del progetto

Per rimuovere la cura del progetto e ripristinare l’intero set di componenti nella barra a sinistra:

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Fai clic su **[!UICONTROL Remove Curation]** (Crea set di dati).
1. Fai clic su **[!UICONTROL Done]** (Crea set di dati da schema).

## Cura delle suite di rapporti virtuali

Per applicare la cura a livello di suite di rapporti in modo che venga applicata a più progetti contemporaneamente, puoi [curare componenti in una suite di rapporti virtuale](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-components.html?lang=it).

>[!NOTE]
> La cura delle suite di rapporti virtuali viene sempre applicata prima della cura del progetto. Ciò significa che anche se il progetto curato include alcuni componenti, essi verranno filtrati se la suite di rapporti virtuale curata non li include.

## Opzione Show All per mostrare tutti i componenti

In un progetto curato o in una suite di rapporti virtuale, al destinatario verrà offerta l’opzione per **[!UICONTROL Show All]** componenti nella barra a sinistra. [!UICONTROL Show All] mostra diversi set di componenti in base a:

* Livello di autorizzazione dell’utente (amministratore o non amministratore)
* Ruolo di progetto (proprietario/editor o meno)
* Tipo di cura applicata (suite di rapporti virtuali o progetto)
* Componenti di proprietà o condivisi con l’utente. I componenti di proprietà o condivisi includono segmenti, metriche calcolate e intervalli di date. Non includono componenti implementati come eVar, Prop ed eventi personalizzati.

Nota: i ruoli di visualizzazione non amministratori non hanno accesso alla barra a sinistra di un progetto, pertanto sono stati omessi dalla tabella seguente.

| Tipo di cura | Amministratori | Ruolo di proprietario del progetto o editor non amministratore | Ruolo duplicato non amministratore |
|---|---|---|---|
| Suite di rapporti virtuale curata | Tutti i componenti della suite di rapporti virtuali non curati | Componenti della suite di rapporti virtuali non curati di cui è proprietario il ruolo o che sono stati condivisi con il ruolo | Componenti della suite di rapporti virtuali non curati di cui è proprietario il ruolo o che sono stati condivisi con il ruolo |
| Progetto curato | Tutti i componenti di progetto non curati | Tutti i componenti di progetto non curati | I componenti di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato in una suite di rapporti virtuale curata | Tutti i componenti non curati, visualizzati in **[!UICONTROL Non-Curated Project Components]** e **[!UICONTROL Non-Curated Virtual report suite components]** | Tutti i componenti di progetto non curati E i componenti non curati della suite di rapporti virtuali di proprietà o condivisi con il ruolo | Componenti di progetto e suite di rapporti virtuali non curati di cui è proprietario il ruolo o che sono stati condivisi con il ruolo |
