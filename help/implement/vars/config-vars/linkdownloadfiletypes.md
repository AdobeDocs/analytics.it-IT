---
title: linkDownloadFileTypes
description: Determina le estensioni di file che vengono tracciate automaticamente come collegamenti di download.
feature: Appmeasurement Implementation
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
role: Admin, Developer
TQID: https://experienceleague.adobe.com/xe-ClVo-348u2ash9QODi2hIdGrVv6sIeN739EfPZ7c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 395
ht-degree: 18%

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

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Data Collection], impostare il valore desiderato nel campo di testo **[!UICONTROL Download link qualifier]**.

## Download manuale del qualificatore del collegamento con il Web SDK

[Configura](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) il SDK utilizzando [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html?lang=it#automaticLinkTracking). Il campo utilizza regex sull’URL su cui è stato fatto clic per determinare se si tratta di un collegamento di download valido. Se `downloadLinkQualifier` non è definito, il valore predefinito è `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Scaricare le estensioni tramite l’estensione Adobe Analytics

Download Extensions è un elenco di estensioni di file con un campo da aggiungere al pannello a soffietto [!UICONTROL Link Tracking] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
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
