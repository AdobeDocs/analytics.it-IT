---
description: Una proprietà Web può essere un qualsiasi raggruppamento di uno o più domini e sottodomini con una libreria di regole, inclusa in un unico codice da incorporare.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: Creare proprietà Web
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 14%

---


# Creare proprietà Web

Una proprietà Web può essere un qualsiasi raggruppamento di uno o più domini e sottodomini con una libreria di regole, inclusa in un unico codice da incorporare.

>[!NOTE]
>
>Solo un utente con diritti di amministratore può creare una proprietà. Per ulteriori informazioni sui ruoli, consulta [Creazione e gestione di gruppi in DTM](https://docs.adobe.com/content/help/en/dtm/using/admin/groups.html) nella Documentazione prodotto Gestione tag dinamica.

Puoi gestire e tenere traccia di queste risorse con Gestione dinamica dei tag. Ad esempio, supponete di disporre di più siti Web basati su un modello e di voler tenere traccia delle stesse risorse su tutti questi siti Web. È possibile applicare una proprietà Web a più domini.

Per informazioni generali sulle proprietà Web e sulle procedure ottimali, vedere Proprietà [](https://docs.adobe.com/content/help/it-IT/dtm/using/admin/web-property.html) Web nella Documentazione prodotto Gestione tag dinamica.

1. Andate alla pagina della società, quindi fate clic su **[!UICONTROL Add Property]**.

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
    <td colname="col2"> <p>URL di base della proprietà. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Questo sito si estende su più domini </span> </td> 
    <td colname="col2"> <p>Puoi aggiungere e rimuovere domini se vuoi che i dati dei visitatori persistano tra domini diversi. Se questa opzione è selezionata, i dati per la visita persistono tra i sottodomini. </p> <p>Questa impostazione consente di specificare la modalità di tracciamento del traffico tra i sottodomini o i domini associati. I collegamenti ai sottodomini vengono trattati come collegamenti in uscita. Le visite ai sottodomini vengono tracciate separatamente. </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. (Facoltativo) Configura [!UICONTROL Advanced Settings].

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Elemento </th> 
    <th colname="col2" class="entry"> Descrizione </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Consenti approvazioni a più regole</span> </td> 
    <td colname="col2"> <p>Consente l'approvazione simultanea di più regole per questa proprietà. L'approvazione predefinita consente solo l'approvazione di una singola regola. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Abilita pubblicazione selettiva</span> </td> 
    <td colname="col2"> <p>Specifica se consentire agli utenti di selezionare le regole approvate da pubblicare. Questa è l'opzione predefinita. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nome cookie di tracciamento</span> </td> 
    <td colname="col2"> <p>Ignora il nome predefinito del cookie di tracciamento. Puoi personalizzare il nome utilizzato da Gestione tag dinamica per monitorare il tuo stato di rifiuto per ricevere altri cookie. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Timeout tag</span> </td> 
    <td colname="col2"> <p>Specifica per quanto tempo Gestione tag dinamica attende che un tag venga attivato prima che venga disattivato e che venga annullata la richiesta di tag. </p> <p> Grazie al funzionamento di Gestione tag dinamica, non preoccuparti che questo sia un numero elevato. Gestione dinamica dei tag offre metodi efficaci per garantire che i tag lenti non influenzino l’esperienza dell’utente. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Ritardo ancoraggio</span> </td> 
    <td colname="col2"> <p>Specifica per quanto tempo Gestione tag dinamica attende che i tag vengano attivati sui collegamenti selezionati prima di passare alla pagina successiva. Il valore predefinito è 100 millisecondi. </p> <p>Ritardi più lunghi migliorano l'accuratezza del tracciamento. Adobe consiglia un ritardo di 500 millisecondi o meno, impercettibile per l'utente. </p> <p>Gestione tag dinamica attenderà fino al tempo specificato, ma se il beacon viene attivato prima, il ritardo viene ridotto. (Ossia, l'utente non deve sempre attendere per l'intera durata del ritardo). </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Create Property]**.
