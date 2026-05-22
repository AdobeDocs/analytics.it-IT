---
description: Vengono descritti i miglioramenti relativi all’inoltro lato server necessari in base al regolamento UE sulla conformità dei cookie.
title: Conformità a GDPR/ePrivacy e inoltro lato server
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
TQID: 'https://experienceleague.adobe.com/MH--f5MxzLFOkDV8B-JzqMULLbY1ota6efoJ8T1ne58'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 301a0341e725ca15f1700046528ea5f42969add4
workflow-type: tm+mt
source-wordcount: 573
ht-degree: 52%

---

# Conformità a GDPR/ePrivacy e inoltro lato server

Questa sezione specifica i miglioramenti relativi all’inoltro lato server introdotti in base al [regolamento UE sulla conformità dei cookie](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies), entrato in vigore il 30 settembre 2017.

L&#39;inoltro lato server viene utilizzato per condividere in tempo reale i dati da Adobe Analytics ad altre soluzioni CX Enterprise, come Audience Manager. Quando è abilitato, l&#39;inoltro lato server consente ad Analytics di inviare dati ad altre soluzioni CX Enterprise e a queste di inviarli ad Analytics durante il processo di raccolta dei dati.

In precedenza, l’inoltro lato server non disponeva di un metodo che permettesse di distinguere eventi/hit di consenso e pre-consenso. A partire dal 1° novembre 2018, in qualità di titolare del trattamento dei dati (cliente Adobe Analytics) puoi limitare i dati divulgati prima del consenso ad Adobe Analytics e impedirne l’inoltro a Adobe Audience Manager. Una nuova variabile di contesto dell’implementazione consente di contrassegnare ogni hit per cui non è stato ricevuto il consenso. La variabile, se impostata, impedisce che tali hit vengano inviati ad Adobe Audience Manager finché non sia stato ricevuto il consenso.

Quando la nuova variabile di contesto `cm.ssf=1` esiste in un hit, questo viene contrassegnato e non viene inoltrato lato server a Adobe Audience Manager. Al contrario, se questa stringa non viene visualizzata su un hit, l’hit viene inoltrato a Adobe Audience Manager.

L’inoltro lato server è bidirezionale: se applicato a un hit che viene inoltrato a Adobe Audience Manager, Audience Analytics riceve informazioni sui segmenti per tale hit da Adobe Audience Manager e lo restituisce ad Analytics. Di conseguenza, gli hit non inoltrati sul lato server da Analytics a Adobe Audience Manager non verranno arricchiti con l’elenco degli ID del segmento da Adobe Audience Manager. Pertanto, sarà presente un sottoinsieme di traffico/hit che non riceve informazioni sull’ID del segmento da Adobe Audience Manager.

## Dettagli di implementazione {#section_FFA8B66085BF469FAB5365C944FE38F7}

In base al metodo di implementazione adottato, segui questi passaggi.

| Metodo di implementazione | Passaggi |
|--- |--- |
| Tag in Adobe Experience Platform | Se hai installato l’estensione Adobe Analytics, aggiungi la seguente definizione di variabile di dati di contesto all’editor di codice personalizzato nella configurazione Azione di una regola: <br/>`s.contextData['cm.ssf'] = '1'` <br/>Nota: definisci la variabile contextdata e impostala su 1 per i clienti che non hanno acconsentito al marketing mirato. Imposta la variabile `contextdata` su *0* per i clienti che hanno acconsentito al marketing mirato. |
| AppMeasurement | Aggiungi al file AppMeasurement.js la definizione della variabile contextdata: <br/>`s.contextData['cm.ssf'] = '1'` <br/>Nota: definisci la variabile contextdata e impostala su 1 per i clienti che non hanno acconsentito al marketing mirato. Imposta la variabile contextdata su 0 per i clienti che hanno acconsentito al marketing mirato. |

## Reportistica (facoltativo) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puoi utilizzare Adobe Analytics per generare rapporti sulla quantità di traffico basata sul consenso e di conseguenza inoltrata lato server rispetto al traffico non basato sul consenso e non inoltrata a Adobe Audience Manager.

Per configurare questo tipo di reportistica, usa le regole di elaborazione per mappare a nuova variabile di contesto su una variabile di traffico personalizzata (prop). A questo scopo, eseguie le seguenti operazioni:

1. Implementa la variabile “cm.ssf” (come illustrato sopra).
1. [Abilita la proprietà.](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
1. Utilizza le regole di elaborazione per mappare la variabile di contesto sulla proprietà.

   1. Passa a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** , quindi seleziona una suite di rapporti.
   1. Fai clic su **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** .
   1. Fai clic su **[!UICONTROL Add Rule.]**
   1. In **[!UICONTROL Always Execute]**, sovrascrivi il valore della proprietà abilitata con la variabile di contesto “cm.ssf(Context Data)”.
   1. Fai clic su **[!UICONTROL Save]**.
