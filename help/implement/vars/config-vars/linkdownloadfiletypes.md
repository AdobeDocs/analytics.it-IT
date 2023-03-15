---
title: linkDownloadFileTypes
description: Determina le estensioni di file che vengono tracciate automaticamente come collegamenti di download.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 19%

---

# linkDownloadFileTypes

Quando [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackdownloadlinks.md) (Web SDK) è abilitato e un visitatore fa clic su un collegamento, AppMeasurement controlla l’URL del collegamento per individuare le estensioni del tipo di file. Se l’URL del collegamento contiene un tipo di file corrispondente, viene inviata automaticamente una richiesta di immagine del collegamento di download.

Utilizzare `linkDownloadFileTypes` per personalizzare le estensioni di file da considerare come collegamenti per il download.

>[!NOTE]
>
>Solo i clic effettivi vengono tracciati automaticamente. I seguenti tipi di collegamenti non vengono tracciati automaticamente:
>
>* Download di file che iniziano automaticamente al caricamento di una pagina
>* Download che si attivano dopo un reindirizzamento
>* Fai clic con il pulsante destro del mouse e seleziona &quot;Salva oggetto con nome...&quot;
>* Collegamenti che utilizzano JavaScript, ad esempio `javascript:openLink()`
>
>Per questi tipi di download, puoi inviare manualmente un [`link tracking`](../functions/tl-method.md) chiamare.

Se un collegamento cliccato corrisponde ai criteri del collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Scaricare il qualificatore dei collegamenti tramite l’estensione Web SDK

Il [!UICONTROL Download link qualifier] il campo di testo utilizza regex per determinare se un collegamento su cui è stato fatto clic può essere considerato un collegamento di download.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Data Collection], imposta il valore desiderato in **[!UICONTROL Download link qualifier]** campo di testo.

## Scaricare il qualificatore di collegamento implementando manualmente il Web SDK

[Configura](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) l’SDK che utilizza [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). Il campo utilizza regex sull’URL su cui è stato fatto clic per determinare se si tratta di un collegamento di download valido. Se `downloadLinkQualifier` non è definito, il valore predefinito è impostato su `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Scaricare le estensioni tramite l’estensione Adobe Analytics

Download Extensions è un elenco di estensioni di file con un campo che consente di aggiungerne altre nella sezione [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Link Tracking], che mostra il campo **[!UICONTROL Download Extensions]**.

Aggiungere estensioni di file all&#39;elenco immettendo testo nel campo e facendo clic su **[!UICONTROL Add]**. Rimuovere le estensioni di file dall&#39;elenco facendo clic sulle rispettive **&#39;X&#39;** icona.

## s.linkDownloadFileTypes in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.linkDownloadFileTypes` variable è una stringa di estensioni di file separate da virgola. Non utilizzare spazi.

Se questa variabile non è definita, il tracciamento automatico dei collegamenti di download non funziona (anche se [`trackDownloadLinks`](trackdownloadlinks.md) è `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
