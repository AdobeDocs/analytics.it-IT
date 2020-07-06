---
title: currencyCode
desciption: For eCommerce sites, set the currency the page deals in.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '804'
ht-degree: 0%

---


# currencyCode

Per i siti che utilizzano commercio, ricavi e valuta è una parte importante di  Analytics. Molti siti, soprattutto quelli che si estendono su più paesi, utilizzano valute diverse. Utilizzare la `currencyCode` variabile per assicurarsi che gli attributi delle entrate siano nella valuta corretta.

Se non `currencyCode` è definito, i valori monetari definiti dalla [`products`](../page-vars/products.md) variabile e gli eventi valutari sono trattati come se fossero uguali alla valuta della suite di rapporti. Consulta Impostazioni [account](/help/admin/admin/general-acct-settings-admin.md) generali nella guida per l&#39;utente amministratore per visualizzare la valuta della suite di rapporti.

Se `currencyCode` è definito e corrisponde alla valuta della suite di rapporti, non viene applicata alcuna conversione di valuta.

Se `currencyCode` è definito ed è diverso dalla valuta della suite di rapporti, Adobe applica una conversione valutaria basata sul tasso di cambio del giorno corrente. Adobe collabora con [XE](https://xe.com) per convertire la valuta ogni giorno. Tutti i valori memorizzati nei server di raccolta dati vengono in ultima istanza memorizzati nella valuta della suite di rapporti.

>[!IMPORTANT]
>
>Se `currencyCode` contiene un valore non valido, l&#39;intero hit viene eliminato causando la perdita di dati. Accertatevi che questa variabile sia definita correttamente se la utilizzate nell’implementazione.

Questa variabile non persiste tra gli hit. Accertatevi che questa variabile sia definita in ogni pagina che include eventi di ricavi o di valuta.

## Codice valuta in  lancio Adobe Experience Platform

Codice valuta è un campo situato sotto la struttura di [!UICONTROL General] navigazione durante la configurazione dell&#39;estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espandere la [!UICONTROL General] struttura a soffietto, che mostra il [!UICONTROL Currency Code] campo.

È possibile utilizzare un codice valuta predefinito o un codice valuta personalizzato. Se si utilizza un codice valuta personalizzato, assicurarsi che il codice sia valido.

## Codice valuta in  Adobe Experience Platform SDK Mobile

Il codice valuta viene passato agli SDK Mobile del Adobe Experience Platform  tramite le variabili dei dati contestuali nell&#39;estensione Adobe  Analytics.

1. Impostare il codice della valuta in una variabile di dati contestuali durante `trackState` o `trackAction`.
2. Create una regola di elaborazione nella console di amministrazione di Adobe  Analytics per la suite di rapporti. Impostare la regola per sovrascrivere la variabile Codice valuta.
3. Passa il codice della valuta alla `products` variabile della chiamata a `trackState` o `trackAction`.

È possibile utilizzare un codice valuta predefinito o un codice valuta personalizzato. Se si utilizza un codice valuta personalizzato, assicurarsi che il codice sia valido.

## s.currencyCode nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.currencyCode` variabile è una stringa contenente un codice maiuscolo di 3 lettere che rappresenta la valuta nella pagina.

```js
s.currencyCode = "USD";
```

Sono validi i seguenti codici di valuta:

| Codice della valuta | Descrizione valuta |
| --- | --- |
| `AED` | Dirhams degli Emirati Arabi Uniti |
| `AFA` | Afganistan |
| `ALL` | Albania Leke |
| `AMD` | Armenia Drams |
| `ANG` | Guilde d&#39;Atille Olandesi |
| `AOA` | Angola Kwanza |
| `ARS` | Pesos Argentina |
| `AUD` | Dollaro australiano |
| `AWG` | Aruba Guilders |
| `AZM` | Manat Azerbaijan |
| `BAM` | Bosnia-Erzegovina Marka convertibile |
| `BBD` | Barbados Dollari |
| `BDT` | Bangladesh Taka |
| `BGN` | Bulgaria Leva |
| `BHD` | Dinari del Bahrein |
| `BIF` | Franchi del Burundi |
| `BMD` | Dollaro delle Bermuda |
| `BND` | Dollaro del Brunei |
| `BOB` | Bolivia |
| `BRL` | Brasile Reais |
| `BSD` | Dollaro delle Bahamas |
| `BTN` | Bhutan Ngultrum |
| `BWP` | Botswana Pulas |
| `BYR` | Rubli della Bielorussia |
| `BZD` | Dollaro Belize |
| `CAD` | Dollaro canadese |
| `CDF` | Congo/Kinshasa Francs |
| `CHF` | franchi svizzeri |
| `CLP` | Pesos Cile |
| `CNY` | renminbi cinese Yuan |
| `COP` | Pesos Colombia |
| `CRC` | Coloni Costa Rica |
| `CSD` | Dinari serbi |
| `CUP` | Cuba Pesos |
| `CVE` | Escudos del Capo Verde |
| `CYP` | Sterlina di Cipro |
| `CZK` | Repubblica Ceca, Corea |
| `DJF` | Djibouti Francs |
| `DKK` | Corona danese |
| `DOP` | Pesos Repubblica Dominicana |
| `DZD` | Dinari algerini |
| `EEK` | Estonia Krooni |
| `EGP` | Sterlina egiziana |
| `ERN` | Eritrea Nakfa |
| `ETB` | Birr Etiopia |
| `EUR` | Euro |
| `FJD` | Dollaro delle Figi |
| `FKP` | Ferite delle Isole Falkland |
| `GBP` | Sterlina britannica |
| `GEL` | Georgia Lari |
| `GGP` | Ferite di Guernsey |
| `GHC` | Ghana Cedis |
| `GIP` | Margini di Gibilterra |
| `GMD` | Gambia Dalasi |
| `GNF` | Francia |
| `GTQ` | Guatemala Quetzales |
| `GYD` | Dollaro della Guyana |
| `HKD` | Dollaro di Hong Kong |
| `HNL` | Honduras Lempiras |
| `HRK` | Croazia Kuna |
| `HTG` | Haiti Gourdes |
| `HUF` | Forint Ungheria |
| `IDR` | Rupie indonesiane |
| `ILS` | Israele - nuovi Shekel |
| `IMP` | Isola di Man |
| `INR` | Rupie indiane |
| `IQD` | Dinari iracheni |
| `IRR` | Iran Rials |
| `ISK` | Corona islandese |
| `JEP` | Limiti di Jersey |
| `JMD` | Dollari Giamaica |
| `JOD` | Dinari giordani |
| `JPY` | Yen del Giappone |
| `KES` | Kenia Scillings |
| `KGS` | Soma del Kirghizistan |
| `KHR` | Cambogia Riels |
| `KMF` | Comore Francs |
| `KPW` | Corea del Nord |
| `KRW` | Corea del Sud |
| `KWD` | Dinari del Kuwait |
| `KYD` | Dollaro delle Isole Cayman |
| `KZT` | Tenge Kazakistan |
| `LAK` | Laos Kips |
| `LBP` | Libano: ferite |
| `LKR` | Rupie dello Sri Lanka |
| `LRD` | Dollaro liberiano |
| `LSL` | Lesotho Maloti |
| `LTL` | Lituania Litai |
| `LVL` | Lettonia Lati |
| `LYD` | Dinari libici |
| `MAD` | Marocco |
| `MDL` | Moldavia |
| `MGA` | Ariete Madagascar |
| `MKD` | Macedonia - Denar |
| `MMK` | Myanmar Kyats |
| `MNT` | Mongolia Tugriks |
| `MOP` | Macau Patacas |
| `MRO` | Mauritania Ouguiyas |
| `MTL` | Malta Liri |
| `MUR` | Rupie Mauritius |
| `MVR` | Maldive Rufiyaa |
| `MWK` | Malawi Kwacha |
| `MXN` | Pesos messicani |
| `MYR` | Malesia Ringgits |
| `MZM` | Mozambico Meticais |
| `NAD` | Dollari Namibia |
| `NGN` | Nigeria Nairas |
| `NIO` | Nicaragua Gold Cordobas |
| `NOK` | Norvegia Kroner |
| `NPR` | Rupie del Nepal |
| `NZD` | Dollaro neozelandese |
| `OMR` | Oman Rials |
| `PAB` | Panama Balbos |
| `PEN` | Sole Nuevose Perù |
| `PGK` | Papua Nuova Guinea Kina |
| `PHP` | Pesos Filippine |
| `PKR` | Rupie pakistane |
| `PLN` | Polonia Zlotych |
| `PYG` | Paraguay Guarani |
| `QAR` | Qatar Riyals |
| `ROL` | Romania Lei |
| `RUR` | Rubli della Russia |
| `RWF` | Francese del Ruanda |
| `SAR` | Arabia Saudita Riyals |
| `SBD` | Dollaro delle Isole Salomone |
| `SCR` | Rupie Seychelles |
| `SDD` | Dinari sudanesi |
| `SEK` | Corona svedese |
| `SGD` | Dollari Singapore |
| `SHP` | Sant&#39;Helena |
| `SIT` | Talleri Slovenia |
| `SKK` | Repubblica Slovacca |
| `SLL` | Sierra Leone |
| `SOS` | Somalia Scellino |
| `SPL` | Seborga Luigini |
| `SRD` | Dollaro di Suriname |
| `SRG` | Guilder Suriname |
| `STD` | São Tomé e Principe Dobras |
| `SVC` | Coloni El Salvador |
| `SYP` | Sterlina siriana |
| `SZL` | Swaziland Emalangeni |
| `THB` | Baht Thailandia |
| `TJS` | Tagikistan Somoni |
| `TMM` | Turkmenistan Manat |
| `TND` | Dinari tunisini |
| `TOP` | Tonga Pa&#39;anga |
| `TRL` | Turchia Liras |
| `TTD` | Dollaro di Trinidad e Tobago |
| `TVD` | Tuvalu Dollari |
| `TWD` | Nuovi dollari di Taiwan |
| `TZS` | Scellino della Tanzania |
| `UAH` | Ucraina |
| `UGX` | Scelte ugandesi |
| `USD` | Dollaro statunitense |
| `UYU` | Pesos dell&#39;Uruguay |
| `UZS` | Uzbekistan |
| `VEB` | Venezuela Bolivares |
| `VND` | Dong del Vietnam |
| `VUV` | Vanuatu Vatu |
| `WST` | Samoa Tala |
| `XAF` | Communauté Financière Africaine Francs B |
| `XAG` | Argento |
| `XAU` | Oscursioni Gold |
| `XCD` | Dollaro dei Caraibi orientali |
| `XDR` | Fondo Monetario Internazionale |
| `XOF` | Communauté Financière Africaine Francs B |
| `XPD` | Palladio |
| `XPF` | Compagnie Français du Pacifique Francs |
| `XPT` | Platinum |
| `YER` | Yemen Rials |
| `ZAR` | Rand sudafricano |
| `ZMK` | Zambia Kwacha |
| `ZWD` | Dollaro dello Zimbabwe |
