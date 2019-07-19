---
title: Implementare Adobe Analytics in un ambiente di sviluppo
seo-title: Implementare Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare Adobe Experience Platform Launch per distribuire Adobe Analytics nell'ambiente di sviluppo.
seo-description: Scopri come utilizzare Adobe Experience Platform Launch per distribuire Adobe Analytics nell'ambiente di sviluppo.
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Implementare un'implementazione di Analytics in un ambiente di sviluppo

Una volta creata e configurata una proprietà in Launch, le librerie sono pronte per essere distribuite e codice implementate sul sito.

## Prerequisiti

[Crea e configura una proprietà per Adobe Analytics in Launch](create-analytics-property.md): Accedi allo strumento e crea uno spazio per l'implementazione di Analytics.

## Creare adattatori e ambienti

Launch include molti flussi di lavoro organizzativi nella distribuzione del codice. Segui questi passaggi per creare i componenti minimi necessari per un'implementazione Analytics. In qualità di amministratore di Launch, puoi lavorare all'interno della tua organizzazione per stabilire il flusso di lavoro corretto per la distribuzione delle soluzioni Adobe.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Fate clic sulla proprietà Launch che intendete implementare sul sito.
3. Fate clic sulla scheda Adattatori, quindi su Aggiungi adattatore.
4. Denomina «Akamai», quindi seleziona Akamai nel menu a discesa Tipo. Fate clic su Salva.
5. Passate alla scheda Ambienti, quindi fate clic su Create New Environment (Crea nuovo ambiente).
6. Selezionate Sviluppo, denominatelo "Dev Environment", quindi selezionate l'adattatore Akamai dal menu a discesa. Fate clic su Crea, quindi su Chiudi.
7. Fate clic su Aggiungi ambiente, selezionate Staging, denominatelo "Staging Environment", quindi selezionate l'adattatore Akamai. Fate clic su Crea, quindi su Chiudi.
8. Fate nuovamente clic su Aggiungi ambiente, selezionate Produzione, denominatelo «Ambiente di produzione», quindi selezionate l'adattatore Akamai. Fate clic su Crea, quindi su Chiudi.

## Creare una libreria di sviluppo

Nonostante tutte le modifiche e le configurazioni effettuate finora, non è stato ancora pubblicato alcun codice. La creazione di una libreria, tradotta in modo approssimativo come raccolta di modifiche, consente la pubblicazione di codice da utilizzare sul sito.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Fate clic sulla proprietà Launch che intendete implementare sul sito.
3. Fate clic sulla scheda Pubblicazione, quindi su Aggiungi nuova libreria.
4. Denominate la libreria «Modifiche iniziali» e selezionate l'ambiente di sviluppo.
5. Fate clic su Aggiungi tutte le risorse modificate, che elenca automaticamente Adobe Analytics, Identity Service e Core.
6. Fate clic su Salva.
7. Nella schermata di pubblicazione del flusso di lavoro di pubblicazione, fate clic sul menu a discesa accanto alla nuova libreria, quindi fate clic su Genera per sviluppo. Dopo alcuni secondi, il punto giallo della libreria diventa verde, a indicare che la build ha avuto esito positivo.
8. Fare clic sulla scheda Ambienti, quindi sull'ambiente di sviluppo.
9. In «Install Launch», copiate i blocchi di codice e forniteli ai proprietari del sito Web dell'organizzazione.

## Installare Launch nell'ambiente di sviluppo del sito Web

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. Questo codice viene comunemente inserito nel modello di archiviazione del sito. Una pagina vuota contenente il codice di implementazione si presenta come segue:

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

Un motivo comune è dato dal fatto che gli elementi esistono già in altre librerie inviate a staging o produzione. Quando create inizialmente le librerie, accertatevi che solo le risorse modificate vengano aggiunte alla libreria.

## Documentazione e risorse aggiuntive

- [Guida introduttiva all'avvio](https://docs.adobelaunch.com/getting-started): Scopri il flusso di lavoro di base di Launch
- [Amministrazione lancio](https://docs.adobelaunch.com/administration): Ulteriori informazioni su adattatori e ambienti

## Passaggi successivi

[Convalida l'implementazione di Analytics e pubblica la produzione](validate-publish-prod.md): Inizia a ottenere il valore da Adobe Analytics.
