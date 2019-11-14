---
description: Esempio contenente un esempio di chiamate server inviate in una comune interazione con il cliente.
keywords: Analytics Implementation
solution: Analytics
subtopic: Visitors
title: Visita di esempio
topic: Developer and implementation
uuid: bc5f8f56-52e3-42d8-af1a-7f5c7b9496c0
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Visita di esempio

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Fai riferimento alla documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcdc/)Adobe Experience Cloud Device Co-op.

Esempio contenente un esempio di chiamate server inviate in una comune interazione con il cliente.

| Chiamata server | Azione | Cookie ID visitatore | Variabile ID visitatore | ID visitatore effettivo | Numero pagina visita | Numero visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visitatore fa clic su un collegamento in un messaggio e-mail di marketing e visita il sito dal computer di casa. Questo visitatore ha visitato il sito 7 altre volte in passato. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita 7 pagine aggiuntive sul tuo sito. | 1 | - | 1 | 2-8 | 8 |
| 9 | Effettua l'autenticazione sul computer di casa. | 1 | CID1 | CID1 | 9 <br>Questo è il primo hit di CID1 in assoluto, quindi prende il sopravvento e continua sul profilo del visitatore dall'ID visitatore 1.</br> | 8 |
| 10 | Visita 1 pagina aggiuntiva. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Apre il sito dal laptop in ufficio. Il visitatore non ha visitato il sito prima di utilizzare questo dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | Effettua l'autenticazione sul laptop. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualizzazioni 1 pagina aggiuntiva. | 2 | CID1 | CID1 | 2 | 9 |
