---
title: Gestire le annotazioni
description: Come gestire le annotazioni in Workspace.
role: User, Admin
feature: Annotations
exl-id: 37a538cc-9ea7-4cb1-8ee8-e8e474ad5b08
source-git-commit: 20ab0e9728969c4cc11227a1255e41e3d1a1540f
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 100%

---

# Gestire le annotazioni

Il gestore [!UICONTROL Components] > [!UICONTROL Annotations] offre diversi modi per gestire le annotazioni, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferite.

Il gestore [!UICONTROL Annotations] mostra tutte le annotazioni di cui sei proprietario che sono state assegnate a tutti i tuoi progetti e che sono state condivise con te.

>[!NOTE]
>
>Non vengono invece visualizzate le [!UICONTROL Annotations] che hai creato solo per un progetto specifico.

## Interfaccia utente di Annotations Manager (Gestione annotazioni)

![](assets/annotation-mgr.png)

| Elemento nell’interfaccia utente | Descrizione |
| --- | --- | 
| [!UICONTROL Title and Description] | Forniti nel generatore di annotazioni. Per modificare il titolo e la descrizione, fai clic sul collegamento del titolo, che ti riporta al generatore di annotazioni. |
| [!UICONTROL Report Suite] | Le suite di rapporti a cui viene applicata l’annotazione. |
| [!UICONTROL Owner] | Proprietario dell’annotazione. In quanto utente non amministratore, puoi visualizzare solo le annotazioni che possiedi o quelle che sono state condivise con te. |
| [!UICONTROL Applied Date Range] | Data o intervallo di date a cui viene applicata l’annotazione. |
| [!UICONTROL Shared with] | Elenca con quanti singoli utenti o gruppi hai condiviso l’annotazione. Fai clic per ulteriori dettagli. |
| [!UICONTROL Date Modified] | Data e ora dell’ultima modifica apportata all’annotazione. |

{style="table-layout:auto"}

## Modificare le annotazioni

La modifica di un’annotazione consente di regolare gli intervalli di date, i colori, l’ambito o se deve essere applicata o meno a tutte le suite di rapporti o a tutti i progetti. È possibile modificare le annotazioni in due modi:

* In un grafico a linee, porta il cursore sull’annotazione e fai clic sull’icona a forma di matita nella finestra a comparsa.

* In [!UICONTROL Annotations Manager], fai clic sul titolo dell’annotazione.

Entrambe queste opzioni consentono di tornare al [!UICONTROL Annotations Builder]. Da qui è possibile apportare le modifiche necessarie e salvare la nuova versione.

## Condividere le annotazioni

Quando condividi delle annotazioni o usi quelle che sono state condivise con te, tieni presente quanto segue:

* Supponiamo che crei un progetto con annotazioni per il solo progetto, e quindi lo condividi con un altro utente. Le annotazioni verranno visualizzate, ma non possono essere modificate o eliminate dagli utenti con cui condividi il progetto.

* Se salvi un’annotazione e la condividi direttamente con un utente, questa può essere modificata o eliminata solo se l’utente dispone dei diritti di amministratore.

* Per ricapitolare: se il progetto è condiviso con te, l’annotazione viene visualizzata solo in quel determinato progetto. Se l’annotazione viene condivisa direttamente con te, viene visualizzata in tutti i progetti in cui è possibile visualizzarla.

## Annotazioni e fusi orari

Tutte le annotazioni vengono create con una marca temporale, ma non con informazioni sul fuso orario o sulle ore. Al momento del rapporto, viene sempre applicato il fuso orario della suite di rapporti del pannello. Quindi un’annotazione creata per il giorno di Natale si attiva il 25 dicembre, indipendentemente dal fuso orario della suite di rapporti in cui ti trovi.

Un altro esempio è Capodanno. Ogni ora, in un fuso orario diverso iniziano i fuochi d’artificio per festeggiare il nuovo anno. Alle 22:00 US Mountain Time, sulla costa orientale degli Stati Uniti è già mezzanotte e iniziano i fuochi d’artificio.

## Altre attività di annotazione

La funzione di gestione delle annotazioni consente agli amministratori di modificare, aggiungere, assegnare tag, eliminare, rinominare, approvare, copiare, esportare e filtrare le annotazioni. questa funzione non è visibile agli utenti non amministratori.

Quando selezioni una o più annotazioni, viene visualizzata la barra delle attività.

| Attività | Descrizione |
| --- | --- |
| [!UICONTROL Add] | Consente di accedere al generatore di Annotazioni da dove è possibile creare nuove annotazioni. |
| [!UICONTROL Tag] | Tutti gli utenti possono creare tag per le annotazioni e applicarne uno o più a una singola annotazione. È tuttavia possibile visualizzare solo i tag delle annotazioni di tua proprietà. Che tipo di tag è utile creare? Di seguito sono riportati alcuni suggerimenti di tag utili:<ul><li>Tag basati sui nomi dei team, ad esempio Social Marketing e Mobile Marketing</li><li>Tag del progetto (tag di analisi), ad esempio Analisi per pagina di ingresso</li><li>Tag di categorie: uomo; geografia</li><li>Tag del flusso di lavoro: curato per (una specifica unità operativa); approvato</li></ul> |
| [!UICONTROL Delete] | L’eliminazione di un’annotazione ne comporta la rimozione da qualsiasi progetto dell’organizzazione. |
| [!UICONTROL Rename] | La ridenominazione di un’annotazione ne comporta la rinomina in tutti i progetti a cui è stata applicata. |
| [!UICONTROL Copy] | Crea una copia distinta con il proprio ID di annotazione, ma con nome e definizione uguali. |
| [!UICONTROL Export to CSV] | Esporta la definizione dell’annotazione in un file .csv. |
| [!UICONTROL Filter] (barra a sinistra) | Filtra in base a tag, suite di rapporti, proprietari e altri filtri (Personali, Approvati, Preferiti, Condivisi con me e Mostra tutto). |

{style="table-layout:auto"}
