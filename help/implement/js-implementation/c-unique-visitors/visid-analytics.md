---
description: Quando un utente visita il sito, un cookie permanente viene impostato dal server Web Adobe includendo il cookie nella risposta HTTP al browser. Questo cookie viene impostato sul dominio di raccolta dati specificato.
keywords: Analytics Implementation
solution: Analytics
title: ID visitatore Analytics
topic: Developer and implementation
uuid: fa7737cc-0190-4d27-af1b-87301a715df2
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# ID visitatore Analytics

Quando un utente visita il sito, un cookie permanente viene impostato dal server Web Adobe includendo il cookie nella risposta HTTP al browser. Questo cookie viene impostato sul dominio di raccolta dati specificato.

When a request is sent to the Adobe data collection server, the header is checked for the visitor ID cookie ( `s_vi`). Se il cookie è presente nella richiesta, viene utilizzato per identificare il visitatore. Se il cookie non è presente, il server genera un ID visitatore univoco, lo imposta come cookie nell’intestazione della risposta HTTP e lo invia nuovamente insieme alla richiesta. Il cookie viene memorizzato nel browser e inviato nuovamente al server di raccolta dati durante le visite successive al sito, consentendo al visitatore di essere identificato attraverso le visite.

## Record di cookie e CNAME di terze parti {#section_61BA46E131004BB2B75929C1E1C93139}

Alcuni browser, come Apple Safari, non memorizzano più i cookie impostati nell’intestazione HTTP da domini che non corrispondono al dominio del sito Web corrente (si tratta di un cookie utilizzato in un contesto di terze parti o di un cookie di terze parti). Ad esempio, se accedi a `mysite.com` e il server di raccolta dati è `mysite.omtrdc.net` il cookie restituito nell'intestazione HTTP da `mysite.omtrdc.net` potrebbe essere rifiutato dal browser.

Per evitare questo problema, molti clienti hanno implementato record CNAME per i propri server di raccolta dati nell'ambito di un'implementazione [di cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/)di prime parti. If a CNAME record is configured to map a hostname on the customer's domain to the data collection server (for example, mapping `metrics.mysite.com` to `mysite.omtrdc.net`), the visitor ID cookie is stored since the data collection domain now matches the domain of the website. Questo aumenta la probabilità che il cookie dell’ID visitatore venga memorizzato, ma introduce alcuni overhead in quanto è necessario configurare i record CNAME e mantenere i certificati SSL per i server di raccolta dati.

## Cookie su dispositivi mobili {#section_7D05AE259E024F73A95C48BD1E419851}

Quando i dispositivi mobili vengono tracciati utilizzando i cookie, è possibile utilizzare alcune impostazioni per modificare il modo in cui si verifica la misurazione. La durata predefinita del cookie è di 5 anni, ma è possibile utilizzare la variabile param della query CL ( `s.cookieLifetime`) per modificare questa impostazione predefinita. Per impostare la posizione del cookie per le implementazioni del nome, utilizzate la stringa di query CDP `s.cookieDomainPeriods`. Il valore predefinito è 2 se non viene specificato alcun valore. e il percorso predefinito è domain.com. Per le implementazioni che non utilizzano CNAME, il percorso del cookie dell’ID visitatore si trova nel dominio 207.net.
