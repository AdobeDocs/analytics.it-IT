---
description: Una proprietà web può essere un raggruppamento di uno o più domini e sottodomini con una libreria di regole, inclusa in un codice di incorporamento.
keywords: Implementazione di Analytics;metodo di implementazione;gestione tag dinamica;dtm;proprietà web;proprietà
title: Creare proprietà Web
topic-fix: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
exl-id: f89381d0-bdf7-4e01-96a3-2ea160da2b44
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 14%

---

# Creare proprietà Web

Una proprietà web può essere un raggruppamento di uno o più domini e sottodomini con una libreria di regole, inclusa in un codice di incorporamento.

>[!NOTE]
>
>Solo un utente con diritti di amministratore può creare una proprietà. Per ulteriori informazioni sui ruoli, consulta [Creare e gestire i gruppi in DTM](https://docs.adobe.com/content/help/en/dtm/using/admin/groups.html) nella Documentazione del prodotto Dynamic Tag Management.

Puoi gestire e tenere traccia di queste risorse con DTM. Ad esempio, supponiamo di avere più siti web basati su un modello e di voler tenere traccia delle stesse risorse su tutti questi siti web. Puoi applicare una proprietà web a più domini.

Per informazioni generali sulle proprietà web e sulle best practice, consulta [Proprietà web](https://docs.adobe.com/content/help/en/dtm/using/admin/web-property.html) nella Documentazione del prodotto Dynamic Tag Management.

1. Passa alla pagina dell’azienda e fai clic su **[!UICONTROL Add Property]**.

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
    <td colname="col1"> <span class="uicontrol"> Questo sito si estende su più domini  </span> </td> 
    <td colname="col2"> <p>Puoi aggiungere e rimuovere domini se desideri che i dati del visitatore persistano tra domini diversi. Se questa opzione è selezionata, i dati per la visita persistono tra i sottodomini. </p> <p>Questa impostazione consente di specificare come tenere traccia del traffico tra i sottodomini o i domini associati. I collegamenti ai sottodomini sono considerati come collegamenti in uscita. Le visite ai sottodomini sono tracciate separatamente. </p> </td> 
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
    <td colname="col2"> <p>Consente l'approvazione di più regole per la proprietà contemporaneamente. L'approvazione predefinita consente solo l'approvazione di una sola regola. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Abilita pubblicazione selettiva</span> </td> 
    <td colname="col2"> <p>Specifica se consentire agli utenti di selezionare le regole approvate pubblicate. Questa è l’opzione predefinita. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Nome cookie di tracciamento</span> </td> 
    <td colname="col2"> <p>Sostituisce il nome predefinito del cookie di tracciamento. Puoi personalizzare il nome utilizzato da Dynamic Tag Management per tenere traccia dello stato di rinuncia alla ricezione di altri cookie. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Timeout tag</span> </td> 
    <td colname="col2"> <p>Specifica per quanto tempo Dynamic Tag Management attende che un tag venga attivato prima che venga eseguito il timeout e che venga annullata la richiesta di tag. </p> <p> A causa del funzionamento di Dynamic Tag Management, non preoccuparti che questo sia un numero elevato. DTM dispone di metodi efficaci per garantire che i tag lenti non influiscano sull’esperienza utente. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> Ritardo ancoraggio</span> </td> 
    <td colname="col2"> <p>Specifica per quanto tempo Dynamic Tag Management attende che i tag attivino i collegamenti selezionati prima di passare alla pagina successiva. Il valore predefinito è 100 millisecondi. </p> <p>Ritardi più lunghi migliorano l'accuratezza del tracciamento. Adobe consiglia un ritardo di 500 millisecondi o meno, impercettibile per l'utente. </p> <p>Dynamic Tag Management attenderà fino al tempo specificato, ma se il beacon viene attivato prima, il ritardo viene interrotto. (Ossia, l'utente non deve sempre attendere per l'intera durata del ritardo). </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Create Property]**.
