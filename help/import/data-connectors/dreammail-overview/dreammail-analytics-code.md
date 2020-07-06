---
description: Se hai selezionato il metodo di raccolta dati del plug-in JavaScript, copia le righe di codice seguenti e aggiungili al codice Analytics  presente sulle pagine.
title: Codice plug-in di Analytics
uuid: c75a6cd2-ee7a-4c2f-98a8-4618d0617b4f
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 6%

---


# Codice plug-in di Analytics{#analytics-plug-in-code}

Se hai selezionato il metodo di raccolta dati del plug-in JavaScript, copia le righe di codice seguenti e aggiungili al codice Analytics  presente sulle pagine.

`/*`

`* Plugin: getQueryParam 2.3`

```
*/ s.getQueryParam=new Function("p","d","u","" +"var s=this,v='',i,t;d=d?d:'';u=u?u:(s.pageURL?s.pageURL:s.wd.locati" +"on);if(u=='f')u=s.gtfs().location;while(p){i=p.indexOf(',');i=i<0?p" +".length:i;t=s.p_gpv(p.substring(0,i),u+'');if(t){t=t.indexOf('#')>-" +"1?t.substring(0,t.indexOf('#')):t;}if(t)v+=v?d+t:t;p=p.substring(i=" +"=p.length?i:i+1)}return v"); s.p_gpv=new Function("k","u","" +"var s=this,v='',i=u.indexOf('?'),q;if(k&&i>-1){q=u.substring(i+1);v" +"=s.pt(q,'&','p_gvf',k)}return v"); s.p_gvf=new Function("t","k","" +"if(t){var s=this,i=t.indexOf('='),p=i<0?t:t.substring(0,i),v=i<0?'T" +"rue':t.substring(i+1);if(p.toLowerCase()==k. oLowerCase())return s." +"epa(v)}return ''");
```

`/*in the s_doPlugins function`

```
s.campaign=s.getQueryParam("ET_CID"); //places query param value from cid in campaign variable s.eVar2=s.getQueryParam("ET_RID"); //places query param value from rid in eVar2 variable
```

>[!NOTE]
>
>Il plug-in di cui sopra presuppone la disponibilità di alcune variabili di commercio personalizzate (eVar). Se le variabili specificate nel plug-in sopra non sono disponibili nella distribuzione Analytics , sostituitele semplicemente con quelle disponibili.
