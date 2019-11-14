---
description: Se altri metodi ID visitatore non riescono, Adobe imposta un cookie di fallback o utilizza una combinazione di indirizzo IP e agente utente per identificare il visitatore.
keywords: Analytics Implementation
solution: Analytics
title: Metodi di fallback ID
topic: Developer and implementation
uuid: f242d481-81f0-4287-be4f-52fd03eb01fc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Metodi di fallback ID

Se altri metodi ID visitatore non riescono, Adobe imposta un cookie di fallback o utilizza una combinazione di indirizzo IP e agente utente per identificare il visitatore.

## Metodo di identificazione del visitatore fallback {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement per JavaScript 1.x e JavaScript H.25.3 (rilasciato a gennaio 2013) contiene un nuovo metodo di identificazione del visitatore fallback per i visitatori il cui browser blocca il cookie impostato dai server di raccolta dati di Adobe (denominato `s_vi`). In precedenza, se non era possibile impostare un cookie, i visitatori venivano identificati utilizzando una combinazione dell'indirizzo IP e della stringa agente utente durante la raccolta dei dati.

With this update, if the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2 year expiration and is used as the fallback identification method going forward. Questa modifica dovrebbe comportare una maggiore precisione nei conteggi delle visite e dei visitatori in situazioni in cui non è possibile impostare il cookie principale ( `AMCV_` o `s_vi`).

Il totale delle visite include tutti i visitatori identificati dal `s_vi` cookie o mediante un metodo di fallback.

## Indirizzo IP, agente utente, indirizzo IP gateway {#section_104819D74C594ECE879144FCC5DEF4BF}

. Se non è possibile impostare il cookie `AMCV_` o `s_vi` e i `s_fid` cookie, i visitatori vengono identificati utilizzando una combinazione di indirizzo IP e agente utente.
