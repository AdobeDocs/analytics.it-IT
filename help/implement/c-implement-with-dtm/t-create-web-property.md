---
description: Una proprietà Web può essere un qualsiasi raggruppamento di uno o più domini e sottodomini con una libreria di regole, inclusa in un codice da incorporare.
keywords: Implementazione di Analytics; metodo di implementazione; gestione tag dinamica; dtm; Web, proprietà; property
seo-description: Una proprietà Web può essere un qualsiasi raggruppamento di uno o più domini e sottodomini con una libreria di regole, inclusa in un codice da incorporare.
seo-title: Crea proprietà Web
solution: Analytics
title: Crea proprietà Web
topic: Sviluppatore e implementazione
uuid: f 19 d 5504-eb 44-4 d 93-a 387-7470 ab 4 b 3 a 3 a
translation-type: tm+mt
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Crea proprietà Web

Una proprietà Web può essere un qualsiasi raggruppamento di uno o più domini e sottodomini con una libreria di regole, inclusa in un codice da incorporare.

>[!NOTE]
>
>Solo un utente con diritti di amministratore può creare una proprietà. For more information about roles, see [Create and Manage Groups in DTM](https://marketing.adobe.com/resources/help/en_US/dtm/groups.html) in the Dynamic Tag Management Product Documentation.

Puoi gestire e tenere traccia di queste risorse con Gestione dinamica dei tag. Ad esempio, supponete di disporre di più siti Web basati su un modello e di tenere traccia delle stesse risorse su tutti questi siti Web. Puoi applicare una proprietà Web a più domini.

For general information about web properties and best practices, see [Web Properties](https://marketing.adobe.com/resources/help/en_US/dtm/web_property.html) in the Dynamic Tag Management Product Documentation.

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

   ![](assets/dtm-create-web-property.png)

1. Compila i campi:

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elemento </th> 
    <th colname="col2" class="entry"> Descrizione </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nome</span> </td> 
    <td colname="col2"> <p>Nome della proprietà. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>L'URL di base della proprietà. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Questo sito si estende su più domini </span> </td> 
    <td colname="col2"> <p>Puoi aggiungere e rimuovere domini se vuoi che i dati dei visitatori persistano tra i domini. Se questa opzione è selezionata, i dati della visita vengono conservati tra i sottodomini. </p> <p>Questa impostazione consente di specificare la modalità di tracciamento del traffico tra i domini o i domini associati. I collegamenti ai sottodomini sono trattati come collegamenti in uscita. Le visite ai sottodomini vengono tracciate separatamente. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Optional) Configure [!UICONTROL Advanced Settings].

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elemento </th> 
    <th colname="col2" class="entry"> Descrizione </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Consenti approvazioni con più regole</span> </td> 
    <td colname="col2"> <p>Consente l'approvazione simultanea di più regole per questa proprietà. L'approvazione predefinita consente solo l'approvazione a una singola regola. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Abilita pubblicazione selettiva</span> </td> 
    <td colname="col2"> <p>Specifica se consentire agli utenti di selezionare le regole approvate. Questa è l'opzione predefinita. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nome cookie tracciamento</span> </td> 
    <td colname="col2"> <p>Sostituisce il nome del cookie di tracciamento predefinito. Puoi personalizzare il nome utilizzato Gestione tag dinamica per tenere traccia dello stato di rinuncia per ricevere altri cookie. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Timeout tag</span> </td> 
    <td colname="col2"> <p>Specifica la durata di attesa di un tag da parte di Gestione tag dinamica prima di ridurre il timeout e annullare la richiesta di tag. </p> <p> A causa di come funziona Gestione tag dinamica, non preoccuparti che questo sia un numero elevato. DTM offre metodi efficaci per garantire che i tag lenti non influenzino l'esperienza dell'utente. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Ritardo ancoraggio</span> </td> 
    <td colname="col2"> <p>Specifica per quanto tempo Gestione tag dinamica attende che i tag attivino i collegamenti su un clic prima di passare alla pagina successiva. Il valore predefinito è 100 millisecondi. </p> <p>Ritardi più lunghi migliorano l'accuratezza del tracciamento. Adobe consiglia un ritardo di almeno 500 millisecondi, che l'utente non percepirà. </p> <p>Gestione tag dinamica si aspetta fino al momento specificato, ma se il beacon viene attivato prima, il ritardo viene troncato. Ovvero l'utente non deve sempre attendere l'intera lunghezza del ritardo. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Create Property]**.
