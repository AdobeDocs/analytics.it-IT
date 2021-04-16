---
description: Data Warehouse fornisce una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere queste informazioni, l'esempio seguente è un collegamento per generare una richiesta di Data Warehouse.
title: 'Caso di utilizzo: estrazione degli ID visitatore'
feature: Strumenti di amministrazione
uuid: ed228334-619c-43d7-b781-a18af73b00bb
exl-id: b1fc41af-31c7-42cd-aab7-0c659577781d
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 3%

---

# Caso di utilizzo: estrazione degli ID visitatore

Data Warehouse fornisce una funzione che consente di estrarre un elenco di ID visitatore. Questi ID non sono ID cookie, ma ID acquisiti in una delle variabili di conversione. Anche se esistono altri modi per ottenere queste informazioni, l&#39;esempio seguente è un collegamento per generare una richiesta di Data Warehouse.

Ad esempio, supponiamo che la tua azienda invii e-mail di marketing a clienti e potenziali clienti. Ciascuno di questi destinatari di posta elettronica dispone di un ID univoco nel sistema di posta elettronica (ad esempio *`EMAIL Contact ID`*). Hai impostato le tue e-mail in modo che quando i contatti ricevono un&#39;e-mail e fanno clic su uno dei loro collegamenti, il visitatore arrivi al tuo sito web con un ID campagna e un ID contatto e-mail univoco. Ad esempio, il collegamento e-mail potrebbe risolvere i seguenti problemi:

```js
https://www.test.com/?cid=springmailblast&mid=1363660158
```

L’impostazione di queste variabili di conversione (eVar) consente di vedere le prestazioni di ogni e-mail (tramite l’ID della campagna) e la frequenza con cui ciascun destinatario e-mail ha visitato il sito (tramite l’ID del contatto e-mail).

Supponi di acquisire questi ID. La maggior parte degli esperti di marketing desidera segmentare il proprio comportamento sui siti web e quindi vedere se possono recommercializzare con coloro che soddisfano determinati criteri. Ad esempio, potresti voler inviare un’e-mail di remarketing a tutti i destinatari di e-mail che sono venuti sul tuo sito dall’e-mail e hanno visualizzato (o completato) un modulo web. A questo scopo, trova un modo per identificare gli ID dei contatti e-mail di coloro che compilano il modulo specifico.

Un modo per farlo è utilizzare un rapporto Subrelation conversione per suddividere il valore di eVar ID modulo tramite l’eVar ID contatto e-mail. Tuttavia, è disponibile una funzione predefinita per eseguire questa operazione utilizzando Data Warehouse. Questa funzione ti consente di sapere quali eVar memorizza gli ID utente univoci (in questo caso EMAIL Contact ID) e di estrarre facilmente tali ID utilizzando il data warehouse. Utilizzando questa funzione, puoi creare automaticamente una richiesta di data warehouse che richiama gli ID visitatore univoci di cui sei interessato.
