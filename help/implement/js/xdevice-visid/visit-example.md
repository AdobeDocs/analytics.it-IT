---
description: Esempio contenente un esempio di chiamate server inviate in un’interazione con il cliente comune.
keywords: Implementazione di Analytics
subtopic: Visitors
title: Esempio di identificazione dei visitatori cross-device
feature: Implementation Basics
exl-id: c68bb745-29de-48e3-8731-d714503a2447
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 8%

---

# Esempio di identificazione dei visitatori cross-device

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra i dispositivi non è più consigliato. Consulta [Analytics tra dispositivi](/help/components/cda/overview.md) nella guida utente Componenti.

L’esempio seguente illustra il funzionamento dell’identificazione dei visitatori cross-device utilizzando un esempio di chiamate al server inviate in un’interazione con il cliente comune.

| Chiamata server | Azione | Cookie ID visitatore | Variabile ID visitatore | ID visitatore effettivo | Numero di pagina visita | Numero di visite |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visitatore fa clic su un collegamento in un’e-mail di marketing e visita il sito dal computer di casa. Questo visitatore ha visitato il tuo sito altre 7 volte in passato. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita altre 7 pagine del sito. | 1 | - | 1 | 2-8 | 8 |
| 9 | Autentica nel computer di casa. | 1 | CID1 | CID1 | 9 <br>Questo è il primo hit di CID1 in assoluto, quindi subentra e continua sul profilo del visitatore da ID visitatore 1. | 8 |
| 10 | Visita 1 pagina aggiuntiva. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Apre il sito dal laptop in ufficio. Il visitatore non ha visitato il tuo sito prima di utilizzare questo dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | Autentica su notebook. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualizza 1 pagina aggiuntiva. | 2 | CID1 | CID1 | 2 | 9 |

## Conteggio delle visite

Analytics conta una visita ogni volta che vede un hit con un numero di pagina di visita uguale a 1.

Utilizzando la tabella precedente, è stata conteggiata una nuova visita 4 volte: negli hit 1, 9, 11 e 12.

## Conteggio dei visitatori

Analytics conta ogni ID visitatore effettivo univoco come visitatore univoco.

Utilizzando la tabella precedente, un nuovo visitatore è stato conteggiato 3 volte: negli hit 1, 9 e 10.

Quando utilizzi l’identificazione dei visitatori cross-device, il numero di visitatori univoci visibili può aumentare. Il visitatore può essere conteggiato due volte nella stessa visita: una volta per la visita iniziale e di nuovo dopo che l’utente è autenticato.

![](assets/visitors.png)

Dopo l’associazione iniziale, i conteggi delle visite tornano alla normalità perché il visitatore è associato tramite il suo cookie del browser. Se il visitatore in un secondo momento visualizza il sito e poi si autentica, il conteggio dei visitatori non viene gonfiato perché l’ID visitatore effettivo non cambia dopo l’autenticazione.

![](assets/visitors_2.png)

Assicurati di essere il più coerente possibile nell’identificazione dei visitatori univoci. Ad esempio, utilizza sempre `visitorID` quando l’utente è autenticato.
