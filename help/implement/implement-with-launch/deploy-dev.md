---
title: Implementare Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare Adobe Experience Platform Launch per distribuire Adobe Analytics al tuo ambiente di sviluppo.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Implementazione di un'implementazione di Analytics in un ambiente di sviluppo

Una volta creata e configurata una proprietà in Launch, le librerie sono pronte per essere distribuite e il codice è implementato sul sito.

## Prerequisiti

[Crea e configura una proprietà per Adobe Analytics in Launch](create-analytics-property.md): Accedi allo strumento e crea uno spazio per la tua implementazione Analytics.

## Creare adattatori e ambienti

Launch consente di gestire molti flussi di lavoro organizzativi durante la distribuzione del codice. Segui questi passaggi per creare i componenti minimi necessari per un'implementazione di Analytics. In qualità di amministratore di Launch, potete lavorare all'interno dell'organizzazione per stabilire il flusso di lavoro corretto per la distribuzione delle soluzioni Adobe.

1. Vai ad [Adobe Experience Platform Launch](https://launch.adobe.com) ed effettua l'accesso, se richiesto.
2. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
3. Fare clic sulla scheda Adattatori, quindi su Aggiungi adattatore.
4. Denominatela "Akamai", quindi selezionate Akamai nel menu a discesa del tipo. Fate clic su Salva.
5. Passare alla scheda Ambienti, quindi fare clic su Crea nuovo ambiente.
6. Selezionate Sviluppo, denominate "Dev Environment", quindi selezionate la scheda Akamai dal menu a discesa. Fate clic su Crea, quindi su Chiudi.
7. Fate clic su Add Environment (Aggiungi ambiente), selezionate Staging (Gestione temporanea), denominate "Staging Environment" (Ambiente di gestione temporanea), quindi selezionate la scheda di rete Akamai. Fate clic su Crea, quindi su Chiudi.
8. Fate di nuovo clic su Aggiungi ambiente, selezionate Produzione, denominate "Ambiente produzione", quindi selezionate la scheda Akamai. Fate clic su Crea, quindi su Chiudi.

## Creare una libreria di dev

Nonostante tutte le modifiche e le configurazioni apportate finora, non è stato pubblicato alcun codice. La creazione di una libreria, approssimativamente tradotta come raccolta di modifiche, consente la pubblicazione del codice da utilizzare sul sito.

1. Vai ad [Adobe Experience Platform Launch](https://launch.adobe.com) ed effettua l'accesso, se richiesto.
2. Fare clic sulla proprietà Launch che si desidera implementare sul sito.
3. Fate clic sulla scheda Pubblicazione, quindi su Aggiungi nuova libreria.
4. Denominate la libreria "Modifiche iniziali" e selezionate l'ambiente di sviluppo.
5. Fai clic su Aggiungi tutte le risorse modificate, che elenca automaticamente Adobe Analytics, Servizio identità e Core.
6. Fate clic su Salva.
7. Nella schermata del flusso di lavoro di pubblicazione, fate clic sul menu a discesa accanto alla nuova libreria e fate clic su Genera per sviluppo. Dopo alcuni secondi, il punto giallo nella libreria diventa verde, a indicare che la creazione è avvenuta correttamente.
8. Vai alla scheda Ambienti, quindi fai clic sul tuo ambiente di sviluppo.
9. In "Install Launch" (Installa lancio), copiate i blocchi di codice e inviateli ai proprietari del sito Web dell'organizzazione.

## Installa Launch nell’ambiente di sviluppo del tuo sito Web

Se controllate il codice del sito Web, implementate i due blocchi di codice nelle rispettive posizioni (nel `<head>` tag e appena sopra il `</body>` tag di chiusura) in ogni pagina del sito. Questo codice viene comunemente inserito nel modello di overarching del sito. Una pagina vuota contenente solo il codice di implementazione avrà l’aspetto seguente:

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

**Tentativo di creazione non riuscito.**

Un motivo comune è dato dal fatto che esistono già elementi in altre librerie inviate per staging o produzione. Quando create inizialmente le librerie, accertatevi che alla libreria vengano aggiunte solo le risorse modificate.

## Documentazione e risorse aggiuntive

- [Guida introduttiva a Launch](https://docs.adobelaunch.com/getting-started): Scopri il flusso di lavoro di base di Launch
- [Avvia amministrazione](https://docs.adobelaunch.com/administration): Ulteriori informazioni su adattatori e ambienti

## Passaggi successivi

[Convalida dell’implementazione di Analytics e pubblicazione in produzione](validate-publish-prod.md): Inizia a ricavare valore da Adobe Analytics.
