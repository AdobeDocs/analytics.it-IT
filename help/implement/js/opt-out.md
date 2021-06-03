---
title: Collegamenti di rinuncia
description: Scopri come creare e implementare i collegamenti di rinuncia per i visitatori del tuo sito.
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 4%

---

# Implementazione dei collegamenti di opt-out

>[!IMPORTANT]
>
>L’Adobe consiglia di utilizzare il servizio di consenso, in particolare per le organizzazioni interessate dalle normative RGPD. Consulta [Panoramica del servizio Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it) nella guida utente del servizio Experience Cloud Identity.

Alcuni visitatori del sito web preferiscono non includere le informazioni di navigazione nel set di dati. L’Adobe offre ai visitatori del sito web la possibilità di rinunciare alla raccolta delle informazioni. Tutti i tipi di implementazione sono gestiti; la tua organizzazione è responsabile della tua informativa sulla privacy e del rispetto dei termini firmati.

Quando un visitatore raggiunge un URL di rinuncia, gli viene richiesto di installare un cookie di rinuncia. Se un utente sceglie di non essere tracciato e viene impostato un cookie di rinuncia, il file JavaScript continua a inviare dati ai server di Adobe. Tuttavia, tali dati non vengono elaborati o inclusi nei rapporti.

>[!TIP]
>
>Adobe offre anche le impostazioni di privacy in base alla suite di rapporti. Consulta [Impostazioni privacy](../../admin/admin/privacy-settings.md) nella guida utente Admin.

## URL rinuncia

La pagina di rinuncia per la tua organizzazione dipende dal valore della variabile [`trackingServer`](../vars/config-vars/trackingserver.md) nella tua implementazione.

* In Adobe Experience Platform Launch:
   1. Accedi a [launch.adobe.com](https://launch.adobe.com) e fai clic sulla proprietà desiderata.
   2. Fai clic sulla scheda [!UICONTROL Extensions] , quindi fai clic su [!UICONTROL Configure] in Adobe Analytics.
   3. Fare clic sul pannello a soffietto [!UICONTROL General] e annotare il valore [!UICONTROL Tracking Server].

* In un&#39;implementazione JavaScript:
   1. Sul server web, apri il file AppMeasurement.js utilizzato sul tuo sito in un editor di codice o di testo.
   2. Notare il valore della variabile `trackingServer`.

* Utilizzando [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html):
   1. Passa al sito utilizzando il browser Chrome.
   2. Apri il Experience Cloud Debugger, quindi vai a [!UICONTROL Network tab].
   3. Osserva il valore [!UICONTROL Request URL - Hostname] .

Dopo aver trovato il dominio `trackingServer` dell&#39;implementazione, aggiungi il percorso `/optout.html` alla fine. Ad esempio:

* Cookie di terze parti: `https://example.data.adobedc.net/optout.html`
* Cookie di prime parti: `https://stats.example.com/optout.html`

## Parametri della stringa di query di rinuncia

Sono disponibili impostazioni che è possibile caricare automaticamente in questa pagina utilizzando le stringhe di query.

### Impostazioni internazionali

Passa automaticamente alla lingua della pagina di rinuncia includendo il parametro della stringa di query `locale` . Assegna il parametro della stringa di query uno dei seguenti valori:

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

Ad esempio, `https://example.data.adobedc.net/optout.html?locale=ko_KR` carica la pagina di rinuncia in coreano.

>[!TIP]
>
>Il valore della stringa di query `en_US` non è obbligatorio, in quanto la pagina viene caricata in inglese per impostazione predefinita.

### Popup

Aggiunge alla pagina un pulsante &quot;Chiudi finestra&quot;, che consente di rendere la pagina di rinuncia una finestra a comparsa. Utilizzare il parametro della stringa di query `popup` e assegnargli un valore di `1`.

Ad esempio, `https://example.data.adobedc.net/optout.html?popup=1` carica la pagina di rinuncia con un pulsante &quot;Chiudi finestra&quot;.

>[!NOTE]
>
>Storicamente questo parametro della stringa di query ha forzato una finestra a comparsa. Tuttavia, la maggior parte dei browser moderni dà il controllo intorno a pop all&#39;utente finale.

### Rinuncia a clic singolo

Consente all’utente di rinunciare immediatamente al tracciamento. Aggiungi i due parametri della stringa di query `opt_out` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` installa immediatamente il cookie di rinuncia sulla pagina del visitatore.

### Consenso clic singolo

Consente all’utente di dare immediatamente il consenso al tracciamento eliminando il cookie di rinuncia. Aggiungi i due parametri della stringa di query `opt_in` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` elimina immediatamente il cookie di rinuncia per il visitatore.
