---
title: server
description: Popolare la dimensione "Server".
exl-id: 7904c3c2-9a91-497e-89d0-9eed9ae7a902
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 1%

---

# server

La variabile `server` in genere memorizza il nome host del sito. Viene comunemente utilizzato nelle suite di rapporti che contengono dati di più domini. È funzionalmente identico a un prop.

## Server che utilizza tag in Adobe Experience Platform

Puoi impostare il server sia durante la configurazione dell’estensione Analytics (variabili globali) sia in base alle regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Server] .

Puoi impostare il server su qualsiasi valore stringa o elemento dati.

## s.server in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.server` è una stringa che in genere contiene il nome host del sito. ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
