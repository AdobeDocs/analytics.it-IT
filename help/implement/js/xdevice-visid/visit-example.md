---
description: Esempio contenente un esempio di chiamate server inviate in una comune interazione con il cliente.
keywords: Implementazione di Analytics
subtopic: Visitors
title: Esempio di identificazione dei visitatori tra i dispositivi
feature: Implementation Basics
exl-id: c68bb745-29de-48e3-8731-d714503a2447
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 11%

---

# Esempio di identificazione dei visitatori tra i dispositivi

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Vedi [Analisi multidispositivo](/help/components/cda/overview.md) nella guida utente Componenti .

L’esempio seguente illustra il funzionamento dell’identificazione dei visitatori tra dispositivi tramite un esempio di chiamate server inviate in una comune interazione con il cliente.

| Chiamata server | Azione | Cookie ID visitatore | Variabile ID visitatore | ID visitatore effettivo | Numero pagina visita | Numero di visite |
|--- |--- |--- |--- |--- |--- |--- |
| 1 | Un visitatore fa clic su un collegamento in un’e-mail di marketing e visita il sito dal computer di origine. Questo visitatore ha visitato il tuo sito 7 altre volte in passato. | 1 | - | 1 | 1 | 8 |
| 2-8 | Visita 7 pagine aggiuntive sul tuo sito. | 1 | - | 1 | 2-8 | 8 |
| 9 | Esegue l&#39;autenticazione nel computer di casa. | 1 | CID1 | CID1 | 9 <br>(Questo è il primo hit di CID1 in assoluto, quindi prende il sopravvento e continua sul profilo del visitatore da ID visitatore 1.) | 8 |
| 10 | Visita 1 pagina aggiuntiva. | 1 | CID1 | CID1 | 10 | 8 |
| 11 | Apre il sito da laptop in ufficio. Questo visitatore non ha visitato il sito prima di utilizzare questo dispositivo. | 2 | - | 2 | 1 | 1 |
| 12 | Esegue l&#39;autenticazione sul laptop. | 2 | CID1 | CID1 | 1 | 9 |
| 13 | Visualizza 1 pagina aggiuntiva. | 2 | CID1 | CID1 | 2 | 9 |

## Conteggio delle visite

Analytics conta una visita ogni volta che vede un hit con un numero di pagina di visita uguale a 1.

Utilizzando la tabella precedente, una nuova visita è stata conteggiata 4 volte: sugli hit 1, 9, 11 e 12.

## Conteggio dei visitatori

Analytics conta ogni ID visitatore effettivo univoco come visitatore univoco.

Utilizzando la tabella precedente, un nuovo visitatore è stato conteggiato 3 volte: sugli hit 1, 9 e 10.

Quando utilizzi l’identificazione incrociata dei visitatori con più dispositivi, puoi aumentare il numero di visitatori univoci che visualizzi. Il visitatore può essere conteggiato due volte nella stessa visita: una volta per la visita iniziale e una volta che l’utente è autenticato.

![](assets/visitors.png)

Dopo l’associazione iniziale, il conteggio delle visite torna alla normalità perché il visitatore è associato tramite il cookie del browser. Se il visitatore visualizza in un secondo momento il sito e quindi si autentica, il conteggio dei visitatori non si gonfia perché l&#39;ID visitatore effettivo non cambia dopo l&#39;autenticazione.

![](assets/visitors_2.png)

Assicurati di essere il più coerente possibile quando identifichi i visitatori univoci. Ad esempio, utilizza sempre il `visitorID` quando l&#39;utente è autenticato.
