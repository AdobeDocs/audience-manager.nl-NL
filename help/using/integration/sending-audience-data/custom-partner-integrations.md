---
description: Deze pagina maakt een lijst van douaneintegratie tussen de Manager van de Publiek en gegevenspartners.
seo-description: Deze pagina maakt een lijst van douaneintegratie tussen de Manager van de Publiek en gegevenspartners.
seo-title: Aangepaste partnerintegratie
solution: Audience Manager
title: Aangepaste partnerintegratie
translation-type: tm+mt
source-git-commit: 3e7c993b1ddd2829e382de56ea246a667ff3ce0c

---


# Aangepaste partnerintegratie {#custom-partner-integrations}

Deze pagina maakt een lijst van douaneintegratie tussen de Manager van de Publiek en gegevenspartners.

## Oracle Data Cloud {#oracle-data-cloud}

**Beschrijving**

Audience Manager neemt cookie- en mobiele-id-gegevens op van de Oracle Data Cloud for Audience Marketplace via binnenkomende gegevensbestanden. De hieronder beschreven specificaties voor aangepaste integratie verwijzen alleen naar binnenkomende gegevensbestanden die mobiele id&#39;s (IDFA en Android-apparaat-id&#39;s) bevatten.

<br> 

**Integratiespecificaties**

Binnenkomende gegevensbestanden die worden ontvangen van de Oracle Data Cloud verschillen van de standaard syntaxis voor binnenkomende bestandsnamen die wordt beschreven in de vereisten voor naam en bestandsgrootte van [Amazon S3 voor binnenkomende gegevensbestanden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) en van de standaard syntaxis voor binnenkomende bestandsinhoud die wordt beschreven in [Inbound Data File Contents: Syntaxis, ongeldige tekens, variabelen en voorbeelden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

Naast de standaardimplementatievelden voor binnenkomende gegevensbestanden zijn de hieronder gemarkeerde elementen vereist. Zie Syntaxis bestandsnaam en syntaxis bestandsinhoud op de twee pagina&#39;s die hierboven zijn gekoppeld voor beschrijvingen van alle andere standaardvelden en bestandsnaamelementen.

<br> 

**Bestandsnaamgeving**

ODC-bestandsnamen hebben de volgende structuur:

<pre>ftp_dpm_<b>odc</b>_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]</pre>

Het `odc` bestandsnaamelement identificeert het bestand als geïmporteerd vanuit de Oracle Data Cloud en geeft de ingebouwde bestandsvalidator van Audience Manager de opdracht het als zodanig te verwerken.

<br> 

**Bestandsinhoud**

Velden in het binnenkomende gegevensbestand van de ODC moeten in de onderstaande volgorde worden weergegeven:

<pre>&lt;<b>ID type</b>&gt;&lt;TAB&gt;&lt;gebruiker ID&gt;&lt;TAB&gt;&lt;trait ID&gt;,&lt;trait ID&gt;,&lt;trait ID&gt;,..</pre>

Het `ID type` kan zijn:

* IDFA
* Android-apparaat

>[!IMPORTANT]
>
>Verzend geen id&#39;s voor IDFA- en Android-apparaten in hetzelfde binnenkomende gegevensbestand.

<br> 

**Voorbeeld van inbound-bestand voor ODC**

Download het [voorbeeldbestand](/help/using/integration/assets/ftp_dpm_odc_12345_1556223815.sync). Dit bestand kwalificeert verschillende IDFA&#39;s voor de kenmerk-id 38838. U kunt dit bestand openen in een standaardteksteditor of code-editor.