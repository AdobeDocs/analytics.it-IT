---
description: Data Warehouse offre una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID di cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere queste informazioni, l'esempio seguente è un collegamento per la generazione di una richiesta Data Warehouse.
solution: Analytics
title: 'Caso di utilizzo: estrazione degli ID visitatore'
topic: Admin tools
uuid: ed228334-619c-43d7-b781-a18af73b00bb
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Caso di utilizzo: estrazione degli ID visitatore

Data Warehouse offre una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID di cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere queste informazioni, l'esempio seguente è un collegamento per la generazione di una richiesta Data Warehouse.

Ad esempio, supponiamo che la tua azienda invii e-mail di marketing a clienti e potenziali clienti. Ciascun destinatario ha un ID univoco nel sistema e-mail (ad esempio *`EMAIL Contact ID`*). Le e-mail vengono configurate in modo che quando i contatti ricevono un messaggio e-mail e fanno clic su uno dei relativi collegamenti, il visitatore arrivi sul sito Web con un ID campagna e un ID contatto e-mail univoco. Ad esempio, il collegamento e-mail potrebbe essere:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

L’impostazione di queste variabili di conversione (eVar) consente di visualizzare le prestazioni di ogni e-mail (tramite l’ID della campagna) e la frequenza con cui ciascun destinatario e-mail ha visitato il sito (tramite l’ID del contatto e-mail).

Supponete che stiate acquisendo questi ID. La maggior parte degli esperti di marketing desidera segmentare il proprio comportamento nei siti Web e quindi vedere se possono rivendere il mercato a coloro che soddisfano determinati criteri. Ad esempio, potrebbe essere utile inviare un'e-mail di ricommercializzazione a tutti i destinatari di posta elettronica che sono venuti sul sito dall'e-mail e hanno visualizzato (o completato) un modulo del sito Web. A tal fine, è possibile identificare gli ID di contatto e-mail di coloro che compilano il modulo specifico.

Un modo per farlo è utilizzare un rapporto Conversione Subrelation per suddividere il valore eVar ID modulo tramite eVar ID contatto eMAIL. Tuttavia, è disponibile una funzione precostruita per farlo utilizzando Data Warehouse. Questa funzione consente di individuare l'eVar che memorizza gli ID utente univoci (in questo caso l'ID contatto e-mail) e di estrarre facilmente tali ID utilizzando il data warehouse. Utilizzando questa funzione, puoi creare automaticamente una richiesta data warehouse che richiama gli ID visitatore univoci per i quali sei interessato.
