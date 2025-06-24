---
title: linkDownloadFileTypes
description: Determina le estensioni di file che vengono tracciate automaticamente come collegamenti di download.
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 15%

---

# linkDownloadFileTypes

Quando [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) è abilitato e un visitatore fa clic su un collegamento, AppMeasurement controlla che nell&#39;URL del collegamento siano presenti estensioni di tipo file. Se l’URL del collegamento contiene un tipo di file corrispondente, viene inviata automaticamente una richiesta di immagine del collegamento di download.

Utilizzare `linkDownloadFileTypes` per personalizzare le estensioni di file da considerare come collegamenti di download.

>[!NOTE]
>
>Solo i clic effettivi vengono tracciati automaticamente. I seguenti tipi di collegamenti non vengono tracciati automaticamente:
>
>* Download di file che iniziano automaticamente al caricamento di una pagina
>* Download che si attivano dopo un reindirizzamento
>* Fai clic con il pulsante destro del mouse e seleziona &quot;Salva oggetto con nome...&quot;
>* Collegamenti che utilizzano JavaScript, ad esempio `javascript:openLink()`
>
>Per questi tipi di download, è possibile inviare manualmente una chiamata [`link tracking`](../functions/tl-method.md).

Se un collegamento cliccato corrisponde ai criteri del collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Scaricare il qualificatore di collegamento tramite l’estensione Web SDK

Il campo di testo [!UICONTROL Download link qualifier] utilizza regex per determinare se un collegamento su cui è stato fatto clic può essere considerato un collegamento di download.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Data Collection], impostare il valore desiderato nel campo di testo **[!UICONTROL Download link qualifier]**.

## Download manuale del qualificatore del collegamento con il Web SDK

[Configura](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) il SDK utilizzando [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). Il campo utilizza regex sull’URL su cui è stato fatto clic per determinare se si tratta di un collegamento di download valido. Se `downloadLinkQualifier` non è definito, il valore predefinito è `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Scaricare le estensioni tramite l’estensione Adobe Analytics

Download Extensions è un elenco di estensioni di file con un campo da aggiungere al pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Link Tracking], che mostra il campo **[!UICONTROL Download Extensions]**.

Aggiungere estensioni di file all&#39;elenco immettendo testo nel campo e facendo clic su **[!UICONTROL Add]**. Rimuovere le estensioni di file dall&#39;elenco facendo clic sulla rispettiva icona **&#39;X&#39;**.

## s.linkDownloadFileTypes in AppMeasurement e l’editor di codice personalizzato dell’estensione Analytics

La variabile `s.linkDownloadFileTypes` è una stringa di estensioni di file separate da virgola. Non utilizzare spazi.

Se questa variabile non è definita, il tracciamento automatico dei collegamenti di download non funziona (anche se [`trackDownloadLinks`](trackdownloadlinks.md) è `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
