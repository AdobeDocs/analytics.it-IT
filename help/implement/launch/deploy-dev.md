---
title: Distribuire Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare i tag per distribuire Adobe Analytics nell’ambiente di sviluppo.
feature: Launch Implementation
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 8%

---

# Implementazione di Analytics in un ambiente di sviluppo

Dopo aver creato e configurato una proprietà tag, le librerie sono pronte per essere distribuite e il codice implementato sul sito.

## Prerequisiti

[Creare e configurare una proprietà tag per Adobe Analytics](create-analytics-property.md): accedi allo strumento e crea uno spazio per l’implementazione di Analytics.

## Creare adattatori e ambienti

I tag consentono di gestire molti flussi di lavoro organizzativi durante la distribuzione del codice. Per creare i componenti minimi necessari per un’implementazione di Analytics, segui la procedura riportata di seguito. In qualità di amministratore di tag, puoi lavorare all’interno della tua organizzazione per stabilire il flusso di lavoro corretto per la distribuzione di soluzioni Adobe.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fai clic su **[!UICONTROL Hosts]**, quindi su **[!UICONTROL Add Host]**.
4. Assegna un nome `"Adobe managed"`, e seleziona **[!UICONTROL Managed by Adobe]** nel menu a discesa tipo. Fai clic su Salva.
5. Accedi a **[!UICONTROL Environments]**, quindi fai clic su **[!UICONTROL Add Environment]**.
6. Seleziona **[!UICONTROL Development]**, denominalo `"Dev Environment"`, quindi seleziona l’host gestito dell’Adobe dal menu a discesa. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).
7. Viene visualizzata una finestra modale con le istruzioni di installazione Web. Torneremo a questa finestra in un secondo momento; fai clic su **[!UICONTROL Close]** per ora.
8. Clic **[!UICONTROL Add Environment]**, seleziona **[!UICONTROL Staging]**, denominalo `"Staging Environment"`, quindi seleziona l’host gestito dell’Adobe. Clic **[!UICONTROL Create]**, quindi chiudere la finestra modale di istruzioni di installazione.
9. Clic **[!UICONTROL Add Environment]** di nuovo, seleziona **[!UICONTROL Production]**, denominalo `"Production Environment"`, quindi seleziona l’host gestito dell’Adobe. Clic **[!UICONTROL Create]**, quindi chiudere la finestra modale di istruzioni di installazione.

## Creare una libreria di sviluppo

Nonostante tutte le modifiche e le configurazioni apportate finora, non è stato effettivamente pubblicato alcun codice. La creazione di una libreria, tradotta approssimativamente come una raccolta di modifiche, consente la pubblicazione di codice da utilizzare sul sito.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fai clic su **[!UICONTROL Publishing Flow]** , quindi fai clic su **[!UICONTROL Add Library]**. Consulta [Panoramica sulla pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=it) nella documentazione sui tag per ulteriori informazioni su questa pagina.
4. Denomina la libreria `'Initial changes'`e seleziona il tuo ambiente di sviluppo.
5. Clic **[!UICONTROL Add All Changed Resources]**, che elenca automaticamente Adobe Analytics, Identity Service e Core.
6. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).
7. Torna alla schermata del flusso di lavoro di pubblicazione, fai clic sul menu a discesa accanto alla nuova libreria e fai clic su **[!UICONTROL Build for Development]**. Dopo alcuni secondi, il punto giallo sulla libreria diventa verde, a indicare che la build è stata eseguita correttamente.
8. Accedi a **[!UICONTROL Environments]**, quindi fai clic sull’icona installa a destra dell’ambiente di sviluppo. Questa azione apre nuovamente la finestra modale Istruzioni di installazione Web.
9. Copia i blocchi di codice e forniscili ai proprietari del sito web della tua organizzazione.

## Installare i tag nell’ambiente di sviluppo del sito web

Se controlli il codice del sito web, implementa ogni blocco di codice nella rispettiva posizione:

* Il tag principale appartiene al `<head>` sul sito.
* Se scegli di caricare i tag in modo sincrono, devi includere anche un secondo blocco di codice appena sotto il tag di chiusura `</body>` sul sito. Puoi scegliere di caricare i tag della libreria in modo sincrono attivando/disattivando **[!UICONTROL Load Library Asynchronously]** nelle istruzioni di installazione Web.

Il codice di tag viene in genere inserito nel modello generale del sito. Una pagina vuota contenente solo il codice di implementazione avrà l&#39;aspetto seguente:

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Risoluzione dei problemi

**Tentativo di generazione non riuscito.**

Un motivo comune è che gli elementi esistono già in altre librerie inviate allo staging o alla produzione. Durante la creazione iniziale delle librerie, accertati che solo le risorse modificate vengano aggiunte alla libreria.

## Passaggi successivi

[Convalidare l’implementazione di Analytics e pubblicare in produzione](validate-publish-prod.md): inizia a ottenere valore da Adobe Analytics.
