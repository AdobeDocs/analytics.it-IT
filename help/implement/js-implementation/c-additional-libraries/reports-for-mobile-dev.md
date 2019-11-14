---
description: Poiché i dispositivi mobili sono tracciati tramite un beacon, come gli altri visitatori, la maggior parte dei rapporti sono disponibili e corretti.
keywords: Analytics Implementation;reports;mobile protocols;search engines;search keywords;referring domains;referrers;geosegmentation;domains;connection type;time zone;cookies;java;javascript;monitor colors;monitor resolution;browser width;height;netscape plug-in
solution: Analytics
title: Rapporti per dispositivi mediante protocolli mobile
topic: Developer and implementation
uuid: 4aab125d-c131-4402-9bc8-1c7fd1bb2bee
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Rapporti per dispositivi mediante protocolli mobile

Poiché i dispositivi mobili sono tracciati tramite un beacon, come gli altri visitatori, la maggior parte dei rapporti sono disponibili e corretti.

[!DNL VISTA] può essere utilizzato per modificare i dati raccolti sia dai metodi Mobile che standard. Sono supportati tutti [!UICONTROL Custom] ( [!UICONTROL Insight] e [!UICONTROL prop] ), [!UICONTROL eVar][!UICONTROL Event]e [!UICONTROL Site Traffic][!UICONTROL Pathing] i report.

## Motori di ricerca, parole chiave di ricerca, domini di riferimento e referenti {#section_184D2EF9D906443FBDED04A09CDC50E9}

Questi rapporti hanno dati solo se il referente viene popolato nella richiesta di immagine inviata dalla pagina mobile. Il referente viene compilato tramite il parametro della stringa di query "r", come indicato nel white paper Implementazione senza JavaScript. Dovete inoltre trasmettere manualmente le informazioni di riferimento alla richiesta di immagine.

Il parametro della stringa di query 'r' deve includere il protocollo del referente. Se il protocollo viene lasciato disattivato, il rapporto del referente non viene popolato. Ad esempio, `r=https://msn.com` non utilizzare `r=msn.com`.

## Geosegmentazione e domini {#section_2B4E9443AAFE4ECA961F9E993592E628}

I rapporti sulla segmentazione geografica si basano sull'indirizzo IP del dispositivo che invia la richiesta. Poiché i dispositivi mobili utilizzano un gateway per richiedere immagini dai server Adobe, l'indirizzo IP del gateway viene utilizzato per determinare la geolocalità dell'utente. Poiché i gateway e i relativi indirizzi IP sono registrati per le reti di grandi dimensioni, la geolocalizzazione associata è spesso meno accurata.

I domini sono anche basati sull'indirizzo IP del gateway, il che significa che il rapporto sui domini spesso contiene il nome del gestore che possiede il gateway. A causa di Mobile Virtual Network Operator (MVNO), questo potrebbe non essere accurato.

## Tipi di connessione {#section_0E7FA18178B848AEBB839B1694B4D691}

Adobe mantiene una gamma nota di indirizzi IP appartenenti a gestori di dispositivi mobili. Quando un hit viene ricevuto da un intervallo IP che appartiene a un vettore mobile noto, l'hit viene visualizzato come "Mobile Carrier" nel report sul tipo di connessione. In caso contrario, il traffico mobile è elencato in "Lan/Wifi".

## Fusi orari, Cookie, Java, JavaScript, Colori e risoluzioni monitor, Larghezza e Altezza browser e Plug-in Netscape {#section_158C848273AE4691B4413767E849E846}

Questi report vengono raccolti utilizzando JavaScript per rilevare impostazioni specifiche del browser. Poiché JavaScript non è utilizzato per creare il beacon immagine sui dispositivi mobili, i dati raccolti dagli utenti di dispositivi mobili non sono inclusi in questi rapporti.
