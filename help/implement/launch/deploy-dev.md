---
title: Distribuire Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare i tag per distribuire Adobe Analytics nell’ambiente di sviluppo.
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '551'
ht-degree: 6%

---

# Implementazione di Analytics in un ambiente di sviluppo

Dopo aver creato e configurato una proprietà tag, le librerie sono pronte per essere distribuite e il codice implementato sul sito.

## Prerequisiti

[Crea e configura una proprietà tag per Adobe Analytics](create-analytics-property.md): accedi allo strumento e crea uno spazio per l&#39;implementazione di Analytics.

## Creare adattatori e ambienti

I tag consentono di gestire molti flussi di lavoro organizzativi durante la distribuzione del codice. Per creare i componenti minimi necessari per un’implementazione di Analytics, segui la procedura riportata di seguito. In qualità di amministratore di tag, puoi lavorare all’interno della tua organizzazione per stabilire il flusso di lavoro corretto per la distribuzione di soluzioni Adobe.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fai clic su **[!UICONTROL Hosts]**, quindi su **[!UICONTROL Add Host]**.
4. Denominarlo `"Adobe managed"` e selezionare **[!UICONTROL Managed by Adobe]** nell&#39;elenco a discesa Tipo. Fai clic su Salva.
5. Passare a **[!UICONTROL Environments]**, quindi fare clic su **[!UICONTROL Add Environment]**.
6. Selezionare **[!UICONTROL Development]**, denominarlo `"Dev Environment"`, quindi selezionare l&#39;Adobe di host gestito dall&#39;elenco a discesa. Fai clic su **[!UICONTROL Save]**.
7. Viene visualizzata una finestra modale con le istruzioni di installazione Web. Torneremo a questa finestra in un secondo momento; per ora fai clic su **[!UICONTROL Close]**.
8. Fare clic su **[!UICONTROL Add Environment]**, selezionare **[!UICONTROL Staging]**, denominarlo `"Staging Environment"`, quindi selezionare l&#39;Adobe di host gestito. Fare clic su **[!UICONTROL Create]**, quindi chiudere la finestra modale delle istruzioni di installazione.
9. Fare di nuovo clic su **[!UICONTROL Add Environment]**, selezionare **[!UICONTROL Production]**, denominarlo `"Production Environment"`, quindi selezionare l&#39;host gestito dell&#39;Adobe. Fare clic su **[!UICONTROL Create]**, quindi chiudere la finestra modale delle istruzioni di installazione.

## Creare una libreria di sviluppo

Nonostante tutte le modifiche e le configurazioni apportate finora, non è stato effettivamente pubblicato alcun codice. La creazione di una libreria, tradotta approssimativamente come una raccolta di modifiche, consente la pubblicazione di codice da utilizzare sul sito.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fare clic sulla scheda **[!UICONTROL Publishing Flow]**, quindi su **[!UICONTROL Add Library]**. Per ulteriori informazioni su questa pagina, consulta [Panoramica sulla pubblicazione](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=it) nella documentazione dei tag.
4. Assegnare un nome alla libreria `'Initial changes'` e selezionare l&#39;ambiente di sviluppo.
5. Fai clic su **[!UICONTROL Add All Changed Resources]**, che elenca automaticamente Adobe Analytics, Identity Service e Core.
6. Fai clic su **[!UICONTROL Save]**.
7. Tornando alla schermata del flusso di lavoro di pubblicazione, fare clic sull&#39;elenco a discesa accanto alla nuova raccolta e quindi fare clic su **[!UICONTROL Build for Development]**. Dopo alcuni secondi, il punto giallo sulla libreria diventa verde, a indicare che la build è stata eseguita correttamente.
8. Passa a **[!UICONTROL Environments]**, quindi fai clic sull&#39;icona Installa a destra dell&#39;ambiente di sviluppo. Questa azione apre nuovamente la finestra modale Istruzioni di installazione Web.
9. Copia i blocchi di codice e forniscili ai proprietari del sito web della tua organizzazione.

## Installare i tag nell’ambiente di sviluppo del sito web

Se controlli il codice del sito web, implementa ogni blocco di codice nella rispettiva posizione:

* Il tag principale appartiene al tag `<head>` sul tuo sito.
* Se scegli di caricare i tag in modo sincrono, devi includere anche un secondo blocco di codice appena sotto il tag di chiusura `</body>` sul sito. È possibile scegliere di caricare i tag della libreria in modo sincrono impostando l&#39;opzione **[!UICONTROL Load Library Asynchronously]** nelle istruzioni di installazione Web.

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

**Tentativo di compilazione non riuscito.**

Un motivo comune è che gli elementi esistono già in altre librerie inviate allo staging o alla produzione. Durante la creazione iniziale delle librerie, accertati che solo le risorse modificate vengano aggiunte alla libreria.

## Passaggi successivi

[Convalida l&#39;implementazione di Analytics e pubblica in produzione](validate-publish-prod.md): inizia a trarre valore da Adobe Analytics.
