---
description: La variabile s.products può essere la variabile più sintatticamente complessa utilizzata per la raccolta dei dati.
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Errori comuni nella variabile Products
topic: Developer and implementation
uuid: 94075c56-37c3-44de-bf37-1dfd228c6665
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Errori comuni nella variabile Products

La variabile s.products può essere la variabile più sintatticamente complessa utilizzata per la raccolta dei dati.

Le virgole, i punti e i punti e le tubazioni, nonché i segni uguali, svolgono tutti ruoli specifici nella variabile. Non ha una lunghezza massima totale, ma ogni singola voce di prodotto non può superare i 100 byte (inclusi i caratteri multibyte). Gli errori nell'implementazione di questa variabile sono comprensibili, ma sfortunatamente per gli sviluppatori, [!UICONTROL s.products] è spesso la variabile più importante del sito, perché consente il monitoraggio di ricavi, unità, nomi di prodotti e così via.

Di seguito sono riportati alcuni errori estremamente facili da commettere che possono causare problemi a qualsiasi implementazione.

Accertatevi che i [!UICONTROL category]totali, [!UICONTROL product name]e [!UICONTROL revenue] i totali non contengano virgole e punti e virgola. La virgola viene utilizzata per separare le voci nella [!UICONTROL s.products] stringa. Ciò si verifica quando nella stessa transazione sono presenti due prodotti, il punto e virgola viene utilizzato per delimitare i campi all'interno di una voce. Se si utilizza una virgola o un punto e virgola in qualsiasi altro modo, la raccolta dati presuppone che si stiano separando le voci di prodotto. Prendi in considerazione l'esempio seguente:

```js
s.products="widgets;large widget, 40′x40′;1;19.99,wugs;tiny wug;2;1,999.98";
```

In questa implementazione, lo sviluppatore probabilmente intendeva consentire la raccolta dei dati, come illustrato di seguito:

Categoria 1: widget

Prodotto 1: ampio widget, 40′x40′

Unità 1: 1

Entrate 1: 19,99

Categoria 2: bastonate

Prodotto 2: piccolo treppiede

Unità 2: 2

Entrate 2: 1.999,98

Note le virgole nelle voci Prodotto 1 e Ricavo 2. Indica una nuova voce di prodotto. La raccolta dei dati interpreterebbe quanto segue:

Categoria 1: widget

Prodotto 1: widget grande

Categoria 2: 40'x40'

Prodotto 2: 1

Unità 2: 19,99

Categoria 3: bastonate

Prodotto 3: piccolo treppiede

Unità 3: 2

Entrate 3: 1

Categoria 4: 999,98

Un errore di questo tipo spesso genera valori numerici imprevisti nel [!UICONTROL Products] rapporto, perché il campo delle unità viene registrato come nome del prodotto. Se nel [!UICONTROL Products] rapporto sono presenti nomi di prodotto non validi, controlla l’implementazione della [!UICONTROL s.products] variabile in caso di uso improprio di caratteri riservati, come la virgola.

I nomi di prodotti e categorie non devono contenere caratteri non supportati. Ciò può essere particolarmente difficile nella [!UICONTROL s.products] stringa, perché i nomi dei prodotti spesso contengono caratteri quali ™, © e ®. Questi caratteri devono essere eliminati dai valori di prodotto e categoria prima di essere inseriti in [!UICONTROL s.products]. È inoltre necessario assicurarsi che i simboli di valuta non siano inclusi nei valori delle entrate. I caratteri supportati sono numeri da 1 a 127 dalla tabella ASCII.

Se non si passa una categoria di prodotto nella stringa di prodotto, assicurarsi di includere un punto e virgola (;) in cui la categoria di prodotto viene visualizzata normalmente, come illustrato di seguito:

```js
s.products=";product name"
```

In questo caso, il punto e virgola rappresenta un segnaposto per la categoria di prodotti. Se il punto e virgola viene lasciato fuori dalla stringa del prodotto, il "nome del prodotto" viene conteggiato come categoria, il numero di unità da conteggiare come nome del prodotto, le entrate da conteggiare come unità e così via.
