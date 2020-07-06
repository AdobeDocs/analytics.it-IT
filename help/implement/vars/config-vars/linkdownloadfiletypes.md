---
title: linkDownloadFileTypes
description: Determinare le estensioni di file che vengono tracciate automaticamente come collegamenti per il download.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 1%

---


# linkDownloadFileTypes

Quando [`trackDownloadLinks`](trackdownloadlinks.md) è attivato e un visitatore fa clic su un collegamento, AppMeasurement verifica l’URL del collegamento per le estensioni del tipo di file. Se l’URL del collegamento contiene un tipo di file trovato in `linkDownloadFileTypes`, viene inviata automaticamente una richiesta di immagine del collegamento per il download.

Utilizzare `linkDownloadFileTypes` per personalizzare le estensioni di file da conteggiare come collegamenti di download.

>[!NOTE]
>
>Solo i clic effettivi vengono tracciati automaticamente. I seguenti tipi di collegamenti non vengono tracciati automaticamente:
>
> * Download di file che si avviano automaticamente al caricamento di una pagina
> * Download attivabili dopo un reindirizzamento
> * Fare clic con il pulsante destro del mouse e selezionare &#39;Salva Target con nome...&#39;
> * Collegamenti che utilizzano JavaScript, ad esempio `javascript:openLink()`
>
> 
Per questi tipi di download, potete chiamare manualmente il [`tl()`](../functions/tl-method.md) metodo.

Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Scarica le estensioni in  Adobe Experience Platform Launch

Scarica estensioni è un elenco di estensioni di file con un campo da aggiungere di più sotto la struttura di [!UICONTROL Link Tracking] navigazione quando si configura l&#39;estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espandere la [!UICONTROL Link Tracking] struttura a soffietto, che mostra il [!UICONTROL Download Extensions] campo.

Aggiungete estensioni di file all&#39;elenco immettendo del testo nel campo e facendo clic [!UICONTROL Add]. Rimuovere le estensioni di file dall&#39;elenco facendo clic sulla relativa icona &quot;X&quot;.

## s.linkDownloadFileTypes in AppMeasurement e Launch editor di codice personalizzato

La `s.linkDownloadFileTypes` variabile è una stringa di estensioni di file separate da virgole. Non utilizzate gli spazi.

Se questa variabile non è definita, il tracciamento automatico dei collegamenti per il download non funziona (anche se [`trackDownloadLinks`](trackdownloadlinks.md) è `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
