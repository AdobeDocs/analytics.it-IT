---
title: Dimensioni per dispositivi mobili
description: Dimension basati sull’indirizzo IP del dispositivo.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 0%

---

# Dimensioni per dispositivi mobili

*Questa pagina fa riferimento alle proprietà dei dispositivi mobili che accedono al sito web. Se desideri tenere traccia dei dispositivi su un’app mobile, consulta [Implementazione di Analytics per dispositivi mobili](/help/implement/mobile-device-sdk.md) nella guida utente Implementa .*

Le dimensioni per dispositivi mobili forniscono informazioni approfondite sulle proprietà dei dispositivi mobili che visitano il tuo sito. Puoi utilizzare queste dimensioni per comprendere meglio quali funzioni supporta un dispositivo mobile.

## Popolare queste dimensioni con i dati

Queste dimensioni fanno riferimento a regole di ricerca interne all’Adobe. [!UICONTROL Mobile Carrier] Le ricerche sono determinate dall’indirizzo IP, utilizzando i dati ottenuti da NetAcuity (un prodotto Digital Elements).
Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), tutte le dimensioni per dispositivi mobili non sono pronte all’uso.

## Descrizioni delle dimensioni mobili

>[!NOTE]
>
>Articoli Dimension etichettati `"None"` sono dispositivi non mobili. Se desideri un rapporto che includa solo dispositivi mobili, trascina la dimensione &quot;Dispositivo mobile&quot; nell’area di segmento dell’area di lavoro.

* **Supporto audio per dispositivi mobili**: Determina i formati di file che il dispositivo può riprodurre. I valori di esempio includono `"MP3"`, `"AAC"`e `"MIDI Monophonic"`. I valori di questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.
* **Operatore mobile**: I valori per questa dimensione vengono compilati cercando dati di terze parti (elementi digitali) in base agli indirizzi IP acquisiti da Analytics. I valori di esempio includono `"Reliance Jio"`, `"Airtel"`, `"Vodafone"`e `"Verizon"`.
* **Profondità colore mobile**: Profondità colore del dispositivo mobile, in bit.
* **Supporto cookie per dispositivi mobili**: Determina se il dispositivo mobile supporta i cookie. Questo rapporto non indica se il browser accetta i cookie. Gli elementi del Dimension includono `"Supported"`, `"Not supported"`e `"Unknown"`.
* **Dispositivo mobile**: Il dispositivo mobile utilizzato dal visitatore.
* **Numero dispositivo mobile**: Determina se il dispositivo mobile trasmette il proprio numero. Gli elementi del Dimension includono `"Supported"`, `"Not supported"`e `"Unknown"`.
* **Tipo di dispositivo mobile**: Il tipo di dispositivo mobile. I valori di esempio includono `"Mobile phone"`, `"Tablet"`, `"Media player"`e `"Gaming console"`.
* **DRM mobile**: Il tipo di DRM supportato dal dispositivo mobile. I valori di esempio includono `"DRM OMA forward"`, `"DRM OMA combined delivery"`e `"DRM OMA separate delivery"`.
* **Supporto per immagini per dispositivi mobili**: I tipi di immagini supportati da un dispositivo mobile. I valori di esempio includono `"PNG"`, `"JPEG"`e `"GIF 87"`. I valori di questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.
* **Mobile Information Services**: Tipi di servizi di news supportati dal dispositivo. I dispositivi recenti in genere non segnalano queste informazioni.
* **Java VM mobile**: Le versioni di Java supportate dal dispositivo.
* **Decorazione della posta mobile**: Determina se il dispositivo supporta la funzione Decomail, una volta comune sui dispositivi giapponesi.
* **produttore di dispositivi mobili**: Raggruppa i dispositivi mobili in base al produttore. I valori di esempio includono `"Apple"`, `"Samsung"`, `"Huawei"`e `"Motorola"`.
* **Lunghezza massima segnalibro mobile**: Il numero massimo di byte supportati dal dispositivo mobile negli URL con segnalibro. I dispositivi recenti in genere non hanno un limite.
* **Lunghezza massima URL browser mobile**: Il numero massimo di byte supportati dal dispositivo mobile negli URL. I dispositivi recenti in genere non hanno un limite.
* **Lunghezza massima e-mail mobile**: Il numero massimo di byte supportati dal dispositivo mobile in un messaggio e-mail. I dispositivi recenti in genere non hanno un limite.
* **Protocolli di reti mobili**: I tipi di protocollo supportati dal dispositivo quando si accede a Internet. I valori di esempio includono `"EDGE"`, `"GPRS"`, `"UMTS"`e `"LTE"`.
* **Sistema operativo mobile (obsoleto)**: Utilizza la [Sistema operativo](operating-systems.md) invece.
* **Invio push per dispositivi mobili per comunicare**: Determina se il dispositivo supporta PTT (Push to talk), che consente al dispositivo mobile di comportarsi in modo simile a una radio a due vie. I dispositivi recenti in genere non segnalano questa funzione.
* **Altezza schermo mobile**: Altezza dello schermo, in pixel. Tieni presente che iPhone segnalano sempre `"480"` a causa dell’impossibilità di determinare la versione del dispositivo iPhone. Vedi la sezione seguente sul determinazione della versione del dispositivo iPhone.
* **Dimensioni schermo mobile**: Dimensioni complete del dispositivo mobile in pixel. Le dimensioni dello schermo segnalate non indicano l’orientamento del dispositivo. Indipendentemente dall’orientamento dello schermo, ogni dispositivo ha una risoluzione fissa dello schermo nel rapporto. Questa dimensione si basa sulla ricerca che determina quale orientamento è più probabile. È possibile visualizzare dimensioni quali `"768x1024"` e `"1024x768"` nello stesso rapporto con ogni dimensione che rappresenta uno o più dispositivi diversi.
* **Larghezza dello schermo mobile**: Larghezza dello schermo, in pixel.
* **Supporto video per dispositivi mobili**: Formati e codec di file video supportati dal dispositivo mobile. Esistono diversi elementi dimensionali per diversi codec di file MP4 e 3GPP. I valori di questa dimensione non si escludono a vicenda; un singolo hit può attribuire a più elementi dimensionali.

## Separazione di iPhone per modello o versione

I dispositivi mobili segnalano la versione del firmware nella stringa dell&#39;agente utente, non la versione del dispositivo. Ad esempio, un iPhone di generazione corrente contiene un agente utente identico all&#39;iPhone di ultima generazione se si trova nella stessa versione del firmware. Poiché non è possibile determinare una versione di un dispositivo iPhone utilizzando JavaScript, tutti gli iPhone appartengono allo stesso bucket. Le dimensioni per dispositivi mobili sono strettamente basate su ricerche che fanno riferimento all’agente utente, pertanto vedrai che tutti gli iPhone segnalano una dimensione dello schermo mobile di `320 x 480`.

Se desideri raccogliere la versione del dispositivo iPhone, puoi aggirare questa limitazione in due modi.

* **Utilizzare l’SDK per iOS**: L’SDK per dispositivi mobili contiene dimensioni che espongono la versione del dispositivo da utilizzare nei rapporti. Questo metodo è più ideale per le app mobili che per i siti web.
* **Usa altre variabili disponibili tramite JavaScript**: Alcune variabili, ad esempio `screen.height` e `screen.width`, può essere utilizzato per dedurre la versione del dispositivo. Ad esempio, puoi utilizzare il seguente frammento di codice sul tuo sito:

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   Questo blocco di codice rileva prima se il dispositivo è un iPhone. Se lo è, il codice utilizza JavaScript per estrarre la risoluzione dello schermo in un eVar. Questo metodo consente di rilevare approssimativamente la versione del dispositivo se le risoluzioni dello schermo sono univoche.
