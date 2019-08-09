---
description: Se hai selezionato il metodo di raccolta dei dati javascript, copiate le seguenti righe di codice e aggiungili al codice Adobe Analytics sulle pagine.
seo-description: Se hai selezionato il metodo di raccolta dei dati javascript, copiate le seguenti righe di codice e aggiungili al codice Adobe Analytics sulle pagine.
seo-title: Adobe Analytics Plug-in
title: Adobe Analytics Plug-in
uuid: b 10345 ba -1 e 80-4 e 5 c-af 87-6 e 6 a 9 dc 87 c 00
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Adobe Analytics Plug-in{#adobe-analytics-plug-in-code}

Se hai selezionato il metodo di raccolta dei dati javascript, copiate le seguenti righe di codice e aggiungili al codice Adobe Analytics sulle pagine.

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

>[!NOTE]
>
>Il plug-plugin sopra presuppone che alcune variabili di commerce personalizzate (evar) siano disponibili. Se le variabili specificate nel plug-plugin sopra non sono disponibili nella distribuzione Adobe Analytics, sostituitele semplicemente con quelle disponibili.

