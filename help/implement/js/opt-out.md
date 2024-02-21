---
title: Collegamenti di rinuncia
description: Scopri come creare e implementare collegamenti di rinuncia per i visitatori del tuo sito.
feature: Implementation Basics
exl-id: 08b8c7cc-28c6-45e3-ab44-77471eea8ef1
role: Developer
source-git-commit: bb2b0f715941135d119d862b64c02f05800b3fdd
workflow-type: tm+mt
source-wordcount: '579'
ht-degree: 4%

---

# Implementazione dei collegamenti di opt-out

>[!IMPORTANT]
>
> Questo articolo fornisce **Clienti Adobe Analytics che (prevedono di) implementare Adobe Analytics** sul loro sito web con istruzioni su come fornire agli utenti del sito web collegamenti di rinuncia. <p><p>
> Se sei **visita di un sito web che ha implementato Adobe Analytics**, e desideri rinunciare, **<span style="color:red">questo articolo NON è adatto a te</span>**. Consulta [Adobe di scelte sulla privacy](https://www.adobe.com/privacy/opt-out.html) per controllare il modo in cui Adobe utilizza le informazioni.

Alcuni visitatori del tuo sito web preferiscono non includere le informazioni di navigazione nel set di dati. Adobe offre la possibilità di fornire ai visitatori del sito web un mezzo per rinunciare alle informazioni analizzate.

I collegamenti di rinuncia consentono ai visitatori del sito web di omettere i propri dati dai rapporti di Analytics. Questi collegamenti sono limitati alle implementazioni AppMeasurement; Adobe consiglia di utilizzare [Servizio Opt-in di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=it) invece. Il servizio Opt-in è più robusto e funziona su più prodotti Adobe Experience Cloud, inclusi Adobe Analytics e AppMeasurement.

Quando un visitatore raggiunge un URL di rinuncia, gli viene richiesto di installare un cookie di rinuncia. Se un utente sceglie di non essere tracciato e viene impostato un cookie di rinuncia, AppMeasurement continua a inviare dati ad Adobe. Tuttavia, tali dati non vengono elaborati o inclusi nei rapporti.

>[!TIP]
>
>Adobe offre anche le impostazioni della privacy in base alla suite per report. Consulta [Impostazioni privacy](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/privacy-settings.md) nella guida utente Admin.

## URL di rinuncia

La pagina di rinuncia per la tua organizzazione dipende dalla [`trackingServer`](../vars/config-vars/trackingserver.md) valore variabile nell’implementazione.

* Nell’estensione Analytics:
   1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
   1. Fai clic sulla proprietà del tag desiderata.
   1. Fai clic su [!UICONTROL Extensions] , quindi fai clic su [!UICONTROL Configure] in Adobe Analytics.
   1. Fai clic su [!UICONTROL General] Pannello a soffietto e annota [!UICONTROL Tracking Server] valore.

* In un’implementazione JavaScript:
   1. Sul server web, apri il file AppMeasurement.js utilizzato sul sito in un editor di codice o di testo.
   1. Osserva `trackingServer` valore della variabile.

* Utilizzo di [Adobe Experience Cloud Debugger](https://experienceleague.adobe.com/docs/experience-platform/debugger/home.html):
   1. Passa al sito utilizzando il browser Chrome.
   1. Apri il Experience Cloud Debugger, quindi vai al [!UICONTROL Network tab].
   1. Osserva [!UICONTROL Request URL - Hostname] valore.

Una volta trovati i `trackingServer` dominio, aggiungi il percorso `/optout.html` fino alla fine. Ad esempio:

* Cookie di terze parti: `https://example.data.adobedc.net/optout.html`
* Cookie di prime parti: `https://stats.example.com/optout.html`

## Parametri della stringa di query per la rinuncia

Esistono impostazioni che è possibile caricare automaticamente in questa pagina utilizzando le stringhe di query.

### Impostazioni internazionali

Cambia automaticamente la lingua della pagina di rinuncia includendo `locale` parametro stringa query. Assegna al parametro della stringa di query uno dei seguenti valori:

* `en_US` (Inglese, impostazione predefinita)
* `bg_BG` (Bulgaro)
* `zh_CN` (Cinese semplificato)
* `zh_TW` (Cinese tradizionale)
* `cs_CZ` (Ceco)
* `da_NK` (Danese)
* `nl_NL` (Olandese)
* `et_EE` (estone)
* `fi_FI` (Finlandese)
* `fr_FR` (Francese)
* `de_DE` (Tedesco)
* `el_GR` (Greco)
* `it_IT` (Italiano)
* `jp_JP` (Giapponese)
* `ko_KR` (Coreano)
* `lv_LV` (Lettone)
* `lt_LT` (Lituano)
* `nb_NO` (Norvegese)
* `pl_PL` (Polacco)
* `pt_BR` (Portoghese)
* `sk_SK` (Slovacco)
* `es_ES` (Spagnolo)

Ad esempio: `https://example.data.adobedc.net/optout.html?locale=ko_KR` carica la pagina di rinuncia in coreano.

### Popup

Aggiunge un pulsante Chiudi finestra alla pagina, consentendo al potenziale utente di trasformare la pagina di rinuncia in una finestra a comparsa. Utilizza il `popup` parametro stringa query e assegnargli il valore `1`.

Ad esempio: `https://example.data.adobedc.net/optout.html?popup=1` carica la pagina di rinuncia con un pulsante Chiudi finestra.

>[!NOTE]
>
>Storicamente, questo parametro della stringa di query forzava una finestra a comparsa. Tuttavia, la maggior parte dei browser moderni forniscono all’utente finale il controllo sulle finestre a comparsa.

### Rinuncia con clic singolo

Consente all’utente di rinunciare immediatamente al tracciamento. Aggiungi i due parametri della stringa di query `opt_out` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio: `https://example.data.adobedc.net/optout.html?opt_out=1&confirm_change=1` installa immediatamente il cookie di rinuncia sulla pagina del visitatore.

### Consenso con clic singolo

Consente all’utente di negare immediatamente il consenso al tracciamento eliminando il cookie di rinuncia. Aggiungi i due parametri della stringa di query `opt_in` e `confirm_change`, assegnando a ciascuno un valore di `1`.

Ad esempio: `https://example.data.adobedc.net/optout.html?opt_in=1&confirm_change=1` elimina immediatamente il cookie di rinuncia per il visitatore.
