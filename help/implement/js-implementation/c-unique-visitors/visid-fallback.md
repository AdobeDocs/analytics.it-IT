---
description: Se altri metodi ID visitatore non riescono, Adobe imposta un cookie di fallback o utilizza una combinazione di indirizzo IP e agente utente per identificare il visitatore.
keywords: Implementazione di Analytics
seo-description: Se altri metodi ID visitatore non riescono, Adobe imposta un cookie di fallback o utilizza una combinazione di indirizzo IP e agente utente per identificare il visitatore.
seo-title: Metodi ID di fallback
solution: Analytics
title: Metodi ID di fallback
topic: Sviluppatore e implementazione
uuid: f 242 d 481-81 f 0-4287-be 4 f -52 fd 03 eb 01 fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Metodi ID di fallback

Se altri metodi ID visitatore non riescono, Adobe imposta un cookie di fallback o utilizza una combinazione di indirizzo IP e agente utente per identificare il visitatore.

## Fallback Visitor Identification Method {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement for JavaScript 1.x and JavaScript H.25.3 (released January 2013) contain a new fallback visitor identification method for visitors whose browser blocks the cookie set by Adobe’s data collection servers (called `s_vi`). Precedentemente, se non era possibile impostare un cookie, i visitatori venivano identificati utilizzando una combinazione dell'indirizzo IP e della stringa agente utente durante la raccolta dei dati.

With this update, if the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2 year expiration and is used as the fallback identification method going forward. This change should result in increased accuracy in visit and visitor counts in situations where the primary cookie ( `AMCV_` or `s_vi`) cannot be set.

Visits total includes all visitors that are identified by the `s_vi` cookie or by using a fallback method.

## Indirizzo IP, agente utente, indirizzo IP gateway {#section_104819D74C594ECE879144FCC5DEF4BF}

. If the `AMCV_` or `s_vi` and the `s_fid` cookies cannot be set, visitors are identified using a combination of IP address and User Agent.
