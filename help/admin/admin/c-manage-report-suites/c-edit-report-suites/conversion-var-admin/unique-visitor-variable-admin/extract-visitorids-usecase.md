---
description: Data Warehouse fornisce una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere queste informazioni, l’esempio seguente è un collegamento per generare una richiesta Data Warehouse.
title: 'Caso di utilizzo: estrazione degli ID visitatore'
feature: Admin Tools
role: Admin
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 0%

---

# Caso di utilizzo: estrazione degli ID visitatore

Data Warehouse fornisce una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere queste informazioni, l’esempio seguente è un collegamento per generare una richiesta Data Warehouse.

Ad esempio, supponiamo che la tua azienda invii e-mail di marketing a clienti e potenziali clienti. Ognuno di questi destinatari di posta elettronica dispone di un ID univoco nel sistema di posta elettronica, ad esempio *`EMAIL Contact ID`*. I messaggi di posta elettronica vengono configurati in modo che, quando i contatti ricevono un messaggio di posta elettronica e fanno clic su uno dei collegamenti, il visitatore arrivi al sito Web con un ID campagna e un ID contatto e-mail univoco. Ad esempio, il collegamento di posta elettronica potrebbe risolvere i seguenti problemi:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

Impostandole nelle variabili di conversione (eVar) puoi vedere le prestazioni di ogni e-mail (tramite l’ID campagna) e la frequenza con cui ogni destinatario ha visitato il sito (tramite l’ID contatto E-mail).

Supponiamo che tu stia acquisendo questi ID. La maggior parte degli esperti di marketing vuole segmentare il comportamento dei siti web e vedere se può effettuare il remarketing per coloro che soddisfano determinati criteri. Ad esempio, potrebbe essere utile inviare un messaggio di posta elettronica di remarketing a tutti i destinatari di posta elettronica che sono arrivati al sito tramite il messaggio di posta elettronica e hanno visualizzato (o completato) un modulo del sito Web. A questo scopo, trova un modo per identificare gli ID di contatto e-mail di coloro che hanno completato il modulo specifico.

Un modo per farlo è utilizzare un rapporto di relazione secondaria di conversione per suddividere il valore eVar ID modulo per l’eVar ID contatto e-mail. Tuttavia, è disponibile una funzione predefinita per questa operazione utilizzando Data Warehouse. Questa funzione ti consente di sapere quale eVar memorizza gli ID utente univoci (in questo caso l’ID contatto e-mail) e di estrarre facilmente tali ID utilizzando Data Warehouse. Utilizzando questa funzione, puoi creare automaticamente una richiesta di data warehouse che richiama gli ID visitatore univoci per i quali sei interessato.
