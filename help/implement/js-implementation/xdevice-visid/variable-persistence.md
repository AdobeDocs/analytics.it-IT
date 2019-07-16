---
description: Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l'attribuzione non viene modificata nel set di dati storico.
keywords: Implementazione di Analytics
seo-description: Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l'attribuzione non viene modificata nel set di dati storico.
seo-title: Attribuzione e persistenza
solution: Analytics
title: Attribuzione e persistenza
topic: Sviluppatore e implementazione
uuid: 5 dd 706 be -83 f 6-498 a-a 856-e 3 c 5 af 995348
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Attribuzione e persistenza

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori su dispositivi non è più consigliato. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Quando i profili dei visitatori vengono uniti dopo essere stati associati alla stessa variabile ID visitatore, l&#39;attribuzione non viene modificata nel set di dati storico.

* When the variable `s.visitorID` is set and sent on a hit, the system checks for any other visitor profiles that have a matching visitor ID.
* Se esiste un profilo, il profilo visitatore già presente nel sistema viene usato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.
* Se non viene trovato alcun ID visitatore corrispondente, viene creato un nuovo profilo.

Quando un cliente autenticato arriva per la prima volta al sito, al cliente viene assegnato un profilo visitatore da Adobe Analytics. As shown in [Unique Visitor and Visits Counts](../../../implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC), on authentication a new profile is created. Quando viene creato il nuovo profilo, una visita termina e inizia un&#39;altra visita.

**Sulla prima connessione dati**

L&#39;esempio seguente è una rappresentazione del modo in cui i dati vengono inviati ad Adobe Analytics quando un cliente si autentica per la prima volta, sul primo dispositivo:

* `eVar16` ha una scadenza di 1 giorno e `evar17` scade alla visita.

* The `post_visitor_id` column represents the profile maintained by Adobe Analytics.
* The `post_evar16` and `post_evar17` columns show shows the persistence of eVars.

* `cust_visid` rappresenta un valore impostato in `s.visitorID`.

* Ogni riga è un&#39;hit, una singola richiesta inviata ai server di raccolta dati di Adobe Analytics.

![](assets/xdevice_first.jpg)

On the first data connection containing a previously unrecognized `s.visitorID` value ( `u999` above), the new profile is created. I valori persistenti del profilo precedente vengono trasferiti al nuovo profilo.

* Le evar impostate per la scadenza della visita non vengono copiate nel profilo autenticato. Note the value `car` above is not persisted.
* Le evar impostate per scadere da altre misure verranno copiate nel profilo autenticato. Note the value `apple` is persisted.
* Per le evar persistenti, non viene registrata alcuna metrica Instance (Istanza). Ciò significa che quando si utilizza l&#39;identificazione dei visitatori cross-device, è possibile visualizzare i rapporti in cui la metrica Visite uniche per un valore evar è più grande della metrica Instance (Istanza).

**Connessioni dati successive**

L&#39;esempio seguente è una rappresentazione del modo in cui i dati vengono inviati ad Adobe Analytics quando un cliente si autentica su un nuovo dispositivo, dopo l&#39;autenticazione in un dispositivo diverso:

![](assets/xdevice-subsequent.jpg)

When the customer authenticates his or her id is matched to the previous &#39;authenticated&#39; profile - `2947539300`. The profile used at the start of this visit ( `5477766334477`) is no longer used and no data persists from the file.

* I dati della geolocalizzazione vengono registrati in base al primo hit della visita e non vengono modificati per una singola visita, indipendentemente dal dispositivo utilizzato. Ciò significa che in una nuova connessione dati su un nuovo dispositivo, i dati di geolocalizzazione non sono generalmente inclusi.
* Le colonne della tecnologia come browser, sistema operativo e profondità colore vengono registrate al primo hit di una visita. Come i valori di geolocalizzazione, questi non verranno copiati nel profilo cucito.
* A Marketing Channel such as Direct or Internal which is commonly set up to not overwrite another channel will overwrite other channels on a subsequent data connection containing a first authentication for that device, such as the first authentication shown in [Unique Visitor and Visits Counts](../../../implement/js-implementation/xdevice-visid/xdevice-connecting.md#section_70330AB6724C4E419A4BD0BDD54641AC).

**Casi speciali**

In alcuni altri casi i dati non vengono persistenti dall&#39;autenticazione al profilo autenticato.

* Se un utente è nuovo al sito (non ha mai visitato prima del dispositivo) E quell&#39;utente si autentica entro circa 3 minuti dall&#39;arrivo, nessun valore persiste al profilo autenticato.

