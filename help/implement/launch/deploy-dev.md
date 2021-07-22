---
title: Distribuire Adobe Analytics in un ambiente di sviluppo
description: Scopri come utilizzare i tag per distribuire Adobe Analytics nel tuo ambiente di sviluppo.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: 9b9a338e3652c85ae0f8ce79b98a2babf427ab4c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 4%

---

# Distribuire un&#39;implementazione di Analytics in un ambiente di sviluppo

Dopo aver creato e configurato una proprietà tag, le librerie sono pronte per essere distribuite e implementate il codice sul sito.

>[!NOTE]
>Adobe Experience Platform Launch è stato riclassificato come una suite di tecnologie di raccolta dati nell’Experience Platform. Di conseguenza, sono state introdotte diverse modifiche terminologiche nella documentazione del prodotto. Consulta questo [documento](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) come riferimento consolidato delle modifiche terminologiche.

## Prerequisiti

[Crea e configura una proprietà tag per Adobe Analytics](create-analytics-property.md): Accedi allo strumento e crea uno spazio per la tua implementazione di Analytics.

## Creare adattatori e ambienti

I tag consentono di gestire molti flussi di lavoro organizzativi durante la distribuzione del codice. Segui questi passaggi per creare i componenti minimi necessari per un’implementazione di Analytics. In qualità di amministratore dei tag, puoi lavorare all’interno della tua organizzazione per stabilire il flusso di lavoro corretto per la distribuzione delle soluzioni Adobe.

1. Vai a [Adobe Experience Platform Launch](https://launch.adobe.com) e, se richiesto, accedi.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fare clic sulla scheda Adattatori, quindi fare clic su Aggiungi adattatore.
4. Denomina &quot;Akamai&quot; e seleziona Akamai nel menu a discesa del tipo . Fai clic su Salva.
5. Passa alla scheda Ambienti , quindi fai clic su Crea nuovo ambiente .
6. Seleziona Sviluppo, denominalo &quot;Ambiente di sviluppo&quot;, quindi seleziona l’adattatore Akamai dal menu a discesa. Fare clic su Crea, quindi su Chiudi.
7. Fai clic su Aggiungi ambiente, seleziona Staging, denominalo &quot;Staging Environment&quot;, quindi seleziona l&#39;adattatore Akamai. Fare clic su Crea, quindi su Chiudi.
8. Fai di nuovo clic su Aggiungi ambiente , seleziona Produzione, denominalo &quot;Ambiente produzione&quot;, quindi seleziona la scheda Akamai. Fare clic su Crea, quindi su Chiudi.

## Creare una libreria di sviluppo

Nonostante tutte le modifiche e le configurazioni apportate finora, non è stato pubblicato alcun codice. La creazione di una libreria, tradotta approssimativamente come una raccolta di modifiche, consente di utilizzare la pubblicazione del codice sul sito.

1. Vai a [Adobe Experience Platform Launch](https://launch.adobe.com) e, se richiesto, accedi.
2. Fai clic sulla proprietà tag che intendi implementare sul sito.
3. Fai clic sulla scheda Pubblicazione , quindi su Aggiungi nuova libreria .
4. Denomina la libreria &quot;Modifiche iniziali&quot; e seleziona l&#39;ambiente di sviluppo.
5. Fai clic su Aggiungi tutte le risorse modificate , che elenca automaticamente Adobe Analytics, il servizio Identity e il servizio core.
6. Fai clic su Salva.
7. Nella schermata del flusso di lavoro di pubblicazione, fai clic sul menu a discesa accanto alla nuova libreria e fai clic su Genera per lo sviluppo. Dopo alcuni secondi, il punto giallo della libreria diventa verde e indica che la build è stata completata correttamente.
8. Vai alla scheda Ambienti , quindi fai clic sul tuo ambiente di sviluppo.
9. In &quot;Installa tag&quot;, copia i blocchi di codice e forniscili ai proprietari del sito web della tua organizzazione.

## Installare i tag nell’ambiente di sviluppo del sito web

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

- [Guida](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en) rapida: Scopri il flusso di lavoro di base dell’implementazione dei tag
- [Panoramica](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en) sulla pubblicazione: Ulteriori informazioni sulla pubblicazione e sugli ambienti

## Passaggi successivi

[Convalida l’implementazione di Analytics e pubblica in produzione](validate-publish-prod.md): Inizia a ottenere valore da Adobe Analytics.
