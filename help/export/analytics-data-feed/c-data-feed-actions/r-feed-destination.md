---
description: La sezione Destinazione feed definisce il modo in cui il feed viene distribuito.
keywords: Feed dati;feed;destinazione;sftp;s3;ftp;settings
seo-description: La sezione Destinazione feed definisce il modo in cui il feed viene distribuito.
seo-title: Destinazione feed
solution: Analytics
title: Destinazione feed
uuid: 4a59e8de-e7a6-4f7a-bf42-db7d59e61b4c
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Destinazione feed

La sezione Destinazione feed definisce il modo in cui il feed viene distribuito.

Esistono quattro canali di distribuzione:

* FTP
* SFTP
* Amazon S3
* BLOB di Azure

## FTP {#section_D2B521C49BDE4F91A1999FE222CF306F}

I dati del feed di dati possono essere inviati a una posizione FTP ospitata da Adobe o dal cliente.

Se scegliete di caricare i dati sul server FTP, dovete fornire ad Adobe il nome utente, la password e il percorso di caricamento appropriati. È necessario implementare un processo personalizzato per gestire lo spazio su disco sul server, in quanto Adobe non elimina alcun dato dal server.

![](assets/dest-ftp.jpg)

## SFTP {#section_8D9215E441474D2BBC56228C2BC926E5}

I dati del feed di dati possono essere inviati a una posizione sFTP ospitata da Adobe o dal cliente.

Se scegliete di caricare i dati sul server FTP, dovete fornire ad Adobe il nome utente e il percorso di caricamento appropriati.

<!-- 

Adobe Customer Care will provide you with a Public key. Verify in recording.

 -->

È necessario implementare un processo personalizzato per gestire lo spazio su disco sul server, in quanto Adobe non elimina alcun dato dal server.

![](assets/dest-sftp.jpg)

## Amazon S3 {#section_4191CD7B8D3F419EB850B286B542C14A}

Potete caricare i file in un bucket Amazon S3. Amazon codifica automaticamente i dati a riposo (sui server Amazon). Quando scaricate i dati, questi vengono decrittografati automaticamente.

Se scegliete di caricare i dati tramite Amazon S3, dovete fornire un nome per il socket, un ID chiave di accesso, una chiave segreta e un nome per la cartella.

![](assets/dest-s3.jpg)

Feed dati comunica con le seguenti 11 aree AWS standard (utilizzando, se necessario, l'algoritmo di firma appropriato):

* us-east-1
* us-west-1
* us-west-2
* ap-south-1
* ap-northeast-2
* ap-southeast-1
* ap-southeast-2
* ap-northeast-1
* eu-central-1
* eu-west-1
* sa-east-1

Al momento non è supportata l’area AWS di Beijing, Cina (cn-north-1).

## BLOB di Azure {#section_1E9F1D0E7EAB4189A5D748FCA57D63D1}

È possibile caricare i file in un BLOB di Azure.

![](assets/azure.png)

## Campi {#section_AD54B41BC7C945DC85F5FB8FCD4A4792}

La tabella seguente mostra tutte le opzioni per tutti i canali di distribuzione. Le opzioni disponibili dipendono dal canale di distribuzione selezionato.

<table id="table_F743C620C82349D9943A13B99EA312BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chiave di accesso </p> </td> 
   <td colname="col2"> <p>Immettete il codice di accesso Amazon S3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stucco </p> </td> 
   <td colname="col2"> <p>Immettete la posizione del bucket Amazon S3. </p> <p>Questo valore deve corrispondere al formato fisso S3 corretto. Consultate <a href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html"  > https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html</a>. </p> <p> <p>Nota: Per informazioni dettagliate sulle impostazioni di Amazon S3, consultate <a href="/help/export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D"  > Impostazione BucketOwnerFullControl per i feed</a>di dati Amazon S3. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contenitore </p> </td> 
   <td colname="col2"> <p>Immettere il nome del contenitore BLOB di Azure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Host </p> </td> 
   <td colname="col2"> <p>Specificate il percorso host FTP o SFTP. </p> <p>Questo valore deve essere conforme al formato ftp/sftp corretto <code> ftp.domain.com/subdomain</code> o <code> sftp.domain.com/subdomain</code>. </p> <p> Sono richieste le porte standard 21 e 22 per FTP e sFTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password </p> <p>Conferma password </p> </td> 
   <td colname="col2"> <p>Immettete la password FTP. Torna a conferma </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percorso </p> </td> 
   <td colname="col2"> <p>Selezionare il percorso dell'host o del bucket. Questo percorso deve esistere prima della creazione del feed. </p> <p> <p>Nota: Per informazioni dettagliate sulle impostazioni di Amazon S3, consultate <a href="/help/export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D"  > Impostazione BucketOwnerFullControl per i feed</a>di dati Amazon S3. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account </p> </td> 
   <td colname="col2"> <p> Immettere l'account di archiviazione Azure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiave pubblica </p> </td> 
   <td colname="col2"> <p>Fornite la chiave pubblica SFTP. </p> <p>È necessario scaricare la chiave pubblica per configurare l'archivio SFTP. </p> <p> <p>Nota:  Il download della chiave pubblica non è necessario per creare il feed. </p> </p> <p>Potete utilizzare una chiave pubblica già scaricata al momento della creazione di un feed precedente. </p> <p>Per ulteriori informazioni, consultate <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_sftp_dw.html"  > https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_sftp_dw.html</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiave </p> <p>Conferma chiave </p> </td> 
   <td colname="col2"> <p> Immettere la chiave di accesso all'archivio. Reinserite per confermare. </p> <p> <p>Nota: Consultate <a href="https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys"  > https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys</a> per accedere alle chiavi di accesso. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiave segreta </p> <p>Conferma chiave segreta </p> </td> 
   <td colname="col2"> <p>Immettete la chiave segreta Amazon S3. Reimmettere per confermare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type (Tipo) </p> </td> 
   <td colname="col2"> <p>Selezionare il tipo di destinazione. </p> <p> 
     <ul id="ul_B893EEDA73A34DE0AEB8570BE9027F21"> 
      <li id="li_325546FCEB404C50AA6829573CCA340B">FTP (predefinito) </li> 
      <li id="li_6A2C03115903484797485D073A610607">AmazonS3 </li> 
      <li id="li_C24540F6FCD24702B7693A515CEBE977">SFTP </li> 
      <li id="li_8E03CA78E7FE427C9F6F8B112BC76266">BLOB di Azure </li> 
     </ul> </p> <p>Dopo aver selezionato il tipo di destinazione, l'elenco dei campi cambia per riflettere le opzioni disponibili per la destinazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome utente </p> </td> 
   <td colname="col2"> <p>Immettete il nome utente FTP. </p> </td> 
  </tr> 
 </tbody> 
</table>

