---
title: Cos’è la variabile currencyCode e come si usa?
description: Per i siti di eCommerce, imposta la valuta in cui sono effettuate le offerte della pagina.
feature: Variables
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
source-git-commit: f659d1bde361550928528c7f2a70531e3ac88047
workflow-type: ht
source-wordcount: '949'
ht-degree: 100%

---

# currencyCode

Per i siti che utilizzano Commerce, le entrate e la valuta sono una parte importante di Analytics. Molti siti, soprattutto quelli che interessano più Paesi, utilizzano valute diverse. Utilizza la variabile `currencyCode` per assicurarti che le entrate siano attribuite alla valuta corretta.

La conversione della valuta utilizza la seguente logica su ogni hit. Questi passaggi si applicano ai valori delle entrate assegnati alla variabile [`products`](../page-vars/products.md) e tutti gli eventi elencati come “Valuta” negli [Eventi di successo](/help/admin/admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

* Se `currencyCode` non è definita, Adobe presuppone che tutti i valori di valuta siano la valuta della suite di rapporti. Consulta le [Impostazioni account generali](/help/admin/admin/general-acct-settings-admin.md) nelle Impostazioni della suite di rapporti per visualizzare la valuta della suite di rapporti.
* Se `currencyCode` è definita e corrisponde alla valuta della suite di rapporti, non viene applicata alcuna conversione di valuta.
* Se `currencyCode` è definita ed è diversa dalla valuta della suite di rapporti, Adobe applica una conversione della valuta in base al tasso di cambio del giorno corrente. Adobe collabora con [XE](https://xe.com) per convertire la valuta ogni giorno. Tutti i valori memorizzati nella suite di rapporti si trovano nella valuta della suite di rapporti.
* Se `currencyCode` è impostata su un valore non valido, **l’intero hit viene eliminato causando la perdita di dati.** Assicurati che questa variabile sia definita correttamente ogni volta che viene utilizzata.

Questa variabile non persiste negli hit. Assicurati che questa variabile sia definita in ogni pagina che include entrate o eventi di valuta che non corrispondono alla valuta predefinita della suite di rapporti.

>[!NOTE]
>
>Anche se i codici di valuta possono cambiare tra le pagine, tutte le metriche di valuta in un singolo hit devono utilizzare la stessa valuta.

Quando si implementa questa variabile, **deve** essere utilizzato un punto come separatore di valuta per tutte le valute. Ad esempio, la corona svedese, che in genere visualizza un separatore con la virgola, deve essere modificata per utilizzare un punto nella variabile `products` e in tutti gli eventi di valuta. In Adobe nel reporting viene visualizzato il separatore di valuta corretto.

## Codice valuta utilizzando il Web SDK

Il codice della valuta è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `commerce.order.currencyCode`.

## Codice valuta utilizzando l’estensione di Adobe Analytics

Il Codice valuta è un campo che si trova sotto il pannello a soffietto [!UICONTROL General] durante la configurazione dell’estensione di Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL Currency Code].

È possibile utilizzare un codice valuta predefinito o un codice valuta personalizzato. Se utilizzi un codice valuta personalizzato, assicurati che sia valido.

## Codice valuta in Adobe Experience Platform Mobile SDK

Il codice valuta viene passato agli SDK di Adobe Experience Platform Mobile tramite variabili di dati di contesto nell’estensione di Adobe Analytics.

1. Imposta il codice valuta in una variabile di dati contestuali durante `trackState` o `trackAction`.
1. Crea una regola di elaborazione nell’Admin Console di Adobe Analytics per la suite di rapporti. Imposta la regola per sovrascrivere la variabile Codice valuta.
1. Trasferisci il codice valuta alla variabile `products` nella chiamata a `trackState` o a `trackAction`.

È possibile utilizzare un codice valuta predefinito o un codice valuta personalizzato. Se utilizzi un codice valuta personalizzato, assicurati che sia valido.

## s.currencyCode in AppMeasurement e nell’editor di codice personalizzato dell’estensione di Analytics

La variabile `s.currencyCode` è una stringa contenente un codice in maiuscolo di 3 lettere che rappresenta la valuta nella pagina. I valori fanno distinzione tra maiuscole e minuscole.

```js
s.currencyCode = "USD";
```

I seguenti codici valuta sono validi:

| Codice della valuta | Etichetta |
| --- | --- |
| `AED` | Dirham degli Emirati Arabi Uniti |
| `AFA` | Afghani dell’Afghanistan |
| `ALL` | Lek dell’Albania |
| `AMD` | Dram armeno |
| `ANG` | Fiorino delle Antille Olandesi |
| `AOA` | Kwanza angolano |
| `ARS` | Peso argentino |
| `AUD` | Dollaro australiano |
| `AWG` | Fiorino Aruba |
| `AZM` | Manat Azerbaigian |
| `BAM` | Marka convertibile Bosnia ed Erzegovina |
| `BBD` | Dollaro Barbados |
| `BDT` | Taka Bangladesh |
| `BGN` | Lev Bulgaria |
| `BHD` | Dinaro Bahrein |
| `BIF` | Franco Burundi |
| `BMD` | Dollaro Bermuda |
| `BND` | Dollaro Brunei |
| `BOB` | Boliviano Bolivia |
| `BRL` | Real Brasile |
| `BSD` | Dollaro Bahamas |
| `BTN` | Ngultrum Bhutan |
| `BWP` | Pula Botswana |
| `BYR` | Rublo Bielorussia |
| `BZD` | Dollaro Belize |
| `CAD` | Dollaro Canada |
| `CDF` | Franco Congo/Kinshasa |
| `CHF` | Franco Svizzera |
| `CLP` | Peso Cile |
| `CNY` | Renminbi Cina |
| `COP` | Peso Colombia |
| `CRC` | Colon Costa Rica |
| `CSD` | Dinaro Serbia |
| `CUP` | Peso Cuba |
| `CVE` | Scudo Capo Verde |
| `CYP` | Sterlina Cipro |
| `CZK` | Corona Repubblica Ceca |
| `DJF` | Franco Gibuti |
| `DKK` | Corona Danimarca |
| `DOP` | Peso Repubblica Dominicana |
| `DZD` | Dinaro Algeria |
| `EEK` | Coronia Estonia |
| `EGP` | Sterlina Egitto |
| `ERN` | Nacfa Eritrea |
| `ETB` | Birr Etiopia |
| `EUR` | Euro |
| `FJD` | Dollaro Figi |
| `FKP` | Sterlina Isole Falkland |
| `GBP` | Sterlina Regno Unito |
| `GEL` | Lari Georgia |
| `GGP` | Sterlina Guernsey |
| `GHC` | Cedi Ghana |
| `GIP` | Sterlina Gibilterra |
| `GMD` | Dalasi Gambia |
| `GNF` | Franco Guinea |
| `GTQ` | Quetzal Guatemala |
| `GYD` | Dollaro Guyana |
| `HKD` | Dollaro Hong Kong |
| `HNL` | Lempira Honduras |
| `HRK` | Kuna Croazia |
| `HTG` | Gourde Haiti |
| `HUF` | Fiorino Ungheria |
| `IDR` | Rupia Indonesia |
| `ILS` | Nuovo siclo Israele |
| `IMP` | Sterlina Isola di Man |
| `INR` | Rupia India |
| `IQD` | Dinaro Iraq |
| `IRR` | Riyal Iran |
| `ISK` | Corona Islanda |
| `JEP` | Sterlina Jersey |
| `JMD` | Dollaro Giamaica |
| `JOD` | Dinaro Giordania |
| `JPY` | Yen Giappone |
| `KES` | Scellino Kenya |
| `KGS` | Som Kirghizistan |
| `KHR` | Riel Cambogia |
| `KMF` | Franco Comore |
| `KPW` | Won Corea del Nord |
| `KRW` | Won Corea del Sud |
| `KWD` | Dinaro Kuwait |
| `KYD` | Dollaro Isole Cayman |
| `KZT` | Tenge Kazakistan |
| `LAK` | Kip Laos |
| `LBP` | Sterlina Libano |
| `LKR` | Rupia Sri Lanka |
| `LRD` | Dollaro Liberia |
| `LSL` | Loti Lesotho |
| `LTL` | Litas Lituania |
| `LVL` | Lats Lettonia |
| `LYD` | Dinaro Libia |
| `MAD` | Dirham Marocco |
| `MDL` | Leu Moldavia |
| `MGA` | Ariary Madagascar |
| `MKD` | Dinaro Macedonia |
| `MMK` | Kyat Myanmar |
| `MNT` | Tugrik Mongolia |
| `MOP` | Pataca Macao |
| `MRO` | Ouguiya Mauritania |
| `MTL` | Lira Malta |
| `MUR` | Rupia Mauritius |
| `MVR` | Rufiyaa Maldive |
| `MWK` | Kwacha Malawi |
| `MXN` | Peso Messico |
| `MYR` | Rinngit Malesia |
| `MZM` | Metical Mozambico |
| `NAD` | Dollaro Namibia |
| `NGN` | Naira Nigeria |
| `NIO` | Córdoba d’oro Nicaragua |
| `NOK` | Corona Norvegia |
| `NPR` | Rupia Nepal |
| `NZD` | Dollaro Nuova Zelanda |
| `OMR` | Riyal Oman |
| `PAB` | Balboa Panama |
| `PEN` | Nuevo Sol Perù |
| `PGK` | Kina Papua Nuova Guinea |
| `PHP` | Peso Filippine |
| `PKR` | Rupie Pakistan |
| `PLN` | Zloty Polonia |
| `PYG` | Guarani Paraguay |
| `QAR` | Riyal Qatar |
| `ROL` | Leu Romania |
| `RUR` | Rublo Russia |
| `RWF` | Franco Ruanda |
| `SAR` | Riyal Arabia Saudita |
| `SBD` | Dollaro Isole Salomone |
| `SCR` | Rupia Seychelles |
| `SDD` | Dinaro Sudan |
| `SEK` | Corona Svezia |
| `SGD` | Dollaro Singapore |
| `SHP` | Sterlina Sant’Elena |
| `SIT` | Tallero Slovenia |
| `SKK` | Corona Slovacchia |
| `SLL` | Leone Sierra Leone |
| `SOS` | Scellino Somalia |
| `SPL` | Luigino Seborga |
| `SRD` | Dollaro Suriname |
| `SRG` | Fiorino Suriname |
| `STD` | Dobra São Tomé e Príncipe |
| `SVC` | Colon El Salvador |
| `SYP` | Sterlina Siria |
| `SZL` | Lilangeni eSwatini |
| `THB` | Baht Thailandia |
| `TJS` | Somoni Tagikistan |
| `TMM` | Manat Turkmenistan |
| `TND` | Dinaro Tunisia |
| `TOP` | Pa’anga Tonga |
| `TRL` | Lira Turchia |
| `TTD` | Dollaro Trinidad e Tobago |
| `TVD` | Dollaro Tuvalu |
| `TWD` | Nuovo dollaro Taiwan |
| `TZS` | Scellino Tanzania |
| `UAH` | Grivnia Ucraina |
| `UGX` | Scellino Uganda |
| `USD` | Dollaro Stati Uniti |
| `UYU` | Peso Uruguay |
| `UZS` | Som Uzbekistan |
| `VEB` | Bolivar Venezuela |
| `VND` | Dong Vietnam |
| `VUV` | Vatu Vanuatu |
| `WST` | Tala Samoa |
| `XAF` | Franco Comunità Finanziaria Africana |
| `XAG` | Oncia d’argento |
| `XAU` | Oncia d’oro |
| `XCD` | Dollaro Caraibi orientali |
| `XDR` | Prelievo speciale del Fondo monetario internazionale |
| `XOF` | Franco Comunità Finanziaria Africana |
| `XPD` | Once di palladio |
| `XPF` | Franco CFP |
| `XPT` | Oncia di platino |
| `YER` | Riyal Yemen |
| `ZAR` | Rand Sudafrica |
| `ZMK` | Kwacha Zambia |
| `ZWD` | Dollaro Zimbabwe |
