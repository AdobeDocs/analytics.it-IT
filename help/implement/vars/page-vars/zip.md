---
title: zip
description: Compila manualmente la dimensione "Codice postale" se le impostazioni della suite di rapporti lo consentono.
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 17%

---

# zip

Il `zip` variabile consente di popolare manualmente la dimensione &quot;Codice postale&quot; se [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti. Nelle versioni precedenti di Adobe Analytics, questa variabile poteva essere impostata solo manualmente, in genere durante l’immissione di informazioni di spedizione su un sito di vendita al dettaglio. I miglioramenti apportati ad Adobe Analytics consentono di impostare automaticamente questa variabile utilizzando i dati di geolocalizzazione. Questa variabile non persiste oltre l’hit impostato.

>[!IMPORTANT]
>
>Assicurati che le [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti è impostato sul valore desiderato. Non è possibile utilizzare questa variabile se [!UICONTROL Geo zip] viene sempre utilizzato. Consulta [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) per ulteriori informazioni, consulta la guida utente dell’amministratore.

## Codice postale tramite Web SDK

Il codice postale è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Codice postale tramite l’estensione Adobe Analytics

Puoi impostare il codice postale sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Zip].

Puoi impostare il CAP su qualsiasi valore stringa, inclusi gli elementi dati.

## s.zip in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.zip` variabile è una stringa che in genere contiene un CAP, ma può contenere qualsiasi valore desiderato fino a una lunghezza massima di 50 byte.

```js
s.zip = "84043";
```
