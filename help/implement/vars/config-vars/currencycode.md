---
title: Qual è la variabile currencyCode e come si utilizza?
description: Per i siti di eCommerce, imposta la valuta in cui si trova la pagina.
translation-type: tm+mt
source-git-commit: 4d0d5ca99049e48fcf1f248f78ecef94534b6815
workflow-type: tm+mt
source-wordcount: '824'
ht-degree: 0%

---


# currencyCode

Per i siti che utilizzano l’e-commerce, i ricavi e la valuta sono una parte importante di Analytics. Molti siti, soprattutto quelli che si estendono su più paesi, utilizzano valute diverse. Utilizza la variabile `currencyCode` per assicurarti che gli attributi dei ricavi siano nella valuta corretta.

Se `currencyCode` non è definito, i valori monetari definiti nella variabile [`products`](../page-vars/products.md) e gli eventi di valuta vengono trattati come se fossero uguali alla valuta della suite di rapporti. Per visualizzare la valuta della suite di rapporti, consulta [Impostazioni generali dell’account](/help/admin/admin/general-acct-settings-admin.md) nella guida utente dell’amministratore .

Se `currencyCode` è definito e corrisponde alla valuta della suite di rapporti, non viene applicata alcuna conversione di valuta.

Se `currencyCode` è definito ed è diverso dalla valuta della suite di rapporti, in Adobe viene applicata una conversione di valuta in base al tasso di cambio del giorno corrente. Partner di Adobe con [XE](https://xe.com) per convertire la valuta ogni giorno. Tutti i valori memorizzati nei server di raccolta dati vengono infine memorizzati nella valuta della suite di rapporti.

>[!IMPORTANT]
>
>Se `currencyCode` contiene un valore non valido, l&#39;intero hit viene eliminato causando la perdita di dati. Assicurati che questa variabile sia definita correttamente se la utilizzi nell&#39;implementazione.

Questa variabile non persiste tra i risultati. Assicurati che questa variabile sia definita su ogni pagina che include ricavi o eventi di valuta.

## Codice valuta in Adobe Experience Platform Launch

Il codice valuta è un campo sotto il pannello a soffietto [!UICONTROL General] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
4. Espandi il [!UICONTROL General] pannello a soffietto, che mostra il campo [!UICONTROL Currency Code] .

È possibile utilizzare un codice valuta predefinito o un codice valuta personalizzato. Se utilizzi un codice valuta personalizzato, assicurati che il codice sia valido.

## Codice valuta nell&#39;SDK di Adobe Experience Platform Mobile

Il codice valuta viene passato agli SDK di Adobe Experience Platform Mobile tramite variabili di dati di contesto nell&#39;estensione Adobe Analytics.

1. Imposta il codice della valuta in una variabile di dati di contesto durante `trackState` o `trackAction`.
2. Crea una regola di elaborazione nell’Admin Console di Adobe Analytics per la suite di rapporti. Imposta la regola per sovrascrivere la variabile Codice valuta.
3. Passa il codice della valuta alla variabile `products` nella chiamata a `trackState` o `trackAction`.

È possibile utilizzare un codice valuta predefinito o un codice valuta personalizzato. Se utilizzi un codice valuta personalizzato, assicurati che il codice sia valido.

## s.currencyCode nell&#39;editor di codice personalizzato AppMeasurement e Launch

La variabile `s.currencyCode` è una stringa contenente un codice maiuscolo di 3 lettere che rappresenta la valuta nella pagina.

```js
s.currencyCode = "USD";
```

I seguenti codici valuta sono validi:

| Codice della valuta | Descrizione valuta |
| --- | --- |
| `AED` | Dirhams degli Emirati Arabi Uniti |
| `AFA` | Afghanistan afgani |
| `ALL` | Albania Leke |
| `AMD` | Dram in Armenia |
| `ANG` | Guilibri Di Atille Olandesi |
| `AOA` | Angola Kwanza |
| `ARS` | Pesos Argentina |
| `AUD` | Dollaro australiano |
| `AWG` | Aruba Guilder |
| `AZM` | Manat azeri |
| `BAM` | Marka convertibile Bosnia-Erzegovina |
| `BBD` | Dollari Barbados |
| `BDT` | Taka del Bangladesh |
| `BGN` | Leva |
| `BHD` | Dinari del Bahrein |
| `BIF` | Francs del Burundi |
| `BMD` | Dollaro delle Bermuda |
| `BND` | Dollaro del Brunei |
| `BOB` | Bolivia |
| `BRL` | Brasile Reais |
| `BSD` | Dollaro delle Bahamas |
| `BTN` | Bhutan Ngultrum |
| `BWP` | Pulas Botswana |
| `BYR` | Rubli della Bielorussia |
| `BZD` | Dollaro Belize |
| `CAD` | Dollaro canadese |
| `CDF` | Francs Congo/Kinshasa |
| `CHF` | Franchi svizzeri |
| `CLP` | Pesos del Cile |
| `CNY` | Renminbi cinese Yuan |
| `COP` | Pesos Colombia |
| `CRC` | Colori Costa Rica |
| `CSD` | Dinari serbi |
| `CUP` | Cuba Pesos |
| `CVE` | Escudos del Capo Verde |
| `CYP` | Limiti di Cipro |
| `CZK` | Repubblica Ceca Corea |
| `DJF` | Francesi di Gibuti |
| `DKK` | Corona danese |
| `DOP` | Pesos Repubblica Dominicana |
| `DZD` | Dinari algerini |
| `EEK` | Estonia Krooni |
| `EGP` | Sterlina egiziana |
| `ERN` | Eritrea Nakfa |
| `ETB` | Birra Etiope |
| `EUR` | Euro |
| `FJD` | Dollaro delle Figi |
| `FKP` | Sterline Isole Falkland |
| `GBP` | Sterline Regno Unito |
| `GEL` | Georgia Lari |
| `GGP` | Sterlina di Guernsey |
| `GHC` | Ghana Cedis |
| `GIP` | Limiti di Gibilterra |
| `GMD` | Gambia Dalasi |
| `GNF` | Francs della Guinea |
| `GTQ` | Guatemala Quetzales |
| `GYD` | Dollaro della Guyana |
| `HKD` | Dollaro di Hong Kong |
| `HNL` | Honduras Lempiras |
| `HRK` | Croazia Kuna |
| `HTG` | Haiti Gourdes |
| `HUF` | Fiorino ungherese |
| `IDR` | Rupie indonesiane |
| `ILS` | Israele: nuovi sicli |
| `IMP` | Isola di Man Pound |
| `INR` | Rupes dell&#39;India |
| `IQD` | Dinari iracheni |
| `IRR` | Iran Riyal |
| `ISK` | Corona islandese |
| `JEP` | Ferite da maglia |
| `JMD` | Dollaro giamaicano |
| `JOD` | Dinari giordani |
| `JPY` | Yen del Giappone |
| `KES` | Scalli del Kenya |
| `KGS` | Soma del Kirghizistan |
| `KHR` | Cambogia |
| `KMF` | Francs Comore |
| `KPW` | Corea del Nord |
| `KRW` | La Corea del Sud vince |
| `KWD` | Dinari del Kuwait |
| `KYD` | Dollaro delle Isole Cayman |
| `KZT` | Tenge Kazakistan |
| `LAK` | Kips del Laos |
| `LBP` | Libri |
| `LKR` | Rupie dello Sri Lanka |
| `LRD` | Dollaro liberiano |
| `LSL` | Lesotho Maloti |
| `LTL` | Lituania Litai |
| `LVL` | Lettonia Lati |
| `LYD` | Dinari libici |
| `MAD` | Sporchi marocchini |
| `MDL` | Moldavia |
| `MGA` | Ariete del Madagascar |
| `MKD` | La Macedonia Denuncia |
| `MMK` | Kyat in Myanmar |
| `MNT` | Mongolia Tugriks |
| `MOP` | Macao Patacas |
| `MRO` | Mauritania Ouguiyas |
| `MTL` | Malta Liri |
| `MUR` | Mauritius Rupees |
| `MVR` | Maldive Rufiya |
| `MWK` | Kwacha del Malawi |
| `MXN` | Pesos del Messico |
| `MYR` | Malesia Ringgits |
| `MZM` | Mozambico Meticais |
| `NAD` | Dollaro della Namibia |
| `NGN` | Nigeria Nairas |
| `NIO` | Cordobas d&#39;oro Nicaragua |
| `NOK` | Corona norvegese |
| `NPR` | Rupes del Nepal |
| `NZD` | Dollaro neozelandese |
| `OMR` | Riyal Oman |
| `PAB` | Panama Balboas |
| `PEN` | Sole Nuevos Perù |
| `PGK` | Papua Nuova Guinea Kina |
| `PHP` | Pesos Filippine |
| `PKR` | Rupie pakistane |
| `PLN` | Polonia Zlotych |
| `PYG` | Paraguay Guarani |
| `QAR` | Qatar Riyals |
| `ROL` | Romania Lei |
| `RUR` | Russia Rubli |
| `RWF` | Francs del Ruanda |
| `SAR` | Riyal dell&#39;Arabia Saudita |
| `SBD` | Dollaro delle Isole Salomone |
| `SCR` | Rupie Seychelles |
| `SDD` | Dinari sudanesi |
| `SEK` | Corona svedese |
| `SGD` | Dollaro di Singapore |
| `SHP` | Sant&#39;Helena |
| `SIT` | Talleri Slovenia |
| `SKK` | Slovacchia |
| `SLL` | Leoni della Sierra Leone |
| `SOS` | Somalia Scellino |
| `SPL` | Seborga Luigini |
| `SRD` | Dollaro di Suriname |
| `SRG` | Guilder Suriname |
| `STD` | São Tomé e Principe Dobras |
| `SVC` | Coloni El Salvador |
| `SYP` | Siria: limiti |
| `SZL` | Swaziland Emalangeni |
| `THB` | Baht Thailandia |
| `TJS` | Tagikistan Somoni |
| `TMM` | Turkmenistan Manat |
| `TND` | Dinari tunisini |
| `TOP` | Tonga Pa&#39;anga |
| `TRL` | Turchia Liras |
| `TTD` | Dollaro di Trinidad e Tobago |
| `TVD` | Dollaro Tuvalu |
| `TWD` | Nuovi dollari di Taiwan |
| `TZS` | Scalli della Tanzania |
| `UAH` | Ucraina |
| `UGX` | Scalli dell&#39;Uganda |
| `USD` | Dollaro degli Stati Uniti |
| `UYU` | Pesos Uruguay |
| `UZS` | Uzbekistan |
| `VEB` | Bolivares Venezuela |
| `VND` | Dong del Vietnam |
| `VUV` | Vanuatu Vatu |
| `WST` | Samoa Tala |
| `XAF` | Communauté Financière Africaine Francs B |
| `XAG` | Unioni in argento |
| `XAU` | Oscillazioni oro |
| `XCD` | Dollaro dei Caraibi orientali |
| `XDR` | Strumento speciale del Fondo monetario internazionale |
| `XOF` | Communauté Financière Africaine Francs B |
| `XPD` | Unioni di palladio |
| `XPF` | Compiti Français du Pacifique Francs |
| `XPT` | Unioni platiniche |
| `YER` | Yemen Riyal |
| `ZAR` | Rand sudafricano |
| `ZMK` | Zambia Kwacha |
| `ZWD` | Dollaro dello Zimbabwe |
