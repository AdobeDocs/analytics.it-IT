---
description: nulle
seo-description: nulle
seo-title: PHP
solution: Analytics
subtopic: Note sulla versione
title: PHP
topic: Sviluppatore e implementazione
uuid: 65 a 644 ef -8 e 50-406 b -8 b 12-0582495 d 130 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# PHP{#php}

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivare la registrazione di debug.

## Version 1.2.2 {#section_0D547871DC684417B6CE1370E5C6AAC2}

Release Date: **August 2014**

* Modifiche interne per supportare funzionalità imminenti.

## Version 1.2.1 {#section_5717907F67AB482F860F1DFBCB4198C7}

Release Date: **July 2012**

* Added a check for the "off" returned for the $_SERVER['HTTPS'] in IIS. Without this check, typecasting to boolean ((bool)$_SERVER['HTTPS']) returned true in IE whether the request was made through HTTP or HTTPS. In questo modo, le pagine non sicure tentavano di effettuare una richiesta di immagine protetta.

## Version 1.1 {#section_8F4479681ED642FCB9233459E04FF702}

La Libreria delle misurazioni per PHP 1.1 include i seguenti aggiornamenti dalla versione 1.0:

* Better GeoSegmentation accuracy (when `sendFromServer` is enabled).
* Fixed bug so user can now append to `userAgent` variable.
* Il beacon immagine è ora più conforme con più browser mobili.
* The `imageDimensions` variable now defaults to 5x5 when mobile is enabled.
* Elenco di rilevamento bot rifinito.
* Added debug information (HTTP headers, response, errors, and so forth) when `debugTracking` and `sendFromServer` are enabled.

* Added the `debugFilename` variable (when `sendFromServer` is enabled).

* The pagename variable defaults to `$_SERVER['SCRIPT_NAME']` when neither `pagename` nor `pageURL` are set.

* Supporto completo delle implementazioni CGI di PHP.
* Miglioramenti delle prestazioni.

