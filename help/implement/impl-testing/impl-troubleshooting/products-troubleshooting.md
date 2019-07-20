---
description: La variabile s. products può essere la variabile più sintatticamente complessa utilizzata dalla raccolta dati.
keywords: Implementazione di Analytics
seo-description: La variabile s. products può essere la variabile più sintatticamente complessa utilizzata dalla raccolta dati.
seo-title: Errori comuni nella variabile Prodotti
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Errori comuni nella variabile Prodotti
topic: Sviluppatore e implementazione
uuid: 94075 c 56-37 c 3-44 de-bf 37-1 dfd 228 c 6665
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Errori comuni nella variabile Prodotti

La variabile s. products può essere la variabile più sintatticamente complessa utilizzata dalla raccolta dati.

Virgole, semi-due, tubi ed è uguale a tutti i ruoli di riproduzione specifici della variabile. Non dispone di lunghezza massima complessiva, ma ogni singola voce non può essere superiore a 100 byte (inclusi caratteri multibyte). Mistakes in implementation of this variable are understandable, but unfortunately for developers, [!UICONTROL s.products] is often a site's most important variable because it makes possible the tracking of revenue, units, product names, and so forth.

Di seguito sono riportati alcuni errori estremamente semplici che possono causare problemi su qualsiasi implementazione.

Make sure that your [!UICONTROL category], [!UICONTROL product name], and [!UICONTROL revenue] totals are devoid of commas and semi-colons. The comma is used to separate entries in the [!UICONTROL s.products] string. Questo accade quando si hanno due prodotti nella stessa transazione, mentre il punto e virgola viene usato per delimitare i campi all'interno di una voce. Se utilizzate una virgola o un punto e virgola in qualsiasi altro modo, la raccolta dati presuppone che state separando le voci del prodotto. Prendi in considerazione l'esempio seguente:

```js
s.products="widgets;large widget, 40′x40′;1;19.99,wugs;tiny wug;2;1,999.98";
```

In questa implementazione, lo sviluppatore probabilmente destinato alla raccolta dati deve leggerlo come mostrato di seguito:

Categoria 1: widget

Prodotto 1: widget grande, 40′ x 40′

Unità 1: 1

Ricavi da 1: 19.99

Categoria 2: wugs

Prodotto 2: tiny wug

Unità 2: 2

Ricavi da 2: 1,999.98

Prendete nota delle virgole nelle voci Prodotto 1 e Fatturato 2. Queste indicano una nuova voce di prodotto. La raccolta dati interpreterebbe quanto segue:

Categoria 1: widget

Prodotto 1: widget grande

Categoria 2: 40 'x 40 '

Prodotto 2: 1

Unità 2: 19.99

Categoria 3: wugs

Prodotto 3: tiny wug

Unità 3: 2

Ricavi da 3: 1

Categoria 4: 999.98

A mistake like this often results in unexpected numerical values in the [!UICONTROL Products] report, because the units field is recorded as the product name. If you see invalid product names in your [!UICONTROL Products] report, review your [!UICONTROL s.products] variable implementation for misuse of reserved characters, like the comma.

I nomi di prodotto e categoria non devono contenere caratteri non supportati. This can be especially difficult in the [!UICONTROL s.products] string, because product names are often likely to contain characters such as ™, ©, and ®. These characters need to be stripped out of the product and category values before they are placed into [!UICONTROL s.products]. Inoltre, devi accertarti che i simboli di valuta non siano inclusi nei valori delle entrate. I caratteri supportati sono numeri 1-127 dalla tabella ASCII.

Se non passate una categoria di prodotto nella stringa di prodotto, accertatevi di includere un punto e virgola (;) in cui la categoria di prodotto viene normalmente visualizzata, come illustrato di seguito:

```js
s.products=";product name"
```

In questo caso, il punto e virgola rappresenta un segnaposto per la categoria di prodotto. Se il semon-on viene escluso dalla stringa di prodotto, il «nome prodotto» viene conteggiato come categoria, il numero di unità da conteggiare come nome del prodotto, le entrate da conteggiare come unità e così via.
