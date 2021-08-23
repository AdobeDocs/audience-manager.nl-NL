---
description: Beschrijft de vereiste gebieden, de syntaxis, en de overeenkomsten die worden gebruikt om een uitgaand gegevensdossier te noemen.
seo-description: Beschrijft de vereiste gebieden, de syntaxis, en de overeenkomsten die worden gebruikt om een uitgaand gegevensdossier te noemen.
seo-title: Syntaxis en voorbeelden van uitgaande gegevensbestanden
solution: Audience Manager
title: Syntaxis en voorbeelden van uitgaande gegevensbestanden
uuid: effdcaf6-c37c-45f3-9d2f-a938a9da47a6
feature: Uitgaande gegevensoverdrachten
exl-id: 0944da72-5a8d-45a2-951e-b2988eb3d490
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 5%

---

# Naam van uitgaande-databestand: syntaxis en voorbeelden{#outbound-data-file-name-syntax-and-examples}

Beschrijft de vereiste gebieden, de syntaxis, en de overeenkomsten die worden gebruikt om een uitgaand gegevensdossier te noemen.

<!-- c_name_reqs_outbound.xml -->

>[!NOTE]
>
>De stijlelementen (`monospaced text`, *italics*, vierkante haken `[ ]` `( )`, enz.) in dit document de elementen en opties van de code aangeven. Zie [Stijlconventies voor code- en tekstelementen](../../../reference/code-style-elements.md) voor meer informatie.

## Syntaxis en bestandsnaamelementen {#syntax-file-name}

Uitgaande bestandsnamen bevatten de volgende elementen. Alle onderstaande elementen zijn optioneel.

```
[SYNC_TYPE][_DID][_MASTER_DPID][_PID_ALIAS][_SYNC-MODE][_TIMESTAMP]SPLITNUM.sync[.gz]
```

### Parameters

De tabel definieert de elementen in de naam van een uitgaand gegevensbestand.

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bestandsnaamelement </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_TYPE </i></code> </p> </td> 
   <td colname="col2"> <p>Verwijst naar de methoden voor gegevensoverdracht. Overdrachtsmethoden zijn onder meer: </p> 
    <ul id="ul_4E0CFC7A34E04E2FA216A07E3654D6EE"> 
     <li id="li_0066B99222A64BE9975AE2E91511FB77">FTP - Overdracht met SFTP </li> 
     <li id="li_646767FE8AD247B88D0DD5461349F019"> <span class="keyword"> Amazon S3  </span> - Overdracht naar  <span class="keyword"> Amazon AWS  </span> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>DID </i></code> </p> </td> 
   <td colname="col2"> <p>Doel-id. </p> <p>In <span class="keyword"> Audience Manager </span>, is een bestemming de instantie van de integratie waar u uw doelsegmenten kunt in kaart brengen. De klanten kunnen veelvoudige bestemmingen, afhankelijk van het bedrijfsvereiste hebben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>MASTER_DPID </i></code> </p> </td> 
   <td colname="col2"> <p>Data-provider of gegevensbron-id. Deze id geeft het type gebruikersnaam aan dat aanwezig is in de bestandsinhoud. De meest gebruikte gebruikersnamen zijn: </p> <p> 
     <ul id="ul_CC22D019ECED4B17A7695708001F2C1B"> 
      <li id="li_94DAFA169380405981AFEF1B581997E6">20914 - <span class="keyword"> Google Advertiser ID </span> (raw, unhashed) </li> 
      <li id="li_DE74BE06331C49CF87606A192D815B96">20915 - <span class="keyword"> Apple ID for Advertisers </span> (raw, unhashed) </li> 
      <li id="li_E0A033FEC3174EF08E93EB7C65266337">Leveranciers-id - gebruikers-id's van derden (web/cookie) </li> 
     </ul> </p> <p>Zie <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/global-data-sources.html">Algemene databronnen</a> voor meer informatie.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>PID_ALIAS </i></code> </p> </td> 
   <td colname="col2"> De klant-id van het externe platform. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SYNC_MODE </i></code> </p> </td> 
   <td colname="col2"> <p>De synchronisatiemodus is een macro-plaatsaanduiding die een label toevoegt aan de bestandsnaam op basis van het synchronisatietype. De types van synchronisatie omvatten volledig en stijgende. Deze worden in de bestandsnaam weergegeven als <code> iter </code> of <code> full </code>. </p> 
    <ul id="ul_3B3585CEF1434951B6FDCDD29E5013CD"> 
     <li id="li_947D94E9CFAC4041AC1AAEB191805529"> <code> iter </code>: Geeft een "iteratieve" of incrementele synchronisatie aan. Een incrementeel bestand bevat alleen nieuwe gegevens die zijn verzameld sinds de laatste synchronisatie. </li> 
     <li id="li_13ADB3B3346943DAA767A1F416482D3C"> <code> full </code>: Geeft een volledige synchronisatie aan. Een volledig gesynchroniseerd bestand bevat oude gegevens en eventuele nieuwe gegevens die zijn verzameld sinds de laatste synchronisatie. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>TIMESTAMP </i></code> </p> </td> 
   <td colname="col2"> <p>Een UNIX-tijdstempel van 13 cijfers in milliseconden, in de UTC-tijdzone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code><i>SPLITNUM</i></code></p> </td> 
   <td colname="col2"> <p>Een geheel getal. Identificeert een deel van een dossier dat in veelvoudige delen is verdeeld om verwerkingstijden te verbeteren. Het getal geeft aan tot welk deel van het oorspronkelijke bestand de gegevens behoren.</p>  <p>Het gehele getal moet ten minste drie cijfers lang zijn, voorafgegaan door nullen, als de gesplitste grootte kleiner is dan 100 delen.</p>  <p>Het oorspronkelijke bestand heeft geen splitsingsnummer. Het eerste gesplitste bestand eindigt bij 001. Zie onderstaande voorbeelden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>.gz (optional) </i></code> </p> </td> 
   <td colname="col2"> <p>GZIP-compressie. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeelden van bestandsnamen {#file-name-examples}

### Scenario 1

Bestanden die naar een [!DNL Amazon S3]-locatie worden verzonden, met *`PID_ALIAS="XYZCustomer"`* en met [!DNL Google Advertiser IDs] in de bestandsinhoud.

Bijvoorbeeld incrementele bestanden:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000001.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_iter_1486140844000002.sync.gz </code> </li> 
</ul>

Bijvoorbeeld volledige bestanden:

<ul class="simplelist"> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000.sync.gz </code> </li> 
 <li> <code> S3_1234_20914_XYZCustomer_full_1486140844000001.sync.gz </code> </li> 
</ul>

### Scenario 2

Bestanden die naar de locatie [!DNL FTP] worden verzonden, zonder *`PID_ALIAS`* en met [!DNL Apple Advertiser IDs] in de bestandsinhoud:

Bijvoorbeeld incrementele bestanden:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Bijvoorbeeld volledige bestanden:

<ul class="simplelist"> 
 <li> <code> ftp_1234_20915_full_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_20915_full_1486140843000001.sync.gz </code> </li> 
</ul>

**Scenario 3**: Bestanden die naar de  [!DNL FTP] locatie worden verzonden, met  *`PID_ALIAS="XYZCustomer"`* en met een gebruikersnaam van een andere gebruiker in de bestandsinhoud (  *`Vendor ID=45454`*):

Bijvoorbeeld incrementele bestanden:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_iter_1486140843000001.sync.gz </code> </li> 
</ul>

Bijvoorbeeld volledige bestanden:

<ul class="simplelist"> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200.sync.gz </code> </li> 
 <li> <code> ftp_1234_45454_XYZCustomer_full_1486140843200001.sync.gz </code> </li> 
</ul>

## Inhoud van uitgaande gegevensbestanden: Syntaxis en parameters {#outbound-contents-syntax}

Beschrijft de vereiste gebieden, de syntaxis, en de overeenkomsten die worden gebruikt om informatie in een uitgaand gegevensdossier te organiseren. Maak uw gegevens op volgens deze specificaties.

<!-- c_outbound_data_file.xml -->

>[!NOTE]
>
>De stijlelementen (`monospaced text`, *italics*, vierkante haken `[ ]` `( )`, enz.) in dit document de elementen en opties van de code aangeven. Zie [Stijlconventies voor code- en tekstelementen](../../../reference/code-style-elements.md) voor meer informatie.

### Syntaxis

Velden in het gegevensbestand worden in deze volgorde weergegeven:

`UUID<SPACE>SEGMENT_1,SEGMENT_2<SPACE>REMOVED_SEGMENT_,...`

### Parameters

De tabel bevat variabelen die de inhoud van een gegevensbestand definiëren.

<table id="table_109BA747CFDA40108370EFEB208C7E11"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code><i>UUID </i></code> </p> </td> 
   <td colname="col2"> <p>Een unieke gebruikers-id die wordt toegewezen door <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>&lt;SPACE&gt; </i></code> </p> </td> 
   <td colname="col2"> <p>Scheid UUID en segmentgegevens met een ruimte </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>De segment-id waartoe een bezoeker behoort. Scheid meerdere segmenten met een komma. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>REMOVED_SEGMENT_N </i></code> </p> </td> 
   <td colname="col2"> <p>De segment-id waarvan de gebruiker is uitgesloten. Scheid meerdere segmenten met een komma. Met een volledige synchronisatie, kunt u de verwijderde segmenten negeren omdat het gegevensdossier de volledige lijst van huidige segmenten voor de gebruiker zal bevatten. Gewoonlijk, wilt u over segmenten weten een gebruiker tot eerder dan die behoort die zij uit zijn verwijderd. Zie ook <a href="../../../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md#outbound-data-file-name-syntax-and-examples"> Naam uitgaand gegevensbestand: Syntaxis en voorbeelden </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Voorbeeld: Basisbestandsindeling

Een gegevensbestand met de juiste indeling kan er ongeveer als volgt uitzien. Deze bestandsinvoer geeft aan dat een gebruiker voor de segmenten 24, 26 en 27 in aanmerking komt. Zo nodig scheidt een spatie de `UUID` en segment-id&#39;s. Een andere ruimte scheidt de reeksen segment IDs. In dit voorbeeld behoort een gebruiker tot de segmenten 24, 26 en 27. Ze zijn verwijderd uit segmenten 25 en 28.

```
59767559181262060060278870901087098252  24,26,27  25,28
```
