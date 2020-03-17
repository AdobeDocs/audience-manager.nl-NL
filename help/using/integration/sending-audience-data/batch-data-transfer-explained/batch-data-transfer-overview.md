---
description: Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in de Manager van het Publiek willen brengen.
keywords: inbound, batch, batch upload, batch data
seo-description: Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in de Manager van het Publiek willen brengen. Gebruik hiertoe de optie voor batchupload in Audience Manager.
seo-title: Batchgegevens verzenden naar Auditiebeheer - Overzicht
solution: Audience Manager
title: Batchgegevens verzenden naar Auditiebeheer - Overzicht
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
translation-type: tm+mt
source-git-commit: 2e3adc8f0b2fe6efd9ca57f1d763ee4476d2edee

---


# Batchgegevens verzenden naar Auditiebeheer - Overzicht{#send-batch-data-to-audience-manager-overview}

Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in de Manager van het Publiek willen brengen.

## Voordelen

<!-- c_offline_to_online.xml -->

U kunt gegevens van andere systemen ter beschikking stellen in de Manager van het Publiek. Ons systeem kan u helpen waarde te ontgrendelen en gebruikersgegevens te benutten die u eerder hebt verzameld. Dit omvat informatie over aankopen, klantenonderzoeken, registratiegegevens, [!DNL CRM] gegevensbanken, enz. Hoewel elke integratie haar eigen uitdagingen oplevert, delen zij allen deze gemeenschappelijke stappen. Bekijk dit materiaal om de vereiste inspanning voor het online plaatsen van uw offlinegegevens te verminderen.

## Stap 1: Gebruikersnamen synchroniseren

Tijdens synchronisatie, wijst de Manager van de Publiek unieke IDs aan cliënten en hun gebruikers toe. Deze id&#39;s worden respectievelijk [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) en [!UICONTROL Unique User ID] ([!UICONTROL UUID]) genoemd. De Manager van het publiek gebruikt [!UICONTROL DPID] en [!UICONTROL UUID] om gebruikers te identificeren en hen voor eigenschappen, segmenten, publieksgroepen, en voor rapportering te kwalificeren. Bovendien zoekt onze gegevensverzamelingscode ([!UICONTROL DIL]) naar deze id&#39;s om bezoekersgegevens van uw website vast te leggen. Wanneer deze stap is voltooid, moeten Audience Manager en uw offline opslagplaats overeenkomstige id&#39;s voor elk gebruikersrecord bevatten.

Belangrijke overwegingen met betrekking tot deze stap:

* **Plaatsing client-id:** Audience Manager moet weten waar uw client-id op uw website wordt weergegeven (bijvoorbeeld: wordt deze opgeslagen in een cookie, een variabele Analytics, in paginacode, enz.).
* **Uitsluiten[!DNL PII]:** Gebruikersnamen mogen geen persoonlijk identificeerbare gegevens ([!DNL PII]) bevatten.
* **Hoofdlettergebruik en inhoudsgevoeligheid:** Tijdens een realtime gegevenssynchronisatie moeten gebruikers-id&#39;s die door Audience Manager van uw site zijn vastgelegd, overeenkomen met id&#39;s die vanuit uw offline opslagplaats zijn doorgegeven. Als offlinerecords bijvoorbeeld informatie bevatten over [!DNL User123]de site die id weergeeft als [!DNL USER123], worden deze door Audience Manager als verschillende bezoekers beschouwd. Hierdoor kan de online-informatie voor deze bezoeker niet worden gekoppeld aan de corresponderende records in uw offlinedatabase. Id&#39;s moeten exact overeenkomen.

Zie [Identiteitssynchronisatie voor Binnenkomende Overdrachten](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md)van Gegevens.

<!-- 

<p> <b>Step 2: Create a Translation File</b> </p> 
<p>A translation file classifies data according to uniform and logical hierarchy. It is a taxonomy that helps you organize information from general categories (e.g., geography) to more precise classifications (e.g., <i>geography > United States > New York</i>). Also, it labels data with to easy to understand names such as "gender=male" or "color=green" instead of with your internal SKUs, abbreviations, or other names. The file lets Audience Manager display this information in a readable, logical manner. You and your data partners must create and share the translation file with Audience Manager before any real-time or server-to-server data transfers can begin. You can update this file on a schedule relevant to your business needs. </p> 
<p>Important considerations about this step: </p> 
<ul id="ul_6A05AECB0BD649B1BF1B34058E9008E2"> 
 <li id="li_39817ED898F14156A77FCAC066FE0968"> <b>Create a comprehensive list:</b> The translation file must include all the possible values that can be passed in on a particular key. For example, if you have category key called "color" and it accepts the values "red," "green," and "blue," the translation file must contain <i>all</i> those elements. </li> 
 <li id="li_19CAD7683BCF45278E2991C1EDBC9903"> <b>Case and content sensitivity:</b> The key-values in the file must match the values actually passed in to Audience Manager from your website. </li> 
</ul> 
<p>See DATA TRANSLATION FILE. </p>

 -->

## Stap 2: Gegevensbestandsindeling

Bestandsnamen en inhoud volgen strikte richtlijnen. U *moet* gegevensbestanden een naam geven en ordenen volgens deze specificaties in deze handleiding. Zie:

* [Amazon S3-naamvereisten voor binnenkomende gegevensbestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhoud binnenkomend gegevensbestand: Syntaxis, variabelen en voorbeelden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online gegevens zijn beschikbaar voor offlinemarketinginspanningen

Wanneer u offline gegevens online brengt, kunt u deze informatie voor offlinecampagnes nog gebruiken. Om dit te doen, exporteert de Manager van de Publiek eigenschap en segmentinformatie naar een [!DNL FTP] of [!DNL Amazon S3] plaats van uw keus. Neem contact op met de manager van de Oplossingen van de Partner voor extra informatie of hulp.

## Omgevingen

Audience Manager biedt de volgende omgevingen voor het wegvallen van bestanden:

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

Systeemengineers, ontwikkelaars of technische/implementatieteams moeten het beschreven [proces voor de overdracht van](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) batchgegevens en de andere artikelen in deze sectie evalueren. Deze artikelen bevatten informatie over overdrachtprotocollen, bestandsinhoud en vereisten voor bestandsnamen.