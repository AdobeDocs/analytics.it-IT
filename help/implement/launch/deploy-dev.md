---
title: Distribuire Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare i tag per distribuire Adobe Analytics nel tuo ambiente di sviluppo.
feature: Launch Implementation
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 8%

---

# Distribuire un&#39;implementazione di Analytics in un ambiente di sviluppo

Dopo aver creato e configurato una proprietà tag, le librerie sono pronte per essere distribuite e implementate il codice sul sito.

## Prerequisiti

[Creare e configurare una proprietà tag per Adobe Analytics](create-analytics-property.md): Accedi allo strumento e crea uno spazio per la tua implementazione di Analytics.

## Creare adattatori e ambienti

I tag consentono di gestire molti flussi di lavoro organizzativi durante la distribuzione del codice. Segui questi passaggi per creare i componenti minimi necessari per un’implementazione di Analytics. In qualità di amministratore dei tag, puoi lavorare all’interno della tua organizzazione per stabilire il flusso di lavoro corretto per la distribuzione delle soluzioni Adobe.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fai clic su **[!UICONTROL Hosts]**, quindi su **[!UICONTROL Add Host]**.
4. Denomina `"Adobe managed"`, quindi seleziona **[!UICONTROL Managed by Adobe]** nell’elenco a discesa tipo . Fai clic su Salva.
5. Passa a **[!UICONTROL Environments]**, quindi fai clic su **[!UICONTROL Add Environment]**.
6. Seleziona **[!UICONTROL Development]**, denomina `"Dev Environment"`, quindi seleziona l’host gestito di Adobe dall’elenco a discesa. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).
7. Viene visualizzata una finestra modale che mostra le istruzioni di installazione Web. Torneremo a questa finestra in un secondo momento; click **[!UICONTROL Close]** per ora.
8. Fai clic su **[!UICONTROL Add Environment]**, seleziona **[!UICONTROL Staging]**, denomina `"Staging Environment"`, quindi seleziona l’host gestito di Adobe. Fai clic su **[!UICONTROL Create]**, quindi chiudi la finestra modale delle istruzioni di installazione.
9. Fai clic su **[!UICONTROL Add Environment]** di nuovo, seleziona **[!UICONTROL Production]**, denomina `"Production Environment"`, quindi seleziona l’host gestito di Adobe. Fai clic su **[!UICONTROL Create]**, quindi chiudi la finestra modale delle istruzioni di installazione.

## Creare una libreria di sviluppo

Nonostante tutte le modifiche e le configurazioni apportate finora, non è stato pubblicato alcun codice. La creazione di una libreria, tradotta approssimativamente come una raccolta di modifiche, consente di utilizzare la pubblicazione del codice sul sito.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fai clic sul pulsante **[!UICONTROL Publishing Flow]** scheda , quindi fai clic su **[!UICONTROL Add Library]**. Vedi [Panoramica sulla pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=it) per ulteriori informazioni su questa pagina, consulta la documentazione sui tag .
4. Assegna un nome alla libreria `'Initial changes'`, quindi seleziona l’ambiente di sviluppo.
5. Fai clic su **[!UICONTROL Add All Changed Resources]**, che elenca automaticamente Adobe Analytics, il servizio Identity e il servizio core.
6. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).
7. Nella schermata del flusso di lavoro di pubblicazione, fai clic sull’elenco a discesa accanto alla nuova libreria e fai clic su **[!UICONTROL Build for Development]**. Dopo alcuni secondi, il punto giallo della libreria diventa verde e indica che la build è stata completata correttamente.
8. Passa a **[!UICONTROL Environments]**, quindi fai clic sull’icona di installazione a destra dell’ambiente di sviluppo. Questa azione riapre la finestra modale Istruzioni di installazione web.
9. Copia i blocchi di codice e forniscili ai proprietari del sito web della tua organizzazione.

## Installare i tag nell’ambiente di sviluppo del sito web

Se controlli il codice del tuo sito web, implementa ogni blocco di codice nella rispettiva posizione:

* Il tag principale appartiene alla `<head>` sul sito.
* Se scegli di caricare i tag in modo sincrono, devi anche includere un secondo blocco di codice appena sotto la chiusura `</body>` sul sito. Puoi scegliere di caricare i tag della libreria in modo sincrono attivando l’ **[!UICONTROL Load Library Asynchronously]** nelle istruzioni di installazione web.

Il codice di tag viene in genere inserito nel modello di panoramica del sito. Una pagina vuota contenente solo codice di implementazione avrà un aspetto simile al seguente:

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

**Il tentativo di creazione non riesce.**

Un motivo comune è che esistono già elementi in altre librerie inviate alla gestione temporanea o alla produzione. Quando crei inizialmente le librerie, assicurati che alla libreria vengano aggiunte solo le risorse modificate .

## Passaggi successivi

[Convalidare l’implementazione di Analytics e pubblicare in produzione](validate-publish-prod.md): Inizia a ottenere valore da Adobe Analytics.
