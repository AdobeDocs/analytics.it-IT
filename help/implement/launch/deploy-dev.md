---
title: Distribuire Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare Adobe Experience Platform Launch per distribuire Adobe Analytics nell’ambiente di sviluppo.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 2%

---

# Distribuire un&#39;implementazione di Analytics in un ambiente di sviluppo

Una volta creata e configurata una proprietà in Launch, le librerie sono pronte per essere distribuite e il codice implementato sul sito.

## Prerequisiti

[Crea e configura una proprietà per Adobe Analytics in Launch](create-analytics-property.md): Accedi allo strumento e crea uno spazio per la tua implementazione di Analytics.

## Creare adattatori e ambienti

Launch gestisce molti flussi di lavoro organizzativi nella distribuzione del codice. Segui questi passaggi per creare i componenti minimi necessari per un’implementazione di Analytics. In qualità di amministratore di Launch, puoi lavorare all’interno della tua organizzazione per stabilire il flusso di lavoro corretto per la distribuzione delle soluzioni Adobe.

1. Vai a [Adobe Experience Platform Launch](https://launch.adobe.com) e, se richiesto, accedi.
2. Fai clic sulla proprietà Launch che intendi implementare sul tuo sito.
3. Fare clic sulla scheda Adattatori, quindi fare clic su Aggiungi adattatore.
4. Denomina &quot;Akamai&quot; e seleziona Akamai nel menu a discesa del tipo . Fai clic su Salva.
5. Passa alla scheda Ambienti , quindi fai clic su Crea nuovo ambiente .
6. Seleziona Sviluppo, denominalo &quot;Ambiente di sviluppo&quot;, quindi seleziona l’adattatore Akamai dal menu a discesa. Fare clic su Crea, quindi su Chiudi.
7. Fai clic su Aggiungi ambiente, seleziona Staging, denominalo &quot;Staging Environment&quot;, quindi seleziona l&#39;adattatore Akamai. Fare clic su Crea, quindi su Chiudi.
8. Fai di nuovo clic su Aggiungi ambiente , seleziona Produzione, denominalo &quot;Ambiente produzione&quot;, quindi seleziona la scheda Akamai. Fare clic su Crea, quindi su Chiudi.

## Creare una libreria di sviluppo

Nonostante tutte le modifiche e le configurazioni apportate finora, non è stato pubblicato alcun codice. La creazione di una libreria, tradotta approssimativamente come una raccolta di modifiche, consente di utilizzare la pubblicazione del codice sul sito.

1. Vai a [Adobe Experience Platform Launch](https://launch.adobe.com) e, se richiesto, accedi.
2. Fai clic sulla proprietà Launch che intendi implementare sul tuo sito.
3. Fai clic sulla scheda Pubblicazione , quindi su Aggiungi nuova libreria .
4. Denomina la libreria &quot;Modifiche iniziali&quot; e seleziona l&#39;ambiente di sviluppo.
5. Fai clic su Aggiungi tutte le risorse modificate , che elenca automaticamente Adobe Analytics, il servizio Identity e il servizio core.
6. Fai clic su Salva.
7. Nella schermata del flusso di lavoro di pubblicazione, fai clic sul menu a discesa accanto alla nuova libreria e fai clic su Genera per lo sviluppo. Dopo alcuni secondi, il punto giallo della libreria diventa verde e indica che la build è stata completata correttamente.
8. Vai alla scheda Ambienti , quindi fai clic sul tuo ambiente di sviluppo.
9. In &quot;Installa Launch&quot;, copia i blocchi di codice e forniscili ai proprietari del sito web dell’organizzazione.

## Installare Launch nell’ambiente di sviluppo del sito web

Se controlli il codice del tuo sito web, implementa i due blocchi di codice nelle rispettive posizioni (nel tag `<head>` e appena sopra il tag di chiusura `</body>` ) su ogni pagina del sito. Questo codice viene comunemente inserito nel modello di panoramica del sito. Una pagina vuota contenente solo codice di implementazione avrà un aspetto simile al seguente:

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
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Risoluzione dei problemi

**Il tentativo di creazione non riesce.**

Un motivo comune è che esistono già elementi in altre librerie inviate alla gestione temporanea o alla produzione. Quando crei inizialmente le librerie, assicurati che alla libreria vengano aggiunte solo le risorse modificate .

## Documentazione e risorse aggiuntive

- [Guida introduttiva a Launch](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html): Scopri il flusso di lavoro di base di Launch
- [Pubblicazione](https://experienceleague.adobe.com/docs/launch/using/reference/publish/overview.html) Launch: Ulteriori informazioni sulla pubblicazione e sugli ambienti

## Passaggi successivi

[Convalida l’implementazione di Analytics e pubblica in produzione](validate-publish-prod.md): Inizia a ottenere valore da Adobe Analytics.
