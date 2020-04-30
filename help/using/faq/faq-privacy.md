---
description: Antwoorden op algemene vragen of problemen met betrekking tot privacy en gegevens.
seo-description: Antwoorden op algemene vragen of problemen met betrekking tot privacy en gegevens.
seo-title: Veelgestelde vragen over privacy en gegevensbewaring
solution: Audience Manager
title: Veelgestelde vragen over privacy en gegevensbewaring
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Veelgestelde vragen over privacy en gegevensbewaring{#privacy-and-data-retention-faq}

Antwoorden op algemene vragen of problemen met betrekking tot privacy en gegevens.

<!-- faq_privacy.xml -->

## Veelgestelde vragen over privacy {#privacy-faq}

>[!TIP]
>
>Ga naar het [Adobe Privacy Center](https://www.adobe.com/privacy.html) voor meer informatie.

**Hoe gebruikt Audience Manager cookies en welke cookies worden ingesteld?**

Zie [Audience Manager Cookies](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html).

**Kunnen klanten van Audience Manager in de VS doelgebruikers zijn op EU-eigendommen?**

Ja. Audience Manager werkt met klanten die internationale eigenschappen en voorraden hebben. De EU heeft strenge privacywetten, maar Audience Manager heeft klanten die gegevens van de eerste partij gebruiken voor doelgroepen in Europa. De manager van het publiek kan steun richten op het publiek van de EU, maar het is uw verantwoordelijkheid om de lokale privacyregels na te leven.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Veelgestelde vragen over gegevensbewaring {#data-retention-faq}

In de volgende tabel worden de retentietijden voor verschillende gegevenstypen en opslagsystemen weergegeven.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gegevenstype, bron of opslag </th> 
   <th colname="col2" class="entry"> Bewaarperiode gegevens </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Back-end servers </p> </td> 
   <td colname="col2"> <p>120 dagen. </p> <p> Audience Manager verwijdert gebruikersgegevens van onze back-endservers 120 dagen nadat een gebruiker voor het laatst op het platform Audience Manager is gezien. Als <span class="keyword"> Audience Manager</span> de gebruikersactiviteit binnen deze cyclus van 120 dagen registreert, zullen wij deze gegevens nog 120 dagen bewaren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-servers </p> </td> 
   <td colname="col2"> <p> 14 dagen. </p> <p>Audience Manager verwijdert gebruikersgegevens van onze Edge-servers 14 dagen nadat een gebruiker voor het laatst op het platform Audience Manager is weergegeven. Als <span class="keyword"> Audience Manager</span> de gebruikersactiviteit binnen deze cyclus van 14 dagen registreert, zullen wij deze gegevens nog 14 dagen bewaren. Als de gebruiker na de periode van 14 dagen weer actief wordt, zal er een vertraging tussen die eerste nieuwe paginamening en zijn wanneer de gebruiker actionable wordt. Het duurt 6-18 uur om het volledige profiel weer naar het randcentrum terug te krijgen na meer dan 14 dagen inactiviteit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Onbewerkte logboeken </p> </td> 
   <td colname="col2"> <p>180 dagen (verwijderd na 180 dagen geen activiteit). </p> <p>Onbewerkte logbestanden zijn gegevens die door een Edge-server worden ontvangen via HTTP-aanroepen of van onbeheerde bestanden die worden verzonden naar <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aanmeldingsgegevens Advertentieserver </p> </td> 
   <td colname="col2"> <p><b>Rapportage</b> </p> <p>Logbestanden worden maximaal 30 dagen bewaard voor rapportagedoeleinden. We blijven niet doorgaan met onovertroffen logbestanden (bv. logbestanden waarvoor geen id-synchronisatie bestaat tussen de server-id van de bezoeker en de <span class="keyword"> Audience Manager</span> -id) in onze back-endopslag en bijbehorende logbestanden die zijn opgeslagen in <span class="keyword"> Amazon S3</span> , worden maximaal 30 dagen bewaard. </p> <p><b>Werkbare logbestanden</b> </p> <p>Zowel gematchte als niet-gematchte logbestanden worden tot 30 dagen bewaard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CRM-profielen (geverifieerde profielen) </p> </td> 
   <td colname="col2"> <p>Het standaardtime-to-live (TTL) interval voor inactieve CRM-level profielen (Customer IDs) is 24 maanden. Nochtans, kunt u de Manager UI van de Publiek gebruiken om het interval van TTL voor inactieve CRM-vlakke profielen tussen één maand en 5 jaar te verminderen of uit te breiden. Dit kunt u doen wanneer u een gegevensbron voor meerdere apparaten maakt of bewerkt.</p> <p>Voor meer informatie, zie de Montages van de Gegevensbron in <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Create een Gegevensbron van het Apparaat van de Interfactie </a>.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobiele apparaat-id's </p> </td> 
   <td colname="col2"> <p>De retentievoorwaarden voor id's van mobiele apparaten (<a href="../reference/ids-in-aam.md"> IDFA, GAID</a>) volgen de in de eerste twee rijen beschreven snelheid, back-end servers en Edge-servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CDF (Customer Data Feeds) </p> </td> 
   <td colname="col2"> <p>Een CDF-bestand bevat dezelfde gegevens als een <span class="keyword"> Audience Manager</span> -gebeurtenisaanroep (/gebeurtenis) naar onze servers verzendt. De retentieperiode is 8 dagen. Raadpleeg de <a href="../features/cdf-files.md"> Veelgestelde vragen over CDF Intro</a> en <a href="../faq/faq-cdf.md"> CDF voor meer informatie over CDF</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Toewijzingen tussen gesynchroniseerde id's </p> </td> 
   <td colname="col2"> <p>De levensduur van de <a href="../features/administration/usage-limits.md#id-mapping-limits"> id-toewijzingen</a> tussen cookie-id's van Audience Manager (<a href="../reference/ids-in-aam.md">Audience Manager Unique User ID's of AAM UIDs</a>) en cookie-id's van derden is beperkt tot 120 dagen. De levensduur van de id-toewijzing wordt telkens opnieuw ingesteld wanneer het cookie van Audience Manager wordt weergegeven in het netwerk Audience Manager. De meest recente synchronisatie voor id-toewijzing blijft behouden gedurende de levensduur van de AAM UUID (Unique User ID) van AAM <a href="../reference/ids-in-aam.md"></a>Audience Manager.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Binnenkomende gegevens </p> </td> 
   <td colname="col2"> <p>Dit zijn binnenkomende gegevens die u via FTP naar <span class="keyword"> Audience Manager</span> verzendt of rechtstreeks naar een <span class="keyword"> Amazon S3</span> -directory. Zie de <a href="../faq/faq-inbound-data-ingestion.md"> Binnenkomende Veelgestelde vragen</a>over de gegevensverwerking van de Klant. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uitgaande gegevens </p> </td> 
   <td colname="col2"> <p>Dit zijn de partijgegevens die de Manager <span class="keyword"></span> van het Publiek naar derde activeringspartners verzendt. De retentieperiode is 8 dagen. Voor meer details over Uitgaande gegevens, gelieve te verwijzen naar <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md"> Uitgaande Overdrachten</a>van de Partij. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bewaring van kwalificatiegegevens {#trait-qual}

In de onderstaande tabel staan de retoucheringsopties voor beroepskwalificaties.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Treinbewerking </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Een kenmerk verwijderen </p> </td> 
   <td colname="col2"> <p>Als u een eigenschap verwijdert, worden de kwalificatiegegevens van de eigenschap verwijderd uit alle gebruikersprofielen die in het verleden voor de eigenschap waren gekwalificeerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Trainingslimiet bereikt </p> </td> 
   <td colname="col2"> <p>We stellen een limiet van 100.000 beroepskwalificaties voor elk gebruikersprofiel op. De limiet geldt voor geverifieerde profielen en apparaatprofielen. Als een gebruikersprofiel deze limiet bereikt, worden de oudste vakkwalificaties verwijderd, op basis van de eerste-in-uitbasis. </p> <p>Lees voor meer informatie onze <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit"> kwalificatielimiet</a>Trait. </p> </td> 
  </tr> 
 </tbody> 
</table>

