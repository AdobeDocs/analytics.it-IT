---
title: Raccolta dati regionali per la Cina
seo-title: Adobe Analytics China RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Raccolta dati regionali per la Cina

La raccolta regionale di dati (RDC) di Adobe in Cina consente ai clienti cinesi di inviare dati direttamente a un centro di raccolta dati (DCC) in Cina, anziché ad altre ubicazioni a livello globale. Questo migliora i tempi di caricamento delle pagine e la precisione dei dati rispetto all'invio dei dati a CC al di fuori della Cina.

> [!IMPORTANT] Esiste un costo aggiuntivo associato all'uso del nodo RDC Cina. Prima di implementare la raccolta dati in Cina utilizzando il nodo RDC descritto in questo documento, contatta il responsabile commerciale aziendale per verificare di avere correttamente diritto a questa funzionalità.

## Impostazione del server di tracciamento per la Cina

Il tracciamento può essere portato in Cina RDC in qualsiasi punto che è conveniente per il vostro servizio. Per qualsiasi proprietà digitale (ad esempio un'app mobile o una pagina Web) che desideri indirizzare a China RDC, modifica il server di tracciamento in:

`<namespace>.sc.adobedc.cn`

Accertarsi di inserire lo spazio nomi appropriato. Questo si trova in genere all’inizio del server di tracciamento esistente. Ad esempio: `<namespace>.sc.adobedc.cn` - anche se qualsiasi valore dello spazio nomi funzionerà. Puoi anche puntare un record [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) di prime parti non SSL a questa nuova posizione.

Non impostare il valore trackingServer globalmente, per tutte le proprietà e le aree geografiche, su China RDC se una parte sostanziale della tua base di clienti è al di fuori della Cina. Il trackingServer deve essere impostato sul valore China RDC solo per i clienti che si trovano in Cina. In caso contrario, ciò influirà negativamente sulla velocità degli utenti al di fuori della Cina, in quanto obbliga la raccolta dei dati ad andare in Cina e tornare indietro per ricevere una risposta.

## Identificazione degli utenti in Cina

Indipendentemente da dove è ospitata la tua proprietà digitale o dalla lingua utilizzata, i tuoi utenti in Cina registreranno dei miglioramenti se utilizzi il nodo RDC in Cina. Di conseguenza, si consiglia di determinare quali utenti si trovano in Cina e quindi utilizzare China RDC per tali utenti. I metodi che possono facilitare l’identificazione di questi utenti comprendono:

* Utilizzando una soluzione GeoIP affidabile.  Potresti decidere di utilizzare una soluzione lato server per integrarti facilmente con Adobe Experience Platform Launch (o Gestione dei tag dei dati). In questo caso, la posizione può essere determinata includendo un elemento dati standard nel lancio della piattaforma Experience o nell'oggetto DTM. Oppure, potete utilizzare una soluzione GeoIP lato client. In questo caso, Experience Platform Launch può essere collegato al codice lato client. Notare che tali soluzioni possono richiedere all'utente di passare al sito localizzato. Questo comporta il rischio che la prima pagina venga conteggiata dal server di tracciamento globale e la seconda pagina da quella in Cina, il che può comportare una visita a doppio conteggio. Seguite le best practice per le soluzioni GeoIP. Adobe non è responsabile della precisione della soluzione GeoIP in uso.

* Utilizzo della struttura del sito o della lingua del browser (l’ `navigator.language / accept-language` intestazione). Il vantaggio di questo metodo è un costo inferiore ed eventualmente una migliore prestazione. Lo svantaggio di questo metodo è che i visitatori di lingua cinese che si recano al di fuori della Cina sono soggetti a velocità influenzate negativamente.
* Utilizzo di una soluzione di hosting basata in Cina e impostazione di trackingServer su China RDC in base all’host in uso. Anche questo aumenterà notevolmente la velocità.

## Limiti attuali

Le attuali limitazioni di China RDC:

1. China RDC non supporta SSL di prime parti ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) in JavaScript) o l’inoltro lato [server](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) ad Adobe Audience Manager.
2. Sebbene [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) ed [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) siano supportati, i domini Target e Demdex non sono attualmente nella Cina continentale e non avranno gli stessi vantaggi in termini di velocità o affidabilità di quelli della Cina RDC.

## L'impegno di Adobe nei confronti della Cina

Adobe pianifica di mantenere l’avanzamento di China RDC in modo permanente e alla fine aggiungerà il supporto per funzioni quali SSL di prime parti e inoltro lato server. Adobe pianifica inoltre di fornire un dominio demdex (o equivalente) in Cina per supportare completamente la raccolta ECID e Audience Manager dall'interno del paese. I clienti che iniziano a utilizzare Adobe China RDC possono continuare a utilizzare questo endpoint di raccolta dati a tempo indeterminato.
