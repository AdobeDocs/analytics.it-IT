---
title: zip
description: Compila manualmente la dimensione "Codice postale" se le impostazioni della suite di rapporti lo consentono.
feature: Appmeasurement Implementation
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
role: Admin, Developer
TQID: https://experienceleague.adobe.com/y46MdBiCa0og3VQb56p5qcAOyr-2mbJmRUsYXnKjYic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 257
ht-degree: 18%

---

# zip

La variabile `zip` ti consente di popolare manualmente la dimensione &quot;Codice postale&quot; se [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti lo consente. Nelle versioni precedenti di Adobe Analytics, questa variabile poteva essere impostata solo manualmente, in genere durante l’immissione di informazioni di spedizione su un sito di vendita al dettaglio. I miglioramenti apportati ad Adobe Analytics consentono di impostare automaticamente questa variabile utilizzando i dati di geolocalizzazione. Questa variabile non persiste oltre l’hit impostato.

>[!IMPORTANT]
>
>Assicurarsi che [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti sia impostato sul valore desiderato. Non è possibile utilizzare questa variabile se [!UICONTROL Geo zip] è sempre utilizzato. Per ulteriori informazioni, consulta [Impostazioni account generali](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) nella guida utente dell&#39;amministratore.

## Codice di avviamento postale tramite Web SDK

Il codice postale è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.placeContext.geo.postalCode`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.zip`

## Codice postale tramite l’estensione Adobe Analytics

Puoi impostare il codice postale sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
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
