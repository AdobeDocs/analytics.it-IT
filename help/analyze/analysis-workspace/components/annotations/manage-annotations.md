---
title: Gestire le annotazioni
description: Come gestire le annotazioni in Workspace.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 4f0bd39b64535be8ba55e97d65177f6ef291ef6c
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 60%

---

# Gestire le annotazioni

Il [!UICONTROL Annotations manager] mostra tutte le annotazioni di tua proprietà o che sono state condivise con te. Le annotazioni specifiche del progetto non vengono visualizzate qui. Puoi utilizzare questa interfaccia per condividere, filtrare, assegnare tag, copiare, eliminare e impostare come preferite le annotazioni. Gli amministratori possono gestire e approvare le annotazioni.

**[!UICONTROL Components]** > **[!UICONTROL Annotations]**

## Interfaccia utente di Annotations Manager (Gestione annotazioni)

![](assets/annotation-mgr.png)

| Elemento nell’interfaccia utente | Descrizione |
| --- | --- | 
| [!UICONTROL Title and Description] | Forniti nel generatore di annotazioni. Per modificare il titolo e la descrizione, fai clic sul collegamento del titolo, che ti riporta al generatore di annotazioni. |
| [!UICONTROL Report Suite] | Le suite di rapporti a cui si applica questa annotazione. |
| [!UICONTROL Owner] | Proprietario dell’annotazione. In quanto utente non amministratore, puoi visualizzare solo le annotazioni che possiedi o quelle che sono state condivise con te. |
| [!UICONTROL Applied Date Range] | Data o intervallo di date a cui viene applicata l’annotazione. |
| [!UICONTROL Shared with] | Elenca con quanti singoli utenti o gruppi hai condiviso l’annotazione. Fai clic per ulteriori dettagli. |
| [!UICONTROL Date Modified] | Data e ora dell’ultima modifica apportata all’annotazione. |

{style="table-layout:auto"}

## Modificare le annotazioni

La modifica di un’annotazione consente di regolare intervalli di date, colori, ambito o se questa si applica a tutte le suite di rapporti o a tutti i progetti. È possibile modificare le annotazioni in due modi:

* In un grafico a linee, porta il cursore sull’annotazione e fai clic sull’icona a forma di matita nella finestra a comparsa.
* In [!UICONTROL Annotations Manager], fai clic sul titolo dell’annotazione.

Entrambe queste opzioni consentono di tornare al [!UICONTROL Annotations Builder]. Da qui è possibile apportare le modifiche necessarie e salvare la nuova versione.

## Condividere le annotazioni

Quando condividi delle annotazioni o usi quelle che sono state condivise con te, tieni presente quanto segue:

* Se crei un progetto con annotazioni solo progetto e lo condividi con un altro utente, le annotazioni non possono essere modificate o eliminate dagli utenti con cui condividi il progetto.
* Se salvi un’annotazione e la condividi direttamente con un utente, questa può essere modificata o eliminata solo se l’utente dispone dei diritti di amministratore.
* Se un progetto viene condiviso con te con un’annotazione relativa al solo progetto, questa viene visualizzata solo in quel progetto. Se l’annotazione viene condivisa direttamente con te, viene visualizzata in tutti i progetti in cui è possibile visualizzarla.

## Annotazioni e fusi orari

Tutte le annotazioni vengono create con una marca temporale, ma non con informazioni sul fuso orario o sulle ore. Al momento del rapporto, viene sempre applicato il fuso orario della suite di rapporti del pannello. Ad esempio, un’annotazione creata per Natale si verifica il 25 dicembre, indipendentemente dal fuso orario della suite di rapporti in cui ti trovi.

## Altre attività di annotazione

La funzione di gestione delle annotazioni consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le annotazioni. questa funzione non è visibile agli utenti non amministratori.

Quando selezioni almeno un’annotazione sono disponibili opzioni aggiuntive:

| Attività | Descrizione |
| --- | --- |
| [!UICONTROL Add] | Consente di accedere al generatore Annotazioni per creare annotazioni. |
| [!UICONTROL Tag] | Tutti gli utenti possono creare tag per le annotazioni e applicarne uno o più a una annotazione. Tuttavia, puoi visualizzare solo i tag per le annotazioni di tua proprietà. |
| [!UICONTROL Delete] | L’eliminazione di un’annotazione ne comporta la rimozione da qualsiasi progetto dell’organizzazione. |
| [!UICONTROL Rename] | La ridenominazione di un’annotazione ne comporta la rinomina in tutti i progetti a cui è stata applicata. |
| [!UICONTROL Copy] | Crea una copia distinta con il proprio ID di annotazione, ma con nome e definizione uguali. |
| [!UICONTROL Export to CSV] | Esporta la definizione dell’annotazione in un file .csv. |
| [!UICONTROL Filter] (barra a sinistra) | Filtra in base a tag, suite di rapporti, proprietari e altri filtri (Personali, Approvati, Preferiti, Condivisi con me e Mostra tutto). |

{style="table-layout:auto"}
