---
description: Descrive come definire codici valuta di destinazione per il funzionamento del supporto per più divise.
title: Supporto multivaluta
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# Supporto multivaluta

Questo documento descrive come definire i codici di valuta di destinazione per il supporto per più divise.

I codici valuta di destinazione sono definiti a tre livelli:

## Livello pagina

È possibile impostare una variabile JavaScript per la valuta di destinazione a livello di pagina. Il proprietario del sito imposta questa variabile con il codice valuta ISO 4217 di tre lettere appropriato (come indicato di seguito in questo documento). Se la variabile [currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) non è impostata a questo livello, la valuta predefinita sarà la stessa specificata nella suite di rapporti. Se la variabile a livello di pagina è in conflitto con la variabile specificata nella suite di rapporti, la variabile nella suite di rapporti avrà la precedenza.


## Livello suite di rapporti

La valuta **di** base è specificata al momento della [creazione delle suite](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)per report. Questa è l&#39;impostazione predefinita per la valuta e ha la precedenza sui codici valuta impostati a livello di pagina. Pertanto, se una suite di rapporti ha ordini che accettano dollari statunitensi, euro e sterline britanniche e la suite di rapporti ha un codice valuta predefinito impostato su &quot;Dollari USA&quot;, il database back-end di reporting traduce tutte le transazioni in Dollari USA.

I rapporti di marketing utilizzano il tasso di cambio al momento della richiesta dell&#39;immagine per convertire i valori di valuta a livello di pagina nei valori di valuta predefiniti della suite di rapporti. Le suite di rapporti utilizzano &quot;Dollari USA&quot; come valuta predefinita.


## Livello report

Gli utenti possono impostare la valuta predefinita indicata per la sessione di accesso utente. È possibile accedervi tramite il collegamento Opzioni **di** visualizzazione in qualsiasi rapporto di conversione. I rapporti di marketing utilizzano il tasso di cambio al momento dell&#39;esecuzione del rapporto per convertire i valori della valuta della suite di rapporti in valori della valuta specificati nel rapporto.

## Codici valuta supportati (ISO 4217)

Analytics supporta attualmente i seguenti formati di valuta per le transazioni di conversione:


AFA Afghanistan Afghanistan Afghanistan (AFA)

AFN Afghanistan Afghanistan Afghanistan (AFN)

Albania Leke (ALL)

Dinari algerini DZD (DZD)

&#39;AOA&#39; Angola Kwanza (AOA)

&#39;ARS&#39; Argentina Pesos (ARS)

&#39;AMD&#39; Armenia Drams (AMD)

&#39;AWG&#39; Aruba Guilders (AWG)

&#39;AUD&#39; Australia Dollari (AUD)

AZM&#39; Azerbaijan Manats (AZM)

&quot;AZN&quot; Azerbaijan New Manats (AZN)

Dollari Bahamas &quot;BSD&quot; (BSD)

Dinari del Bahrein &#39;BHD&#39; (BHD)

&#39;BDT&#39; Bangladesh Taka (BDT)

Barbados Dollari &quot;BBD&quot;

&#39;BYR&#39; Bielorussia Rubles (BYR)

Dollari Belize &#39;BZD&#39; (BZD)

Dollaro delle Bermuda BMD

&#39;BTN&#39; Bhutan Ngultrum (BTN)

BOB Bolivia Bolivianos (BOB)

&quot;BAM&quot; Bosnia-Erzegovina Marka convertibile (BAM)

BWP (Botswana Pulas)

&#39;BRL&#39; Brasile Reais (BRL)

Bollari Brunei (BND)

&#39;BGN&#39; Bulgaria Leva (BGN)

&#39;BIF&#39; Burundi Francs (BIF)

&#39;KHR&#39; Cambogia Riels (KHR)

Dollari canadesi &quot;CAD&quot; (CAD)

Escudo Capo Verde (CVE)

Dollaro delle Isole Cayman &#39;KYD&#39; (KYD)

&quot;CLP&quot; Cile Pesos (CLP)

Cina &#39;CNY&#39; Yuan renminbi (CNY)

&quot;COP&quot; Pesos Colombia (COP)

XOF&#39; Communauté Financière Africaine Francs BCEAO (XOF)

XAF&quot; Communauté Financière Africaine Francs BEAC (XAF)

KMF Comoros Francs (KMF)

Comptoir &#39;XPF&#39; Français du Pacifique Francs (XPF)

CDF Congo/Kinshasa Francs (CDF)

Coloni &#39;CRC&#39; Costa Rica (CRC)

HRK Croazia Kuna (HRK)

Prezzi &#39;CUC&#39; Cuba convertibili (CUC)

&#39;CUP&#39; Cuba Pesos (CUP)

&#39;CYP&#39; Sterline di Cipro (CYP)

&quot;CZK&quot; Repubblica Ceca Koruny (CZK)

DKK Danimarca Kroner (DKK)

DJF&#39; Djibouti Francs (DJF)

&quot;DOP&quot; Repubblica Dominicana Pesos (DOP)

Dollaro dei Caraibi orientali (XCD)

Sterlina egiziana &quot;EGP&quot;

Coloni El Salvador SVC

ERN Eritrea Nakfa (ERN)

ERR &#39;XBT&#39; (XBT)

&quot;EEK&quot; Estonia Krooni (EEK)

ETB Etiopia Birr (ETB)

Euro (EUR)

Sterline delle Isole Falkland &quot;FKP&quot;

Dollari Figi &quot;FJD&quot; (FJD)

GMD Dalasi (GMD)

&quot;GEL&quot; Georgia Lari (GEL)

GHC&#39; Ghana Cedis (GHC)

GHS&#39; Ghana Cedis (GHS)

&quot;GIP&quot; Gibilterra (GIP)

Oune Gold &#39;XAU&#39; (XAU)

&#39;GTQ&#39; Guatemala Quetzales (GTQ)

Sterline GGP Guernsey (GGP)

&quot;GNF&quot; Guinea Francs (GNF)

Dollari Guyana &#39;GYD&#39; (GYD)

&quot;HTG&quot; Haiti Gourdes (HTG)

HNL Honduras Lempiras (HNL)

&quot;HKD&quot; Dollari di Hong Kong (HKD)

&quot;HUF&quot; Ungheria Forint (HUF)

&quot;ISK&quot; Islanda Kronur (ISK)

Rupie &#39;INR&#39; India (INR)

&#39;IDR&#39; Indonesia Rupiah (IDR)

Diritti speciali di prelievo del Fondo monetario internazionale XDR

Iran Rials (IRR)

&quot;IQD&quot; Iraq Dinars (IQD)

&#39;IMP&#39; Isola di Man Pound (IMP)

&quot;ILS&quot; Israel New Shekels (ILS)

Dollari giamaicani &quot;JMD&quot; (JMD)

&#39;JPY&#39; Japan Yen (JPY)

&#39;JEP&#39; Jersey Pound (JEP)

Dinari giordani JOD (JOD)

&#39;KZT&#39; Kazakhstan Tenge (KZT)

&#39;KES&#39; Kenya Shillings (KES)

KWD (KWD)

&#39;KGS&#39; Kyrgyzstan Soms (KGS)

LAK&#39; Laos Kips (LAK)

&quot;LVL&quot; Lettonia Lati (LVL)

&quot;LBP&quot; Lebanon Pound (LBP)

&#39;LSL&#39; Lesotho Maloti (LSL)

Dollari &#39;LRD&#39; Liberia (LRD)

Dinari &#39;LYD&#39; Libia (LYD)

&quot;LTL&quot; Lituania Litai (LTL)

&#39;MOP&#39; Macau Patacas (MOP)

&#39;MKD&#39; Macedonia Denars (MKD)

Ariaria Madagascar &quot;MGA&quot; (MGA)

&#39;MWK&#39; Malawi Kwachas (MWK)

&#39;MYR&#39; Malaysia Ringgits (MYR)

Rufiya delle Maldive &quot;MVR&quot; (MVR)

MTL Malta Liri (MTL)

&quot;MRO&quot; Mauritania Ouguiyas (ORP)

&quot;MUR&quot; Mauritius Rupees (MUR)

MXN&#39; Mexico Pesos (MXN)

&#39;MDL&#39; Moldova Lei (MDL)

&quot;MNT&quot; Mongolia Tugriks (MNT)

&#39;MAD&#39; Morocco Dirhams (MAD)

&#39;MZN&#39; Mozambico Meticais (MZN)

&#39;MZM&#39; Mozambico Meticais (MZM)

&#39;MMK&#39; Myanmar Kyats (MMK)

&quot;NAD&quot; Dollari Namibia (NAD)

&#39;NPR&#39; Nepal Rupees (NPR)

&quot;ANG&quot; Olandesi Antille Guilder (ANG)

Dollaro neozelandese NZD

&#39;NIO&#39; Nicaragua Cordobas (NIO)

&quot;NGN&quot; Nigeria Nairas (NGN)

&#39;KPW&#39; Corea del Nord ha vinto (KPW)

&quot;NOK&quot; Norway Kroner (NOK)

&#39;OMR.&#39; Oman Rials (OMR)

Rupie pakistane &#39;PKR&#39; (PKR)

Unioni di palladio &#39;XPD&#39; (XPD)

&quot;PAB&quot; Panama Balboas (PAB)

PGK Papua Nuova Guinea Kina (PGK)

&#39;PYG&#39; Paraguay Guarani (PYG)

&#39;PEN&#39; Perù Nuevos Soles (PEN)

PHP&#39; Filippine Pesos (PHP)

&#39;XPT&#39; Platinum Ounces (XPT)

&quot;PLN&quot; Polonia Zlotych (PLN)

QAR (QAR)

&quot;ROL&quot; Romania Lei (ROL)

&quot;RON&quot; Romania Nuova Lei (RON)

Rubli della Russia &quot;RUB&quot; (RUB)

Rubli della Russia &quot;RUR&quot;

RWF Francs (RWF)

&#39;SHP&#39; Saint Helena Pound (SHP)

&#39;WST&#39; Samoa Tala (WST)

&quot;STD&quot; São Tomé e Principe Dobras (STD)

&#39;SAR&#39; Arabia Saudita Riyals (SAR)

&#39;SPL&#39; Seborga Luigini (SPL)

Dinari serbi &quot;RSD&quot; (RSD)

&quot;CSD&quot; Dinari serbi (CSD)

&quot;SCR&quot; Rupie delle Seychelles (SCR)

&quot;SLL&quot; Sierra Leone (SLL)

&#39;XAG&#39; Silver Ounces (XAG)

&quot;SGD&quot; Dollaro di Singapore (SGD)

&#39;SKK&#39; Slovacchia Koruny (SKK)

Talleri sloveni SIT

Dollari &quot;SBD&quot; delle Isole Salomone (SBD)

Scelte &#39;SOS&#39; Somalia (SOS)

&#39;ZAR&#39; South Africa Rand (ZAR)

&#39;KRW&#39; ha vinto la Corea del Sud (KRW)

&quot;LKR&quot; Sri Lanka Rupees (LKR)

&quot;SDD&quot; Dinari sudanesi (SDD)

&#39;SDG&#39; Sudan Pound (SDG)

Dollari Suriname SRD (SRD)

Guilders &#39;SRG&#39; Suriname (SRG)

&quot;SZL&quot; Swaziland Emalangeni (SZL)

&quot;SEK&quot; Svezia Kronor (SEK)

franchi svizzeri CHF (CHF)

&#39;SYP&#39; Syria Pound (SYP)

&#39;TWD&#39; Taiwan New Dollars (TWD)

TJS Tagikistan Somoni (TJS)

Scelte TZS Tanzania (TZS)

&#39;THB&#39; Thailand Baht (THB)

&#39;TOP&#39; Tonga Pa&#39;anga (TOP)

Dollari Trinidad e Tobago (TTD)

TND Tunisia Dinars (TND)

&#39;TRY&#39; Lira Turchia (TRY)

&#39;CTRL&#39; Turchia Liras (CTRL)

&#39;TMM&#39; Turkmenistan Manats (TMM)

&#39;TMT&#39; Turkmenistan New Manats (TMT)

&quot;TVD&quot; Dollaro Tuvalu (TVD)

&#39;UGX&#39; Uganda Shillings (UGX)

&#39;UAH&#39; Ucraina Hryvnia (UAH)

&#39;AED&#39; United Arab Emirates Dirhams (AED)

&quot;GBP&quot; Sterlina britannica (GBP)

&quot;USD&quot; selezionato Dollaro statunitense (USD)

&#39;UYU&#39; Uruguay Pesos (UYU)

&#39;UZS&#39; Uzbekistan Sums (UZS)

&#39;VUV&#39; Vanuatu Vatu (VUV)

&quot;VEB&quot; Venezuela Bolivares (VEB)

&quot;VEF&quot; Venezuela Bolivares Fuertes (VEF)

&#39;VND&#39; Vietnam Dong (VND)

&#39;YER&#39; Yemen Rials (YER)

&#39;ZMK&#39; Zambia Kwacha (ZMK)

&#39;ZMW&#39; Zambia Kwacha (ZMW)

Dollari Zimbabwe &#39;ZWD&#39; (ZWD)


## Esempio di AppMeasurement.js

La `currencyCode` variabile può essere definita a livello globale nel file AppMeasurement.js. La definizione della variabile currencyCode in questo file assicura che tutte le transazioni valutarie utilizzino un codice valuta uniforme. L&#39;esempio seguente specifica Euro come `currencyCode` variabile nel file AppMeasurement.js `CONFIG SECTION` . Tutti gli eventi di acquisto saranno interpretati segnalando come &quot;Euro&quot;.

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

Per ulteriori informazioni sulla modifica del file AppMeasurement.js, vedi [Inserimento di codice nel file](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)AppMeasurement.js.

## Note aggiuntive sull’implementazione

* Tenere presente che, mentre i codici valuta possono variare tra le pagine, tutti gli elementi delle linee di conversione definiti in una determinata richiesta di pagina devono utilizzare la stessa valuta (ad esempio, non è possibile definire Euro, Sterline britanniche e Dollari USA nella stessa visualizzazione pagina). Se non si desidera eseguire alcuna conversione valutaria, lasciare vuoto il valore currencyCode. In questo modo i valori inviati vengono passati direttamente ai report senza conversione.

* Se si imposta un currencyCode non valido (qualsiasi valore non presente nell&#39;elenco dei codici di valuta supportati), l&#39;intero hit viene escluso e i dati non vengono raccolti per la transazione. Prima di impostare `currencyCode` in produzione, utilizzate una suite di rapporti di prova per verificare che i dati vengano raccolti e che la conversione della valuta sia corretta.

* Valute che non utilizzano un punto (.) come separatore deve essere modificato per utilizzare il punto invece del separatore tipico. Ad esempio, la corona svedese, che utilizza una virgola (,), deve essere modificata per utilizzare un punto invece della virgola. Analytics utilizza la virgola per separare i valori e i dati non verranno passati correttamente. Il punto passerà correttamente il valore ai report.
