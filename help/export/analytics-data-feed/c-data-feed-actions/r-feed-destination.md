---
description: La sezione Feed di feed definisce la modalità di distribuzione del feed.
keywords: Feed dati; feed; destination; sftp; s 3; ftp; settings
seo-description: La sezione Feed di feed definisce la modalità di distribuzione del feed.
seo-title: Destinazione feed
solution: Analytics
title: Destinazione feed
uuid: 4 a 59 e 8 de-e 7 a 6-4 f 7 a-bf 42-db 7 d 59 e 61 b 4 c
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Destinazione feed

La sezione Feed di feed definisce la modalità di distribuzione del feed.

Esistono quattro canali di distribuzione:

* FTP
* SFTP
* Amazon S 3
* Azure Blob

## FTP {#section_D2B521C49BDE4F91A1999FE222CF306F}

I dati dei feed di dati possono essere inviati a una posizione FTP in hosting su Adobe o cliente.

Se selezionate dei dati caricati sul server FTP, dovete fornire ad Adobe il nome utente, la password e il percorso di caricamento appropriati. È necessario implementare un processo personalizzato per gestire lo spazio su disco sul server, in quanto Adobe non elimina alcun dato dal server.

![](assets/dest-ftp.jpg)

## SFTP {#section_8D9215E441474D2BBC56228C2BC926E5}

I dati dei feed di dati possono essere inviati a una posizione sftp in hosting su Adobe o cliente.

Se selezionate dei dati caricati sul server FTP, dovete fornire ad Adobe il nome utente e il percorso di caricamento appropriati.

<!-- 

Adobe Customer Care will provide you with a Public key. Verify in recording.

 -->

È necessario implementare un processo personalizzato per gestire lo spazio su disco sul server, in quanto Adobe non elimina alcun dato dal server.

![](assets/dest-sftp.jpg)

## Amazon S3 {#section_4191CD7B8D3F419EB850B286B542C14A}

Potete caricare i file in un bucket Amazon S 3. Amazon effettua automaticamente la cifratura dei dati rimanenti (sui server Amazon). Quando scaricate i dati, viene decifrato automaticamente.

Se selezionate dei dati caricati tramite Amazon S 3, dovete fornire un Nome Bucket, un ID Key Key, una Chiave segreta e un nome di cartella.

![](assets/dest-s3.jpg)

I feed dati comunicano alle seguenti 11 aree AWS standard (utilizzando l'algoritmo di firma appropriato, dove necessario):

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

## Azure Blob {#section_1E9F1D0E7EAB4189A5D748FCA57D63D1}

Potete caricare i file su un blob Azure.

![](assets/azure.png)

## Fields {#section_AD54B41BC7C945DC85F5FB8FCD4A4792}

Nella tabella seguente sono visualizzate tutte le opzioni per tutti i canali di distribuzione. Le opzioni disponibili dipendono dal canale di distribuzione selezionato.

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
   <td colname="col2"> <p>Immettete il tasto di accesso Amazon S 3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Secchio </p> </td> 
   <td colname="col2"> <p>Inserire la posizione di Amazon S 3. </p> <p>Questo valore deve corrispondere al formato corretto di bucket S 3. (See <a href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html" format="html" scope="external"> https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-s3-bucket-naming-requirements.html</a>.) </p> <p> <p>Note: See <a href="../../../export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D" format="dita" scope="local"> BucketOwnerFullControl setting for Amazon S3 data feeds</a>, below, for details about the Amazon S3 settings. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Contenitore </p> </td> 
   <td colname="col2"> <p>Immettete il nome del contenitore Azure Blob. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Host </p> </td> 
   <td colname="col2"> <p>Specificate la posizione host FTP o SFTP. </p> <p>This value must comply to the proper ftp/sftp format, <code> ftp.domain.com/subdomain</code> or <code> sftp.domain.com/subdomain</code>. </p> <p> Le porte standard 21 e 22 per FTP e sftp sono obbligatorie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password </p> <p>Conferma password </p> </td> 
   <td colname="col2"> <p>Immettete la password FTP. Reenter per confermare </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percorso </p> </td> 
   <td colname="col2"> <p>Selezionare il percorso dell'host o del bucket. Questo percorso deve esistere prima della creazione del feed. </p> <p> <p>Note: See <a href="../../../export/analytics-data-feed/feed-troubleshooting.md#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D" format="dita" scope="local"> BucketOwnerFullControl setting for Amazon S3 data feeds</a>, below, for details about the Amazon S3 settings. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account </p> </td> 
   <td colname="col2"> <p> Immettete l'account archiviazione Azure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiave pubblica </p> </td> 
   <td colname="col2"> <p>Fornite la chiave pubblica SFTP. </p> <p>È necessario scaricare la chiave pubblica per configurare l'archivio SFTP. </p> <p> <p>Nota: Non è necessario scaricare la chiave pubblica per creare il feed. </p> </p> <p>Potete utilizzare una chiave pubblica che è già stata scaricata durante la creazione di un feed precedente. </p> <p>For more information, see <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_sftp_dw.html" format="html" scope="external"> https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_sftp_dw.html</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiave </p> <p>Conferma chiave </p> </td> 
   <td colname="col2"> <p> Inserite il codice di accesso all'archiviazione. Digitate nuovamente per confermare. </p> <p> <p>Note: See <a href="https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys" format="https" scope="external"> https://docs.microsoft.com/en-us/azure/storage/common/storage-create-storage-account#view-and-copy-storage-access-keys</a> for accessing access keys. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Chiave segreta </p> <p>Conferma chiave segreta </p> </td> 
   <td colname="col2"> <p>Immettete la chiave segreta Amazon S 3. Reinserite per confermare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Type (Tipo) </p> </td> 
   <td colname="col2"> <p>Selezionate il tipo di destinazione. </p> <p> 
     <ul id="ul_B893EEDA73A34DE0AEB8570BE9027F21"> 
      <li id="li_325546FCEB404C50AA6829573CCA340B">FTP (predefinito) </li> 
      <li id="li_6A2C03115903484797485D073A610607">AmazonS3 </li> 
      <li id="li_C24540F6FCD24702B7693A515CEBE977">SFTP </li> 
      <li id="li_8E03CA78E7FE427C9F6F8B112BC76266">Azure Blob </li> 
     </ul> </p> <p>Dopo aver selezionato il tipo di destinazione, l'elenco dei campi cambia in base alle opzioni disponibili per la destinazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome utente </p> </td> 
   <td colname="col2"> <p>Immettete il nome utente FTP. </p> </td> 
  </tr> 
 </tbody> 
</table>

