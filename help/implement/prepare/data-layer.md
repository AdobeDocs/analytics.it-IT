---
title: Creare un livello di dati
description: Scopri cos’è un livello dati nell’implementazione di Analytics e come può essere utilizzato per mappare le variabili in  Adobe Analytics.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 4%

---


# Creare un livello di dati

Un livello dati è un framework di oggetti JavaScript presenti sul sito che contiene tutti i valori variabili utilizzati nell&#39;implementazione. Consente un maggiore controllo e una manutenzione più semplice nell&#39;implementazione.

## Prerequisiti

[Crea un documento](solution-design.md) di progettazione della soluzione: è importante che l&#39;organizzazione si allinei ai requisiti di tracciamento. Prima di contattare i team di sviluppo dell&#39;organizzazione, accertatevi di essere preparati con un documento di progettazione della soluzione.

## Flusso di lavoro

L’implementazione  Adobe Analytics tramite un livello dati segue in genere i seguenti passaggi:

1. **Per implementare un livello** dati, collabora con il team di sviluppo del sito: Il team di sviluppo del sito è principalmente responsabile della compilazione dell&#39;oggetto livello dati con i valori corretti. Consultate questa pagina con il team di sviluppo del sito per assicurarvi che le aspettative siano allineate tra i team.

   >[!NOTE]
   >
   >Le seguenti  Adobi  specifiche consigliate per il livello dei dati sono facoltative. Se si dispone già di un livello dati, o in altro modo si sceglie di non seguire  specifiche  Adobe, assicurarsi che l&#39;organizzazione si allinea alle specifiche da seguire.
1. **Convalidare il livello dati utilizzando una console** del browser: Una volta creato il livello dati, è possibile verificare che funzioni utilizzando la console sviluppatore di qualsiasi browser. È possibile aprire la console di sviluppo nella maggior parte dei browser utilizzando la `F12` chiave. Un valore di variabile di esempio è `digitalData.page.pageInfo.pageID`.
1. **Utilizzare  Adobe Experience Platform Launch per mappare gli oggetti livello dati su elementi** di dati di Launch: Create elementi di dati in Launch e mapparli sugli attributi JavaScript descritti nel livello di dati.
1. **Utilizzate l&#39;estensione Adobe Analytics  in Launch per mappare gli elementi dati sulle variabili** di Analytics: Seguendo il documento di progettazione della soluzione, assegna ogni elemento dati alla variabile Analytics appropriata.

## Specifiche

 Adobe consiglia di seguire il [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) delineato dal [Customer Experience Digital Data Community Group](https://www.w3.org/community/custexpdata/). Utilizzate le sezioni seguenti per comprendere in che modo gli elementi del livello dati interagiscono con  Adobe Analytics.

È consigliabile utilizzare l&#39;oggetto livello dati di insieme `digitalData`. L&#39;esempio seguente elenca un oggetto JSON con un livello dati abbastanza completo con valori di esempio:

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

Usa il report [Customer Experience Digital Data Layer](https://www.w3.org/2013/12/ceddl-201312.pdf) (Livello dati digitale esperienza cliente) per informazioni dettagliate su ciascun oggetto e oggetto secondario. Non tutti i siti utilizzano tutti gli oggetti; ad esempio, se si ospita un sito di notizie, è improbabile che sia stato utilizzato per l&#39;array di `digitalData.product` oggetti.

I livelli di dati sono estensibili; se hai dei requisiti specifici per la tua organizzazione, puoi includere oggetti nel livello dati per adattarli a tali esigenze.

## Impostazione dei valori del livello dati

I livelli dati generano in genere lato server, facendo riferimento agli stessi oggetti utilizzati per creare il contenuto del sito. Definite il livello dati del sito in base ai requisiti di tracciamento impostati nel documento [di progettazione della](solution-design.md)soluzione aziendale.

## Passaggi successivi

[Mappare gli oggetti livello dati agli elementi](../launch/layer-to-elements.md)dati: Utilizzate il livello dati del sito in  Adobe Experience Platform Launch.
