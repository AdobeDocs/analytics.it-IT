---
title: Dimensioni di ricerca mobile
description: Dimension basati sull’indirizzo IP e sull’agente utente del dispositivo.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 0%

---

# Dimensioni di ricerca mobile

*Questa pagina fa riferimento alle proprietà dei dispositivi mobili che accedono al sito web. Consulta [Dimensioni del ciclo di vita mobile](lifecycle-dimensions.md) o [Metriche del ciclo di vita mobile](../metrics/lifecycle-metrics.md) per il tracciamento all’interno di un’app mobile.*

Ricerca mobile [dimensioni](overview.md) fornisci informazioni sulle proprietà dei dispositivi mobili che visitano il tuo sito. Queste proprietà si basano sull’agente utente e sull’indirizzo IP dell’hit. Puoi utilizzare queste dimensioni per comprendere meglio le funzioni supportate da un dispositivo mobile.

## Popola queste dimensioni con i dati

Queste dimensioni fanno riferimento a regole di ricerca interne a Adobe.

* Per [!UICONTROL Mobile Carrier] dimensione, partner di Adobe con [Elemento digitale](https://www.digitalelement.com/) utilizzo di NetAcuity per mantenere le ricerche tra l&#39;indirizzo IP e il gestore di telefonia mobile.
* Per tutte le altre dimensioni dei dispositivi mobili, Adobe collabora con [DeviceAtlas](https://deviceatlas.com/) per mantenere le ricerche tra l’agente utente e ogni rispettiva dimensione mobile.

La disponibilità di queste dimensioni dipende dal tipo di implementazione:

* Ad AppMeasurement, le implementazioni di queste dimensioni funzionano in modo predefinito.
* Per le implementazioni dell’SDK web, abilita [!UICONTROL Geo Lookup] (per gestore di telefonia mobile) o [!UICONTROL Device Lookup] (per tutte le altre dimensioni) quando [configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html).

## Descrizioni delle dimensioni mobile

>[!NOTE]
>
>Elementi Dimension etichettati `"None"` sono dispositivi non mobili. Se desideri un rapporto che includa solo i dispositivi mobili, trascina la dimensione &quot;Dispositivo mobile&quot; nell’area del segmento dell’area di lavoro di Workspace.

* **[!UICONTROL Mobile audio support]**: determina i formati di file che il dispositivo può riprodurre. I valori di esempio includono `"MP3"`, `"AAC"`, e `"MIDI Monophonic"`. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.
* **[!UICONTROL Mobile carrier]**: provider di dati o telefono per il dispositivo. I valori di esempio includono `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`, e `"Verizon"`.
* **[!UICONTROL Mobile color depth]**: profondità colore del dispositivo mobile, in bit.
* **[!UICONTROL Mobile cookie support]**: determina se il dispositivo mobile supporta i cookie. Questa dimensione non indica se il browser accetta i cookie. Gli elementi del Dimension includono `"Supported"`, `"Not supported"`, e `"Unknown"`.
* **[!UICONTROL Mobile device]**: dispositivo mobile utilizzato dal visitatore.
* **[!UICONTROL Mobile device number]**: determina se il dispositivo mobile trasmette il suo numero. Questa dimensione non fornisce il numero di cellulare stesso. Gli elementi del Dimension includono `"Supported"`, `"Not supported"`, e `"Unknown"`.
* **[!UICONTROL Mobile device type]**: tipo di dispositivo mobile. I valori di esempio includono `"Mobile phone"`, `"Tablet"`, `"Media player"`, e `"Gaming console"`.
* **[!UICONTROL Mobile DRM]**: tipo di DRM supportato dal dispositivo mobile. I valori di esempio includono `"DRM OMA forward"`, `"DRM OMA combined delivery"`, e `"DRM OMA separate delivery"`.
* **[!UICONTROL Mobile image support]**: i tipi di immagini supportati dal dispositivo mobile. I valori di esempio includono `"PNG"`, `"JPEG"`, e `"GIF 87"`. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.
* **[!UICONTROL Mobile information services]**: i tipi di servizi di notizie supportati dal dispositivo. I dispositivi moderni in genere non segnalano queste informazioni.
* **[!UICONTROL Mobile Java VM]**: versioni di Java supportate dal dispositivo.
* **[!UICONTROL Mobile mail decoration]**: determina se il dispositivo supporta [Diventa](https://en.wikipedia.org/wiki/Decome), una funzione una volta popolare sui dispositivi giapponesi.
* **[!UICONTROL Mobile manufacturer]**: classifica i dispositivi mobili per produttore. I valori di esempio includono `"Apple"`, `"Samsung"`, `"Huawei"`, e `"Motorola"`.
* **[!UICONTROL Mobile max bookmark length]**: numero massimo di byte supportati dal dispositivo mobile negli URL con segnalibro. I dispositivi moderni in genere non hanno un limite.
* **[!UICONTROL Mobile max browser URL length]**: numero massimo di byte supportati dal dispositivo mobile negli URL. I dispositivi moderni in genere non hanno un limite.
* **[!UICONTROL Mobile max email length]**: numero massimo di byte supportati dal dispositivo mobile in un messaggio e-mail. I dispositivi moderni in genere non hanno un limite.
* **[!UICONTROL Mobile net protocols]**: i tipi di protocollo supportati dal dispositivo per l’accesso a Internet. I valori di esempio includono `"EDGE"`, `"GPRS"`, `"UMTS"`, e `"LTE"`.
* **[!UICONTROL Mobile operating system (deprecated)]**: utilizza [Sistema operativo](operating-systems.md) al suo posto.
* **[!UICONTROL Mobile push to talk]**: determina se il dispositivo supporta il PTT (Push to talk), che consente al dispositivo mobile di comportarsi in modo simile a una radio a due vie. I dispositivi moderni in genere non segnalano questa funzione.
* **[!UICONTROL Mobile screen height]**: altezza dello schermo, in pixel. iPhone segnala sempre `"480"` a causa dell’impossibilità di determinare la versione del dispositivo iPhone. Consulta la sezione seguente sulla determinazione della versione del dispositivo iPhone.
* **[!UICONTROL Mobile screen size]**: dimensioni complete del dispositivo mobile in pixel. Le dimensioni dello schermo riportate non indicano l’orientamento del dispositivo. Indipendentemente dall’orientamento dello schermo, nel rapporto ogni dispositivo ha una risoluzione fissa dello schermo. Questa dimensione si basa su ricerche che determinano quale orientamento è più probabile. Puoi vedere dimensioni come `"768x1024"` e `"1024x768"` nello stesso rapporto, in cui ogni dimensione rappresenta uno o più dispositivi diversi.
* **[!UICONTROL Mobile screen width]**: larghezza dello schermo, in pixel.
* **[!UICONTROL Mobile video support]**: formati e codec di file video supportati dal dispositivo mobile. Esistono diversi elementi dimensionali per diversi codec di file MP4 e 3GPP. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.

## Separazione di iPhone per modello o versione

I dispositivi mobili segnalano la versione del firmware nella stringa dell’agente utente, non la versione del dispositivo. Ad esempio, un iPhone della generazione corrente contiene un agente utente identico all’iPhone dell’ultima generazione se si trovano nella stessa versione del firmware. Poiché non è possibile determinare la versione di un dispositivo iPhone utilizzando JavaScript, tutti gli iPhone appartengono allo stesso bucket. Le dimensioni di Mobile si basano rigorosamente su ricerche che fanno riferimento all’agente utente, per cui tutti gli iPhone presentano una dimensione dello schermo del dispositivo mobile pari a `320 x 480`.

Se desideri raccogliere la versione del dispositivo iPhone, puoi aggirare questa limitazione in due modi.

* **Utilizzare l’SDK di Mobile**: l’SDK di Mobile contiene dimensioni che espongono la versione del dispositivo per l’utilizzo nei rapporti. Questo metodo è più ideale per le app mobili che per i siti web.
* **Usa altre variabili disponibili tramite JavaScript**: alcune variabili, come `screen.height` e `screen.width`, può essere utilizzato per dedurre la versione del dispositivo. Ad esempio, puoi utilizzare il seguente frammento di codice sul sito:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Questo blocco di codice rileva innanzitutto se il dispositivo è un iPhone. In caso affermativo, il codice utilizza JavaScript per richiamare la risoluzione dello schermo in un eVar. Questo metodo consente di rilevare approssimativamente la versione del dispositivo se le risoluzioni dello schermo sono univoche.
