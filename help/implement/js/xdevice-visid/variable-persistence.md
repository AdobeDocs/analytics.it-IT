---
description: Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l’attribuzione non viene modificata nel set di dati storici.
keywords: Implementazione di Analytics
title: Attribuzione e persistenza
topic-fix: Developer and implementation
uuid: 5dd706be-83f6-498a-a856-e3c5af995348
exl-id: 7a6305f6-c8ec-4f26-8373-45ce586bc69d
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 1%

---

# Attribuzione e persistenza

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Consulta [Analisi multidispositivo](/help/components/cda/overview.md) nella guida utente dei componenti.

Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l’attribuzione non viene modificata nel set di dati storici.

* Quando la variabile `s.visitorID` viene impostata e inviata su un hit, Adobe verifica la presenza di qualsiasi altro profilo visitatore con un ID visitatore corrispondente.
* Se esiste un profilo, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.
* Se non viene trovato alcun ID visitatore corrispondente, viene creato un nuovo profilo.

Quando un cliente non autenticato arriva per la prima volta sul tuo sito, Adobe Analytics gli assegna un profilo visitatore. Quando viene creato il nuovo profilo, termina una visita e inizia un’altra.

## Esempio 1

L’esempio seguente rappresenta il modo in cui i dati vengono inviati ad Adobe Analytics quando un cliente si autentica per la prima volta sul primo dispositivo:

* `eVar16` ha una scadenza di 1 giorno e  `evar17` scade in visita.
* La colonna `post_visitor_id` rappresenta il profilo gestito da Adobe Analytics. Le colonne dei post vengono generalmente visualizzate nei feed di dati. Consulta [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente relativa all’esportazione.
* Le colonne `post_evar16` e `post_evar17` mostrano la persistenza delle eVar.
* `cust_visid` rappresenta un valore impostato in  `s.visitorID`.
* Ogni riga è un &quot;hit&quot;, una singola richiesta inviata ai server di raccolta dati Adobe Analytics.

![Esempio 1 tra dispositivi](assets/xdevice_first.jpg)

Nella prima connessione dati contenente un valore `s.visitorID` non riconosciuto in precedenza (`u999` sopra) viene creato un nuovo profilo. I valori persistenti dal profilo precedente vengono trasferiti al nuovo profilo.

* Le eVar impostate per la scadenza sulla visita non vengono copiate nel profilo autenticato. Il valore `car` sopra non viene mantenuto.
* Le eVar impostate per la scadenza da altre misure verranno copiate nel profilo autenticato. Il valore `apple` viene mantenuto.
* Per le eVar persistenti, non viene registrata alcuna metrica Instance (Istanza). Questo significa che quando si utilizza l’identificazione dei visitatori tra dispositivi, è possibile visualizzare rapporti in cui la metrica Visite univoche per un valore di eVar è maggiore della metrica Instance (Istanza).

>[!NOTE]
>
>Se un utente è nuovo del tuo sito (non ha mai visitato il tuo sito prima su questo dispositivo) e si autentica entro circa 3 minuti dall&#39;arrivo, non persistono valori nel profilo autenticato.

## Esempio 2

L&#39;esempio seguente rappresenta il modo in cui i dati vengono inviati ad Adobe Analytics quando un cliente si autentica su un nuovo dispositivo, dopo che si è autenticato in precedenza su un dispositivo diverso.

![Esempio 2 tra dispositivi](assets/xdevice-subsequent.jpg)

Quando il cliente esegue l’autenticazione, viene confrontato con il precedente profilo &quot;autenticato&quot; - `2947539300`. Il profilo utilizzato all’inizio della visita ( `5477766334477`) non viene più utilizzato e il file non contiene dati.

* I dati di segmentazione geografica vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato. Ciò significa che in una connessione dati successiva su un nuovo dispositivo, i dati di segmentazione geografica generalmente non sono inclusi.
* Le colonne tecnologiche come browser, sistema operativo e profondità del colore vengono registrate al primo hit di una visita. Come i valori di geosegmentazione, non vengono copiati nel profilo vincolato.
* I canali di marketing sovrascrivono altri canali in una connessione dati successiva contenente una prima autenticazione per quel dispositivo.
