---
description: Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l’attribuzione non viene modificata nel set di dati storici.
keywords: Implementazione di Analytics
title: Attribuzione e persistenza
feature: Implementation Basics
exl-id: 7a6305f6-c8ec-4f26-8373-45ce586bc69d
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 1%

---

# Attribuzione e persistenza

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra i dispositivi non è più consigliato. Consulta [Analytics tra dispositivi](/help/components/cda/overview.md) nella guida utente Componenti.

Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l’attribuzione non viene modificata nel set di dati storici.

* Quando la variabile `s.visitorID` è impostato e inviato in seguito a un hit, Adobe verifica la presenza di altri profili visitatore con un ID visitatore corrispondente.
* Se è presente un profilo, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.
* Se non viene trovato alcun ID visitatore corrispondente, viene creato un nuovo profilo.

Quando un cliente non autenticato arriva sul tuo sito, gli viene assegnato un profilo visitatore da Adobe Analytics. Quando viene creato il nuovo profilo, termina una visita e inizia un’altra visita.

## Esempio 1

L’esempio seguente rappresenta il modo in cui i dati vengono inviati ad Adobe Analytics quando un cliente si autentica per la prima volta sul primo dispositivo:

* `eVar16` ha una scadenza di 1 giorno e `evar17` scade durante la visita.
* Il `post_visitor_id` rappresenta il profilo gestito da Adobe Analytics. Le colonne Post vengono generalmente visualizzate nei feed di dati. Consulta [Feed dati](/help/export/analytics-data-feed/data-feed-overview.md) nella guida utente Esporta.
* Il `post_evar16` e `post_evar17` Le colonne mostrano la persistenza delle eVar.
* `cust_visid` rappresenta un valore impostato in `s.visitorID`.
* Ogni riga corrisponde a un &quot;hit&quot;, una singola richiesta inviata ai server di raccolta dati di Adobe Analytics.

![Esempio tra dispositivi 1](assets/xdevice_first.jpg)

Sulla prima connessione dati contenente un elemento non riconosciuto in precedenza `s.visitorID` valore (`u999` sopra), viene creato un nuovo profilo. I valori persistenti del profilo precedente vengono trasferiti al nuovo profilo.

* Le eVar impostate per la scadenza alla visita non vengono copiate nel profilo autenticato. Nota il valore `car` non viene mantenuto.
* Le eVar impostate per la scadenza da altre misure verranno copiate nel profilo autenticato. Nota il valore `apple` persistente.
* Per le eVar persistenti, non viene registrata alcuna metrica di istanza. Ciò significa che quando si utilizza l’identificazione dei visitatori cross-device, è possibile visualizzare rapporti in cui la metrica Visite univoche per un valore eVar è maggiore della metrica Istanza.

>[!NOTE]
>
>Se un utente non ha mai visitato prima il tuo sito su questo dispositivo e si autentica entro circa 3 minuti dall’arrivo, al profilo autenticato non persiste alcun valore.

## Esempio 2

L’esempio seguente rappresenta il modo in cui i dati vengono inviati ad Adobe Analytics quando un cliente si autentica su un nuovo dispositivo, dopo averlo precedentemente autenticato su un dispositivo diverso.

![Esempio tra dispositivi 2](assets/xdevice-subsequent.jpg)

Quando il cliente si autentica, viene trovata una corrispondenza con il precedente profilo &quot;autenticato&quot;: `2947539300`. Profilo utilizzato all’inizio di questa visita ( `5477766334477`) non viene più utilizzato e nessun dato persiste dal file.

* I dati di geosegmentazione vengono registrati in base al primo hit della visita e non cambiano per una singola visita indipendentemente dal dispositivo utilizzato. Ciò significa che in una connessione dati successiva su un nuovo dispositivo, i dati di geosegmentazione non sono generalmente inclusi.
* Le colonne della tecnologia come browser, sistema operativo e profondità del colore vengono registrate al primo hit di una visita. Come i valori di segmentazione geografica, non vengono copiati nel profilo unito.
* I canali di marketing sovrascrivono altri canali su una connessione dati successiva contenente una prima autenticazione per quel dispositivo.
