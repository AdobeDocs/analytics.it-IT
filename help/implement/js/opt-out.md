---
title: Collegamenti di rinuncia
description: Scopri come creare e implementare collegamenti di rinuncia per i visitatori del tuo sito.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
hide: true
hidefromtoc: true
role: Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 4%

---

# Implementazione dei collegamenti di opt-out

>[!IMPORTANT]
>
> Questo articolo fornisce a **clienti Adobe Analytics che (prevedono di) implementare Adobe Analytics** sul proprio sito Web istruzioni su come fornire agli utenti del sito Web collegamenti di rinuncia. <p><p>
><p>-ERR:REF-NOT-FOUND-<p>-ERR:REF-NOT-FOUND-> Se **stai visitando un sito Web che ha implementato Adobe Analytics** e desideri rinunciare, **<span style="color:red">questo articolo NON è adatto a te</span>**. Consulta [Opzioni sulla privacy di Adobe](https://www.adobe.com/privacy/opt-out.html) per controllare come Adobe utilizza le tue informazioni.

Alcuni visitatori del tuo sito web preferiscono non includere le informazioni di navigazione nel set di dati. Adobe offre la possibilità di fornire ai visitatori del sito web un mezzo per rinunciare alle informazioni analizzate.

I collegamenti di rinuncia consentono ai visitatori del sito web di omettere i propri dati dai rapporti di Analytics. Questi collegamenti sono limitati alle implementazioni di AppMeasurement; Adobe consiglia di utilizzare il servizio Opt-in di [Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it). Il servizio Opt-in è più robusto e funziona su più prodotti Adobe Experience Cloud, tra cui Adobe Analytics e AppMeasurement.

Quando un visitatore raggiunge un URL di rinuncia, gli viene richiesto di installare un cookie di rinuncia. Se un utente sceglie di non essere tracciato e viene impostato un cookie di rinuncia, AppMeasurement continua a inviare dati ad Adobe. Tuttavia, tali dati non vengono elaborati o inclusi nei rapporti.

>[!TIP]
>
>Adobe offre anche le impostazioni della privacy in base alla suite di rapporti. Consulta [Impostazioni privacy](/help/admin/tools/manage-rs/edit-settings/general/privacy-settings.md) nella guida utente dell&#39;amministratore.

## URL di rinuncia

La pagina di rinuncia per l&#39;organizzazione dipende dal valore della variabile [`trackingServer`](../vars/config-vars/trackingserver.md) nell&#39;implementazione.

* Nell’estensione Analytics:
   1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
   1. Fai clic sulla proprietà del tag desiderata.
   1. Fare clic sulla scheda [!UICONTROL Extensions], quindi su [!UICONTROL Configure] in Adobe Analytics.
   1. Fare clic sul pannello a soffietto [!UICONTROL General] e prendere nota del valore [!UICONTROL Tracking Server].

* In un’implementazione JavaScript:
   1. Sul server web, apri il file AppMeasurement.js utilizzato sul sito in un editor di codice o di testo.
   1. Nota il valore della variabile `trackingServer`.

* Utilizzo di [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Passa al sito utilizzando il browser Chrome.
   1. Apri Experience Cloud Debugger, quindi passa a [!UICONTROL Network tab].
   1. Nota il valore [!UICONTROL Request URL - Hostname].

Dopo aver trovato il dominio `trackingServer` dell&#39;implementazione, aggiungere il percorso `/optout.html` alla fine. Ad esempio:

* Cookie di terze parti: `https://example.data.adobedc.net/optout.html`
* Cookie di prime parti: `https://stats.example.com/optout.html`

## Parametri della stringa di query per la rinuncia

Esistono impostazioni che è possibile caricare automaticamente in questa pagina utilizzando le stringhe di query.

### Impostazioni internazionali

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
