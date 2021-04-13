---
description: Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in Audience Manager willen brengen.
keywords: inbound, batch, batch upload, batch data
seo-description: Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in Audience Manager willen brengen. Gebruik hiervoor de optie voor batchupload in Audience Manager.
seo-title: Overzicht van batchdata verzenden naar Audience Manager
solution: Audience Manager
title: Overzicht van batchdata verzenden naar Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Binnenkomende gegevensoverdrachten
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 5%

---

# Batchgegevens verzenden naar [!DNL Audience Manager] Overzicht {#send-batch-data-to-audience-manager-overview}

Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in [!DNL Audience Manager] willen brengen.

## Voordelen

U kunt gegevens van andere systemen in [!DNL Audience Manager] ter beschikking stellen. Ons systeem kan u helpen waarde te ontgrendelen en gebruikersgegevens te benutten die u eerder hebt verzameld. Dit omvat informatie over aankopen, klantenonderzoeken, registratiegegevens, [!DNL CRM] databases, enz. Hoewel elke integratie haar eigen uitdagingen oplevert, delen zij allen deze gemeenschappelijke stappen. Bekijk dit materiaal om de vereiste inspanning voor het online plaatsen van uw offlinegegevens te verminderen.

## Stap 1: Gebruikersnamen synchroniseren

Tijdens synchronisatie wijst [!DNL Audience Manager] unieke id&#39;s toe aan clients en hun gebruikers. Deze id&#39;s worden respectievelijk [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) en [!UICONTROL Unique User ID] ([!UICONTROL UUID]) genoemd. [!DNL Audience Manager] gebruikt  [!UICONTROL DPID] en  [!UICONTROL UUID] om gebruikers te identificeren en hen voor,  [!UICONTROL traits]  [!UICONTROL segments]publieksgroepen, en voor rapportering te kwalificeren. Bovendien zoekt onze gegevensverzamelingscode ([!UICONTROL DIL]) naar deze id&#39;s om bezoekersgegevens van uw website vast te leggen. Wanneer deze stap is voltooid, moeten [!DNL Audience Manager] en uw offline opslagplaats overeenkomstige id&#39;s bevatten voor elk gebruikersrecord.

Belangrijke overwegingen met betrekking tot deze stap:

* **Clientid plaatsen:** [!DNL Audience Manager] moet weten waar uw client-id op uw website wordt weergegeven (wordt deze bijvoorbeeld opgeslagen in een cookie, een analysevariabele, in paginacode, enz.).
* **Uitsluiten  [!DNL PII]:** gebruikersnamen mogen geen identificeerbare gegevens ([!DNL PII]) bevatten.
* **Hoofdlettergevoelig en inhoudsgevoelig:** Tijdens een realtime gegevenssync  [!DNL Audience Manager] moeten gebruikers-id&#39;s die van uw site worden vastgelegd, overeenkomen met id&#39;s die vanuit uw offline opslagruimte zijn doorgegeven. Als offlinerecords bijvoorbeeld informatie bevatten over [!DNL User123], maar uw site geeft die id weer als [!DNL USER123], ziet [!DNL Audience Manager] deze als verschillende bezoekers. Hierdoor kan de online-informatie voor deze bezoeker niet worden gekoppeld aan de corresponderende records in uw offlinedatabase. Id&#39;s moeten exact overeenkomen.

Zie [ID Synchronization for Inbound Data Transfers](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Stap 2: Gegevensbestandsindeling

Bestandsnamen en inhoud volgen strikte richtlijnen. U *moet* naam geven en gegevensbestanden ordenen volgens deze specificaties in deze handleiding. Zie:

* [Amazon S3-naamvereisten voor binnenkomende databestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhoud binnenkomend gegevensbestand: Syntaxis, variabelen en voorbeelden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online gegevens zijn beschikbaar voor offlinemarketinginspanningen

Wanneer u offline gegevens online brengt, kunt u deze informatie voor offlinecampagnes nog gebruiken. Hiervoor exporteert [!DNL Audience Manager] de kenmerken en segmentinformatie naar een [!DNL FTP]- of [!DNL Amazon S3]-locatie van uw keuze. Neem contact op met de manager van de Oplossingen van de Partner voor extra informatie of hulp.

## Omgevingen

[!DNL Audience Manager] biedt de volgende omgevingen voor het uitzetten van bestanden:

<table id="table_A61AA64578944B23B5A7355F2A76E882"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Omgeving </th> 
   <th colname="col02" class="entry"> Service </th> 
   <th colname="col2" class="entry"> Locatie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Productie</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p> <code> ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <b>Bètaomgeving</b> </td> 
   <td colname="col02"> FTP </td> 
   <td colname="col2"> <p><code> sandbox-ftp-in.demdex.com</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col02"> S3 </td> 
   <td colname="col2"> <p> <code> demdex-s2s-clients-sandbox-us-east-1</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Verdere technische lezing

Systeemengineers, ontwikkelaars of technische/implementatieteams dienen [Batch Data Transfer Process Described](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) en de andere artikelen in deze sectie te evalueren. Deze artikelen bevatten informatie over overdrachtprotocollen, bestandsinhoud en vereisten voor bestandsnamen.
