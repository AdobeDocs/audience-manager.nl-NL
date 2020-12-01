---
description: Deze pagina maakt een lijst van douaneintegratie tussen Audience Manager en gegevenspartners.
seo-description: Deze pagina maakt een lijst van douaneintegratie tussen Audience Manager en gegevenspartners.
seo-title: Aangepaste partnerintegraties
solution: Audience Manager
title: Aangepaste partnerintegraties
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 3%

---


# Aangepaste partnerintegraties {#custom-partner-integrations}

Deze pagina maakt een lijst van douaneintegratie tussen Audience Manager en gegevenspartners.

## Oracle Data Cloud {#oracle-data-cloud}

### Beschrijving

Audience Manager neemt cookie- en mobiele-id-gegevens op van de Oracle Data Cloud voor Audience Marketplace via binnenkomende gegevensbestanden. De hieronder beschreven specificaties voor aangepaste integratie verwijzen alleen naar binnenkomende gegevensbestanden die mobiele id&#39;s (IDFA en Android-apparaat-id&#39;s) bevatten.

### Integratiespecificaties

Binnenkomende gegevensbestanden die worden ontvangen van de Oracle Data Cloud verschillen van de standaard syntaxis voor de binnenkomende bestandsnaam die wordt beschreven in [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) en van de standaard syntaxis voor de binnenkomende bestandsinhoud die wordt beschreven in [Inbound Data File Contents: Syntaxis, Ongeldige tekens, variabelen en voorbeelden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Naast de standaardimplementatievelden voor binnenkomende gegevensbestanden zijn de hieronder gemarkeerde elementen vereist. Zie Syntaxis bestandsnaam en syntaxis bestandsinhoud op de twee pagina&#39;s die hierboven zijn gekoppeld voor beschrijvingen van alle andere standaardvelden en bestandsnaamelementen.

### Bestandsnaamgeving

ODC-bestandsnamen hebben de volgende structuur:

`ftp_dpm_`**`odc`**`_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Het bestandsnaamelement `odc` identificeert het bestand als geïmporteerd uit de Oracle Data Cloud en geeft de Audience Manager de instructie de inbound file validator te verwerken.

### Bestandsinhoud

Velden in het binnenkomende gegevensbestand van de ODC moeten in de onderstaande volgorde worden weergegeven:

`<`**`ID type`**`><TAB><user ID><TAB><trait ID>,<trait ID>,<trait ID>,...`

De `ID type` kan zijn:

* IDFA
* Android-apparaat

>[!IMPORTANT]
>
>Verzend geen id&#39;s voor IDFA- en Android-apparaten in hetzelfde binnenkomende gegevensbestand.

## Voorbeeld van inbound-bestand voor ODC

Download het [voorbeeldbestand](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Dit bestand kwalificeert verschillende IDFA&#39;s voor de kenmerk-id 38838. U kunt dit bestand openen in een standaardteksteditor of code-editor.