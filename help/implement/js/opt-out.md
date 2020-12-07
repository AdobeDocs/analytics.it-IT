---
title: Collegamenti per il rifiuto
description: Scoprite come creare e implementare i collegamenti di rifiuto per i visitatori del sito.
translation-type: tm+mt
source-git-commit: dfe2b09b2ee287219d18099c51b6fbd7c86bab21
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 4%

---


# Implementazione dei collegamenti di opt-out

>[!IMPORTANT]
>
> Adobe raccomanda di utilizzare il servizio di consenso, in particolare per le organizzazioni che si occupano delle norme GDPR. Consultate [Panoramica](https://docs.adobe.com/content/help/it-IT/id-service/using/implementation/opt-in-service/optin-overview.html) del servizio di consenso nella guida utente del servizio identità  Experience Cloud.

Alcuni visitatori del sito Web preferiscono non includere nel set di dati le relative informazioni di navigazione.  Adobe offre la possibilità di fornire ai visitatori del sito Web un mezzo per rinunciare alla raccolta delle informazioni. Tutti i tipi di implementazione sono inclusi; la tua organizzazione è responsabile della tua informativa sulla privacy e della conformità ai termini firmati.

Quando un visitatore raggiunge l’URL di rinuncia, gli viene richiesto di installare un cookie di rinuncia. Se un utente sceglie di non essere monitorato e viene impostato un cookie di rinuncia, il file JavaScript continua a inviare dati ai server  Adobe. Tuttavia, tali dati non vengono elaborati o inclusi nei report.

>[!TIP]
>
> Adobe offre inoltre le impostazioni di privacy per ogni suite di rapporti. Consulta Impostazioni [](../../admin/admin/privacy-settings.md) privacy nella guida utente dell&#39;amministratore.

## URL rifiuto

La pagina di rifiuto per l’organizzazione dipende dal valore della [`trackingServer`](../vars/config-vars/trackingserver.md) variabile nell’implementazione.

* In  Adobe Experience Platform Launch:
   1. Accedete a [launch.adobe.com](https://launch.adobe.com) e fate clic sulla proprietà desiderata.
   2. Fare clic sulla [!UICONTROL Extensions] scheda, quindi fare clic [!UICONTROL Configure] sotto  Adobe Analytics.
   3. Fate clic sulla [!UICONTROL General] struttura a soffietto e prendete nota del [!UICONTROL Tracking Server] valore.

* In un&#39;implementazione JavaScript:
   1. Sul server Web, apri il file AppMeasurement.js utilizzato sul tuo sito in un editor di codice o di testo.
   2. Prendete nota del valore della `trackingServer` variabile.

* Utilizzo di [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it-IT):
   1. Andate al sito utilizzando il browser Chrome.
   2. Aprite il Experience Cloud Debugger, quindi andate al [!UICONTROL Network tab].
   3. Note the [!UICONTROL Request URL - Hostname] value.

Dopo aver trovato il `trackingServer` dominio di implementazione, aggiungi il percorso `/optout.html` alla fine. Ad esempio:

* Cookie di terze parti: `https://example.sc.adobedc.net/optout.html`
* Cookie di prime parti: `https://stats.example.com/optout.html`

## Parametri della stringa query di rifiuto

Esistono impostazioni che è possibile caricare automaticamente in questa pagina utilizzando le stringhe di query.

### Impostazioni internazionali

Cambiate automaticamente la lingua della pagina di rifiuto includendo il parametro della stringa di `locale` query. Assegnare il parametro della stringa di query uno dei seguenti valori:

* en_US (inglese, predefinito)
* bg_BG (bulgaro)
* zh_CN (cinese semplificato)
* zh_TW (cinese tradizionale)
* cs_CZ (ceco)
* da_NK (danese)
* nl_NL (olandese)
* et_EE (estone)
* fi_FI (finlandese)
* fr_FR (francese)
* de_DE (tedesco)
* el_GR (greco)
* it_IT (italiano)
* jp_JP (giapponese)
* ko_KR (coreano)
* lv_LV (lettone)
* lt_LT (lituano)
* nb_NO (norvegese)
* pl_PL (polacco)
* pt_BR (portoghese)
* sk_SK (Slovacco)
* es_ES (spagnolo)

Ad esempio, `https://example.sc.adobedc.net/optout.html?locale=ko_KR` carica la pagina di rifiuto in coreano.

>[!TIP]
>
>Il valore della stringa di `en_US` query non è obbligatorio, in quanto la pagina viene caricata in inglese per impostazione predefinita.

### Popup

Aggiunge alla pagina un pulsante Chiudi finestra, che consente di rendere la pagina di rifiuto una finestra a comparsa. Utilizzate il parametro della stringa di `popup` query e assegnategli un valore di `1`.

Ad esempio, `https://example.sc.adobedc.net/optout.html?popup=1` carica la pagina di rifiuto con un pulsante &#39;Chiudi finestra&#39;.

>[!NOTE]
>
>Storicamente questo parametro della stringa di query ha forzato una finestra a comparsa. Tuttavia, la maggior parte dei browser moderni offre il controllo sui pop-up all&#39;utente finale.

### Opzione per clic singolo

Consente all&#39;utente di rifiutare immediatamente il tracciamento. Aggiungete i due parametri della stringa di query `opt_out` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, installa `https://example.sc.adobedc.net/optout.html?opt_out=1&confirm_change=1` immediatamente il cookie di rinuncia sulla pagina del visitatore.

### Opzione con un solo clic

Consente all&#39;utente di rifiutare immediatamente il tracciamento eliminando il cookie di rinuncia. Aggiungete i due parametri della stringa di query `opt_in` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, elimina `https://example.sc.adobedc.net/optout.html?opt_in=1&confirm_change=1` immediatamente il cookie di rinuncia per il visitatore.
