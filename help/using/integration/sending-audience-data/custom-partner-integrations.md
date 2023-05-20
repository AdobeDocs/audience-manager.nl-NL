---
description: Deze pagina maakt een lijst van douaneintegratie tussen Audience Manager en gegevenspartners.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Aangepaste partnerintegraties
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 2%

---

# Aangepaste partnerintegraties {#custom-partner-integrations}

Deze pagina maakt een lijst van douaneintegratie tussen Audience Manager en gegevenspartners.

## Gegevenscloud oracle {#oracle-data-cloud}

### Beschrijving

Audience Manager neemt cookie- en mobiele-id-gegevens op van de Oracle Data Cloud voor Audience Marketplace via binnenkomende gegevensbestanden. De hieronder beschreven specificaties voor aangepaste integratie verwijzen alleen naar binnenkomende gegevensbestanden die mobiele id&#39;s (IDFA en Android-apparaat-id&#39;s) bevatten.

### Integratiespecificaties

De binnenkomende Gegevensbestanden die van de Cloud van de Gegevens van het Oracle worden ontvangen verschillen van de standaard binnenkomende dossiernaamsyntaxis die in [Amazon S3-vereisten voor naam en bestandsgrootte voor binnenkomende gegevensbestanden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) en op basis van de standaard syntaxis voor inkomende bestandsinhoud die wordt beschreven in [Inhoud binnenkomend gegevensbestand: Syntaxis, ongeldige tekens, variabelen en voorbeelden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Naast de standaardimplementatievelden voor binnenkomende gegevensbestanden zijn de hieronder gemarkeerde elementen vereist. Zie Syntaxis bestandsnaam en syntaxis bestandsinhoud op de twee pagina&#39;s die hierboven zijn gekoppeld voor beschrijvingen van alle andere standaardvelden en bestandsnaamelementen.

### Bestandsnaamgeving

ODC-bestandsnamen hebben de volgende structuur:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

De `odc` bestandsnaamelement geeft aan dat het bestand wordt geïmporteerd uit de gegevenscloud van het Oracle en geeft de Audience Manager de instructie het bestand als zodanig te verwerken.

### Bestandsinhoud

Velden in het binnenkomende gegevensbestand van de ODC moeten in de onderstaande volgorde worden weergegeven:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

De `ID type` kan:

* IDFA
* Android-apparaat

>[!IMPORTANT]
>
>Verzend geen id&#39;s voor IDFA- en Android-apparaten in hetzelfde binnenkomende gegevensbestand.

## Voorbeeld van inbound-bestand voor ODC

Download de [voorbeeldbestand](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Dit bestand kwalificeert verschillende IDFA&#39;s voor de kenmerk-id 38838. U kunt dit bestand openen in een standaardteksteditor of code-editor.
