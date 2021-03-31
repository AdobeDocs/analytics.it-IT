---
description: Descrive come definire codici valuta di destinazione per il funzionamento del supporto multi-valuta.
title: Supporto multi-valuta
uuid: null
translation-type: tm+mt
source-git-commit: 4359f451692b86087efe27d4b3ec49ca85b7addc
workflow-type: tm+mt
source-wordcount: '1383'
ht-degree: 3%

---


# Supporto multi-valuta

Questo documento descrive come definire i codici valuta di destinazione per il supporto per più valute.

I codici di valuta di destinazione sono definiti a tre livelli:

## Livello pagina

Puoi impostare una variabile JavaScript per la valuta di destinazione a livello di pagina. Il proprietario del sito imposta questa variabile con il codice valuta ISO 4217 a tre lettere appropriato (come indicato di seguito in questo documento). Se la variabile [currencyCode](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/config-vars/currencycode.html) non è impostata a questo livello, la valuta predefinita sarà la stessa di quella specificata nella suite di rapporti. Se la variabile a livello di pagina è in conflitto con la variabile specificata nella suite di rapporti, la variabile nella suite di rapporti avrà la precedenza.


## Livello suite di rapporti

La **valuta di base** viene specificata quando [si creano suite di rapporti](https://docs.adobe.com/content/help/it-IT/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html). Questa è l&#39;impostazione predefinita per la valuta e ha la precedenza sui codici della valuta impostati a livello di pagina. Pertanto, se una suite di rapporti ha ordini che accettano dollari USA, euro e sterline britanniche e la suite di rapporti ha un codice valuta predefinito impostato su &quot;Dollari USA&quot;, il database back-end di reporting traduce tutte le transazioni in Dollari USA.

I rapporti di marketing utilizzano il tasso di cambio nel momento in cui si verifica la richiesta di immagine per tradurre i valori di valuta a livello di pagina nei valori di valuta predefiniti della suite di rapporti. Le suite di rapporti utilizzano &quot;Dollari USA&quot; come valuta predefinita.


## Livello del rapporto

Gli utenti possono impostare la valuta predefinita indicata per la sessione di accesso dell’utente. È possibile accedervi tramite il collegamento **Opzioni di visualizzazione** in qualsiasi rapporto di conversione. I rapporti di marketing utilizzano il tasso di cambio al momento dell’esecuzione del rapporto per tradurre i valori di valuta della suite di rapporti in valori di valuta specificati nel rapporto.

## Codici valuta supportati (ISO 4217)

Analytics supporta attualmente i seguenti formati di valuta per le transazioni di conversione:


Afganistan Afghanistan (AFA)

Afn Afghanistan Afghanistan Afghanistan (AFN)

Albania Leke (ALL)

Dinari algerini &quot;DZD&quot; (DZD)

AOA&#39; Angola Kwanza (AOA)

&#39;ARS&#39; Argentina Pesos (ARS)

Drams &quot;AMD&quot; Armenia (AMD)

&#39;AWG&#39; Aruba Guilders (AWG)

&quot;AUD&quot; Dollaro australiano (AUD)

AZM&#39; Azerbaijan Manats (AZM)

&quot;AZN&quot; Azerbaijan nuovi manat (AZN)

Dollari Bahamas &quot;BSD&quot; (BSD)

Dinari del Bahrein &quot;BHD&quot; (BHD)

&#39;BDT&#39; Bangladesh Taka (BDT)

Dollari Barbados &quot;BBD&quot; (BBD)

Rubli bielorussi &quot;BYR&quot; (BYR)

Dollari Belize &quot;BZD&quot; (BZD)

Dollaro delle Bermuda (BMD)

&quot;BTN&quot; Ngultrum Bhutan (BTN)

Bolivia Bolivianos (BOB)

&quot;BAM&quot; Bosnia-Erzegovina Marka convertibile (BAM)

&quot;BWP&quot; Botswana Pulas (BWP)

Brasile Reais (BRL)

Dollaro del Brunei (BND)

&#39;BGN&#39; Bulgaria Leva (BGN)

Francs Burundi BIF (BIF)

&#39;KHR&#39; Cambogia Riels (KHR)

Dollari canadesi &quot;CAD&quot; (CAD)

Escudos del Capo Verde (CVE)

Dollaro delle Isole Cayman &quot;KYD&quot; (KYD)

Pesos cileni &quot;CLP&quot; (CLP)

Cina &#39;CNY&#39; Yuan Renminbi (CNY)

&quot;COP&quot; Pesos Colombia (COP)

XOF&#39; Communauté Financière Africaine Francs BCEAO (XOF)

XAF&#39; Communauté Financière Africaine Francs BEAC (XAF)

&quot;KMF&quot; Comoros Francs (KMF)

Comptoirs Français du Pacifique Francs (XPF)

Francs Congo/Kinshasa (CDF)

Coloni &#39;CRC&#39; Costa Rica (CRC)

&quot;HRK&quot; Croazia Kuna (HRK)

Pesos convertibili a Cuba (CUC)

&#39;CUP&#39; Cuba Pesos (CUP)

Limiti di Cipro CYP (CYP)

&quot;CZK&quot; Repubblica Ceca Koruny (CZK)

&quot;DKK&quot; Danimarca Kroner (DKK)

DJF Djibouti Francs (DJF)

&quot;DOP&quot; Repubblica Dominicana Pesos (DOP)

Dollaro dei Caraibi orientali (XCD)

&quot;EGP&quot; Egitto Pound (EGP)

Coloni El Salvador SVC

ERN&#39; Eritrea Nakfa (ERN)

ERR &#39;XBT&#39; (XBT)

&quot;EEK&quot; Estonia Krooni (EEK)

ETB&#39; Etiopia Birr (ETB)

Euro (EUR)

Sterlina delle Isole Falkland &quot;FKP&quot; (FKP)

Dollaro figiano &quot;FJD&quot; (FJD)

GMD Gambia Dalasi (GMD)

&quot;GEL&quot; Georgia Lari (GEL)

Ghana Cedis (GHC)

Ghana Cedis (GHS)

&#39;GIP&#39; Gibilterra limiti (GIP)

Unioni Gold XAU (XAU)

Quetzales Guatemala GTQ (GTQ)

Sterline di Guernsey GGP (GGP)

Francs della Guinea (GNF)

Dollari Guyana &quot;GYD&quot; (GYD)

&quot;HTG&quot; Haiti Gourdes (HTG)

HNL Honduras Lempiras (HNL)

&quot;HKD&quot; Dollaro di Hong Kong (HKD)

&quot;HUF&quot; Ungheria Forint (HUF)

&quot;ISK&quot; Islanda Kronur (ISK)

&quot;INR&quot; India Rupees (INR)

&quot;IDR&quot; Indonesia Rupiah (IDR)

Diritti speciali di prelievo (XDR) del Fondo monetario internazionale

Iran Rials (IRR)

Dinari iracheni &quot;IQD&quot; (IQD)

Isola di Man Pound (IMP)

&#39;ILS&#39; Israel New Shekels (ILS)

Dollari giamaicani &quot;JMD&quot; (JMD)

JPY&#39; Japan Yen (JPY)

&#39;JEP&#39; Jersey Pound (JEP)

Dinari giordani &quot;JOD&quot; (JOD)

Tenge Kazakistan &quot;KZT&quot; (KZT)

Shillings Kenya KES (KES)

Dinari kuwaitiani &#39;KWD&#39; (KWD)

KGS Soms kirghizo (KGS)

&#39;LAK&#39; Laos Kips (LAK)

&quot;LVL&quot; Lettonia Lati (LVL)

&quot;LBP&quot; Libano: ferite (LBP)

&#39;LSL&#39; Lesotho Maloti (LSL)

Dollari della Liberia (LRD)

Dinari libici &quot;LYD&quot; (LYD)

&quot;LTL&quot; Lituania Litai (LTL)

&#39;MOP&#39; Macau Patacas (MOP)

&#39;MKD&#39; Macedonia Denars (MKD)

Ariary Madagascar &quot;MGA&quot; (MGA)

Malawi Kwachas (MWK)

Ringgits Malesia &#39;MYR&#39; (MYR)

Rufiya delle Maldive &#39;MVR&#39; (MVR)

&quot;MTL&quot; Malta Liri (MTL)

&quot;MRO&quot; Mauritania Ouguiyas (ORP)

&quot;MUR&quot; Mauritius Rupees (MUR)

MXN&#39; Messico Pesos (MXN)

&quot;MDL&quot; Moldova Lei (MDL)

&quot;MNT&quot; Tugriks Mongolia (MNT)

&quot;MAD&quot; Marocco Dirhams (MAD)

MZN&#39; Mozambico Meticais (MZN)

&quot;MZM&quot; Mozambico Meticais (MZM)

&quot;MMK&quot; Myanmar Kyats (MMK)

Dollari della Namibia &quot;NAD&quot; (NAD)

Rupie del Nepal &#39;NPR&#39; (NPR)

Guilder per le Antille olandesi ANG (ANG)

Dollari neozelandesi (NZD)

&quot;NIO&quot; Nicaragua Cordobas (NIO)

&quot;NGN&quot; Nigeria Nairas (NGN)

&#39;KPW&#39; ha vinto la Corea del Nord (KPW)

&quot;NOK&quot; Norvegia Kroner (NOK)

&#39;OMR.&#39; Oman Rials (OMR)

&quot;PKR&quot; Pakistan Rupees (PKR)

Unioni di palladio &quot;XPD&quot; (XPD)

Panama Balboas (PAB)

&#39;PGK&#39; Papua Nuova Guinea Kina (PGK)

Paraguay Guarani (PYG)

&quot;PEN&quot; Nevos Soles (PEN) Perù

PHP&#39; Filippine Pesos (PHP)

Unioni platiniche &#39;XPT&#39; (XPT)

&quot;PLN&quot; Polonia Zlotych (PLN)

QAR (QAR)

&quot;ROL&quot; Romania Lei (ROL)

&quot;RON&quot; Romania New Lei (RON)

Rubli Russia &#39;RUB&#39; (RUB)

Rubli russi &quot;RUR&quot; (RUR)

Francs del Ruanda (RWF)

&quot;SHP&quot; Saint Helena Pound (SHP)

&#39;WST&#39; Samoa Tala (WST)

STD São Tomé e Principe Dobras (STD)

Riyals (RAS) dell&#39;Arabia Saudita

&quot;SPL&quot; Seborga Luigini (SPL)

Dinari serbi &quot;RSD&quot; (RSD)

&quot;CSD&quot; Dinari serbi (CSD)

&quot;SCR&quot; Seicelle Rupees (SCR)

&quot;SLL&quot; Sierra Leone Leones (SLL)

Unioni d&#39;argento XAG (XAG)

Dollaro di Singapore (SGD)

&quot;SKK&quot; Slovacchia Koruny (SKK)

Talleri Slovenia SIT (SIT)

Dollaro delle Isole Salomone &quot;SBD&quot; (SBD)

Scalli somali &quot;SOS&quot; (SOS)

ZAR (ZAR)

&#39;KRW&#39; ha vinto la Corea del Sud (KRW)

Rupia dello Sri Lanka &#39;LKR&#39; (LKR)

SDD (Sudan Dinars)

&quot;SDG&quot; Sudan Pound (SDG)

Dollari di Suriname &quot;SRD&quot; (SRD)

Guilder a Suriname &quot;SRG&quot; (SRG)

&quot;SZL&quot; Swaziland Emalangeni (SZL)

&quot;SEK&quot; Svezia Kronor (SEK)

franchi svizzeri CHF (CHF)

&#39;SYP&#39; Syria Pound (SYP)

&quot;TWD&quot; Taiwan nuovi dollari (TWD)

TJS Tagikistan Somoni (TJS)

Scalli Tanzania (TZS)

&#39;THB&#39; Thailand Baht (THB)

&quot;TOP&quot; Tonga Pa&#39;anga (TOP)

Dollaro di Trinidad e Tobago (TTD)

Dinari tunisini &quot;TND&quot; (TND)

&quot;TRY&quot; Lira Turchia (TRY)

&quot;CTRL&quot; Turchia Liras (CTRL)

&quot;TMM&quot; Turkmenistan Manats (TMM)

&#39;TMT&#39; Turkmenistan New Manats (TMT)

Dollari Tuvalu &quot;TVD&quot; (TVD)

Shillings Uganda &#39;UGX&#39; (UGX)

Ucraina Hryvnia (UAH)

Dirhams degli Emirati Arabi Uniti &quot;AED&quot; (AED)

&quot;GBP&quot; Sterline del Regno Unito (GBP)

&quot;USD&quot; selezionato Dollari degli Stati Uniti (USD)

&quot;UYU&quot; Uruguay Pesos (UYU)

UZS&#39; Uzbekistan Sums (UZS)

&#39;VUV&#39; Vanuatu Vatu (VUV)

&quot;VEB&quot; Venezuela Bolivares (VEB)

&quot;VEF&quot; Venezuela Bolivares Fuertes (VEF)

&#39;VND&#39; Vietnam Dong (VND)

Yemen Rials &#39;YER&#39; (YER)

&quot;ZMK&quot; Zambia Kwacha (ZMK)

&#39;ZMW&#39; Zambia Kwacha (ZMW)

Dollari dello Zimbabwe &quot;ZWD&quot; (ZWD)


## Esempio di AppMeasurement.js

La variabile `currencyCode` può essere definita globalmente nel file AppMeasurement.js . La definizione della variabile currencyCode in questo file assicura che tutte le transazioni valutarie utilizzino un codice valuta uniforme. L&#39;esempio seguente specifica Euros come variabile `currencyCode` nel `CONFIG SECTION` del file AppMeasurement.js. Tutti gli eventi di acquisto saranno interpretati segnalando come operazioni &quot;Euro&quot;.

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

Per ulteriori informazioni sulla modifica del file AppMeasurement.js, consulta [Inserimento di codice nel file AppMeasurement.js](https://docs.adobe.com/content/help/it-IT/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.translate.html).

## Note aggiuntive sull’implementazione

* Tieni presente che mentre i codici valuta possono cambiare tra le pagine, tutti gli elementi delle linee di conversione definiti in una determinata richiesta di pagina devono utilizzare la stessa valuta (ad esempio, non è possibile definire Euro, Sterline britanniche e Dollari USA nella stessa visualizzazione di pagina). Se non si desidera eseguire alcuna conversione di valuta, lasciare vuoto il valore currencyCode. In questo modo i valori inviati vengono passati direttamente ai rapporti senza conversione.

* L&#39;impostazione di un currencyCode non valido (qualsiasi valore non presente nell&#39;elenco dei codici di valuta supportati) comporta l&#39;esclusione dell&#39;intero hit e la mancata raccolta dei dati per la transazione. Prima di impostare `currencyCode` in produzione, utilizza una suite di rapporti di prova per verificare che i dati siano raccolti e che la conversione di valuta sia corretta.

* Valute che non utilizzano un punto (.) come separatore deve essere modificato per utilizzare il punto anziché il separatore tipico. Ad esempio, lo svedese Krona, che utilizza una virgola (,), deve essere modificato per utilizzare un punto invece della virgola. Analytics utilizza la virgola per separare i valori e i dati non verranno passati correttamente. Il periodo passa correttamente il valore ai rapporti.
