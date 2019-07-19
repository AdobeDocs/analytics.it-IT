---
title: Creare una suite di rapporti
seo-title: Creare una suite di rapporti in Adobe Analytics
description: Creare un contenitore di base per la raccolta di dati in Adobe Analytics.
seo-description: Creare un contenitore di base per la raccolta di dati in Adobe Analytics.
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# Creare una suite di rapporti

Una suite di rapporti è un silo di dati utilizzati da Adobe Analytics per inviare rapporti. Un'organizzazione può avere molte suite di rapporti, ciascuna contenente set di dati diversi. Sebbene in passato fossero importanti le suite di rapporti separate, una singola suite di rapporti diventa più vantaggiosa. L'introduzione alle suite di rapporti virtuali e all'elaborazione dei tempi di report consente all'utente di creare sottoinsiemi personalizzati di dati, consentendo la flessibilità di ottenere dati globali e specifici per il sito.

Questo articolo è progettato per amministratori a livello di sistema o amministratori di analisi per prepararsi alla raccolta di dati.

## Prerequisiti

[Guida per il primo amministratore di Adobe Analytics](first-admin-guide.md): Assicurati che un amministratore a livello di sistema vi abbia concesso l'accesso ad Adobe Analytics tramite l'Admin Console di Experience Cloud

## Creare una suite di rapporti

> [!NOTE]Nota: Esiste inoltre un modo per creare una suite di rapporti in Adobe Analytics utilizzando l'amministratore legacy. Adobe consiglia di utilizzare la procedura guidata di configurazione della suite di rapporti descritta qui.

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. Fai clic sull'icona 9 quadrati in alto a destra, quindi fai clic sul logo di Analytics colorato.
1. Dovresti visualizzare automaticamente una finestra modale «Benvenuti nella finestra modale di Adobe Analytics». In caso contrario, fate clic sull'icona della Guida in alto a destra, quindi selezionate Benvenuti in Adobe Analytics.
1. Nella finestra modale, fate clic su Avvia configurazione.
1. Seguite ogni prompt che delinea le nozioni di base come tipo di proprietà, settore e fuso orario. Fate clic su Avanti.
1. La suite di rapporti è stata creata. Adobe consiglia anche di disporre di una suite di rapporti per la fase di sviluppo, pertanto il test non danneggia i dati dei clienti. Fai clic sull'icona della Guida in alto a destra, quindi seleziona nuovamente Benvenuti in Adobe Analytics.
1. Nella finestra modale, fate clic su Avvia configurazione.
Assegna un nome a questa suite di rapporti, tranne se aggiungi "- DEV" alla fine. Poiché questa suite di rapporti riceverà solo traffico interno, le dimensioni stimate possono essere il più piccolo.
1. Fai clic su Avanti per terminare la creazione della suite di rapporti di sviluppo.

## Risoluzione dei problemi   

**Dopo aver eseguito l'accesso a Experience Cloud, l'icona Analisi è disattivata.**

Ciò significa che al tuo account non sono state assegnate le autorizzazioni corrette ad Analytics. Lavorate con un amministratore a livello di sistema nella vostra organizzazione per fare in modo che apparteniate a un profilo con autorizzazioni adeguate per accedere ad Adobe Analytics.

**Dopo aver eseguito l'accesso ad Adobe Analytics, mancano i popup e il menu a discesa «Benvenuti in Adobe Analytics».**

Assicurati di aver effettuato l'accesso tramite Experience Cloud, non tramite my. omniture. com. L'utente che accede a my.omniture.com non dispone della procedura guidata di configurazione della suite di rapporti.

## Passaggi successivi

[Crea e configura una proprietà per Adobe Analytics in Launch](../../implement/implement-with-launch/create-analytics-property.md): Creare un'area per gestire l'implementazione di Analytics
