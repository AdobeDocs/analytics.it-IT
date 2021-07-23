---
title: Acquisire i termini di ricerca interni
description: Utilizza una variabile personalizzata per acquisire i termini di ricerca interna.
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---


# Acquisire i termini di ricerca interni

Il reporting di ricerca interna è integrale per molte organizzazioni e non è una dimensione preconfigurata con Adobe Analytics. Tuttavia, con il minimo sforzo di implementazione, è possibile acquisire facilmente la generazione di rapporti per i termini di ricerca interni.

## Prerequisiti

[Convalida un&#39;implementazione di sviluppo e pubblica in produzione](../launch/validate-publish-prod.md): Questa pagina presuppone che tu disponga di un&#39;implementazione di lavoro di base e che tu veda una richiesta di immagine Adobe Analytics nel debugger di Adobe.

## Creare un eVar per adattarsi alla ricerca interna

Segui [Amministratore variabili di conversione](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) per creare un nuovo eVar dedicato alla ricerca interna. Assegna all&#39;eVar un nome facilmente riconoscibile (ad esempio &quot;Termine di ricerca interno&quot;) e registra il nuovo eVar nel [documento di progettazione della soluzione](../prepare/solution-design.md) della tua organizzazione.

## Determinare la parola chiave di ricerca interna

La maggior parte delle ricerche interne utilizza stringhe di query per trasmettere dati di parole chiave tra le pagine. Utilizza la ricerca interna del tuo sito e osserva l’URL nella pagina dei risultati della ricerca:

`https://example.com/search.html?q=kittens`

Se la ricerca interna del sito non utilizza l’URL, cerca il termine di ricerca in altre posizioni, ad esempio un livello di dati o un cookie. Collabora con il team di sviluppo del sito se non sei sicuro di dove trovare il termine di ricerca interno.

## Assegnare il parametro della stringa di query a un elemento dati

Segui [Mappatura di oggetti livello dati su elementi dati](../launch/layer-to-elements.md). Quando selezioni **[!UICONTROL Data Element Type]**, seleziona **[!UICONTROL Query string parameter]** invece di **[!UICONTROL JavaScript Variable]**. Inserisci il parametro della stringa di query desiderato (in genere `q`) nel campo di testo.

## Mappa l’elemento dati su eVar

Segui [Mappa gli elementi dati sulle variabili Analytics](../launch/elements-to-variable.md). Assicurati di selezionare lo stesso eVar creato nelle impostazioni della suite di rapporti.

## Avvia la distribuzione dei tag

Segui [Implementare un&#39;implementazione di Analytics in un ambiente di sviluppo](../launch/deploy-dev.md). Dopo aver confermato il funzionamento nell&#39;ambiente di sviluppo, puoi [Convalidare un&#39;implementazione di sviluppo e pubblicare in produzione](../launch/validate-publish-prod.md).

## Generazione di rapporti in Workspace

Dai un po&#39; di tempo alla tua implementazione per raccogliere i dati, quindi puoi iniziare a utilizzare la dimensione in Analysis Workspace.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali AdobeID.
2. Se non hai effettuato l’accesso automatico ad Adobe Analytics, fai clic sull’icona a 9 griglie in alto a destra e seleziona **[!UICONTROL Analytics]**.
3. Fai clic sulla scheda **[!UICONTROL Workspace]** e crea un nuovo progetto.
4. Individua il nome dell’eVar creato in Dimension e trascinalo nell’area di lavoro.
