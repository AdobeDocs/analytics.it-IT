---
description: Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l'attribuzione non viene modificata nel set di dati storici.
keywords: Analytics Implementation
title: Attribuzione e persistenza
topic: Developer and implementation
uuid: 5dd706be-83f6-498a-a856-e3c5af995348
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---


# Attribuzione e persistenza

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Consultate [Analisi cross-device](/help/components/cda/overview.md) nella guida utente dei componenti.

Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l&#39;attribuzione non viene modificata nel set di dati storici.

* Quando la variabile `s.visitorID` viene impostata e inviata su un hit,  Adobe verifica la presenza di qualsiasi altro profilo visitatore con un ID visitatore corrispondente.
* Se esiste un profilo, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.
* Se non viene trovato alcun ID visitatore corrispondente, viene creato un nuovo profilo.

Quando un cliente non autenticato arriva per la prima volta sul sito, al cliente viene assegnato un profilo visitatore da  Adobe Analytics. Quando viene creato il nuovo profilo, una visita termina e un&#39;altra inizia.

## Esempio 1

L&#39;esempio seguente rappresenta il modo in cui i dati vengono inviati a  Adobe Analytics quando un cliente si autentica per la prima volta sul primo dispositivo:

* `eVar16` ha una scadenza di 1 giorno e  `evar17` scade alla visita.
* La colonna `post_visitor_id` rappresenta il profilo gestito da  Adobe Analytics. Le colonne di post vengono generalmente visualizzate nei feed di dati. Consultate [Feed di dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente all&#39;esportazione.
* Le colonne `post_evar16` e `post_evar17` mostrano la persistenza delle eVar.
* `cust_visid` rappresenta un valore impostato in  `s.visitorID`.
* Ogni riga corrisponde a un &quot;hit&quot;, una singola richiesta inviata ai server di raccolta dati  Adobe Analytics.

![Esempio 1 tra dispositivi](assets/xdevice_first.jpg)

Nella prima connessione dati contenente un valore `s.visitorID` precedentemente non riconosciuto (`u999` sopra), viene creato un nuovo profilo. I valori persistenti del profilo precedente vengono trasferiti al nuovo profilo.

* Le eVar impostate per scadere alla visita non vengono copiate nel profilo autenticato. Notate che il valore `car` sopra non è persistente.
* Le eVar impostate per scadere da altre misure verranno copiate nel profilo autenticato. Il valore `apple` è persistente.
* Per le eVar persistenti, non viene registrata alcuna metrica Instance (Istanza). Questo significa che quando si utilizza l’identificazione visitatore tra dispositivi, è possibile visualizzare rapporti in cui la metrica Visite univoche per un valore di eVar  è maggiore della metrica Instance (Istanza).

>[!NOTE]
>
>Se un utente è nuovo al sito (non ha mai visitato prima su questo dispositivo) e si autentica entro circa 3 minuti dall&#39;arrivo, nessun valore persiste nel profilo autenticato.

## Esempio 2

L&#39;esempio seguente rappresenta il modo in cui i dati vengono inviati a  Adobe Analytics quando un cliente esegue l&#39;autenticazione su un nuovo dispositivo, dopo essere stato precedentemente autenticato su un dispositivo diverso.

![Esempio cross-device 2](assets/xdevice-subsequent.jpg)

Quando il cliente esegue l&#39;autenticazione, viene confrontato con il profilo &#39;autenticato&#39; precedente - `2947539300`. Il profilo utilizzato all&#39;inizio della visita ( `5477766334477`) non è più utilizzato e il file non contiene dati.

* I dati di geosegmentazione vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato. Ciò significa che in una connessione dati successiva su un nuovo dispositivo, i dati di geosegmentazione non sono in genere inclusi.
* Le colonne tecnologiche come browser, sistema operativo e profondità del colore vengono registrate al primo hit di una visita. Come i valori di geosegmentazione, non vengono copiati nel profilo con punti.
* I canali di marketing sovrascrivono altri canali su una connessione dati successiva contenente una prima autenticazione per quel dispositivo.
