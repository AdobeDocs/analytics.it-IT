---
description: Quando un utente visita il sito, un cookie permanente viene impostato dal server Web Adobe inserendolo nella risposta HTTP al browser. Questo cookie viene impostato sul dominio di raccolta dati specificato.
keywords: Implementazione di Analytics
seo-description: Quando un utente visita il sito, un cookie permanente viene impostato dal server Web Adobe inserendolo nella risposta HTTP al browser. Questo cookie viene impostato sul dominio di raccolta dati specificato.
seo-title: ID visitatore Analytics
solution: Analytics
title: ID visitatore Analytics
topic: Sviluppatore e implementazione
uuid: fa 7737 cc -0190-4 d 27-af 1 b -87301 a 715 df 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID visitatore Analytics

Quando un utente visita il sito, un cookie permanente viene impostato dal server Web Adobe inserendolo nella risposta HTTP al browser. Questo cookie viene impostato sul dominio di raccolta dati specificato.

When a request is sent to the Adobe data collection server, the header is checked for the visitor ID cookie ( `s_vi`). Se il cookie è presente nella richiesta, viene utilizzato per identificare il visitatore. Se il cookie non è presente nella richiesta, il server genera un ID visitatore univoco, lo imposta come cookie nell'intestazione della risposta HTTP e lo invia nuovamente insieme alla richiesta. Il cookie viene memorizzato nel browser e viene inviato nuovamente al server di raccolta dati durante le successive visite al sito, che consente al visitatore di essere identificato nelle visite.

## Third-Party Cookies and CNAME records {#section_61BA46E131004BB2B75929C1E1C93139}

Alcuni browser, come Apple Safari, non memorizzano più i cookie impostati nell'intestazione HTTP dai domini che non corrispondono al dominio del sito Web corrente (si tratta di un cookie utilizzato in un contesto di terze parti o di un cookie di terze parti). For example, if you are on `mysite.com` and your data collection server is `mysite.omtrdc.net`, the cookie that is returned in the HTTP header from `mysite.omtrdc.net` might be rejected by the browser.

To avoid this, many customers have implemented CNAME records for their data collection servers as part of a [first-party cookie implementation](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). If a CNAME record is configured to map a hostname on the customer's domain to the data collection server (for example, mapping `metrics.mysite.com` to `mysite.omtrdc.net`), the visitor ID cookie is stored since the data collection domain now matches the domain of the website. Questo aumenta la probabilità che il cookie ID visitatore venga memorizzato, ma introduce un sovraccarico in quanto è necessario configurare i record CNAME e gestire i certificati SSL per i server di raccolta dati.

## Cookies on Mobile Devices {#section_7D05AE259E024F73A95C48BD1E419851}

Quando i dispositivi mobili vengono tracciati utilizzando i cookie, è possibile utilizzare alcune impostazioni per modificare il modo in cui si verifica la misurazione. Cookie default lifetime is 5 years, but you can use the CL query param variable ( `s.cookieLifetime`) to change this default. To set the cookie location for cname implementations, use the CDP query string `s.cookieDomainPeriods`. Il valore predefinito è 2 se non viene specificato alcun valore. e il percorso predefinito è domain. com. Per le implementazioni che non utilizzano CNAME, la posizione del cookie ID visitatore si trova nel dominio 207. net.
