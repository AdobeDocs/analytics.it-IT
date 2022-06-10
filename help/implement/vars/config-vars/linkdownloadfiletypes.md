---
title: linkDownloadFileTypes
description: Determina le estensioni di file che vengono tracciate automaticamente come collegamenti per il download.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# linkDownloadFileTypes

Quando [`trackDownloadLinks`](trackdownloadlinks.md) (AppMeasurement) o [`clickCollectionEnabled`](trackdownloadlinks.md) (SDK web) è abilitato e un visitatore fa clic su un collegamento, AppMeasurement controlla l&#39;URL del collegamento per le estensioni di tipo file. Se l’URL del collegamento contiene un tipo di file corrispondente, viene inviata automaticamente una richiesta di immagine del collegamento di download.

Utilizzo `linkDownloadFileTypes` per personalizzare quali estensioni di file si desidera conteggiare come collegamenti per il download.

>[!NOTE]
>
>Solo i clic effettivi vengono tracciati automaticamente. I seguenti tipi di collegamenti non vengono tracciati automaticamente:
>
>* Download di file che si avviano automaticamente al caricamento di una pagina
>* Download che si attivano dopo un reindirizzamento
>* Fai clic con il pulsante destro del mouse e seleziona &quot;Salva Target con nome..&quot;
>* Collegamenti che utilizzano JavaScript, ad esempio `javascript:openLink()`
>
>Per questi tipi di download, puoi inviare manualmente un [`link tracking`](../functions/tl-method.md) chiama.

Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Download del qualificatore di collegamento tramite l&#39;estensione SDK per web

La [!UICONTROL Download link qualifier] il campo di testo utilizza regex per determinare se un collegamento selezionato si qualifica come collegamento per il download.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Data Collection], imposta il valore desiderato nel **[!UICONTROL Download link qualifier]** campo di testo.

## Download manuale del qualificatore di collegamento per l&#39;implementazione dell&#39;SDK per web

[Configura](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) l&#39;SDK con [`downloadLinkQualifier`](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html#automaticLinkTracking). Il campo utilizza l’espressione regex sull’URL selezionato per determinare se si tratta di un collegamento di download valido. Se `downloadLinkQualifier` non è definito, il valore predefinito è impostato su `\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$`.

```json
alloy("configure", {
  "downloadLinkQualifier": "\\.(exe|zip|wav|mp3|mov|mpg|avi|wmv|pdf|doc|docx|xls|xlsx|ppt|pptx)$"
});
```

## Scaricare le estensioni utilizzando l’estensione Adobe Analytics

Scarica estensioni è un elenco di estensioni di file con un campo per aggiungere di più sotto [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela **[!UICONTROL Download Extensions]** campo .

Aggiungi estensioni di file all’elenco inserendo testo nel campo e facendo clic su **[!UICONTROL Add]**. Rimuovi estensioni di file dall&#39;elenco facendo clic sulle rispettive **&#39;X&#39;** icona.

## s.linkDownloadFileTypes in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.linkDownloadFileTypes` è una stringa di estensioni di file separate da virgola. Non utilizzare spazi.

Se questa variabile non è definita, il monitoraggio automatico dei collegamenti per il download non funziona (anche se [`trackDownloadLinks`](trackdownloadlinks.md) è `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
