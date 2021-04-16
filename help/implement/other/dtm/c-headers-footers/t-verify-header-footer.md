---
description: Verifica che la libreria Dynamic Tag Management venga caricata correttamente sul sito.
keywords: Implementazione di Analytics;metodo di implementazione;gestione tag dinamica;dtm;codice;codice pagina;codice intestazione;codice piè di pagina;codice di incorporamento;verifica codice;verifica codice intestazione;verifica codice piè di pagina;scheda incorporamento;incorpora
title: Verificare il codice di intestazione e piè di pagina
topic-fix: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
exl-id: bed44ba7-8e0e-49e2-bedc-fb1ba66e5b18
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 6%

---

# Verificare il codice di intestazione e piè di pagina

Verifica che la libreria Dynamic Tag Management venga caricata correttamente sul sito.

1. Apri il tuo sito nel browser.
1. Apri il [!UICONTROL Developer Console] facendo clic con il pulsante destro del mouse e scegliendo **[!UICONTROL Inspect Element]** > **[!UICONTROL Console]**.
1. Premere **[!UICONTROL Enter]**.

   Se il codice è stato installato correttamente, verrà visualizzato *`true`* nella console.

   Se il codice non è stato installato correttamente, verrà visualizzato l&#39;errore di riferimento:

   `_satellite is not defined`

   Se ricevi questo errore, assicurati che:

* Hai incluso il codice di intestazione completo in ogni pagina del sito nella sezione [!DNL HEAD] , il più vicino possibile al tag `<head>` .
* Non sono presenti caratteri imprevisti nello snippet di codice, potenzialmente a causa della copia e dell&#39;incolla da un documento formattato.
