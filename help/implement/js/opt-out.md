---
title: Collegamenti di rinuncia
description: Scopri come creare e implementare collegamenti di rinuncia per i visitatori del tuo sito.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
role: Developer
TQID: https://experienceleague.adobe.com/3X3RsfI3J96Ml4Q2UvnaaPLfBihSPvD-bfE8-yZujzU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 628
ht-degree: 6%

---

# Implementazione dei collegamenti di opt-out

>[!IMPORTANT]
>
> Questo articolo fornisce a **clienti Adobe Analytics che (prevedono di) implementare Adobe Analytics** sul proprio sito Web istruzioni su come fornire agli utenti del sito Web collegamenti di rinuncia. <p><p>> Se **stai visitando un sito Web che ha implementato Adobe Analytics** e desideri rinunciare, **<span style="color:red">questo articolo NON è adatto a te</span>**. Consulta [Opzioni sulla privacy di Adobe](https://www.adobe.com/privacy/opt-out.html) per controllare come Adobe utilizza le tue informazioni.

Alcuni visitatori del tuo sito web preferiscono non includere le informazioni di navigazione nel set di dati. Adobe offre la possibilità di fornire ai visitatori del sito web un mezzo per rinunciare alle informazioni analizzate.

I collegamenti di rinuncia consentono ai visitatori del sito web di omettere i propri dati dai rapporti di Analytics. Questi collegamenti sono limitati alle implementazioni di AppMeasurement; Adobe consiglia di utilizzare il servizio Opt-in [Adobe CX Enterprise](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it). Il servizio Opt-in è più affidabile e funziona su più prodotti Adobe CX Enterprise, inclusi Adobe Analytics e AppMeasurement.

Quando un visitatore raggiunge un URL di rinuncia, gli viene richiesto di installare un cookie di rinuncia. Se un utente sceglie di non essere tracciato e viene impostato un cookie di rinuncia, AppMeasurement continua a inviare dati ad Adobe. Tuttavia, tali dati non vengono elaborati o inclusi nei rapporti.

>[!TIP]
>
>Adobe offre anche le impostazioni della privacy in base alla suite di rapporti. Consulta [Impostazioni privacy](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md) nella guida utente dell&#39;amministratore.

## URL di rinuncia

La pagina di rinuncia per l&#39;organizzazione dipende dal valore della variabile [`trackingServer`](../vars/config-vars/trackingserver.md) nell&#39;implementazione.

* Nell’estensione Analytics:
   1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
   1. Fai clic sulla proprietà del tag desiderata.
   1. Fare clic sulla scheda [!UICONTROL Extensions], quindi su [!UICONTROL Configure] in Adobe Analytics.
   1. Fare clic sul pannello a soffietto [!UICONTROL General] e prendere nota del valore [!UICONTROL Tracking Server].

* In un’implementazione JavaScript:
   1. Sul server web, apri il file AppMeasurement.js utilizzato sul sito in un editor di codice o di testo.
   1. Nota il valore della variabile `trackingServer`.

* Utilizzo di [Adobe CX Enterprise Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Passa al sito utilizzando il browser Chrome.
   1. Aprire CX Enterprise Debugger, quindi passare a [!UICONTROL Network tab].
   1. Nota il valore [!UICONTROL Request URL - Hostname].

Dopo aver trovato il dominio `trackingServer` dell&#39;implementazione, aggiungere il percorso `/optout.html` alla fine. Ad esempio:

* Cookie di terze parti: `https://example.data.adobedc.net/optout.html`
* Cookie di prime parti: `https://stats.example.com/optout.html`

## Parametri della stringa di query per la rinuncia

Esistono impostazioni che è possibile caricare automaticamente in questa pagina utilizzando le stringhe di query.

### Lingua

Cambia automaticamente la lingua della pagina di rinuncia includendo il parametro della stringa di query `locale`. Assegna al parametro della stringa di query uno dei seguenti valori:

* `en_US` (inglese, predefinito)
* `bg_BG` (bulgaro)
* `zh_CN` (Cinese semplificato)
* `zh_TW` (cinese tradizionale)
* `cs_CZ` (ceco)
* `da_NK` (danese)
* `nl_NL` (olandese)
* `et_EE` (estone)
* `fi_FI` (finlandese)
* `fr_FR` (francese)
* `de_DE` (tedesco)
* `el_GR` (greco)
* `it_IT` (italiano)
* `jp_JP` (giapponese)
* `ko_KR` (coreano)
* `lv_LV` (lettone)
* `lt_LT` (lituano)
* `nb_NO` (norvegese)
* `pl_PL` (polacco)
* `pt_BR` (portoghese)
* `sk_SK` (slovacco)
* `es_ES` (spagnolo)

Ad esempio, `https://example.data.adobedc.net/optout.html?locale=ko_KR` carica la pagina di rinuncia in coreano.

### Popup

Aggiunge un pulsante Chiudi finestra alla pagina, consentendo al potenziale utente di trasformare la pagina di rinuncia in una finestra a comparsa. Utilizzare il parametro della stringa di query `popup` e assegnargli il valore `1`.

Ad esempio, `https://example.data.adobedc.net/optout.html?popup=1` carica la pagina di rinuncia con un pulsante Chiudi finestra.

>[!NOTE]
>
>Storicamente, questo parametro della stringa di query forzava una finestra a comparsa. Tuttavia, la maggior parte dei browser moderni forniscono all’utente finale il controllo sulle finestre a comparsa.

### Rinuncia con clic singolo

Consente all’utente di rinunciare immediatamente al tracciamento. Aggiungere i due parametri della stringa di query `opt_out` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` installa immediatamente il cookie di rinuncia sulla pagina del visitatore.

### Consenso con clic singolo

Consente all’utente di negare immediatamente il consenso al tracciamento eliminando il cookie di rinuncia. Aggiungere i due parametri della stringa di query `opt_in` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio, `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` elimina immediatamente il cookie di rinuncia per il visitatore.
