---
title: Creare una suite di rapporti
description: Creare un contenitore di base per la raccolta dei dati in  Adobe Analytics.
translation-type: tm+mt
source-git-commit: 6efb60ae2f565e67426c78bf830ada655e29b3af
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 9%

---


# Creare una suite di rapporti

Una suite di rapporti è un silo di dati che  Adobe Analytics utilizza per estrarre i rapporti. Un&#39;organizzazione può disporre di numerose suite di rapporti, ciascuna delle quali contiene set di dati diversi. Sebbene in passato fossero importanti suite di rapporti separate, avere una singola suite di rapporti è diventato più vantaggioso. L&#39;introduzione alle suite di rapporti virtuali e l&#39;elaborazione dei tempi di rapporto consente all&#39;utente di creare sottoinsiemi di dati personali, consentendo la flessibilità di ottenere sia dati globali che specifici per il sito.

Questo articolo è progettato per amministratori di sistema o amministratori di analisi per prepararsi alla raccolta dei dati.

## Prerequisiti

[Adobe Analytics First Admin Guide](first-admin-guide.md): Assicurati che un amministratore a livello di sistema ti abbia concesso l’accesso a  Adobe Analytics tramite il Experience Cloud   Admin Console

## Creare una suite di rapporti {#create-report-suite}

>[!NOTE]
>
>È inoltre possibile creare una suite di rapporti in  Adobe Analytics utilizzando l&#39;amministratore legacy.  Adobe consiglia di utilizzare la procedura guidata di configurazione della suite di rapporti descritta qui.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
1. Viene visualizzata automaticamente una finestra modale &quot;Benvenuti  Adobe Analytics&quot;. In caso contrario, fate clic sull&#39;icona della guida in alto a destra, quindi selezionate &quot;Benvenuti  Adobe Analytics&quot;.
1. Nella finestra modale, fate clic su Avvia impostazione.
1. Seguite ogni prompt che illustra le nozioni di base come tipo di proprietà, settori e fuso orario. Fai clic su Avanti.
1. La suite di rapporti ora viene creata.  Adobe consiglia anche di disporre di una suite di rapporti per lo sviluppo, pertanto il test non tinge i dati dei clienti. Fate clic sull&#39;icona della guida in alto a destra, quindi selezionate nuovamente Benvenuti  Adobe Analytics.
1. Nella finestra modale, fate clic su Avvia impostazione.
Denominate la suite di rapporti allo stesso modo, tranne l&#39;aggiunta di &quot;- DEV&quot; alla fine. Poiché questa suite di rapporti riceve solo traffico interno, la dimensione stimata può essere la più piccola.
1. Fai clic su Avanti per completare la creazione della suite di rapporti dev.

Per ulteriori informazioni sui passaggi descritti in questa finestra modale, consulta [Implementazione modale](/help/implement/prepare/implementation-modal.md) nella guida per l’utente Implementa.

## Risoluzione dei problemi

**Dopo aver effettuato l&#39;accesso al Experience Cloud , l&#39;icona Analytics è disattivata.**

Ciò significa che al tuo account non sono state concesse le autorizzazioni corrette per Analytics. Consultate un amministratore a livello di sistema nella vostra organizzazione per assicurarvi di appartenere a un profilo con autorizzazioni adeguate per accedere  Adobe Analytics.

**Dopo aver effettuato l&#39;accesso a  Adobe Analytics, il menu a comparsa e il menu a discesa &#39;Benvenuti  Adobe Analytics&#39; risulta mancante.**

Assicurati di aver effettuato l’accesso tramite l’Experience Cloud  e non tramite my.omniture.com. L&#39;utente che accede tramite my.omniture.com non dispone della procedura guidata di configurazione della suite di rapporti.

## Passaggi successivi

[Crea e configura una proprietà per  Adobe Analytics in Launch](/help/implement/launch/create-analytics-property.md): Creare un&#39;area per gestire l&#39;implementazione di Analytics
