---
description: Le condizioni determinano quando viene attivata una regola basata sugli eventi.
keywords: Dynamic Tag Management;rule;create rule;new rule;event-based rule;delay link activation;apply event handler directly to element;bubbling;event bubbling
solution: Experience Cloud,Analytics,Target
title: Creare condizioni per le regole basate su eventi
uuid: a847391c-5aec-4d64-8a35-388587731598
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 2%

---


# Creare condizioni per le regole basate su eventi

Le condizioni determinano quando viene attivata una regola basata sugli eventi.

1. Selezionare il tipo di interazione da monitorare, ad esempio i clic del mouse o l&#39;invio di un modulo.

   ![](assets/condition-event-based.png)

   Per ulteriori informazioni, consulta Tipi [di](https://docs.adobe.com/content/help/en/dtm/using/resources/rules/t-rules-event-conditions.html) eventi nella Documentazione prodotto Gestione tag  Adobe.

1. Se necessario, abilitate le seguenti opzioni:

   | Elemento | Descrizione |
   |--- |--- |
   | Ritardo attivazione collegamento | Selezionate questa opzione se l’evento attiva un collegamento e desiderate che il collegamento ritardi fino a quando l’evento non ha tempo per essere attivato. |
   | Applicare il gestore eventi direttamente all&#39;elemento | Applica il gestore eventi all&#39;elemento specifico di destinazione. Questa impostazione è legata al concetto di generazione di bolle e livelli in un browser. |

   Ad esempio, quando si fa clic su un&#39;immagine all&#39;interno di un tag di ancoraggio come `<a href="abc.html"><img src="xyz.png"/></a>`, è possibile che il clic sia associato al tag di ancoraggio, perché il tag si trova nel flusso delle bolle. Tuttavia, quando ispezionate il clic negli strumenti di sviluppo, il clic potrebbe influenzare solo il `<img>` tag. Per garantire che l’evento venga gestito correttamente, associate il clic con il `<img>` tag e non dipendono dal browser per visualizzare il clic su un elemento padre. Un evento come un clic può potenzialmente generare un effetto `<body>`. È importante capire dove l&#39;evento è effettivamente associato, ed eseguire il targeting specifico per assicurarsi che la regola venga attivata correttamente.

   *Bubbling* significa che l’evento viene catturato e gestito per la prima volta dall’elemento più interno e quindi propagato agli elementi esterni.

1. Indicate il nome del tag da monitorare e altre proprietà a cui il tag deve corrispondere.

   ![](assets/condition-event-based2.png)

   Consultate [Utilizzo del selettore](https://docs.adobe.com/content/help/en/dtm/using/resources/rules/t-rules-event-conditions.html#concept_DDF500DCB8214658AEDECDE69ED1D4AF) CSS nella Documentazione prodotto Gestione tag dinamica per informazioni su come trovare il tag elemento corretto.

1. Selezionare e impostare eventuali criteri o tipi di condizioni aggiuntivi da associare alla regola.

   ![](assets/condition-event-based3.png)

1. Indicate le preferenze per quanto riguarda il bollo degli eventi.

   Il bubbling degli eventi è uno dei metodi di propagazione degli eventi nel DOM HTML.

   | Se tu... | Selezionare questa opzione |
   |--- |--- |
   | Desiderate interazioni correlate su elementi secondari del selettore di regole identificato per attivare la regola. | Consente la generazione di eventi su elementi figlio. |
   | Si desidera evitare la generazione di bolle quando l&#39;elemento figlio attiva già un proprio evento. | Non consentire se l&#39;elemento figlio attiva già l&#39;evento. |
   | Non si desidera che gli eventi del selettore di regole identificato vadano oltre l&#39;elemento stesso nella gerarchia degli eventi. | Non consentire che gli eventi si propaghino ai genitori. |
