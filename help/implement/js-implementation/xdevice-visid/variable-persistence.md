---
description: Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l'attribuzione non viene modificata nel set di dati storici.
keywords: Analytics Implementation
solution: Analytics
title: Attribuzione e persistenza
topic: Developer and implementation
uuid: 5dd706be-83f6-498a-a856-e3c5af995348
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Attribuzione e persistenza

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l'attribuzione non viene modificata nel set di dati storici.

* Quando la variabile `s.visitorID` viene impostata e inviata su un hit, il sistema verifica la presenza di qualsiasi altro profilo visitatore con un ID visitatore corrispondente.
* Se esiste un profilo, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.
* Se non viene trovato alcun ID visitatore corrispondente, viene creato un nuovo profilo.

Quando un cliente non autenticato arriva per la prima volta sul sito, ad esso viene assegnato un profilo visitatore da Adobe Analytics. Come mostrato in Conteggio visitatori e visite [univoci](/help/implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC), al momento dell'autenticazione viene creato un nuovo profilo. Quando viene creato il nuovo profilo, una visita termina e un'altra inizia.

**Sulla prima connessione dati**

L'esempio seguente è una rappresentazione di come i dati vengono inviati ad Adobe Analytics quando un cliente si autentica per la prima volta, sul primo dispositivo:

* `eVar16` ha una scadenza di 1 giorno e `evar17` scade alla visita.

* La `post_visitor_id` colonna rappresenta il profilo gestito da Adobe Analytics.
* Le colonne `post_evar16` e `post_evar17` mostrano la persistenza delle eVar.

* `cust_visid` rappresenta un valore impostato in `s.visitorID`.

* Ogni riga corrisponde a un "hit", una singola richiesta inviata ai server di raccolta dati di Adobe Analytics.

![](assets/xdevice_first.jpg)

Nella prima connessione dati contenente un `s.visitorID` valore non riconosciuto in precedenza ( `u999` sopra), viene creato il nuovo profilo. I valori persistenti del profilo precedente vengono trasferiti al nuovo profilo.

* Le eVar impostate per scadere alla visita non vengono copiate nel profilo autenticato. Il valore `car` sopra riportato non è persistente.
* Le eVar impostate per scadere da altre misure verranno copiate nel profilo autenticato. Il valore `apple` è persistente.
* Per le eVar persistenti, non viene registrata alcuna metrica Instance (Istanza). Questo significa che quando si utilizza l'identificazione visitatore tra dispositivi, è possibile visualizzare rapporti in cui la metrica Visite univoche per un valore eVar è maggiore della metrica Istanza.

**Nelle successive connessioni dati**

L'esempio seguente è una rappresentazione di come i dati vengono inviati ad Adobe Analytics quando un cliente si autentica su un nuovo dispositivo, dopo che è stato precedentemente autenticato su un dispositivo diverso:

![](assets/xdevice-subsequent.jpg)

Quando il cliente esegue l'autenticazione del proprio ID viene confrontato con il profilo "autenticato" precedente - `2947539300`. Il profilo utilizzato all'inizio della visita ( `5477766334477`) non è più utilizzato e il file non contiene dati.

* I dati di geosegmentazione vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato. Ciò significa che in una connessione dati successiva su un nuovo dispositivo, i dati di geosegmentazione non sono in genere inclusi.
* Le colonne tecnologiche come browser, sistema operativo e profondità del colore vengono registrate al primo hit di una visita. Come i valori di geosegmentazione, non saranno copiati nel profilo con punti.
* Un Canale Marketing, come Diretto o Interno, comunemente configurato per non sovrascrivere un altro canale, sovrascriverà altri canali su una connessione dati successiva contenente una prima autenticazione per quel dispositivo, ad esempio la prima autenticazione mostrata in Conteggio Visitatori [univoci e Visite](/help/implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC).

**Casi speciali**

In alcuni altri casi i dati non vengono memorizzati dal profilo non autenticato al profilo autenticato.

* Se un utente è nuovo al sito (non ha mai visitato prima su questo dispositivo) E che si autentica entro circa 3 minuti dall'arrivo, nessun valore persisterà nel profilo autenticato.

