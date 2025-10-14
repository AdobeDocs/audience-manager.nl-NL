---
description: Deze pagina bevat een lijst met aangepaste integratie tussen Audience Manager en gegevenspartners.
seo-description: This page lists custom integrations between Audience Manager and data partners.
seo-title: Custom Partner Integrations
solution: Audience Manager
title: Aangepaste partnerintegratie
feature: Third-party Integration
exl-id: 54af75a4-c05b-42fb-851c-5e242378d9f1
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 0%

---

# Aangepaste partnerintegratie {#custom-partner-integrations}

Deze pagina bevat een lijst met aangepaste integratie tussen Audience Manager en gegevenspartners.

## Oracle Data Cloud {#oracle-data-cloud}

### Beschrijving

Audience Manager neemt cookie- en mobiele-id-gegevens op van de Oracle Data Cloud voor Audience Marketplace via binnenkomende gegevensbestanden. De hieronder beschreven specificaties voor aangepaste integratie verwijzen alleen naar binnenkomende gegevensbestanden die mobiele id&#39;s (IDFA en Android Device ID&#39;s) bevatten.

### Integratiespecificaties

De binnenkomende Dossiers van Gegevens die van de Wolk van de Gegevens van Oracle worden ontvangen verschillen van de standaard binnenkomende die dossiernaamsyntaxis in [&#x200B; wordt beschreven Amazon S3 Naam en de Vereisten van de Grootte van het Dossier voor Binnenkomende Dossiers van Gegevens &#x200B;](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) en van de standaard binnenkomende die syntaxis van de dossierinhoud in [&#x200B; wordt beschreven de Inhoud van het Dossier van Gegevens: Syntaxis, Ongeldige Karakters, Variabelen, en Voorbeelden &#x200B;](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Naast de standaardimplementatievelden voor binnenkomende gegevensbestanden zijn de hieronder gemarkeerde elementen vereist. Zie Syntaxis bestandsnaam en syntaxis bestandsinhoud op de twee pagina&#39;s die hierboven zijn gekoppeld voor beschrijvingen van alle andere standaardvelden en bestandsnaamelementen.

### Bestandsnaamgeving

ODC-bestandsnamen hebben de volgende structuur:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Het element `odc` file name identificeert het bestand als zijnde geïmporteerd uit de Oracle Data Cloud en geeft de Audience Manager binnenkomende bestandsvalidator de opdracht het als zodanig te verwerken.

### Bestandsinhoud

Velden in het binnenkomende gegevensbestand van de ODC moeten in de onderstaande volgorde worden weergegeven:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

De `ID type` kan zijn:

* IDFA
* Android-apparaat-id

>[!IMPORTANT]
>
>Verzend geen IDFA- en Android-apparaat-id&#39;s in hetzelfde binnenkomende gegevensbestand.

## Voorbeeld van inbound-bestand voor ODC

Download het [&#x200B; steekproefdossier &#x200B;](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Dit bestand kwalificeert verschillende IDFA&#39;s voor de kenmerk-id 38838. U kunt dit bestand openen in een standaardteksteditor of code-editor.
