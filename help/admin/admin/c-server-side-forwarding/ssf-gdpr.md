---
description: Spiega i miglioramenti all'inoltro lato server richiesti dal regolamento UE sulla conformità ai cookie.
title: Conformità a RGPD/ePrivacy e inoltro lato server
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
translation-type: tm+mt
source-git-commit: f3eb3c024a80d0b65729929960173f8b3a4267b0
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 9%

---

# Conformità a RGPD/ePrivacy e inoltro lato server

Questa sezione spiega i miglioramenti all&#39;inoltro lato server richiesti dal [Regolamento UE sulla conformità dei cookie](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), entrato in vigore il 30 settembre 2017.

L&#39;inoltro lato server viene utilizzato per condividere in tempo reale i dati da Adobe Analytics ad altri [!DNL Experience Cloud Solutions], ad Audience Manager. Quando abilitato, l’inoltro lato server consente ad Analytics di inviare dati push ad altre soluzioni Experience Cloud e a queste soluzioni di inviare dati in Analytics durante il processo di raccolta dei dati.

In precedenza, l&#39;inoltro lato server non aveva un modo per delineare tra eventi/hit di consenso e pre-consenso. A partire dal 1° novembre 2018, in qualità di titolare del trattamento dei dati (cliente Adobe Analytics) puoi limitare i dati pre-consenso ad Adobe Analytics e impedirne l’inoltro a AAM. Una nuova variabile di contesto dell&#39;implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all&#39;AAM fino al ricevimento del consenso.

Quando questa nuova variabile di contesto, `cm.ssf=1`, esiste su un hit, questo hit viene contrassegnato e non viene inoltrato al AAM lato server. Viceversa, se questa stringa non viene visualizzata su un hit, l&#39;hit viene inoltrato a AAM.

L&#39;inoltro lato server è bidirezionale, il che significa che quando viene applicato a un hit e quell&#39;hit viene inoltrato a AAM, Audience Analytics riceve informazioni sui segmenti per quell&#39;hit da AAM e lo invia nuovamente ad Analytics. Di conseguenza, gli hit che non sono inoltrati sul lato server da Analytics a AAM non verranno arricchiti con l’elenco degli ID del segmento da AAM. Pertanto, ci sarà un sottoinsieme di traffico/hit che non otterrà le informazioni ID del segmento da AAM.

## Dettagli implementazione {#section_FFA8B66085BF469FAB5365C944FE38F7}

A seconda del metodo di implementazione, segui questi passaggi.

| Metodo di implementazione | Passaggi |
|--- |--- |
| Adobe Experience Platform Launch | Supponendo che sia installata l’estensione Adobe Analytics, aggiungi la seguente definizione di variabile di dati di contesto all’editor di codice personalizzato nella configurazione Azione di una regola: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definisci la variabile contextdata e impostala su 1 se un cliente non dà il consenso al marketing mirato. Imposta la variabile `contextdata` su *0* per i clienti che hanno acconsentito al marketing mirato. |
| AppMeasurement | Aggiungi la definizione della variabile di dati di contesto al file AppMeasurement.js :  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definisci la variabile contextdata e impostala su 1 se un cliente non dà il consenso al marketing mirato. Imposta la variabile contextdata su 0 per i clienti che hanno acconsentito al marketing mirato. |

## Reporting (facoltativo) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puoi utilizzare Adobe Analytics per generare rapporti sulla quantità di traffico basata sul consenso e, di conseguenza, il traffico è stato inoltrato lato server rispetto a quanto traffico non è basato sul consenso e non è stato inoltrato a AAM.

Per configurare questo tipo di reporting, mappare la nuova variabile di contesto su una variabile di traffico personalizzata (prop) tramite le regole di elaborazione. Per farlo

1. Implementa la variabile &quot;cm.ssf&quot; (come mostrato sopra).
1. [Abilita la proprietà .](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilizza le regole di elaborazione per mappare la variabile di contesto alla proprietà .

   1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** , quindi seleziona una suite di rapporti.
   1. Fai clic su  **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** .
   1. Fai clic su **[!UICONTROL Add Rule.]**
   1. In **[!UICONTROL Always Execute]** sovrascrivi il valore della proprietà abilitata con la variabile di contesto &quot;cm.ssf(Context Data)&quot;.
   1. Fai clic su **[!UICONTROL Save]**.
