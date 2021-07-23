---
title: Creare un livello di dati
description: Scopri cosa è un livello di dati nell’implementazione di Analytics e come può essere utilizzato per mappare le variabili in Adobe Analytics.
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 4%

---

# Creare un livello di dati

Un livello dati è un framework di oggetti JavaScript sul sito che contiene tutti i valori variabili utilizzati nell&#39;implementazione. Consente un maggiore controllo e una manutenzione più semplice nell’implementazione.

## Prerequisiti

[Crea un documento di progettazione della soluzione](solution-design.md) : è importante che l&#39;organizzazione si allinei ai requisiti di tracciamento. Assicurati di essere preparato con un documento di progettazione della soluzione prima di avvicinarti ai team di sviluppo della tua organizzazione.

## Flusso di lavoro

L’implementazione di Adobe Analytics tramite un livello dati in genere segue questi passaggi:

1. **Collabora con il team di sviluppo del sito per implementare un livello** dati: Il team di sviluppo del sito è principalmente responsabile della compilazione dell&#39;oggetto livello dati con valori corretti. Rivedi questa pagina con il tuo team di sviluppo del sito per assicurarti che le aspettative siano allineate tra i team.

   >[!NOTE]
   >
   >Le specifiche dei livelli dati consigliate di Adobe sono facoltative. Se disponi già di un livello di dati, o in altro modo scegli di non seguire le specifiche di Adobe, assicurati che l&#39;organizzazione sia allineata alle specifiche da seguire.
1. **Convalida il livello dati utilizzando una console** del browser: Una volta creato un livello dati, puoi verificare che funzioni utilizzando qualsiasi console di sviluppo del browser. Puoi aprire la Developer Console nella maggior parte dei browser utilizzando il tasto `F12` . Un valore di variabile di esempio è `digitalData.page.pageInfo.pageID`.
1. **Utilizza i tag Adobe Experience Platform per mappare gli oggetti livello dati su elementi** dati: Crea elementi dati nell’interfaccia utente di raccolta dati in Adobe Experience Platform e mappali agli attributi JavaScript descritti nel livello dati.
1. **Utilizza l’estensione tag di Adobe Analytics per mappare gli elementi dati sulle variabili** di Analytics: Seguendo il documento di progettazione della soluzione, assegna ogni elemento dati alla variabile Analytics appropriata.

## Specifiche

L&#39;Adobe consiglia di seguire [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) descritto da [Customer Experience Digital Data Community Group](https://www.w3.org/community/custexpdata/). Utilizza le sezioni seguenti per comprendere in che modo gli elementi del livello dati interagiscono con Adobe Analytics.

L’oggetto livello dati globale consigliato da utilizzare è `digitalData`. L’esempio seguente elenca un oggetto JSON a livello di dati abbastanza completo con valori di esempio:

```js
digitalData = {
    pageInstanceID: "Example page - production",
    page: {
        pageInfo: {
            pageID: "5093",
            pageName: "Example page",
            destinationURL: "https://example.com/index.html",
            referringURL: "https://example.com/referrer.html",
            sysEnv: "desktop",
            variant: "2",
            version: "1.14",
            breadCrumbs: ["Home","Example group","Example page"],
            author: "J Smith",
            issueDate: "Example date",
            effectiveDate: "Example date",
            expiryData: "Example date",
            language: "en-US",
            geoRegion: "US",
            industryCodes: "Example industry codes",
            publisher: "Example publisher"
        },
        category: {
            primaryCategory: "Example page category",
            subCategory: "Sub-category example"
        },
        attributes: {
            country: "US",
            language: "en-US"
        }
    },
    product: [{
        productInfo: {
            productID: "4859",
            productName: "Example product",
            description: "Example description",
            productURL: "https://example.com/product.html",
            productImage: "https://example.com/product_image.png",
            productThumbnail: "https://example.com/product_thumbnail.png",
            manufacturer: "Example manufacturer",
            quantity: 1,
            size: "Product size"
        },
        category: {
            primaryCategory: "Example product category",
            subCategory: "Example sub-category"
        }
    }],
    cart: {
        cartID: "934856",
        price: {
            basePrice: 200.00,
            voucherCode: "EXAMPLEVOUCHER1",
            voucherDiscount: 0.50,
            currency: "USD",
            taxRate: 0.20,
            shipping: 5.00,
            shippingMethod: "UPS",
            priceWithTax: 120,
            cartTotal: 125
        }
    },
    transaction: {
        transactionID: "694025",
        profile: {
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com"
            },
            address: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            },
            shippingAddress: {
                line1: "123 Vague Street",
                line2: "Apt 1",
                city: "Austin",
                stateProvince: "TX",
                postalCode: "78610",
                country: "USA"
            }
        }
    },
    event: [{
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    component: [{
        componentInfo: {
            componentID: "4921",
            componentName: "Example component"
        },
        category: {
            primaryCategory: "Example event category",
            subCategory: "Example sub-category"
        }
    }],
    user: [{
        segment: "Premium membership",
        profile: [{
            profileInfo: {
                profileID: "exampleprofile",
                userName: "exampleusername",
                email: "user@example.com",
                language: "en-US",
                returningStatus: "New"
            },
            social: {
                facebook: "examplefacebookid",
                twitter: "exampletwitterhandle"
            }
        }]
    }],
    privacy: {
        accessCategories: [{
            categoryName: "Default",
            domains: "adobedtm.com"
        }]
    },
    version: "1.0"
}
```

Utilizza il rapporto [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) per informazioni dettagliate su ciascun oggetto e sottooggetto. Non tutti i siti utilizzano tutti gli oggetti; ad esempio, se si ospita un sito di notizie, è improbabile che sia stato utilizzato per l&#39;array di oggetti `digitalData.product`.

I livelli dati sono estensibili; se hai dei requisiti specifici per la tua organizzazione, puoi includere oggetti nel livello dati per soddisfare tali esigenze.

## Impostazione dei valori del livello dati

I livelli dati generalmente generano lato server, facendo riferimento agli stessi oggetti utilizzati per creare il contenuto del sito. Stabilisci il livello di dati del sito in base ai requisiti di tracciamento impostati nel documento di progettazione della soluzione [della tua organizzazione](solution-design.md).

## Passaggi successivi

[Mappatura di oggetti livello dati su elementi](../launch/layer-to-elements.md) dati: Utilizza il livello dati del tuo sito in Adobe Experience Platform.
