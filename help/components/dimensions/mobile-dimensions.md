---
title: Dimensioni per dispositivi mobili
description: Dimension basati sull'indirizzo IP del dispositivo.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '901'
ht-degree: 0%

---

# Dimensioni per dispositivi mobili

*Questa pagina fa riferimento alle proprietà dei dispositivi mobili che accedono al sito web. Se desideri tenere traccia dei dispositivi su un’app mobile, consulta [Implementazione di Analytics per dispositivi mobili](/help/implement/mobile-device-sdk.md) nella guida utente Implementa.*

Dispositivi mobili [dimensioni](overview.md) fornisci informazioni sulle proprietà dei dispositivi mobili che visitano il tuo sito. Puoi utilizzare queste dimensioni per comprendere le funzioni supportate da un dispositivo mobile.

## Popola queste dimensioni con i dati

Queste dimensioni fanno riferimento a regole di ricerca interne a Adobe. [!UICONTROL Mobile Carrier] Le ricerche sono determinate dall’indirizzo IP, utilizzando i dati ottenuti da NetAcuity (un prodotto Digital Elements).
Se utilizzi una libreria di AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), tutte le dimensioni dei dispositivi mobili funzionano in modo predefinito.

## Descrizioni delle dimensioni mobile

>[!NOTE]
>
>Elementi Dimension etichettati `"None"` sono dispositivi non mobili. Se desideri un rapporto che includa solo i dispositivi mobili, trascina la dimensione &quot;Dispositivo mobile&quot; nell’area del segmento dell’area di lavoro di Workspace.

* **Supporto audio per dispositivi mobili**: determina i formati di file che il dispositivo può riprodurre. I valori di esempio includono `"MP3"`, `"AAC"`, e `"MIDI Monophonic"`. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.
* **Operatore mobile**: i valori per questa dimensione vengono compilati cercando i dati di terze parti (elementi digitali) in base agli indirizzi IP acquisiti da Analytics. I valori di esempio includono `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`, e `"Verizon"`.
* **Profondità colore mobile**: profondità colore del dispositivo mobile, in bit.
* **Supporto cookie per dispositivi mobili**: determina se il dispositivo mobile supporta i cookie. Questo rapporto non indica se il browser accetta i cookie. Gli elementi del Dimension includono `"Supported"`, `"Not supported"`, e `"Unknown"`.
* **Dispositivo mobile**: dispositivo mobile utilizzato dal visitatore. **Nota**: Digital Elements pubblica periodicamente aggiornamenti per riconoscere i dispositivi nuovi o aggiornati.
* **Numero dispositivo mobile**: determina se il dispositivo mobile trasmette il suo numero. Gli elementi del Dimension includono `"Supported"`, `"Not supported"`, e `"Unknown"`.
* **Tipo di dispositivo mobile**: tipo di dispositivo mobile. I valori di esempio includono `"Mobile phone"`, `"Tablet"`, `"Media player"`, e `"Gaming console"`.
* **DRM mobile**: tipo di DRM supportato dal dispositivo mobile. I valori di esempio includono `"DRM OMA forward"`, `"DRM OMA combined delivery"`, e `"DRM OMA separate delivery"`.
* **Supporto immagini per dispositivi mobili**: i tipi di immagini supportati dai dispositivi mobili. I valori di esempio includono `"PNG"`, `"JPEG"`, e `"GIF 87"`. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.
* **Servizi di informazione mobile**: i tipi di servizi di notizie supportati dal dispositivo. I dispositivi recenti in genere non segnalano queste informazioni.
* **VM Java mobile**: versioni di Java supportate dal dispositivo.
* **Decorazione della posta mobile**: determina se il dispositivo supporta Decomail, una funzione una volta popolare sui dispositivi giapponesi.
* **Produttore di dispositivi mobili**: raggruppa i dispositivi mobili per produttore. I valori di esempio includono `"Apple"`, `"Samsung"`, `"Huawei"`, e `"Motorola"`.
* **Lunghezza massima segnalibro mobile**: numero massimo di byte supportati dal dispositivo mobile negli URL con segnalibro. I dispositivi recenti in genere non hanno un limite.
* **Lunghezza massima URL browser mobile**: numero massimo di byte supportati dal dispositivo mobile negli URL. I dispositivi recenti in genere non hanno un limite.
* **Lunghezza massima e-mail mobile**: numero massimo di byte supportati dal dispositivo mobile in un messaggio e-mail. I dispositivi recenti in genere non hanno un limite.
* **Protocolli di rete per dispositivi mobili**: i tipi di protocollo supportati dal dispositivo per l’accesso a Internet. I valori di esempio includono `"EDGE"`, `"GPRS"`, `"UMTS"`, e `"LTE"`.
* **Sistema operativo mobile (obsoleto)**: utilizza [Sistema operativo](operating-systems.md) al suo posto.
* **Push-to-talk per dispositivi mobili**: determina se il dispositivo supporta il PTT (Push to talk), che consente al dispositivo mobile di comportarsi in modo simile a una radio a due vie. I dispositivi recenti in genere non segnalano questa funzione.
* **Altezza schermo mobile**: altezza dello schermo, in pixel. Nota che gli iPhone segnalano sempre `"480"` a causa dell’impossibilità di determinare la versione del dispositivo iPhone. Consulta la sezione seguente sulla determinazione della versione del dispositivo iPhone.
* **Dimensioni schermo del dispositivo mobile**: dimensioni complete del dispositivo mobile in pixel. Le dimensioni dello schermo riportate non indicano l’orientamento del dispositivo. Indipendentemente dall’orientamento dello schermo, nel rapporto ogni dispositivo ha una risoluzione fissa dello schermo. Questa dimensione si basa su ricerche che determinano quale orientamento è più probabile. Puoi vedere dimensioni come `"768x1024"` e `"1024x768"` nello stesso rapporto, in cui ogni dimensione rappresenta uno o più dispositivi diversi.
* **Larghezza schermo mobile**: larghezza dello schermo, in pixel.
* **Supporto video per dispositivi mobili**: formati e codec di file video supportati dal dispositivo mobile. Esistono diversi elementi dimensionali per diversi codec di file MP4 e 3GPP. I valori in questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.

## Separazione di iPhone per modello o versione

I dispositivi mobili segnalano la versione del firmware nella stringa dell’agente utente, non la versione del dispositivo. Ad esempio, un iPhone della generazione corrente contiene un agente utente identico all’iPhone dell’ultima generazione se si trovano nella stessa versione del firmware. Poiché non è possibile determinare la versione di un dispositivo iPhone utilizzando JavaScript, tutti gli iPhone appartengono allo stesso bucket. Le dimensioni di Mobile si basano strettamente sulle ricerche che fanno riferimento all’agente utente, pertanto scoprirai che tutti gli iPhone segnalano una dimensione dello schermo mobile di `320 x 480`.

Se desideri raccogliere la versione del dispositivo iPhone, puoi aggirare questa limitazione in due modi.

* **Utilizzare l’SDK di iOS**: l’SDK per dispositivi mobili contiene dimensioni che espongono la versione del dispositivo per l’utilizzo nei rapporti. Questo metodo è più ideale per le app mobili che per i siti web.
* **Usa altre variabili disponibili tramite JavaScript**: alcune variabili, come `screen.height` e `screen.width`, può essere utilizzato per dedurre la versione del dispositivo. Ad esempio, puoi utilizzare il seguente frammento di codice sul sito:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Questo blocco di codice rileva innanzitutto se il dispositivo è un iPhone. In caso affermativo, il codice utilizza JavaScript per richiamare la risoluzione dello schermo in un eVar. Questo metodo consente di rilevare approssimativamente la versione del dispositivo se le risoluzioni dello schermo sono univoche.
