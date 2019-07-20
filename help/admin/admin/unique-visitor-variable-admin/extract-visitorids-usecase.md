---
description: Data Warehouse fornisce una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere tali informazioni, l'esempio seguente è una scelta rapida per generare una richiesta Data Warehouse.
seo-description: Data Warehouse fornisce una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere tali informazioni, l'esempio seguente è una scelta rapida per generare una richiesta Data Warehouse.
seo-title: Caso d'uso - Estrazione degli ID visitatore
solution: Analytics
title: Caso d'uso - Estrazione degli ID visitatore
topic: Strumenti di amministrazione
uuid: ed 228334-619 c -43 d 7-b 781-a 18 af 73 b 00 bb
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caso d'uso - Estrazione degli ID visitatore

Data Warehouse fornisce una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere tali informazioni, l'esempio seguente è una scelta rapida per generare una richiesta Data Warehouse.

Ad esempio, si supponga che la tua attività invia e-mail marketing a clienti e potenziali clienti. Each of these e-mail recipients has a unique ID in your e-mail system (such as *`EMAIL Contact ID`*). Configurate le e-mail in modo che, quando i contatti ricevono un messaggio e-mail e fate clic su uno dei collegamenti, il visitatore arrivi al vostro sito Web con un ID campagna e un ID contatto univoco e-mail. Ad esempio, il collegamento e-mail può risolvere:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

L'impostazione delle variabili di conversione (evars) consente di vedere il modo in cui ogni e-mail viene eseguita (tramite l'ID della campagna) e la frequenza con cui ogni destinatario e-mail ha visitato il sito (tramite l'ID contatto e-mail).

Immagina di acquisire questi ID. La maggior parte degli esperti di marketing desiderano segmentare il comportamento del sito Web e quindi verificare se possono reimmettere il mercato a coloro che soddisfano determinati criteri. Ad esempio, potrebbe essere necessario inviare un messaggio e-mail di ricommercializzazione a tutti i destinatari che hanno inviato il messaggio e-mail dal sito e che hanno visualizzato (o completato) un modulo Web. A tal fine, è possibile identificare gli ID contatto e-mail di coloro che hanno completato il modulo specifico.

Un modo per farlo consiste nell'utilizzare un report della sottorelazione conversione per suddividere il valore evar di ID modulo tramite l'evar ID contatto e-mail. Tuttavia, per farlo è disponibile una funzione già creata con Data Warehouse. Questa funzione consente di sapere quale evar memorizza gli ID utente univoci (ID contatto e-mail in questo caso) e ti consente di estrarre facilmente tali ID tramite data warehouse. Utilizzando questa funzione, puoi creare automaticamente una richiesta data warehouse che estrae gli ID visitatore unici di interesse.
