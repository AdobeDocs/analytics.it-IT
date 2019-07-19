---
description: Esempio contenente un esempio di chiamate server inviate in un'interazione comune del cliente.
keywords: Implementazione di Analytics
seo-description: Esempio contenente un esempio di chiamate server inviate in un'interazione comune del cliente.
seo-title: Visita di esempio
solution: Analytics
subtopic: Visitatori
title: Visita di esempio
topic: Sviluppatore e implementazione
uuid: bc 5 f 8 f 56-52 e 3-42 d 8-af 1 a -7 f 5 c 7 b 9496 c 0
translation-type: tm+mt
source-git-commit: 67cc404c4502b1b7be3f089538d8a28d5cf7f659

---


# Visita di esempio

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori su dispositivi non è più consigliato. Please refer to the [Adobe Experience Cloud Device Co-op Documentation](https://marketing.adobe.com/resources/help/en_US/mcdc/).

Esempio contenente un esempio di chiamate server inviate in un'interazione comune del cliente.

| Chiamata server | Azione | Cookie ID visitatore | Variabile ID visitatore | ID visitatore effettivo | Numero pagina visita | Numero visita |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visitatore fa clic su un collegamento in un messaggio e-mail di marketing e accede al sito dal computer di casa. Questo visitatore ha visitato il sito 7 volte in passato. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita altre 7 pagine sul sito. | 1 | - | 1 | 2-8 | 8 |
| 9 | Esegue l'autenticazione sul computer principale. | 1 | CID1 | CID1 | 9 <br>This is CID1's first hit ever, so it takes over and continues on the visitor profile from Visitor ID 1.</br> | 8 |
| 10 | Visits 1 additional page. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Apre il sito dal laptop in ufficio. Questo visitatore non ha visitato il sito prima di usare il dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | Esegue l'autenticazione su laptop. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualizza 1 pagina aggiuntiva. | 2 | CID1 | CID1 | 2 | 9 |