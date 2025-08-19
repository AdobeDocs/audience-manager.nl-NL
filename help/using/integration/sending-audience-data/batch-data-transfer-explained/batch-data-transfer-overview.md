---
description: Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in Audience Manager willen brengen.
keywords: inbound, batch, batch upload, batch data
seo-description: An overview for technical and non-technical customers who want to bring data from other systems (offline) into Audience Manager. To do so, use the batch upload option in Audience Manager.
seo-title: Send Batch Data to Audience Manager Overview
solution: Audience Manager
title: Batchgegevens naar Audience Manager verzenden - Overzicht
uuid: 472583b1-5057-4add-8e3c-5e50762c88e0
feature: Inbound Data Transfers
exl-id: ba95537e-30c9-4546-9456-55f46dbe29ff
source-git-commit: f02e6bcfb7ff3560d9624c3dce7ff065a3a75748
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 2%

---

# Batchgegevens verzenden naar [!DNL Audience Manager] -overzicht {#send-batch-data-to-audience-manager-overview}

Een overzicht voor technische en niet-technische klanten die gegevens van andere systemen (off-line) in [!DNL Audience Manager] willen brengen.

## Voordelen

U kunt gegevens van andere systemen beschikbaar maken in [!DNL Audience Manager]. Ons systeem kan u helpen waarde te ontgrendelen en gebruikersgegevens te benutten die u eerder hebt verzameld. Dit omvat informatie over aankopen, klantenonderzoeken, registratiegegevens, [!DNL CRM] databases, enz. Hoewel elke integratie haar eigen uitdagingen oplevert, delen zij allen deze gemeenschappelijke stappen. Bekijk dit materiaal om de vereiste inspanning voor het online plaatsen van uw offlinegegevens te verminderen.

## Stap 1: Gebruikersnamen synchroniseren

Tijdens de synchronisatie wijst [!DNL Audience Manager] unieke id&#39;s toe aan clients en hun gebruikers. Deze id&#39;s worden respectievelijk [!UICONTROL Data Provider ID] ([!UICONTROL DPID]) en [!UICONTROL Unique User ID] ([!UICONTROL UUID]) genoemd. [!DNL Audience Manager] gebruikt de [!UICONTROL DPID] en [!UICONTROL UUID] om gebruikers te identificeren en hen voor [!UICONTROL traits], [!UICONTROL segments], publieksgroepen, en voor rapportering te kwalificeren. Bovendien zoekt onze gegevensverzamelingscode ([!UICONTROL DIL]) naar deze id&#39;s om bezoekersgegevens van uw website vast te leggen. Wanneer deze stap is voltooid, moeten [!DNL Audience Manager] en uw offline opslagplaats overeenkomstige id&#39;s voor elk gebruikersrecord bevatten.

Belangrijke overwegingen over deze stap:

* **plaatsing van identiteitskaart van de Cliënt:** [!DNL Audience Manager] moet weten waar uw cliëntidentiteitskaart op uw website verschijnt (b.v., wordt het opgeslagen in een koekje, een variabele van de Analyse, in paginacode, enz.).
* **sluit [!DNL PII] uit:** Gebruiker IDs moet geen persoonlijk identificeerbare informatie ([!DNL PII]) bevatten.
* **Geval en inhoudsgevoeligheid:** tijdens een gegevenssynchronisatie in real time, gebruiker IDs die van uw plaats door [!DNL Audience Manager] wordt gevangen moet beantwoorden aan IDs die van uw off-line bewaarplaats wordt overgegaan. Als offlinerecords bijvoorbeeld informatie bevatten over [!DNL User123] , maar uw site geeft die id weer als [!DNL USER123] , dan ziet [!DNL Audience Manager] deze als verschillende bezoekers. Hierdoor kan de online-informatie voor deze bezoeker niet worden gekoppeld aan de corresponderende records in uw offlinedatabase. Id&#39;s moeten exact overeenkomen.

Zie [ Synchronisatie van identiteitskaart voor Binnenkomende Overdrachten van Gegevens ](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md).

## Stap 2: Gegevensbestandsindeling

Bestandsnamen en inhoud volgen strikte richtlijnen. U *moet* gegevensdossiers volgens deze specificaties in deze gids noemen en organiseren. Zie:

* [Amazon S3-naamvereisten voor binnenkomende databestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* [Inbound Data File Contents: Syntax, Variables en Examples](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)

## Online gegevens zijn beschikbaar voor offlinemarketinginspanningen

Wanneer u offline gegevens online brengt, kunt u deze informatie voor offlinecampagnes nog gebruiken. Hiervoor exporteert [!DNL Audience Manager] informatie over kenmerken en segmenten naar een [!DNL FTP] - of [!DNL Amazon S3] -locatie van uw keuze. Neem contact op met de manager van de Oplossingen van de Partner voor extra informatie of hulp.

## Omgevingen

[!DNL Audience Manager] biedt de volgende omgevingen voor het uitzetten van bestanden:

| Omgeving | Service | Locatie |
|---------|----------|---------|
| Productie | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-clients</li><li>ftp-in.demdex.com</li></ul> |
| Beta omgeving | <ul><li>Amazon S3</li><li>FTP</li></ul> | <ul><li>demdex-s2s-client-sandbox-us-East-1</li><li>sandbox-ftp-in.demdex.com</li></ul> |

{style="table-layout:auto"}

## Verdere technische lezing

De ingenieurs van systemen, ontwikkelaars, of de technische/implementatieteams zouden [ beschreven Proces van de Overdracht van Gegevens van de Partij ](../../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) en de andere artikelen in deze sectie moeten herzien. Deze artikelen bevatten informatie over overdrachtprotocollen, bestandsinhoud en vereisten voor bestandsnamen.
