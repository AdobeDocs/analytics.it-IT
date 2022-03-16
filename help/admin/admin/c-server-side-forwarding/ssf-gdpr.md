---
description: Vengono descritti i miglioramenti relativi all’inoltro lato server necessari in base al regolamento UE sulla conformità dei cookie.
title: Conformità a RGPD/ePrivacy e inoltro lato server
feature: Server-Side Forwarding
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: ht
source-wordcount: '526'
ht-degree: 100%

---

# Conformità a RGPD/ePrivacy e inoltro lato server

Questa sezione specifica i miglioramenti relativi all’inoltro lato server introdotti in base al [regolamento UE sulla conformità dei cookie](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies), entrato in vigore il 30 settembre 2017.

L’inoltro lato server viene utilizzato per condividere in tempo reale dati da Adobe Analytics ad altre [!DNL Experience Cloud Solutions], come ad esempio Audience Manager. Se abilitato, l’inoltro lato server consente ad Analytics di trasmettere i dati ad altre soluzioni Experience Cloud e a queste di trasmetterli ad Analytics durante il processo di raccolta dei dati.

In precedenza, l’inoltro lato server non disponeva di un metodo che permettesse di distinguere eventi/hit di consenso e pre-consenso. A partire dal 1° novembre 2018, in qualità di titolare del trattamento dei dati (cliente Adobe Analytics) puoi limitare i dati pre-consenso ad Adobe Analytics e impedirne l’inoltro ad AAM. Una nuova variabile di contesto dell’implementazione consente di contrassegnare ogni hit per cui non è stato ricevuto il consenso. La variabile, se impostata, impedisce che tali hit vengano inviati ad AAM finché non sia stato ricevuto il consenso.

Se l’hit contiene la nuova variabile di contesto `cm.ssf=1`, viene contrassegnato con un flag e non viene effettuato l’inoltro lato server ad AAM. Viceversa, se tale stringa non è presente, l’hit viene inoltrato ad AAM.

L’inoltro lato server è bidirezionale: se applicato a un hit che viene inoltrato ad AAM, Audience Analytics riceve informazioni sui segmenti per tale hit da AAM e lo restituisce ad Analytics. Di conseguenza, gli hit non inoltrati sul lato server da Analytics ad AAM non verranno integrati con l’elenco degli ID del segmento da AAM. Pertanto, sarà presente un sottoinsieme di traffico/hit che non riceve informazioni sull’ID del segmento da AAM.

## Dettagli di implementazione {#section_FFA8B66085BF469FAB5365C944FE38F7}

In base al metodo di implementazione adottato, segui questi passaggi.

| Metodo di implementazione | Passaggi |
|--- |--- |
| Tag in Adobe Experience Platform | Se hai installato l’estensione Adobe Analytics, aggiungi la seguente definizione di variabile di dati di contesto all’editor di codice personalizzato nella configurazione Azione di una regola: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota: definisci la variabile contextdata e impostala su 1 per i clienti che non hanno acconsentito al marketing mirato. Imposta la variabile `contextdata` su *0* per i clienti che hanno acconsentito al marketing mirato. |
| AppMeasurement | Aggiungi al file AppMeasurement.js la definizione della variabile contextdata: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Nota: definisci la variabile contextdata e impostala su 1 per i clienti che non hanno acconsentito al marketing mirato. Imposta la variabile contextdata su 0 per i clienti che hanno acconsentito al marketing mirato. |

## Reportistica (facoltativo) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

Puoi utilizzare Adobe Analytics per generare rapporti di confronto tra la quantità di traffico basata sul consenso (per cui quindi è stato effettuato l’inoltro lato server) e la quantità di traffico non basato sul consenso (per cui quindi non è stato effettuato l’inoltro ad AAM).

Per configurare questo tipo di reportistica, usa le regole di elaborazione per mappare a nuova variabile di contesto su una variabile di traffico personalizzata (prop). A questo scopo, eseguie le seguenti operazioni:

1. Implementa la variabile “cm.ssf” (come illustrato sopra).
1. [Abilita la proprietà.](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. Utilizza le regole di elaborazione per mappare la variabile di contesto sulla proprietà.

   1. Passa a  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** , quindi seleziona una suite di rapporti.
   1. Fai clic su **[!UICONTROL Edit Report Suite]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]** .
   1. Fai clic su **[!UICONTROL Add Rule.]**
   1. In **[!UICONTROL Always Execute]**, sovrascrivi il valore della proprietà abilitata con la variabile di contesto “cm.ssf(Context Data)”.
   1. Fai clic su **[!UICONTROL Save]**.
