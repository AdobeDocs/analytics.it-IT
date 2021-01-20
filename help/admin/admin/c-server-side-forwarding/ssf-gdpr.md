---
description: Spiega i miglioramenti all'inoltro lato server che sono stati richiesti dal regolamento UE sulla conformità dei cookie.
title: Conformità a RGPD/ePrivacy e inoltro lato server
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: tm+mt
source-git-commit: b3ea538d0d6e6ebbbbd17871aacaed7527cf3976
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 9%

---


# Conformità a RGPD/ePrivacy e inoltro lato server

In questa sezione vengono illustrati i miglioramenti all&#39;inoltro lato server richiesti dalla [normativa UE sulla conformità ai cookie](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm), che è entrata in vigore il 30 settembre 2017.

L&#39;inoltro lato server viene utilizzato per condividere in tempo reale i dati da  Adobe Analytics ad altri [!DNL Experience Cloud Solutions], come  Audience Manager. Se abilitata, l&#39;inoltro lato server consente anche ad Analytics di inviare i dati ad altre soluzioni di  Experience Cloud e che tali soluzioni inviino i dati ad Analytics durante il processo di raccolta dei dati.

In precedenza, l&#39;inoltro lato server non aveva un modo per delineare tra eventi/hit di consenso e pre-consenso. A partire dal 1° novembre 2018, il titolare del trattamento ( cliente Adobe Analytics) ha la possibilità di limitare i dati di pre-consenso a  Adobe Analytics e impedire che vengano inoltrati a AAM. Una nuova variabile di contesto dell&#39;implementazione consente di contrassegnare le richieste dove non è stato ricevuto il consenso. La variabile, quando impostata, impedisce che queste richieste vengano inviate all&#39;AAM fino al ricevimento del consenso.

Quando la nuova variabile di contesto `cm.ssf=1` esiste in un hit, l’hit viene contrassegnato e non viene inoltrato al AAM sul lato server. Al contrario, se questa stringa non viene visualizzata su un hit, l’hit viene inoltrato a AAM.

L&#39;inoltro lato server è bidirezionale, il che significa che quando viene applicato a un hit e l&#39;hit viene inoltrato a AAM,  Audience Analytics riceve le informazioni sul segmento per quell&#39;hit da AAM e lo invia nuovamente ad Analytics. Di conseguenza, gli hit che non vengono inoltrati sul lato server da Analytics a AAM non saranno arricchiti con l’elenco degli ID del segmento da AAM. Di conseguenza, vi sarà un sottoinsieme di hit/traffico che non riceverà informazioni ID segmento da AAM.

## Dettagli implementazione {#section_FFA8B66085BF469FAB5365C944FE38F7}

A seconda del metodo di implementazione, attenetevi alla seguente procedura.

| Metodo di implementazione | Passaggi |
|--- |--- |
| Adobe Experience Platform Launch | Se avete installato l&#39;estensione Adobe Analytics , aggiungete la seguente definizione di variabile di dati di contesto all&#39;editor di codice personalizzato nella configurazione Azione di una regola: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definite la variabile contextdata e impostatela su 1 se il cliente non acconsente al marketing di destinazione. Impostate la variabile `contextdata` su *0* per i clienti che hanno acconsentito al marketing di destinazione. |
| DTM | Aggiungi la definizione della variabile di dati contestuali all’editor del codice pagina personalizzato: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definite la variabile contextdata e impostatela su 1 se il cliente non acconsente al marketing di destinazione. Impostate la variabile contextdata su 0 per i clienti che hanno acconsentito al marketing di destinazione. |
| AppMeasurement | Aggiungi la definizione della variabile di dati contestuali al file AppMeasurement.js:  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota:  Definite la variabile contextdata e impostatela su 1 se il cliente non acconsente al marketing di destinazione. Impostate la variabile contextdata su 0 per i clienti che hanno acconsentito al marketing di destinazione. |

## Reporting (facoltativo) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puoi utilizzare  Adobe Analytics per segnalare la quantità di traffico basata sul consenso e, di conseguenza, è stata inoltrata sul lato server rispetto alla quantità di traffico non basata sul consenso e non è stata inoltrata a AAM.

Per configurare questo tipo di rapporto, mappate la nuova variabile di contesto su una variabile di traffico personalizzata (prop) tramite le regole di elaborazione. Per eseguire questa operazione

1. Implementate la variabile &quot;cm.ssf&quot; (come mostrato sopra).
1. [Abilitate la proprietà.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilizzare le regole di elaborazione per mappare la variabile di contesto alla proprietà.

   1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** , quindi seleziona una suite di rapporti.
   1. Fai clic su  **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** .
   1. Fai clic su **[!UICONTROL Add Rule.]**
   1. In **[!UICONTROL Always Execute]** sovrascrivere il valore del prop attivato con la variabile di contesto &quot;cm.ssf(Context Data)&quot;.
   1. Fai clic su **[!UICONTROL Save]**.

