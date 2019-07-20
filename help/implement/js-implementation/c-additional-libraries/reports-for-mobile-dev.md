---
description: Poiché i dispositivi mobili vengono tracciati tramite un beacon, come per altri visitatori, la maggior parte dei report sono disponibili e corretti.
keywords: Implementazione di Analytics; rapporti; protocolli per dispositivi mobili; motori di ricerca; parole chiave di ricerca; domini di riferimento; referrer; geosegmentazione; domini; tipo di connessione; fuso orario; cookie; java; javascript; colori del monitor; risoluzione del monitor; larghezza browser; height; plug-in netscape
seo-description: Poiché i dispositivi mobili vengono tracciati tramite un beacon, come per altri visitatori, la maggior parte dei report sono disponibili e corretti.
seo-title: Rapporti per dispositivi mediante protocolli mobili
solution: Analytics
title: Rapporti per dispositivi mediante protocolli mobili
topic: Sviluppatore e implementazione
uuid: 4 aab 125 d-c 131-4402-9 bc 8-1 c 7 fd 1 bb 2 bee
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporti per dispositivi mediante protocolli mobili

Poiché i dispositivi mobili vengono tracciati tramite un beacon, come per altri visitatori, la maggior parte dei report sono disponibili e corretti.

[!DNL VISTA] può essere utilizzato per modificare i dati raccolti dai metodi mobili e standard. All [!UICONTROL Custom] [!UICONTROL Insight] ( [!UICONTROL prop] and [!UICONTROL eVar]), [!UICONTROL Event], [!UICONTROL Site Traffic], and [!UICONTROL Pathing] reports are supported.

## Search Engines, Search Keywords, Referring Domains, and Referrers {#section_184D2EF9D906443FBDED04A09CDC50E9}

Questi rapporti sono dotati solo di dati se il referente viene compilato nella richiesta di immagine inviata dalla pagina mobile. Il referente viene compilato tramite il parametro "r" della stringa query, come descritto nell'implementazione senza white paper javascript. Dovete inoltre trasmettere manualmente le informazioni di riferimento nella richiesta di immagine.

Il parametro della stringa query «r» deve includere il protocollo del referente. Se il protocollo viene lasciato disattivato, il rapporto di riferimento non viene popolato. For example, use `r=https://msn.com` not `r=msn.com`.

## Geosegmentation and Domains {#section_2B4E9443AAFE4ECA961F9E993592E628}

I rapporti di geosegmentazione si basano sull'indirizzo IP del dispositivo che invia la richiesta. Poiché i dispositivi mobili usano un gateway per richiedere immagini da server Adobe, l'indirizzo IP del gateway viene utilizzato per determinare la geolocalità dell'utente. Poiché i gateway e i relativi indirizzi IP sono registrati per reti di grandi dimensioni, la geolocalità associata è spesso meno accurata.

I domini sono anche basati sull'indirizzo IP del gateway, il che significa che il report sui domini contiene spesso il nome del vettore proprietario del gateway. A causa di operatori di rete virtuale mobile (mvnos), questo potrebbe non essere accurato.

## Connection Types {#section_0E7FA18178B848AEBB839B1694B4D691}

Adobe conserva un intervallo noto di indirizzi IP che appartengono a gestori mobili. Quando un hit viene ricevuto da un intervallo IP che appartiene a un operatore di telefonia mobile noto, l'hit viene visualizzato come "Mobile Carrier" nel report Tipo connessione. In caso contrario, il traffico mobile è elencato in "LAN/Wifi".

## Time Zones, Cookies, Java, JavaScript, Monitor Colors and Resolutions, Browser Width and Height, and Netscape Plug-ins {#section_158C848273AE4691B4413767E849E846}

Questi rapporti vengono raccolti utilizzando javascript per rilevare impostazioni specifiche del browser. Poiché javascript non viene usato per creare il beacon immagine su dispositivi mobili, i dati raccolti dagli utenti mobili non sono inclusi in questi report.
