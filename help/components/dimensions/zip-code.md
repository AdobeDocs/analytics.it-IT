---
title: Codice di avviamento postale
description: Il codice postale del visitatore.
feature: Dimensions
exl-id: 597619f8-a581-4491-beb2-c14b1f7b7bec
TQID: https://experienceleague.adobe.com/XHrUXKHrXiH0wsUr0klmPmA-DEq5T5yu18KLNT7oYeo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 9%
---
# Codice di avviamento postale

Il codice postale [dimension](overview.md) segnala il codice postale del visitatore. Puoi utilizzare questa dimensione per saperne di più sul successo della pubblicità locale o per vedere dove nel mondo il tuo sito offre le prestazioni migliori.

## Popolare questa dimensione con i dati

Questa dimensione è univoca in quanto contiene più modi per compilarla con i dati. Puoi utilizzare una delle due opzioni o una combinazione di entrambe:

* Impostare il codice postale direttamente utilizzando la variabile [`zip`](/help/implement/vars/page-vars/zip.md).
* Configuralo per estrarre i dati di geolocalizzazione. Quando si utilizza il comando geo zip, non viene impostata alcuna variabile. Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito. Per le implementazioni di Web SDK, abilita [!UICONTROL Geo Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

[!UICONTROL Zip option] in [Impostazioni account generali](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) controlla come popolare questa dimensione. La tabella di riferimento seguente si applica quando si imposta direttamente la variabile `zip`.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`zip`](/help/implement/vars/page-vars/zip.md) |
| **Campo Web SDK / XDM** | [`placeContext.geo.postalCode`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/geo) |
| **Parametro query** | [`zip`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<zip>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 50 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi Dimension includono il codice postale del visitatore.

## Paesi con codice postale supportati

* Isole Aland
* Albania
* Algeria
* Argentina
* Armenia
* Austria
* Australia
* Bangladesh
* Barbados
* Belgio
* Brasile
* Bulgaria
* Canada
* Cile
* Cina
* Colombia
* Costa Rica
* Croazia
* Repubblica Ceca
* Danimarca
* Ecuador
* Egitto
* Estonia
* Finlandia
* Francia
* Georgia
* Germania
* Gibilterra
* Grecia
* Grenada
* Guatemala
* Hong Kong RAS della Cina
* Ungheria
* India
* Indonesia
* Irlanda
* Israele
* Italia
* Giappone
* Giordania
* Kazakistan
* Kirghizistan
* Lettonia
* Libano
* Lituania
* Lussemburgo
* Malesia
* Malta
* Mauritius
* Messico
* Marocco
* Mozambico
* Nepal
* Paesi Bassi
* Nuova Zelanda
* Norvegia
* Pakistan
* Panama
* Perù
* Filippine
* Polonia
* Portogallo
* Porto Rico
* Qatar
* Romania
* Federazione russa
* Arabia Saudita
* Senegal
* Serbia
* Singapore
* Slovenia
* Sudafrica
* Corea del Sud
* Spagna
* Sri Lanka
* Svezia
* Svizzera
* Taiwan
* Thailandia
* Tunisia
* Turchia
* Ucraina
* Emirati Arabi Uniti
* Regno Unito
* Stati Uniti
* Uruguay
* Uzbekistan
* Venezuela
* Vietnam
