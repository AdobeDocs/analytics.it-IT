---
description: nulle
seo-description: nulle
seo-title: PHP
solution: Analytics
subtopic: Note sulla versione
title: PHP
topic: Sviluppatore e implementazione
uuid: 65a644ef-8e50-406b-8b12-0582495d130a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# PHP{#php}

> [!NOTE] Per trovare la versione corrente della libreria, attivate la registrazione di debug.

## Versione 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Release Date: **August 2014**

* Modifiche interne per supportare le funzionalità in arrivo.

## Versione 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Release Date: **July 2012**

* È stato aggiunto un controllo per il valore "off" restituito per $_SERVER['HTTPS'] in IIS. Senza questa verifica, digitando booleano ((bool)$_SERVER['HTTPS']) veniva restituito true in IE, a prescindere che la richiesta fosse stata effettuata tramite HTTP o HTTPS. Ciò causava il tentativo da parte di pagine non sicure di effettuare una richiesta di immagine protetta.

## Versione 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

La Libreria misurazioni per PHP 1.1 include i seguenti aggiornamenti dalla versione 1.0:

* Migliore precisione di geosegmentazione (quando `sendFromServer` è abilitata).
* È stato corretto un bug che consentiva all’utente di aggiungere alla `userAgent` variabile.
* Il beacon immagine ora è più compatibile con più browser mobili.
* La `imageDimensions` variabile ora per impostazione predefinita è 5x5 quando è abilitato Mobile.
* Elenco di rilevamento bot perfezionato.
* Sono state aggiunte informazioni di debug (intestazioni HTTP, risposte, errori e così via) quando `debugTracking` e `sendFromServer` sono abilitate.

* Aggiunta la `debugFilename` variabile (quando `sendFromServer` è abilitata).

* Per impostazione predefinita, la variabile nomepagina `$_SERVER['SCRIPT_NAME']` non viene impostata `pagename` né `pageURL` .

* Supporto completo per le implementazioni CGI di PHP.
* Miglioramenti delle prestazioni.

