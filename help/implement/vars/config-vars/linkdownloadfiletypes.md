---
title: linkDownloadFileTypes
description: Determina le estensioni di file che vengono tracciate automaticamente come collegamenti per il download.
feature: Variables
exl-id: 5089571a-d387-4ac7-838f-8bc95b2856fb
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# linkDownloadFileTypes

Quando [`trackDownloadLinks`](trackdownloadlinks.md) se è abilitato e un visitatore fa clic su un collegamento, AppMeasurement controlla l&#39;URL del collegamento per le estensioni del tipo di file. Se l&#39;URL del collegamento contiene un tipo di file trovato in `linkDownloadFileTypes`, viene inviata automaticamente una richiesta di immagine di collegamento per il download.

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
>Per questi tipi di download, puoi chiamare manualmente il [`tl()`](../functions/tl-method.md) metodo .

Se un collegamento selezionato corrisponde ai criteri di collegamento di uscita e di download, il tipo di collegamento di download ha la priorità.

## Scaricare le estensioni utilizzando i tag in Adobe Experience Platform

Scarica estensioni è un elenco di estensioni di file con un campo per aggiungere di più sotto [!UICONTROL Link Tracking] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
4. Espandi la [!UICONTROL Link Tracking] fisarmonica, che rivela [!UICONTROL Download Extensions] campo .

Aggiungi estensioni di file all’elenco inserendo testo nel campo e facendo clic su [!UICONTROL Add]. Rimuovi estensioni di file dall&#39;elenco facendo clic sulla rispettiva icona &quot;X&quot;.

## s.linkDownloadFileTypes in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.linkDownloadFileTypes` è una stringa di estensioni di file separate da virgola. Non utilizzare spazi.

Se questa variabile non è definita, il monitoraggio automatico dei collegamenti per il download non funziona (anche se [`trackDownloadLinks`](trackdownloadlinks.md) è `true`).

```js
s.linkDownloadFileTypes = "doc,docx,eps,jpg,png,svg,xls,ppt,pptx,pdf,xlsx,tab,csv,zip,txt,vsd,vxd,xml,js,css,rar,exe,wma,mov,avi,wmv,mp3,wav,m4v";
```
