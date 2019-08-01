---
description: Se hai selezionato il metodo di raccolta dei dati javascript, copiate le seguenti righe di codice e aggiungili al codice Adobe Analytics sulle pagine.
seo-description: Se hai selezionato il metodo di raccolta dei dati javascript, copiate le seguenti righe di codice e aggiungili al codice Adobe Analytics sulle pagine.
seo-title: Adobe Analytics Plug-in
title: Adobe Analytics Plug-in
uuid: 60 d 80366-d 144-465 a-b 3 de-acc 2341 be 1 cd
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 191c2add5b6762181ff669fddea3e4aa559a5044

---


# Adobe Analytics Plug-In Code {#adobe-analytics-plug-in-code}

Se hai selezionato il metodo di raccolta dei dati javascript, copiate le seguenti righe di codice e aggiungili al codice Adobe Analytics sulle pagine.

`/*`

`* Plugin: getQueryParam 2.3`

`*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");`

`/*in the s_doPlugins function`

`s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable`

>[!NOTE]
>
>Il plug-plugin sopra presuppone che alcune variabili di commerce personalizzate (evar) siano disponibili. Se le variabili specificate nel plug-plugin sopra non sono disponibili nella distribuzione Adobe Analytics, sostituitele semplicemente con quelle disponibili.

