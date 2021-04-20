---
description: Antwoorden op algemene vragen of problemen in verband met privacy en data.
seo-description: Antwoorden op algemene vragen of problemen in verband met privacy en data.
seo-title: Veelgestelde vragen over privacy en dataretentie
solution: Audience Manager
title: Veelgestelde vragen over privacy en dataretentie
uuid: ef558fca-35ff-44f1-8527-f8bee9f2c7e9
feature: Data Governance & Privacy
exl-id: bccf49d7-1a3b-4286-86fb-59e472af4501
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 84%

---

# Veelgestelde vragen over privacy en dataretentie {#privacy-and-data-retention-faq}

Antwoorden op algemene vragen of problemen in verband met privacy en data.

<!-- faq_privacy.xml -->

## Veelgestelde vragen over privacy {#privacy-faq}

>[!TIP]
>
>Ga naar het [Adobe Privacy Center](https://www.adobe.com/nl/privacy.html) voor meer informatie.

**Hoe gebruikt Audience Manager cookies en welke cookies worden ingesteld?**

Zie [Audience Manager-cookies](https://docs.adobe.com/content/help/nl-NL/core-services/interface/ec-cookies/cookies-am.html).

**Kunnen Audience Manager-clients in de VS gebruikers targeten op EU-eigenschappen?**

Ja. Audience Manager werkt met clients die internationale eigenschappen en een internationale inventory hebben. In de EU gelden strenge privacywetten, maar Audience Manager heeft clients die eigen data gebruiken voor doelgroeptargeting in Europa. Audience Manager kan targeting van EU-doelgroepen ondersteunen, maar het is uw verantwoordelijkheid om de lokale privacyvoorschriften na te leven.

<!-- 

<p> <b>Why does the IP address need to be removed from log files?</b> </p> 
<p>While still an open question in the US, regulators in Europe consider IP addresses as personally identifiable information (PII). As a result, companies that collect IP addresses in the EU are subject to strict data processing requirements. To support expansion into the EU, and help reduce compliance requirements for our customers, we remove IP addresses from log files. Also, this change addresses where we believe industry self-regulation and legally required regulations are moving within the United States. Removing IP addresses is a proactive change that will help Audience Manager (and our partners) comply with existing and future PII-related legislation. </p>

 -->

## Veelgestelde vragen over dataretentie {#data-retention-faq}

In de volgende tabel staan de retentietijden voor verschillende datatypen en opslagsystemen.

<table id="table_21C0B13A57A44DE0999FB33F363C88F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Datatype, bron of opslag </th> 
   <th colname="col2" class="entry"> Dataretentieperiode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Back-endservers </p> </td> 
   <td colname="col2"> <p>120 dagen </p> <p> Audience Manager verwijdert gebruikersdata van onze back-endservers 120 dagen nadat een gebruiker voor het laatst op het Audience Manager-platform is gezien. Als <span class="keyword"> Audience Manager</span> gebruikersactiviteit binnen deze cyclus van 120 dagen registreert, zullen wij deze gegevens nog 120 dagen bewaren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Edge-servers </p> </td> 
   <td colname="col2"> <p> 14 dagen </p> <p>Audience Manager verwijdert gebruikersdata van onze Edge-servers 14 dagen nadat een gebruiker voor het laatst op het Audience Manager-platform is gezien. Als <span class="keyword"> Audience Manager</span> gebruikersactiviteit binnen deze cyclus van 14 dagen registreert, zullen wij deze gegevens nog 14 dagen bewaren. Als de gebruiker na de cyclus van 14 dagen weer actief wordt, is er een vertraging tussen die eerste nieuwe paginaweergave en wanneer de gebruiker actioneerbaar wordt. Het duurt 6-18 uur om het volledige profiel weer naar het randcentrum terug te krijgen na meer dan 14 dagen inactiviteit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Onbewerkte logboeken </p> </td> 
   <td colname="col2"> <p>60 dagen (verwijderd na 60 dagen geen activiteit) </p> <p>Onbewerkte logboekbestanden zijn data die door een Edge-server worden ontvangen via HTTP-calls of van onboarded bestanden die naar <span class="keyword"> Audience Manager</span> worden verzonden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Advertentieserverlogboeken </p> </td> 
   <td colname="col2"> <p><b>Rapportage</b> </p> <p>Logboekbestanden worden maximaal 30 dagen bewaard voor rapportagedoeleinden. We bewaren niet-gematchte logboeken (bijv. logboeken waarvoor geen id-synchronisatie is tussen de advertentieserver-id van de bezoeker en de <span class="keyword">Audience Manager</span>-id) niet in onze back-endopslag. Gematchte logboeken die in <span class="keyword">Amazon S3</span> zijn opgeslagen, worden maximaal 30 dagen bewaard. </p> <p><b>Actiegerichte logboekbestanden</b> </p> <p>Zowel gematchte als niet-gematchte logboekbestanden worden maximaal 30 dagen bewaard. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Profielen op CRM-niveau (geverifieerde profielen) </p> </td> 
   <td colname="col2"> <p>Het standaard Time-To-Live-interval (TTL) voor inactieve profielen op CRM-niveau (klant-id’s) is 24 maanden. Nochtans, kunt u het gebruikersinterface van de Audience Manager gebruiken om het interval van TTL voor inactieve CRM-vlakke profielen tussen één maand en 5 jaar te verminderen of uit te breiden. Dit kunt u doen wanneer u een cross-device databron maakt of bewerkt.</p> <p>Zie Databroninstellingen in <a href="../features/profile-merge-rules/merge-rules-start.md#settings">Een cross-device databron maken</a> voor meer informatie.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobiele apparaat-id’s </p> </td> 
   <td colname="col2"> <p>De retentievoorwaarden voor id’s van mobiele apparaten (<a href="../reference/ids-in-aam.md">IDFA, GAID</a>) volgen de cadans die is beschreven in de eerste twee rijen, back-endservers en Edge-servers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CDF (Customer Data Feeds, klantdatafeeds) </p> </td> 
   <td colname="col2"> <p>Een CDF-bestand bevat dezelfde data die een <span class="keyword">Audience Manager</span>-gebeurteniscall (/gebeurtenis) naar onze servers verzendt. De retentieperiode is acht dagen. Raadpleeg <a href="../features/cdf-files.md">CDF Intro</a> en <a href="../faq/faq-cdf.md">Veelgestelde vragen over CDF Intro</a> voor meer informatie over CDF. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Toewijzingen tussen gesynchroniseerde id’s </p> </td> 
   <td colname="col2"> <p>De levensduur van de <a href="../features/administration/usage-limits.md#id-mapping-limits">id-toewijzingen</a> tussen Audience Manager-cookie-id’s (<a href="../reference/ids-in-aam.md">Audience Manager Unique User ID’s of AAM UUID’s</a>) en cookie-id’s van derden is beperkt tot 120 dagen. De levensduur van de id-toewijzing wordt telkens opnieuw ingesteld wanneer het Audience Manager-cookie wordt weergegeven in het Audience Manager-netwerk. De meest recente synchronisatie voor id-toewijzing blijft bewaard gedurende de levensduur van de gekoppelde <a href="../reference/ids-in-aam.md">Audience Manager Unique User ID (AAM UUID)</a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Binnenkomende data </p> </td> 
   <td colname="col2"> <p>Dit zijn binnenkomende data die u via FTP naar <span class="keyword">Audience Manager</span> verzendt, of rechtstreeks naar een <span class="keyword">Amazon S3</span>-directory. Zie de <a href="../faq/faq-inbound-data-ingestion.md">Veelgestelde vragen over opname van binnenkomende klantdata</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uitgaande data </p> </td> 
   <td colname="col2"> <p>Dit zijn de batchdata die <span class="keyword">Audience Manager</span> naar externe activeringspartners verzendt. De retentieperiode is acht dagen. Raadpleeg <a href="../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md">Batchoverdracht van uitgaande data</a> voor meer details over uitgaande data. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Dataretentie van eigenschapkwalificaties {#trait-qual}

In de onderstaande tabel staan de retentieopties voor eigenschapkwalificaties.

<table id="table_7FB42BEF138540AAB6869995C1AB8D3F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Eigenschapbewerkingen </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Een eigenschap verwijderen </p> </td> 
   <td colname="col2"> <p>Als u een eigenschap verwijdert, worden de eigenschapkwalificatiedata verwijderd uit alle gebruikersprofielen die in het verleden voor de eigenschap waren gekwalificeerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eigenschaplimiet bereikt </p> </td> 
   <td colname="col2"> <p>We leggen een limiet op van 100.000 eigenschapkwalificaties voor elk gebruikersprofiel. De limiet geldt voor geverifieerde profielen en apparaatprofielen. Als een gebruikersprofiel deze limiet bereikt, worden de oudste eigenschapkwalificaties verwijderd, de oudste het eerst. </p> <p>Lees voor meer informatie onze <a href="../features/traits/trait-and-segment-qualification-reference.md#trait-qualification-limit">Limiet voor eigenschapkwalificaties</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
