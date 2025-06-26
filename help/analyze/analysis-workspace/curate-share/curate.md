---
description: La cura ti permette di limitare i componenti prima di condividere un progetto.
keywords: Cura di Analysis Workspace
title: Curare progetti
feature: Curate and Share
role: User, Admin
exl-id: 5e23be83-586a-4543-9be9-65c631b8b0b7
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 68%

---

# Curare progetti

La cura ti consente di limitare i componenti (dimensioni, metriche, segmenti, intervalli di date) prima di condividere un progetto. Quando un destinatario apre il progetto, visualizza un set limitato di componenti che hai curato per lui. La cura è un passaggio facoltativo ma consigliato prima di condividere un progetto.

>[!NOTE]
> I profili di prodotto sono il meccanismo principale per determinare quali componenti può vedere un utente. Vengono gestiti tramite l’Admin Console di Adobe Experience Cloud. La cura è un filtro secondario.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Cura progetti](https://video.tv.adobe.com/v/329897?quality=12&learn=on&captions=ita){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


## Applicare la cura del progetto

1. Selezionare **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
I componenti utilizzati nel progetto vengono aggiunti automaticamente.
Se un progetto ha più suite di rapporti, puoi visualizzare un target di rilascio per ogni suite di rapporti nel progetto.
1. (Facoltativo) Per aggiungere altri componenti, trascina i componenti da condividere dal pannello di sinistra alla zona di rilascio **[!UICONTROL Curate components]** per la visualizzazione dati.
1. Seleziona **[!UICONTROL Done]**.

È inoltre possibile applicare la cura dal menu [!UICONTROL Share] selezionando **[!UICONTROL Curate and Share]**. Questa opzione cura automaticamente il progetto con i componenti in uso nel progetto. Puoi aggiungere altri componenti seguendo la procedura descritta sopra.

![](assets/curation-field.png)

Quando un destinatario apre un progetto curato, visualizza solo il set curato di componenti che hai definito:


## Rimuovere la cura del progetto

Per rimuovere la cura del progetto e ripristinare l’intero set di componenti nella barra a sinistra:

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Curate Project Data]**.
1. Seleziona **[!UICONTROL Remove Curation]** (Aggiungi set di dati).
1. Seleziona **[!UICONTROL Done]** (Salva).

## Cura delle suite di rapporti virtuali

Per applicare la cura a livello di suite di rapporti in modo che venga applicata a più progetti contemporaneamente, puoi [curare i componenti in una suite di rapporti virtuale](https://experienceleague.adobe.com/it/docs/analytics/components/virtual-report-suites/vrs-components).

>[!NOTE]
>
> La cura delle suite di rapporti virtuali viene sempre applicata prima della cura del progetto. Anche se il progetto curato include alcuni componenti, questi vengono filtrati se la suite di rapporti virtuale curata non include tali componenti.
> 

## Opzioni di cura del componente

In un progetto curato o in una suite di rapporti virtuale, al destinatario viene offerta l&#39;opzione per **[!UICONTROL Show All]** componenti nella barra a sinistra. [!UICONTROL Show All] mostra diversi set di componenti in base a:

* Livello di autorizzazione dell’utente (amministratore o non amministratore)
* Ruolo di progetto (proprietario/editor o meno)
* Tipo di cura applicata (suite di rapporti virtuali o del progetto)
* Componenti di proprietà o condivisi con l’utente. I componenti di proprietà o condivisi includono segmenti, metriche calcolate e intervalli di date. Non includono componenti implementati, come eVar, prop ed eventi personalizzati.

Nota: i ruoli di visualizzazione non amministratori non hanno accesso alla barra a sinistra di un progetto, pertanto sono stati omessi dalla tabella seguente.

| Tipo di cura | Amministratori | Ruolo di proprietario del progetto o editor non amministratore | Ruolo duplicato non amministratore |
|---|---|---|---|
| Suite di rapporti virtuale curata | Tutti i componenti della suite di rapporti virtuale non curata | I componenti della suite di rapporti virtuale non curata di cui è proprietario l’utente con questo ruolo o che sono stati condivisi con l’utente | I componenti della suite di rapporti virtuale non curata di cui è proprietario l’utente con questo ruolo o che sono stati condivisi con l’utente |
| Progetto curato | Tutti i componenti di progetto non curati | Tutti i componenti di progetto non curati | I componenti di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
| Progetto curato in una suite di rapporti virtuale curata | Tutti i componenti non curati, visualizzati in **[!UICONTROL Non-Curated Project Components]** e **[!UICONTROL Non-Curated Virtual report suite components]** | Tutti i componenti di progetto non curati e quelli della suite di rapporti virtuale non curata di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente | I componenti della suite di rapporti virtuale e di progetto non curati di cui è proprietario l’utente con questo ruolo e che sono stati condivisi con l’utente |
