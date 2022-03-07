---
description: Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in Audience Manager willen brengen.
keywords: inbound, batch, batch upload, batch data
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Overzicht van batchdata verzenden naar Audience Manager
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 4%

---

# Batchgegevens verzenden naar [!DNL Audience Manager] Overzicht {#send-batch-data-to-audience-manager-overview}

Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in willen brengen [!DNL Audience Manager].

## Voordelen

U kunt gegevens van andere systemen beschikbaar maken in [!DNL Audience Manager]. Ons systeem kan u helpen waarde te ontgrendelen en gebruikersgegevens te benutten die u eerder hebt verzameld. Dit omvat informatie over aankopen, klantenenquêtes, registratiegegevens, [!DNL CRM] databases, enz. Hoewel elke integratie haar eigen uitdagingen oplevert, delen zij allen deze gemeenschappelijke stappen. Bekijk dit materiaal om de vereiste inspanning voor het online plaatsen van uw offlinegegevens te verminderen.

## Stap 1: Gebruikersnamen synchroniseren

Tijdens synchronisatie, [!DNL Audience Manager] Hiermee wijst u unieke id&#39;s toe aan klanten en hun gebruikers. Deze id&#39;s worden de [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) en [!UICONTROL Unique User ID] ([!UICONTROL UUID]). [!DNL Audience Manager] gebruikt de [!UICONTROL DPID] en [!UICONTROL UUID] om gebruikers te identificeren en hen te kwalificeren voor [!UICONTROL traits], [!UICONTROL segments], publieksgroepen en voor rapportage. Daarnaast is onze gegevensverzamelingscode ([!UICONTROL DIL]) zoekt naar deze id&#39;s om bezoekersgegevens van uw website vast te leggen. Wanneer deze stap is voltooid, [!DNL Audience Manager] en uw offlineopslagplaats moet overeenkomstige id&#39;s bevatten voor elk gebruikersrecord.

Belangrijke overwegingen met betrekking tot deze stap:

* **Plaatsing client-id:** [!DNL Audience Manager] moet weten waar uw client-id op uw website wordt weergegeven (bijvoorbeeld: is deze opgeslagen in een cookie, een variabele Analytics, in paginacode, enz.).
* **Uitsluiten [!DNL PII]:** Gebruikersnamen mogen geen persoonlijk identificeerbare gegevens bevatten ([!DNL PII]).
* **Hoofdlettergebruik en inhoudsgevoeligheid:** Tijdens een realtime gegevenssynchronisatie worden gebruikers-id&#39;s van uw site vastgelegd door [!DNL Audience Manager] moet overeenkomen met id&#39;s die vanuit uw offlineopslagplaats zijn doorgegeven. Als offlinerecords bijvoorbeeld informatie bevatten over [!DNL User123], maar uw site geeft die id weer als [!DNL USER123], [!DNL Audience Manager] beschouwt deze als verschillende bezoekers . Hierdoor kan de online-informatie voor deze bezoeker niet worden gekoppeld aan de corresponderende records in uw offlinedatabase. Id&#39;s moeten exact overeenkomen.

Zie [ID-synchronisatie voor binnenkomende gegevensoverdrachten](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Stap 2: Gegevensbestandsindeling

Bestandsnamen en inhoud volgen strikte richtlijnen. U *moet* namen en ordenen gegevensbestanden volgens deze specificaties in deze handleiding. Zie:

* [Amazon S3-naamvereisten voor binnenkomende databestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inhoud binnenkomend gegevensbestand: Syntaxis, variabelen en voorbeelden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online gegevens zijn beschikbaar voor offlinemarketinginspanningen

Wanneer u offline gegevens online brengt, kunt u deze informatie voor offlinecampagnes nog gebruiken. Om dit te doen, [!DNL Audience Manager] exportkenmerken en segmentinformatie naar een [!DNL FTP] of [!DNL Amazon S3] de locatie van uw keuze. Neem contact op met de manager van de Oplossingen van de Partner voor extra informatie of hulp.

## Omgevingen

[!DNL Audience Manager] biedt de volgende omgevingen voor het uitzetten van bestanden:

| Omgeving | Service | Locatie |
|---------|----------|---------|
| Productie | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta-omgeving | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-client-sandbox-us-East-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Verdere technische lezing

Systeemengineers, ontwikkelaars of technische/implementatieteams moeten [Batchgegevensoverdrachtproces beschreven](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) en de andere artikelen in deze afdeling. Deze artikelen bevatten informatie over overdrachtprotocollen, bestandsinhoud en vereisten voor bestandsnamen.
