---
description: Condizioni determinano quando viene attivata una regola basata su eventi.
keywords: Gestione tag dinamica; rule; create rule; new rule; regola basata su eventi; ritardare l'attivazione dei collegamenti; applicare il gestore di eventi direttamente all'elemento; bubbling; evento di bubbling
seo-description: Condizioni determinano quando viene attivata una regola basata su eventi.
seo-title: Creare condizioni per le regole basate su eventi
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Creare condizioni per le regole basate su eventi
uuid: a 847391 c -5 aec -4 d 64-8 a 35-388587731598
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Creare condizioni per le regole basate su eventi

Condizioni determinano quando viene attivata una regola basata su eventi.

1. Selezionare il tipo di interazione da tracciare, ad esempio clic del mouse, o inviare un modulo.

   ![](assets/condition-event-based.png)

   For more information, see [Event Types](https://marketing.adobe.com/resources/help/en_US/dtm/event_types.html) in the Adobe Tag Management Product Documentation.

1. Attivate le opzioni seguenti, a seconda delle necessità:

   | Elemento | Descrizione |
   |--- |--- |
   | Ritardo collegamento collegamento | Attivate se l'evento attiva un collegamento e desiderate che il collegamento sia ritardato finché l'evento non avrà il tempo di attivarlo. |
   | Applica il gestore di eventi direttamente all'elemento | Applica il gestore di eventi all'elemento specifico con targeting. Questa impostazione è legata al concetto di bubbling e layering in un browser. |

   For example, when you click an image inside an anchor tag like `<a href="abc.html"><img src="xyz.png"/></a>`, you might expect the click to be associated with the anchor tag, because the tag is in the bubble stream. However, when you inspect the click in the developer tools, the click may actually affect only the `<img>` tag. To ensure that the event is handled correctly, associate the click with the `<img>` tag and do not depend on the browser to bubble up the click to a parent element. An event like a click can potentially bubble up to `<body>`. È importante comprendere in che punto l'evento è effettivamente associato e come destinazione è specificamente necessario che la regola venga attivato correttamente.

   *Lo strumento di bubbling* significa che l'evento viene acquisito e gestito per la prima volta dall'elemento interno e quindi trasmesso agli elementi esterni.

1. Indica il nome del tag da tracciare e altre proprietà a cui desiderate associare il tag.

   ![](assets/condition-event-based2.png)

   See [Using the CSS Selector](https://marketing.adobe.com/resources/help/en_US/dtm/css-selector.html) in the Dynamic Tag Management Product Documentation for information about finding the correct element tag.

1. Selezionare e impostare eventuali criteri o tipi di condizione aggiuntivi da associare alla regola.

   ![](assets/condition-event-based3.png)

1. Indicate la preferenza relativa al bubbling degli eventi.

   La bubbling degli eventi è una modalità di propagazione eventi nel DOM HTML.

   | Se si… | Selezionate questa opzione |
   |--- |--- |
   | Desiderate interazioni correlate sugli elementi secondari del selettore della regola identificato per attivare la regola. | Consente la bolla degli eventi sugli elementi secondari. |
   | Desiderate evitare il bubbling quando l'elemento secondario attiva già un proprio evento. | Non consentite se l'elemento secondario ha già un evento. |
   | Non desiderate che gli eventi del selettore della regola che avete identificato vadano oltre l'elemento stesso nella gerarchia dell'evento. | Non consentite agli eventi di passare in alto agli elementi principali. |
