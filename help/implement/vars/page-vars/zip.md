---
title: zip
description: Compila manualmente la dimensione "Codice postale" se le impostazioni della suite di rapporti lo consentono.
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 17%

---

# zip

La variabile `zip` ti consente di popolare manualmente la dimensione &quot;Codice postale&quot; se [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti lo consente. Nelle versioni precedenti di Adobe Analytics, questa variabile poteva essere impostata solo manualmente, in genere durante l’immissione di informazioni di spedizione su un sito di vendita al dettaglio. I miglioramenti apportati ad Adobe Analytics consentono di impostare automaticamente questa variabile utilizzando i dati di geolocalizzazione. Questa variabile non persiste oltre l’hit impostato.

>[!IMPORTANT]
>
>Assicurarsi che [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti sia impostato sul valore desiderato. Non è possibile utilizzare questa variabile se [!UICONTROL Geo zip] è sempre utilizzato. Per ulteriori informazioni, consulta [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) nella guida utente dell&#39;amministratore.

## Codice di avviamento postale tramite Web SDK

Il codice postale è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Codice postale tramite l’estensione Adobe Analytics

Puoi impostare il codice postale sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Zip].

Puoi impostare il CAP su qualsiasi valore stringa, inclusi gli elementi dati.

## s.zip in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.zip` è una stringa che in genere contiene un CAP, ma può contenere qualsiasi valore desiderato fino a una lunghezza massima di 50 byte.

```js
s.zip = "84043";
```
