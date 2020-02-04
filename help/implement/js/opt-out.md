---
title: Collegamenti per il rifiuto
description: Scoprite come creare e implementare i collegamenti di rifiuto per i visitatori del sito.
translation-type: tm+mt
source-git-commit: 664d0cde8b8b17c86b47858611d459026aab0bef

---


# Implementare i collegamenti di rifiuto

> [!IMPORTANT] Adobe consiglia di utilizzare il servizio di consenso, in particolare per le organizzazioni interessate dalle normative GDPR. Consulta [Panoramica](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) del servizio di consenso nella guida utente del servizio Experience Cloud Identity.

Alcuni visitatori del sito Web preferiscono non includere nel set di dati le relative informazioni di navigazione. Adobe offre ai visitatori del sito Web la possibilità di scegliere se non raccogliere informazioni. Tutti i tipi di implementazione sono inclusi; la tua organizzazione è responsabile della tua informativa sulla privacy e della conformità ai termini firmati.

Quando un visitatore raggiunge l’URL di rinuncia, gli viene richiesto di installare un cookie di rinuncia. Se un utente sceglie di non essere monitorato e viene impostato un cookie di rinuncia, il file JavaScript continua a inviare dati ai server Adobe. Tuttavia, tali dati non vengono elaborati o inclusi nei report.

> [!TIP] Adobe offre inoltre le impostazioni sulla privacy per ogni singola suite di rapporti. Consulta Impostazioni [](../../admin/admin/privacy-settings.md) privacy nella guida utente di amministrazione.

## URL rifiuto

La pagina di rifiuto per l’organizzazione dipende dal valore della [`trackingServer`](../vars/config-vars/trackingserver.md) variabile nell’implementazione.

* In Adobe Experience Platform Launch:
   1. Accedete a [launch.adobe.com](https://launch.adobe.com) e fate clic sulla proprietà desiderata.
   2. Fai clic sulla [!UICONTROL Extensions] scheda, quindi fai clic [!UICONTROL Configure] sotto Adobe Analytics.
   3. Fate clic sulla [!UICONTROL General] struttura a soffietto e prendete nota del [!UICONTROL Tracking Server] valore.

* In un&#39;implementazione JavaScript:
   1. Sul server Web, apri il file AppMeasurement.js utilizzato sul tuo sito in un editor di codice o di testo.
   2. Prendete nota del valore della `trackingServer` variabile.

* Utilizzo di [Adobe Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html):
   1. Andate al sito utilizzando il browser Chrome.
   2. Apri il debugger di Experience Cloud, quindi vai al [!UICONTROL Network tab].
   3. Note the [!UICONTROL Request URL - Hostname] value.

Dopo aver trovato il `trackingServer` dominio di implementazione, aggiungi il percorso `/optout.html` alla fine. Ad esempio:

* Cookie di terze parti: `https://example.sc.omtrdc.net/optout.html`
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

Ad esempio, `https://example.sc.omtrdc.net/optout.html?locale=ko_KR` carica la pagina di rifiuto in coreano.

> [!TIP] Il valore della stringa di `en_US` query non è obbligatorio, in quanto la pagina viene caricata in inglese per impostazione predefinita.

### Popup

Aggiunge alla pagina un pulsante Chiudi finestra, che consente di rendere la pagina di rifiuto una finestra a comparsa. Utilizzate il parametro della stringa di `popup` query e assegnategli un valore di `1`.

Ad esempio, `https://example.sc.omtrdc.net/optout.html?popup=1` carica la pagina di rifiuto con un pulsante Chiudi finestra.

> [!NOTE] Storicamente questo parametro della stringa di query ha forzato una finestra a comparsa. Tuttavia, la maggior parte dei browser moderni dà il controllo intorno ai pop all&#39;utente finale.

### Opzione per clic singolo

Consente all&#39;utente di rifiutare immediatamente il tracciamento. Aggiungete i due parametri della stringa di query `opt_out` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, installa `https://example.sc.omtrdc.net/optout.html?opt_out=1&confirm_change=1` immediatamente il cookie di rinuncia sulla pagina del visitatore.

### Opzione con un solo clic

Consente all&#39;utente di rifiutare immediatamente il tracciamento eliminando il cookie di rinuncia. Aggiungete i due parametri della stringa di query `opt_in` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, elimina `https://example.sc.omtrdc.net/optout.html?opt_in=1&confirm_change=1` immediatamente il cookie di rinuncia per il visitatore.
